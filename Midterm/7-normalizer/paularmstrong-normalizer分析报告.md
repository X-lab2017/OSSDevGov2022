# paularmstrong/normalizer的基本背景和发展历程介绍

## 技术类型

Normalizer是使用javascript语言编写的，用于在前端项目中处理JSON数据。许多API会返回深度嵌套的JSON对象，但是处理这种结构对于javascript应用来说非常困难，比如Flux和Redux。Normalizer是一个小型的但是强大的工具应用，它通过模式定义(schema definition)来处理JSON数据，并且返回嵌套的实体(entity)，每个实体都带有它们本身的从JSON对象中解析出来的ID属性。

## 版本发布历史

参考：https://github.com/paularmstrong/normalizr/releases。Normalizer总共发布了26个版本，目前的最新版本是v3.6.2，发布在2022年3月20日，几乎所有版本都是在2015年到2017年之间发布的。

## 主要贡献者的构成（国家、区域和组织）

最主要的贡献者是Paul Armstrong，来自美国；还有其他提交量较多的贡献者，Dan Gaearon来自美国facebook公司，Daniel Perez Alvarez来自美国twitter公司，Jeff Carbonel来自美国Gusto公司；

## CI/CD的使用

Normalizer在以前的版本中没有在Github上使用过CI/CD流程，但是在最后一个版本，也就是停止维护的版本，写了关闭PR的CI/CD。代码如下：

```yml
name: Close Pull Request

on:
  pull_request_target:
    types: [opened]

jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - uses: superbrothers/close-pull-request@v3
        with:
          comment: 'Normalizr is no longer maintained and does not accept pull requests. Please maintain your own fork of this repository.'
```

表示，一旦有PR的请求到来，就会显示comment所指示的文本。

# 项目的历史轨迹分析

见ipynb文件

# 洞察项目被归档的可能原因

## 可能的归档原因

1、项目被某些人用在不正当场合以谋取利益，生成有破坏性质的内容。

2、开发者想要把精力放在生活或工作的其他方面。

3、不羁放纵爱自由的开发者对此失去了兴趣，想要追寻新的事物，受限于他的个人精力和动力，他要抛弃它，继续前行。

4、GitHub平台本身的规则有不完善之处，给开发者带来了额外的不必要的烦恼，这使得无偿管理维护项目的开发者心生失望。

5、无偿的开源项目分享者，应当得到更多的优势和便利，否则是不公平的。

 

## 可能产生的影响

从用户角度：

1、对于那些需要使用此项目现有功能、资源的用户来说，由于项目已经稳定运行很长时间，因此归档对他们的影响较小。

2、对于那些希望对此项目进行一些改动（增加新的功能、纠正某些错误等）的用户来说，归档会使得他们不能那么做。

3、项目的归档是由于开发者没有精力及时维护，因此，归档能够使项目稳定运行现有功能从而持续给大部分用户提供方便，否则，由于项目更新导致出现问题但没能得到及时的维护反而会影响到用户体验。

 

从开发者角度：

1、一个项目的归档意味着开发者精力的转移，这可能带来另一个更为惊艳的项目，或生活其他方面新的难忘旅程。

2、如果某个热爱者愿意自己维护一个新的版本，他将为给项目带来新鲜血液，或许可以使项目演化的更好。那样话，这理应可以被当作原项目归档带来的成功，同时也给开发者的工作带来更重要的意义。

 

## 开源项目如何持续发展

1、活跃的社区交流，不同思想的碰撞，更多贡献者的努力。

2、无偿的开源项目分享者，应当得到更多的优势和便利，否则是不公平的。

3、完善GitHub平台本身的规则，尽量减少给开发者带来额外的不必要烦恼，这可能使得无偿管理维护项目的开发者心生失望。
