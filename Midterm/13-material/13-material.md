<center><h1>开源课程期中作业 </h1></center>

| 归档开源项目名称 | 13-21399598-angular/material |
| :--------------: | :--------------------------: |
|   **小组成员**   |      刘颖凡 51215903009      |
|                  |      魏如蓝 51215903002      |
|                  |      王原昭 51215903074      |



### 一、项目的基本背景和发展历程介绍

-----

#### 1.1 项目基本情况

- 项目angular/material是github中一个曾高度流行的开源项目，自2014年6月开始创建维护，至2022年1月归档。

- Angular是AngularJS的重写。AngularJS诞生于2009年，由Misko Hevery 等人创建，是一款构建用户界面的前端框架，用于创建高效、复杂、精致的单页面应用，通过新的属性和表达式扩展了 HTML，实现一套框架，多种平台，移动端和桌面端。后为Google收购，官方命名为Angular。AngularJS是用JavaScript编写，而Angular采用TypeScript语言编写，是ECMAScript 6的超集。

- Angular有着诸多特性，最为核心的是：MVVM、模块化、自动化双向数据绑定、语义化标签、依赖注入等等。

- Angular是为了克服HTML在构建应用上的不足而设计的，通过以下技术来解决静态网页技术在构建动态应用上的不足：

  - **类库** - 类库是一些函数的集合，它能帮助你写WEB应用。起主导作用的是你的代码，由你来决定何时使用类库。类库有：jQuery等。
  - **框架** - 框架是一种特殊的、已经实现了的WEB应用，你只需要对它填充具体的业务逻辑。这里框架是起主导作用的，由它来根据具体的应用逻辑来调用你的代码。框架有：knockout、sproutcore等。

- Angular Material 是一个 UI组件库，它在 Angular 中实现了 Material Design。

  

#### 1.2 版本发布历史

- Angular Material共发布了16个版本：

  + 第一个版本发布于2014年10月7日（v0.4）

  + 最后一个版本发布于2022年4月13日（v1.2.5）

    


#### 1.3 主要贡献者

项目参与者众多，主要参与者（commit次数大于100）有如下3位：

- **ThomasBurleson**
  - 国家或地区：Iowa,  USA
  - 所属公司或组织：Mindspace, LLC
  - 该作者主要参与AngularJS的早期工作，主要贡献在2015年至2018年之间，是贡献排名度第一的作者。除AngularJS外，该作者参与多项web应用构建，至今活跃在github，最近一次提交在2022年5月。

- **ajoslin**
  - 国家或地区：USA
  - 该作者是AngularJS早期提交最多的作者，在2015-2016年间完成了541次commits。目前仍高度活跃在github，在过去的一年中有2020次提交，主要工作用JavaScript和TypeScript完成。

- **Splaktar**

  - 国家或地区：Melbourne，FL

  - 所属公司或组织：Devintent

  - 该作者是AngularJS中后期的主要贡献者，至今仍活跃在github，过去的一年中完成了1400次contributions，主要工作用JavaScript和TypeScript完成。

    

#### 1.4 CI/CD的使用

- **CI (Continuous integration, 持续集成)**
  - 在持续集成环境中，开发人员将会频繁的提交代码到主干。这些新提交在最终合并到主线之前，都需要通过编译和自动化测试流进行验证。这样做是基于之前持续集成过程中很重视自动化测试验证结果，以保障所有的提交在合并主线之后的质量问题，对可能出现的一些问题进行预警。

- **CD（持续集成/持续交付）**
  - 持续交付（Continuous delivery）指的是，频繁地将软件的新版本，交付给质量团队或者用户，以供评审。如果评审通过，代码就进入生产阶段。 持续交付可以看作持续集成的下一步。它强调的是，不管怎么更新，软件是随时随地可以交付的。
  - 持续部署（continuous deployment）是持续交付的下一步，指的是代码通过评审以后，自动部署到生产环境。持续部署的目标是，代码在任何时刻都是可部署的，可以进入生产阶段。

- GitHub Actions

  - 本项目使用GitHub Actions。GitHub Actions是由GitHub创建的 CI/CD服务。 它的目的是使所有软件开发工作流程的自动化变得容易。 直接从GitHub构建，测试和部署代码。CI（持续集成）由很多操作组成，比如代码合并、运行测试、登录远程服务器，发布到第三方服务等等。GitHub 把这些操作就称为 actions。
  - GitHub Ac­tions 的配置文件叫做 work­flow 文件，可以在AngularJS代码仓库中的`.github/workflows` 目录中看到配置文件codeql-analysis.yml，其内容如下：

  ```yaml
  name: "CodeQL"
  
  on:
    push:
      branches: [ master ]
    pull_request:
      # The branches below must be a subset of the branches above
      branches: [ master ]
    schedule:
      - cron: '45 16 * * 2'
  
  jobs:
    analyze:
      name: Analyze
      runs-on: ubuntu-latest
  
      strategy:
        fail-fast: false
        matrix:
          language: [ 'javascript' ]
          # CodeQL supports [ 'cpp', 'csharp', 'go', 'java', 'javascript', 'python' ]
          # Learn more:
          # https://docs.github.com/github/finding-security-vulnerabilities-and-errors-in-your-code/configuring-code-scanning#changing-the-languages-that-are-analyzed
  
      steps:
      - name: Checkout repository
        uses: actions/checkout@v2
  
      # Initializes the CodeQL tools for scanning.
      - name: Initialize CodeQL
        uses: github/codeql-action/init@v1
        with:
          languages: ${{ matrix.language }}
          # If you wish to specify custom queries, you can do so here or in a config file.
          # By default, queries listed here will override any specified in a config file.
          # Prefix the list here with "+" to use these queries and those in the config file.
          # queries: ./path/to/local/query, your-org/your-repo/queries@main
  
      # Autobuild attempts to build any compiled languages  (C/C++, C#, or Java).
      # If this step fails, then you should remove it and run the build manually (see below)
      - name: Autobuild
        uses: github/codeql-action/autobuild@v1
  
      # ℹ️ Command-line programs to run using the OS shell.
      # 📚 https://git.io/JvXDl
  
      # ✏️ If the Autobuild fails above, remove it and uncomment the following three lines
      #    and modify them (or add more) to build your code if your project
      #    uses a compiled language
  
      #- run: |
      #   make bootstrap
      #   make release
  
      - name: Perform CodeQL Analysis
        uses: github/codeql-action/analyze@v1
  ```

  - 通过配置文件内容可知，work­flow的触发条件是push，pull_request，schedule，并定义了analyze job，运行在ubuntu系统上，定义了一些action，具体内容写在项目文件```actions/checkout@v2```中。



### 二、项目的历史轨迹分析  

--------

- 关于项目的具体数据分析详见`13-angular/material.ipynb`文件

- 可视化结果展示：

  <img src="E:\DaSE2021-2022(下)\开源\images\1.png" style="zoom:80%;" />

  <img src="E:\DaSE2021-2022(下)\开源\images\2.png" style="zoom:80%;" />

  <img src="E:\DaSE2021-2022(下)\开源\images\3.png" style="zoom:80%;" />

  <img src="E:\DaSE2021-2022(下)\开源\images\4.png" style="zoom:80%;" />

- 几个重要的时间节点：

  - 从上述可视化结果可以发现，开源项目开发者的活跃度与项目本身的关注度和活跃度有很大的关系：本项目在2015-2016年期间有较高的活跃度，相应的活跃的开发者的数量也呈上升趋势；
  - 项目在2016-2020年期间项目活跃开发者的数量有大幅下降的趋势，项目的活跃度也随之降低，查阅资料发现，该项目在此期间没有版本更新（Angular第二个版本发布于2014年12月2日，第三个版本发布于2020年3月14日），提出的issues/PRs无法获得及时的反馈和修改。



### 三、 项目归档原因分析

-------

#### 3.1 从AngularJS到Angular

- AngularJS最初诞生于2009年，由Misko Hevery等人创建，后来被Google收购。在发展过程中，项目组对AngularJS完成了使用Typescript重写的工作，官方命名为Angular。本文分析的项目是第一版本的AngularJS开源文件，由Javascript写成。

- 2022年1月12日，Angular项目发布了停止更新支持AngularJS Materia的通知，项目负责人Mark Thompson发布了博文Discontinued Long Term Support for AngularJS。在博文中他提到，早在2018年，团队就制定了AngularJS的最终维护计划 long-term support(LTS)，受全球疫情影响，LTS工作延长至2021年12月31日。

- 目前团队主要运营AngularJS的继任者：Angular，一个基于TypeScript的免费和开源Web 应用程序框架，他与AngularJS的主要差异有：

  + Angular 没有“范围”或控制器的概念；相反，它使用组件的层次结构作为其主要架构特征

  + Angular 有不同的表达式语法，专注于"[ ]"属性绑定"( )"和事件绑定

  + 模块化——许多核心功能已经转移到模块中

  + Angular 推荐使用微软的TypeScript语言，它引入了以下特性：静态类型，包括泛型；注释

  + TypeScript是ECMAScript 6 (ES6) 的超集，并且向后兼容ECMAScript 5（即：JavaScript）

  + 动态加载

  + 异步模板编译

  + RxJS 提供的迭代回调

  + 支持 Angular Universal，它在服务器上运行 Angular 应用程序

    


#### 3.2 项目可能的归档原因

- **项目较高的关注度与较少的活跃开发者数量之间的矛盾。**

  - 通过第二部分的可视化分析可以看到，Angular项目自上线以来被关注的数量（以star/fork数为例）是百万级别的，但对应的活跃开发者的数量在最活跃时期也仅有6000左右，因此对于这些开发者而言，承担着相对较大的开发压力。

- **开源项目与商业化项目的平衡矛盾。**

  - AngularJS在2009年由Miško Hevery和Adam Abrons开发，作为线上JSON储存服务的软体，它是以兆位元来计价，便于成为企业的应用服务。当初以"GetAngular.com"注册网域，但由于只有少量的注册用户，在两人决定放弃这个商业想法前，就把Angular开源了。因此，如何在开源项目中平衡好开发者的贡献与商业性的回报，对于延续开源项目的生命力起着至关重要的作用。

    

#### 3.3 归档后的影响

- 对于AngularJS，项目归档后，所有项目代码仍会在GitHub公开，但不可以提交新的PR和issue。

- 对于使用AngularJS构建的web应用，Angular团队强烈建议升级成AngularJS的继任者Angular，并从生产力、可扩展性和改进的性能中受益。网站```https://angular.cn/guide/upgrade```中提供了详细的升级教程。

- 对于不进行升级的应用开发者，可以通过查阅github中的已有PR/issue，网站```https://material.angularjs.org/latest/#long-term-support```中的所有信息仍可访问参考。

  

#### 3.4 开源项目如何可持续发展

“开源（Open Source）”的话题热度在近些年颇有蓬勃发展之势。2021年，我国工信部信息技术发展司发布了《“十四五”软件和信息技术服务业发展规划》，其中提到了“开放、平等、协作、共享”的开源模式，加速软件迭代升级，促进产用协同创新，推动产业生态完善，成为全球软件技术和产业创新的主导模式。在软件吞噬世界、开源吞噬软件的今天，如何保持开源生态的可持续性，维持开源项目的活力性，成为了一件值得我们思考的事情。

其中一个不可忽视的原因即是**如何平衡好开发者贡献性与商业性回报的问题**。根据本项目的历史轨迹和归档原因分析可知，对于开源项目而言，有活力的开发者能够保障项目的稳定性和延续性，适度的商业化回馈能够为开发者提供有力的保障，但过度商业化反而会流失掉用户的关注度。

除此之外，根据VM BRASSEUR《开源项目的可持续性：4 个大问题》一文中提到的，考虑开源的项目的可持续性，一般需要考虑四个问题：

- **项目当前的状态。**这一点要求我们对开源项目要有基本的了解，不仅仅是掌握项目的关注人数、issue/PR数量等信息，更要关注贡献者和用户，了解他们对项目的真实看法，从而精准把控项目的痛点和瓶颈。
- **项目未来的规划。**这一点与承接上一条的思想，可以将社区团结起来朝着一个共同的目标，并帮助确定一个方向，以更好地确保项目以可持续的方式发展。
- **项目应该如何从现在的状态到达未来规划的状态。**了解到项目当前状态和未来的发展方向，能够帮助我们理清软件开发的创建路线图，进而列出要处理的功能计划和顺序，将开源项目朝着更加扎实的方向迈进。
- **项目如何保持在我们期待其达到的状态。**最后一个问题是在上面三点基础上进行思考的，这要求我们要定期与项目社区分享，思考并重新审视，以确保项目仍在朝着可持续发展的方向发展。

以上四个问题，将在很大程度上取决于项目本身，包括它的需求、定位以及文化。有些开发者会倾向于制定最低限度可行的计划，然后定期对其进行迭代；而对于其他人而言，“瀑布式方法”更加受到其青睐，即提出详细的路线图来打动潜在的赞助商和贡献者。唯一错误的做法是根本不去做，错误地认为项目的可持续性是可以推迟到以后的事情。



### 参考材料

-----------

> 1. 停止更新声明blog：https://blog.angular.io/discontinued-long-term-support-for-angularjs-cc066b82e65a
> 2. TS版本官网，关于从JS版本升级到TS版本的指南文档：https://angular.cn/guide/upgrade
> 3. JS版本官网：https://material.angularjs.org/latest/#long-term-support
> 4. https://www.fosslife.org/sustainability-open-source-projects-4-big-questions
> 5. https://kaiyuanshe.cn/document/china-os-report-2021/
> 6. https://zh.m.wikipedia.org/zh-hans/AngularJS#Angular_Material

