# elastic/elasticsearch分析报告

## 技术类型

Elasticsearch是一个基于Lucene的搜索服务器。它提供了一个分布式多用户能力的全文搜索引擎，基于RESTful web接口。Elasticsearch是用Java语言开发的，并作为Apache许可条款下的开放源码发布，是一种流行的企业级搜索引擎。Elasticsearch用于云计算中，能够达到实时搜索，稳定，可靠，快速，安装使用方便。

## 版本发布历史

参考：https://github.com/elastic/elasticsearch/releases。elasticsearch总共发布了87个版本，目前的最新版本是v8.2.3，发布在2022年6月14日。

## 主要贡献者的构成（国家、区域和组织等）

创始人[Shay Banon](https://github.com/kimchy)是以色列人，他于2010年2月发布了Elasticsearch的第一个版本，属于早期主要的维护者，但他在2004年就创造了Elasticsearch的前身，称为Compass。在考虑Compass的第三个版本时，他意识到有必要重写Compass的大部分内容，以“创建一个可扩展的搜索解决方案”。因此，他创建了“一个从头构建的分布式解决方案”，并使用了一个公共接口，即HTTP上的JSON，它也适用于Java以外的编程语言。他在2015年以后少有动态发布。

项目的另一位主要贡献者为[Simon Willnauer](https://github.com/s1monw)，目前住在柏林，主要贡献时间为2013年至2019年，期间提交了2880个commit，但离Shay Banon的4738个还是有点差距。

## CI/CD的使用

elastic/elasticsearch使用两个CI/CD。其中一个是**gradle-wrapper-validation.yml**

```yml
name: "Validate Gradle Wrapper"
on: [push]

jobs:
  validation:
    name: "Validation"
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: gradle/wrapper-validation-action@v1
```

此操作验证源代码树中Gradle Wrapper JAR文件的校验和，如果发现未知的Gradle Wrapper JAR文件则失败。

另外一个是**sync-main-branch.yml**

```yml
# Synchronize all pushes to 'master' branch with 'main' branch to facilitate migration
name: "Sync main branch"
on:
  push:
    branches:
      - master

jobs:
  sync_latest_from_upstream:
    runs-on: ubuntu-latest
    name: Sync latest commits from master branch

    steps:
      - name: Checkout target repo
        uses: actions/checkout@v2
        with:
          ref: main

      - name: Sync upstream changes
        id: sync
        uses: aormsby/Fork-Sync-With-Upstream-action@v3.0
        with:
          target_sync_branch: main
          target_repo_token: ${{ secrets.GITHUB_TOKEN }}
          upstream_sync_branch: master
          upstream_sync_repo: elastic/elasticsearch
```

当有代码push在master分支上时，执行sync_latest_from_upstream工作。actions/checkout@v2这个action切换到$GITHUB_WORKSPACE下，所以这个仓库的workflow可以访问它。aormsby/Fork-Sync-With-Upstream-action@v3.0这个action将elastic/elasticsearch的master分支同步到main分支中，main分支应该是非工作分支。

## 其他有价值的信息

Elasticsearch发布的第一个版本是在2010年的二月份，从那之后，Elasticsearch便成了Github上最受人瞩目的项目之一，并且很快就有超过300名开发者加入进来贡献了自己的代码。后来Shay和另一位合伙人成立了公司专注打造Elasticsearch，他们对Elasticsearch进行了一些商业化的包装和支持。

# elasticsearch项目归档的原因

***\*指标分析\****

1、期中项目

（1）每月新增Star数量、每月新增Fork数量变化趋势平稳，呈持续上升状态，即表明了此项目做的事有趣、受欢迎，也显示出用户之间有很多不同的需求，导致项目分支版本越来越多。

（2）每月打开、关闭的Issue数量变化趋势平稳。

（3）每月打开、合并PR的数量变化趋势较为平稳且略有下降，社区贡献者逐渐变少。

（4）每月活跃的开发者数量呈缓慢下降趋势，社区活跃度降低。

2、期末项目

（1）每月新增Star数量、每月新增Fork数量变化趋势平稳，社区发展可持续性较强，较为健康。

（2）每月打开、关闭的Issue数量变化趋势平稳，最近略有下降趋势。

（3）每月打开、合并PR的数量变化趋势较为平稳且近几年有上升趋势，社区贡献者逐渐增加。

（4）每月活跃的开发者数量变化趋势平稳近期略有下降。

 

***\*项目活跃、归档的主要原因\****

一个能够吸引用户经常使用、做出贡献的项目，一定是有趣的、有用的、为用户带来快乐、方便的。如果一个项目主要做的事情具有这些特点，那这个社区就会慢慢的活跃起来。

如何保证一个项目持续活跃、健康发展呢？我们尝试从以上数据的分析中找到答案：及时审查、合并PR，使得社区更加方便好用，同时用户也会获得参与感，增加用户归属感，从而保持甚至增加社区活跃度，避免归档。

当一个开源项目没有及时维护社区、处理用户需求和问题时，用户可能fork后另起炉灶，如果这种情况太多就会导致用户群体分散，使得最初项目走向归档。