宁志成 51215903047、黄继铱 51215903094、唐烨男 51215903057
## 分工

- 宁志成：任务一、任务二1-4
- 黄继铱：环境搭建、任务二5-7
- 唐烨男：任务二8、任务三
## 一、项目的基本背景和发展历程介绍
| 这是[square/dagger](https://github.com/square/dagger)现状 | 这是[google/dagger](https://github.com/google/dagger)现状 |
| --- | --- |
| ![image.png](https://cdn.nlark.com/yuque/0/2022/png/21625412/1652409946270-b8a8e634-4163-4a6b-ba00-1193dd3e9444.png#clientId=u760821d7-8036-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=686&id=jdZmA&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1372&originWidth=2084&originalType=binary&ratio=1&rotation=0&showTitle=false&size=897472&status=done&style=none&taskId=u2fef1d02-5c15-4773-a8df-f63e97cb239&title=&width=1042) | ![image.png](https://cdn.nlark.com/yuque/0/2022/png/21625412/1652409935769-5e932f2b-4401-42aa-8b6b-869cd035e586.png#clientId=u760821d7-8036-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=686&id=KOxSm&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1372&originWidth=2084&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1925360&status=done&style=none&taskId=uaa88b4b3-0f18-41d7-b2c4-c42a2f9a7ac&title=&width=1042) |

它们间有什么关系？请见下文。
### 项目简介
square/dagger仓库的About是这么写的：“A fast dependency injector for Android and Java.” 所以是做Android和Java的依赖注入的。Dagger名字的由来？看了一个硅谷码农的视频介绍，说Dagger的“Dag”是DAG，也就是有向无环图的意思，因为依赖关系构成的就是一个DAG；后面加“ger”组成了单词“dagger”，即匕首的意思。
### 版本发布历史
| 第一个commit来自Jesse Wilson于2012年6月25日 | 第一个commit的内容：一个`README.md` |
| --- | --- |
| ![image.png](https://cdn.nlark.com/yuque/0/2022/png/21625412/1652412019733-751f553f-ae1f-4a66-b249-7b8d5c5997e4.png#clientId=u10acb2f7-27a4-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=122&id=u3792b20d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=244&originWidth=896&originalType=binary&ratio=1&rotation=0&showTitle=false&size=38624&status=done&style=none&taskId=u8d091222-ee44-4850-a3ea-cc440e2f317&title=&width=448) | ![image.png](https://cdn.nlark.com/yuque/0/2022/png/21625412/1652412005473-79124017-4315-4f24-aed8-73c058a7c088.png#clientId=u10acb2f7-27a4-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=414&id=u9b0e03b7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=828&originWidth=1310&originalType=binary&ratio=1&rotation=0&showTitle=false&size=132929&status=done&style=none&taskId=uc3b8c181-166c-4ba9-8db4-51cd7100d8c&title=&width=655) |

该项目用Git的tags标记版本。第一个版本号为0.9，在2012年11月8日发布。之后共有10个tags，版本从0.9.1到1.2.5，最后一个tag在2016年5月10日。2013年的tags最多，共4个。2016年5月在一个礼拜内发布了3次tags。
### 主要贡献者的构成
square/dagger是[square组织](https://github.com/square)的项目，该组织是专注于商业领域的[Square公司](https://squareup.com/us/en)的开发者团队在GitHub上的Organization，该Org现有33个members。Org下的项目聚焦于Java、Android、Kotlin的工具和库。让我们来认识几个square/dagger的核心人物：

| [Jesse Wilson ](https://github.com/swankjesse) | [Jake Wharton](https://github.com/JakeWharton)  | [Christian Edward Gruber](https://github.com/cgruber)  |
| --- | --- | --- |
| ![image.png](https://cdn.nlark.com/yuque/0/2022/png/21625412/1652350647484-acd62414-2e74-4a14-8d28-e05405582617.png#clientId=u1def27d6-90fc-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=230&id=F8I8q&margin=%5Bobject%20Object%5D&name=image.png&originHeight=460&originWidth=460&originalType=binary&ratio=1&rotation=0&showTitle=false&size=250308&status=done&style=none&taskId=u6975f80d-dc82-4881-95ad-a5737798a73&title=&width=230) | ![image.png](https://cdn.nlark.com/yuque/0/2022/png/21625412/1652342680092-8a65da43-3d7c-40c5-b5f5-cc02c51d8fe8.png#clientId=uec2f7b79-04f3-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=230&id=I8F4d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=460&originWidth=460&originalType=binary&ratio=1&rotation=0&showTitle=false&size=309779&status=done&style=none&taskId=uffd0f7f2-2acd-4953-88bf-6a704c5b866&title=&width=230) | ![image.png](https://cdn.nlark.com/yuque/0/2022/png/21625412/1652343823641-45c1b6c1-9120-4538-b01e-b67248ded000.png#clientId=uec2f7b79-04f3-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=230&id=s4DPs&margin=%5Bobject%20Object%5D&name=image.png&originHeight=460&originWidth=460&originalType=binary&ratio=1&rotation=0&showTitle=false&size=298009&status=done&style=none&taskId=uaf61feb5-b335-43c6-b5aa-9b2e72ce700&title=&width=230) |
| 是他提了first commit，所以是作者？他的GitHub非常绿；就职于[@square](https://github.com/square) | Commits最多的男人，他的GitHub十多年来一片绿！就职于[@cashapp](https://github.com/cashapp)和[@square](https://github.com/square) | Commits第二多的男人，他不是square的人，但他是co-creator of Dagger；曾就职于Google和Youtube，现就职于[@cashapp](https://github.com/cashapp) |
| Waterloo, Ontario, Canada | Pittsburgh, PA, USA | Vancouver, WA |

### CI/CD的使用
项目根目录下存在`.travis.yml`文件，所以用了CI；`.buildscript`目录下的配置文件和脚本文件用于构建项目并“Deploy a jar, source jar, and javadoc jar to Sonatype's snapshot repo”，所以有CD。
PS：google/dagger用的是GitHub的Actions。
### 其他有价值的信息
评论数最多的PR是[#299](https://github.com/square/dagger/pull/299)，评论数最多的issue是[#240](https://github.com/square/dagger/issues/240)。
## 二、项目的历史轨迹分析
请见`./38-dagger-history.ipynb`。
## 三、洞察项目被归档的可能原因
这一部分回答本篇报告开头的“它们间有什么关系”。
### 归档可能原因
Google在很早期（2013年2月之前）就folk了起步不久的square/dagger，并且经常把upstream的代码合进来，大体上与square保持同步。

| [Gregory Kick](https://github.com/gk5885) |
| --- |
| ![image.png](https://cdn.nlark.com/yuque/0/2022/png/21625412/1652350982960-d05e65a3-f516-4dca-ba31-1cded6eef3ea.png#clientId=u1def27d6-90fc-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=230&id=XYFGM&margin=%5Bobject%20Object%5D&name=image.png&originHeight=460&originWidth=460&originalType=binary&ratio=1&rotation=0&showTitle=false&size=348954&status=done&style=none&taskId=ua803fe7f-3322-4afb-9d9d-5e7a39cf1cf&title=&width=230) |
| 促使转折的关键人物；GitHub一片白；任职于Google |

在2013年12月，Gregory Kick在square/dagger仓库中提了关键的[#366](https://github.com/square/dagger/issues/366)。在这个issue中，GK反映了Dagger在实际使用中的一些不足之处，并以Google云文档的形式给出了Dagger2.0的proposal，欢迎大家去围观。
一年多后，Google在2015年4月8日的commit发布了Dagger2.0，并且在该版本的[README](https://github.com/google/dagger/blob/dagger-2.0/README.md)中提到了和square/dagger的关系（用`git blame`查看发现都是square/dagger的几个核心贡献者写的这个文档）。在这之后的日子里，square/dagger一共就新增了65个commits，且大多数在2015年和2016年提交的，截止到目前一共703个commits；而google/square在这之后新增了2547个commits，目前仍非常活跃。正如Google在Dagger2.0发布的README中所说的，square/dagger代表的是1.x时代，google/dagger代表的是2.x时代。
以上是我们发现的客观事实，接下来是我们脑补的两个可能的故事：

- 故事一。square/dagger的核心贡献者有部分是Google的员工，他们和Square的人玩得很好，一起开发square/dagger，并且将其fork到google这个Org下，一直关心着这个项目。在#366之前，他们已经有过私下的交流，双方很愉快地认为Google推动Dagger2.0是个很不错的方式。等到Dagger2.0出来后，square/dagger作为Dagger1.x只做平稳的维护工作，直到用户都转移到Dagger2.0。
- 故事二。Google施展它的淫威，把你fork过来，做个更牛逼的，你能怎么办？体面地成为Dagger1.x的奠基者。
### 归档可能产生的影响
对Dagger的用户来说，可能体验更好了。square/dagger的README已经指向google/dagger（Dagger2.X）的链接，用户如果想升级到更好的Dagger2.0，前往google/dagger即可。google/dagger的维护者更多，而且有Google的支持，Dagger社区会更加健壮。
对Dagger的核心贡献者来说，可能有失落，可能也有骄傲？这取决于是上面说的哪个故事。若失落，可能的原因是自己亲手带大的孩子，人家给他包装一下更靓丽了，但是孩子也跟人家了。若骄傲，那便是“嘿，Google看上了我们的项目，还要带它去更好地发展发展”。
### 对开源项目如何可持续发展的理解
三个“有”：

- 有价值。如果一个项目本身非常有它存在的价值，那么人们会主动靠近它。举个极端的例子，代理软件被要求下架，但是无数用户自发地将他们本地的源码传到GitHub上，以相同的名称命名仓库。
- 有人。这个人可以是用户，也可以是贡献者，人与人之间的互动越多越好，这样才能激发人们的成就感和荣誉感，才能形成社区，甚至形成文化。文化潜移默化，经久不衰。
- 有钱。有钱能使鬼推磨，当然也能推开源项目啦。

以上三个“有”，“有价值”和“有钱”非主观努力就一定能实现，但是“有人”这方面，项目维护者可以[努力一下](https://opensource.guide/)。
