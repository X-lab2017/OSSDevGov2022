| 项目id   | 项目名              | 小组成员                                            |
| -------- | ------------------- | --------------------------------------------------- |
| 18275356 | facebookarchive/pop | 王佳妮51215903081 王颖51215903089 杨苗苗51215903097 |

## 一、项目基本背景

### 1.1 项目信息

- ####  项目背景

​		POP是facebook出品的一个动画引擎，用以支持facebook的新闻聚合类应用paper，以优化其人机交互效果。

​		Facebook的工程师Kimon Tsinteris于2014.4.29宣布，Facebook已将Paper背后的动画引擎Pop放到GitHub上供第三方开发者使用，同时也希望第三方开发者的加入能让这个引擎更加完善。

- ####  项目内容

​		Pop适用于iOS、tvOS、MacOS，相较于iOS、OSX中的基本动画效果，Pop在基本的静态动画的基础上进行扩展，支持弹簧动画效果(Spring)与衰减动画效果(Decay)，可以用来创造出更真实的人机交互效果。

Spring可以让用户触摸的元素能反馈出强有力弹动效果；Decay则可以让弹起来的元素缓慢的停下。这两种特效都会将用户的手势速率纳入考量范围进而创建出逼真的交互效果。除了这两种之外，Pop的自定义特性则允许开发者将自己的动画代码插入其中进而创建出独一无二的动画，开源社区成员将可以在Pop的基础上设计出各种各样的特效。

该项目的所有者是facebook，截至目前该项目在GitHub上，关注该项目的人数有1.1k，收藏该项目的人数有19.8k，Fork该项目的人数有2.9k。

- ####  技术类型

该项目的技术类型如下：

<img src="https://github.com/Vesperrrr/OSSDevGov2022/blob/main/9-pop/image-20220516030214712.png" alt="image-20220516030214712" style="zoom: 50%;" />

### 1.2 版本发布历史

Pop共计发布了11个版本，共计310次提交：

| 版本   | 发布时间   | 发布者          |
| ------ | ---------- | --------------- |
| 1.0.1  | 2014.4.29  | Kimon Tsinteris |
| 1.0.2  | 2014.4.29  | Kimon Tsinteris |
| 1.0.3  | 2014.5.1   | Kimon Tsinteris |
| 1.0.4  | 2014.5.3   | Kimon Tsinteris |
| 1.0.5  | 2014.5.17  | Kimon Tsinteris |
| 1.0.6  | 2014.6.19  | Kimon Tsinteris |
| 1.0.7  | 2014.9.27  | Kimon Tsinteris |
| 1.0.8  | 2015.9.17  | Grant Paul      |
| 1.0.9  | 2015.11.30 | Kimon Tsinteris |
| 1.0.10 | 2017.6.19  | Adam Bell       |
| 1.0.11 | 2018.12.12 | Adam Bell       |



### 1.3 主要贡献者的构成

Pop项目共58位贡献者，主要的四名贡献者是Kimon Tsinteris、Adam Bell、nlutsenko、Grant Paul 。

- #### Kimon Tsinteris

国家：希腊(The Hellenic Republic)

区域：雅典(athens)，目前居住于Hawaii State,U.S

<img src="https://github.com/Vesperrrr/OSSDevGov2022/blob/main/9-pop/image-20220516044927033.png" alt="image-20220516044927033" style="zoom: 25%;" />

​		Kimon Tsinteris最初是苹果公司的高级工程师，帮助创造了iPhone和iPad，后来加入了Push Pop Press，成为Push Pop Press的联合创始人之一。

​		他的公司于2011年被Facebook收购。在Facebook，Kimon Tsinteris带领网络走向native transition、Paper和Instant Articles，是Facebook Paper团队的主要成员之一。同时他也是一名活跃的开源贡献者，重新点燃了iOS OSS计划。目前已于2016年从Facebook辞职。

- ####  Adam Bell

国家：U.S.

区域：San Jose，Califonia

 Adam Bell是该项目的次要贡献者，他是Netflix的一名iOS工程师。

![image-20220516024051955](https://github.com/Vesperrrr/OSSDevGov2022/blob/main/9-pop/image-20220516024051955.png)

- ####  Grant Paul 

区域：California

国家：U.S.

![image-20220516024747107](https://github.com/Vesperrrr/OSSDevGov2022/blob/main/9-pop/image-20220516024747107.png)

### 1.4 CI/CD的使用

**CI/CD**：是一种通过在应用开发阶段引入自动化来频繁向客户交付应用的方法。CI/CD的核心概念是持续集成、持续交付和持续部署。它是作为一个面向开发和运营团队的解决方案，主要针对在集成新代码时所引发的问题。

​		1、持续集成（CI）可以帮助开发者更加方便地将代码更改合并到主分支；

​		2、持续交付旨在建立一个可随时将开发环境的功能部署到生产环境的代码库；

​		3、持续部署(CD)作为持续交付的延伸，持续部署可以自动将应用发布到生产环境。

**Travis CI：**提供持续集成服务（Continuous Integration，简称 CI）。它绑定 Github 上面的项目，只要项目仓库有新的Commit，就会自动抓取。然后，提供一个运行环境，执行测试，完成构建，还能部署到服务器。

​		在Pop中，我们可以在仓库中找到`.travis.yml`文件，该文件定义了Travis CI的持续集成和持续交付行为，一旦项目有了新的提交，Travis CI就会根据该文件执行里面的命令。

`.travis.yml`文件的内容如下：

![image-20220516082152120](https://github.com/Vesperrrr/OSSDevGov2022/blob/main/9-pop/image-20220516082152120.png)

该配置文件定义了如下操作：

- ##### 指定运行环境

  - `language`字段指定了默认运行环境，为`objective-c`

  - `env`字段定义环境变量

- ##### 安装依赖包（`install`）

  - `xcpretty`：用于对`xcodebuild`的输出进行格式化。并包含输出report功能。

  - `cocoapods`：`CocoaPods`是一个用来帮助我们管理第三方依赖库的工具，是一个可以自动部署到项目的组件池，CocoaPods会自动完成组件集成到现有项目的工作。它可以解决库与库之间的依赖关系，下载库的源代码，同时通过创建一个`Xcode`文件的`.xcworkspace`文件来将这些第三方库和我们的工程连接起来，CocoaPods会自动完成组件集成到现有项目的工作，供项目使用。

  - 运行`pop install`：安装依赖库

- ##### 构建或测试脚本（`script`）

  - `set -o pipefail`：首先检查管道，要有任何一个命令失败（返回值非0），则整个管道操作被视为失败

  - `xcodebuild`：自动化打包

  - `pod lib lint`：从本地验证pod能否通过验证

- ##### 脚本执行成功后`after_success`

  - `script` 阶段成功时执行`after_success`阶段代码

### 1.5 其他有价值的信息

1、[Facebook 美学转变：从收购 Push Pop Press 开始 | 爱范儿 (ifanr.com)](https://www.ifanr.com/48315)介绍了pop的背景

2、[iOS 走进Facebook POP的世界 - 简书 (jianshu.com)](https://www.jianshu.com/p/0bc2127692e5)介绍了pop的使用

## 二、项目历史轨迹分析

1、见 facebook-pop.ipynb 文件

## 三、归档原因

### 1、归档原因

- ##### 开发者方面

​		该项目是为facebook于2014年推出的产品paper开发的动画引擎，而paper在2016年已经被facebook关闭。观察其开发者Kimon Tsinteris的推特和facebook动态，可以发现其于2016年在facebook离职后，便没有再做工程师。而该项目的第二贡献者Adam Bell是netflix的工程师，不会有那么多的时间去维护这个项目，不去接手这个项目也是理所当然。

- ##### 用户需求方面

​		根据项目历史轨迹分析可以发现该项目在paper关闭以后，便很少有人再关注，推测其为该项目归档的原因之一。且该框架提供的动画本身就足够丰富，在用户体验方面也是得到了很高的评价，所以也不太有必要再去维护.

### 2、归档的影响

- ##### 开发者方面

​		从paper团队的三位主要成员Kimon Tsinteris、Mike Matas和Scott Goodson过往的发言可以看出，他们在开发pop这个动画框架的时候还是很用心的，没有能够将他们的热爱延续下去还是很可惜的。

- ##### 用户方面

​		在项目的issue和网络上，看到很多用户形容这个框架是“革命性的”、“magic”、“里程碑”，并且寻求能够提供类似体验的APP，可以感受到很多用户还是很惋惜的。

### 3、 对开源项目如何可持续发展的理解

​		近年来，众多以开源项目为基础的创业公司诞生并取得了成功，很多企业和个人也纷纷加入开源的行列，但是实现开源项目的可持续发展并不是一件容易的事情。开源项目想要实现可持续的发展，首先项目要有创新，才能吸引更多的关注，提升自身的影响力；其次，光是项目本身优秀还不够，后续的维护也是十分重要的，才能保障发展的可持续性。实现开源项目的可持续发展，光凭开发者的一腔热血还不够，为项目提供金钱和人员上的支持也很重要。
 	   虽然开源已经得到了很多的关注度，但是很多人对开源的概念还是“开源=免费”。很多企业只是将开源产品理所当然地拿来使用，并没有认真思考和对待开源所涉及的商业、权属、贡献等问题。为了实现开源项目的可持续发展，需要普及开源的概念，完善开源知识产权和法律体系，来保护开源资源贡献者的权益，以及保证行业的健康发展。

