## 一、项目的基本背景和发展历程介绍

通过项目仓库的查阅，以及搜索引擎上项目的相关资料，给出项目一些基本的介绍：

* 技术类型
Simian Army 是由在线视频流媒体公司 Netflix 创建的一组开源云测试工具。这些工具用于产生各种故障、检测异常情况来帮助工程师测试 Netflix 在 Amazon Web Services ( AWS ) 基础设施上运行的云服务的可靠性、安全性、弹性和可恢复性。

截至目前该项目在GitHub上，Star数量有7.9k，Fork数量有1.2k。

Simian Army成员包括：

    * Chaos Monkey 会随机终止在生产环境中运行的 EC2 实例。
    * Latency Monkey 在 RESTful 客户端到服务器通信中引入随机延迟，以模拟服务降级并测量上游服务是否正确响应。
    * Conformity Monkey 在发现不符合最佳实践的实例时将其关闭。
    * Doctor Monkey 会在每个实例中运行健康检查，同时也通过其他外部监控指标来检测不健康的实例。一旦检测到不健康的实例，将它们从服务中删除，并且在实例所有者找到问题的原因后终止。
    * Janitor Monkey 搜索未使用的资源并按规则处理，以确保AWS上的环境资源有效避免浪费。
    * Security Monkey 在发现安全违规或漏洞时，如发现未正确配置的AWS安全组，并终止使用该违规安全组的实例。此外，还会确保所有的 SSL 和 DRM 证书有效且无需续订。
    * 10-18 Monkey （l10n-i18n）针对多个区域和国家的客户提供服务的实例，检查有关语言和字符集的配置。
    * Chaos Gorilla 模拟了 AWS 可用区域（AZ）的中断，以验证服务是否会自动平衡至可用的 AZ ，而无需人工干预，也不会给用户带来可见的影响。
目前，Simian Army 开源项目中的成员为Chaos Monkey、Janitor Monkey和Conformity Monkey，其他成员要么已经被弃用，要么从未开源。

Simian Army主要是基于JAVA实现，目前Simian Army已经停止维护和更新。其中的成员：

    * Chaos Monkey 现在是独立的；
    * Janitor Monkey 被 Swabbie 取代；
    * Conformity Monkey 功能将被整合到其他Spinnaker后端服务中

* 版本发布历史
  Simian Army从2010年演进发展的时间线如下所示：

    * 2010年 Netflix 内部开发了 AWS 云上随机终止 EC2 实例的混沌实验工具： Chaos Monkey
    * 2011年 Netflix 释出了其猴子军团工具集： Simian Army
    * 2012年 Netflix 向社区开源由 Java 构建 Simian Army，其中包括 Chaos Monkey V1 版本
    * 2017年 Netflix 开源 Chaos Monkey 由 Golang 重构的 V2 版本，必须集成 CD 工具 Spinnaker 来使用

具体的，目前在github上开源的Simian Army2.5共计发布了4个版本，其中：

    * 第一个版本（v2.5.0）的发布时间是2016年2月24日
    * 最后一个版本（v2.5.3）的发布时间是2017年1月04日
* 主要贡献者的构成：
  SimianArmy项目共有38名贡献者，项目的前三名贡献者为Cory Bennett、Justin Santa Barbara、Ingmar Krush

    * Cory Bennett (coryb)：提交了77次，位于美国加利福尼亚州，现就职于Netflix，邮箱为[cory.bennett@netflix.com](mailto:cory.bennett@netflix.com)
    * Justin Santa Barbara (justinsb): 提交了74次，位于美国，现就职于谷歌，邮箱为[justinsb@google.com](mailto:justinsb@google.com)
    * Ingmar Krush (IngmarKrusch)：提交了51次，位于德国柏林，现就职于Solarisbank，邮箱为[krusch@gmx.de](mailto:krusch@gmx.de)
* CI/CD的使用
CI/CD 是一种通过在应用开发阶段引入自动化来频繁向客户交付应用的方法。CI/CD 的核心概念是持续集成、持续交付和持续部署。具体而言，CI/CD 可让持续自动化和持续监控贯穿于应用的整个生命周期（从集成和测试阶段，到交付和部署）。这些关联的事务通常被统称为"CI/CD 管道"，由开发和运维团队以敏捷方式协同支持。

Travis CI 提供的是持续集成服务（Continuous Integration，简称 CI）。它绑定 Github 上面的项目，只要有新的代码，就会自动抓取。然后，提供一个运行环境，执行测试，完成构建，还能部署到服务器。

Travis 要求项目的根目录下面，必须有一个.travis.yml文件。这是配置文件，指定了 Travis 的行为。该文件必须保存在 Github 仓库里面，一旦代码仓库有新的 Commit，Travis 就会去找这个文件，执行里面的命令。

SimianArmy项目使用的是Travis CI，下面是其.travis.yml文件的内容：

```plain
language: java
jdk:
- oraclejdk8
sudo: required
dist: trusty
install: ./installViaTravis.sh
script: ./buildViaTravis.sh
cache:
  directories: 
  - $HOME/.gradle/caches
env: 
  global: 
  - secure: WCRqvIKdPdIsoDhsJWZNBZhEH7Jdgz2fmkjzozVjs4dq36ySrH71udNtZcPIsTwjmHpRaGX0XCgmwLC5WorS2TBJJ87oghCP3WWQGMBLcCdXHS8quRdAHLHpNfao/BQrBEA/gmCYoJZdmXKFDc+XKXS5NBrHkkvVfLGCumcP0AI= 
  - secure: TKnGiZyCtWWI/ei2lNDvGIjyAI4W8xMNOlXT6tGiWJgexvFQpTl2NgkMqgwbxReyxj37vdUnn9Lb/883G6zL/uB+l5aCjeCG//6GAbJYdrSZQCE/UCo7iMlAxyqfuIlKcJABIhwpP8Fg4RwqxJG19Tbx5ddg8RP8yKAi1QNx06Y= 
  - secure: nUn8s+1fV60Hxb9V9DouFIOGHeBpeTD7l6Yadw4gthvi/tZndZ+L/Crh1Z9pAU69NqEHG/VcFLUMNER7dQ4rugVbcbfQueeCdnVpmStLS97tAl8kArhpWCk8dQi47IANuQw7U0nVlg3pA8w9HLZX6ee9PnhyG1oOnluPC/x2Or4= 
  - secure: KTtxnPJWfkwNwYkd2IxKAc4dUc6jF0Fd6uhrqK5q36z0RnY4b/gKlx8bjGPcZA5hutNmiN/gxyvpbL/bvVg9buQ2vkybaPZpzpLwhHTXiD5accjQUMuwF8DFYpzIb104hkgzHbrW18JRImK539ib5TTanF3I08F04LssSXG8NnY=
```

* 其他有价值的信息
![](https://s3.cn-north-1.amazonaws.com.cn/awschinablog/aws-chaos-engineering-start1.jpg)


图中展示了混沌工程从2010年演进发展的时间线：

* 2010年 Netflix 内部开发了 AWS 云上随机终止 EC2 实例的混沌实验工具： Chaos Monkey
* 2011年 Netflix 释出了其猴子军团工具集： Simian Army
* 2012年 Netflix 向社区开源由 Java 构建 Simian Army，其中包括 Chaos Monkey V1 版本
* 2014年 Netflix 开始正式公开招聘 Chaos Engineer
* 2014年 Netflix 提出了故障注入测试（FIT），利用微服务架构的特性，控制混沌实验的爆炸半径
* 2015年 Netflix 释出 Chaos Kong ，模拟AWS区域（Region）中断的场景
* 2015年 Netflix 和社区正式提出混沌工程的指导思想 – Principles of Chaos Engineering
* 2016年 Kolton Andrus（前 Netflix 和 Amazon Chaos Engineer ）创立了 Gremlin ，正式将混沌实验工具商用化
* 2017年 Netflix 开源 Chaos Monkey 由 Golang 重构的 V2 版本，必须集成 CD 工具 Spinnaker 来使用
* 2017年 Netflix 释出 ChAP （混沌实验自动平台），可视为应用故障注入测试（FIT）的加强版
* 2017年 由Netflix 前混沌工程师撰写的新书“混沌工程”在网上出版
* 2017年 Russell Miles 创立了 ChaosIQ 公司，并开源了 chaostoolkit 混沌实验框架

## 三、洞察项目被归档的可能原因

* 阅读分析项目的相关信息：
    * 主页、主要贡献者发表的相关技术博客
    * Issue 和 PR 中的相关讨论
    * README 文件，贡献者指南，Code of Conduct及其他可能有的相关文档
* 结合一和二中得到的信息和分析结果，尝试总结项目可能的归档原因
  一、结果不可控。

    * Simian Army中，有一些小的扰动，可能会造成一些规模不可预测的故障，比如 Latency Monkey 中服务之间的调用链传递，可能让一个很小的扰动在传递后引发极大的故障。在生产上做这样不可控的实验，是很危险的。
    * 随着故障注入测试（FIT）的提出，社区开始关注利用应用架构的特性，特别是微服务架构，来控制实验的爆炸半径，将受影响的请求隔离到特定的测试帐户或特定设备，避免100％的混乱。
    * 在新的风险可控的混乱工程技术的提出后，Simian Army的风险性让它被历史淘汰，最终归档。
  二、核心理念变化。

    * 所有软件都有生命周期，随着Netflix环境不断变化提出的新的需求，Simian Army的核心理念也发生了变化。相较于集合打包的服务，后来的Netflix更倾向于将服务分离开来，以便它们可以独立发展。通过将Simian Army中的服务分开，每个成员都可以使用不同的技术和部署模型，例如将 Conformity Monkey 功能直接嵌入到 Spinnaker 中，从而在他们进行部署的同一 UI 中为团队提供反馈，从而提高违规行为的可见性，同时能够显示纠正措施。
* 结合你搜集到的信息，尝试分析项目归档后可能产生的影响（对开发者和用户）
    * 对开发者：无法对项目存在的漏洞和功能进行进一步的补充和完善，同时通过这一个项目的学习和实现，可以将自己的学习到的知识投入到下一个项目中。
    * 对用户：用户在使用该项目时产生的问题无法得到回复和解决，用户体验感下降。
* 表述你对开源项目如何可持续发展的理解
    * 资源充足：要实现可持续性，项目必需能够负担自身的各项成本。成本包括基础设施成本（如托管和配套服务），以及开发、更新和维护代码库的成本。成本还包含项目产生的治理成本、营销成本和沟通成本。
    * 非营利性开放开发：当开发的软件其本身并不创造收益时，可以通过开放源代码来降低开发成本，即考虑成立非营利性组织来管理软件的开发。在这种情况下，基础设施成本和管理成本的很大一部分可被此非营利组织吸收，这些成本由使用非营利性组织管理的产品的公司出资维持。同时，这样可以鼓励更多的组织参与到项目中来，因为他们相信，他们始终可以使用项目产品，并以符合所有贡献者利益的方式管理项目产品。
    * 志愿者/用户参与：志愿者/用户对于开源项目同样很重要，因为用户会提出需求并进行测试。只要能够管理用户对特定版本的期望，就能发行开源软件试用版或早期采用者版本用于测试，这便可以大大降低稳定版本发行前的成本。
