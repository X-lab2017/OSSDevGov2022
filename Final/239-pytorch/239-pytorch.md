

| 项目id   | 项目名          | 小组成员                                             |
| -------- | --------------- | ---------------------------------------------------- |
| 65600975 | pytorch/pytorch | 陈诺 51215903008 王帅 51215903058 刘通宇 51215903045 |

# 一、项目的基本背景和发展历程介绍

通过项目仓库的查阅，以及搜索引擎上项目的相关资料，给出项目一些基本的介绍:

## 1.1 技术类型

Pytorch是一个开源的**端到端的机器学习框架**，由Facebook 的 AI 研究小组创建。其作为一个Python软件包，通过一个用户友好的前端、分布式训练以及一个Python库的生态系统，加速了从研究原型到生产部署的路径，实现了快速、灵活的实验和高效的生产。它提供了两个主要功能：

- **张量计算**（如NumPy），具有强大的GPU加速能力
- **建立**在基于磁带的自控系统（**动态**反向传播机制）上的**深度神经网络**

通常情况下，PyTorch可以作为。

- NumPy的替代品，以**利用GPU的力量**
- 一个深度学习研究平台，提供最大的灵活性和速度

Pytorch的框架集成了英特尔MKL和英伟达cuDNN，NCCL等加速库，以最大限度地提高速度。在整体**工作流程**上，PyTorch 使用一种称之为 **imperative / eager** 的范式，即每一行代码都要求构建一个图以定义完整计算图的一个部分。即使完整的计算图还没有完成构建，也可以独立地执行这些作为组件的小计算图，这种动态计算图被称为define-by-run方法。

Pytorch技术上最重要的概念是**张量**（Tensor）。张量就是向量和矩阵的推广，PyTorch 中的张量就是元素为同一数据类型多维矩阵。虽然 PyTorch 的接口是 Python，但**底层主要都是用 C++实现的**，而在 Python 中，集成 C++代码通常被称为"扩展"。

张量主要承载数据，并进行计算。PyTorch 的张量计算使用最底层和基本的张量运算库 ATen，它的自动微分使用 Autograd，该自动微分工具同样建立在 **ATen 框架**上。

而张量在CPU和GPU内存分配上，其实际原始数据并不是立即保存在张量结构中，而是**保存在"存储（Storage）"中**，它是张量结构的一部分。一般张量存储可以通过 Allocator 选择是储存在计算机内存（CPU）还是显存（GPU）。

## 1.2 版本发布历史

Pytorch共计发布了39个[releases](https://github.com/pytorch/pytorch/releases)，其中：

- 第一个releases（v0.1.1 alpha-1）的发布时间是2016年9月1日
- 最后一个releases（v1.11.0 Pytorch 1.11）的发布时间是2022年3月11日

Pytorch共计有24个stable版本和一个candidate：

- [v1.12 (release candidate)](https://pytorch.org/docs/1.12/)
- [v1.11 (stable release)](https://pytorch.org/docs/1.11/)
- [v1.10](https://pytorch.org/docs/1.10/)
- [v1.9.1](https://pytorch.org/docs/1.9.1/)
- [v1.9.0](https://pytorch.org/docs/1.9.0/)
- [v1.8.1](https://pytorch.org/docs/1.8.1/)
- [v1.8.0](https://pytorch.org/docs/1.8.0/)
- [v1.7.1](https://pytorch.org/docs/1.7.1/)
- [v1.7.0](https://pytorch.org/docs/1.7.0/)
- [v1.6.0](https://pytorch.org/docs/1.6.0/)
- [v1.5.1](https://pytorch.org/docs/1.5.1/)
- [v1.5.0](https://pytorch.org/docs/1.5.0/)
- [v1.4.0](https://pytorch.org/docs/1.4.0/)
- [v1.3.1](https://pytorch.org/docs/1.3.1/)
- [v1.3.0](https://pytorch.org/docs/1.3.0/)
- [v1.2.0](https://pytorch.org/docs/1.2.0/)
- [v1.1.0](https://pytorch.org/docs/1.1.0/)
- [v1.0.1](https://pytorch.org/docs/1.0.1/)
- [v1.0.0](https://pytorch.org/docs/1.0.0/)
- [v0.4.1](https://pytorch.org/docs/0.4.1/)
- [v0.4.0](https://pytorch.org/docs/0.4.0/)
- [v0.3.1](https://pytorch.org/docs/0.3.1/)
- [v0.3.0](https://pytorch.org/docs/0.3.0/)
- [v0.2.0](https://pytorch.org/docs/0.2.0/)
- [v0.1.12](https://pytorch.org/docs/0.1.12/)

## 1.3 主要贡献者的构成 (国家、区域和组织等)

据PYTORCH GOVERNANCE 团队所述，PyTorch 团队拥有近 100 名核心成员，来自Facebook 内部和外部，和众多开源贡献者及维护人员。Pytorch的Github项目截止2022年6月28日共2329个贡献者，其中包括4名1000+commits（ezyang, gchanan, malfet, jerryzh168）和10名500+commits的贡献者。

[PYTORCH GOVERNANCE](https://pytorch.org/docs/stable/community/persons_of_interest.html)列出的General Maintainers共6位：

- ### Soumith Chintala (Github：[soumith](https://github.com/soumith))

  个人主页：https://soumith.ch/

  地区： 美国 纽约

  Chintala是Fackbook Meta AI Research 的一名 AI 研究员和程序员，近期方向是机器人，专注于机器学习平台和生成模型。

- ### Edward Yang (Github：[ezyang](https://github.com/ezyang))

  个人主页： [http://ezyang.com](http://ezyang.com/)

  Github账号：ezyang

  地区：美国 加利福尼亚州

  Yang2017年4月毕业于麻省理工学院，后在 Facebook NY 工作至今，任人工智能研究工程师。Yang正在做编程语言和机器学习的交叉点，且主要负责在 GHC 中实现BackPack（一个新的 Haskell 混合模块系统）。

- ### Greg Chanan (Github：[gchanan](https://github.com/gchanan))

  领英：https://www.linkedin.com/in/gregory-chanan-49530836

  地区：美国 纽约

  Chanan2010年毕业于麻省理工，现在Fackbook任技术主管/软件工程经理。

- ### Dmytro Dzhulgakov (Github：[dzhulgakov](https://github.com/dzhulgakov))

  领英：https://www.linkedin.com/in/dzhulgakov

  地区：美国 加利福尼亚州

  Dzhulgakov2012年毕业于国立工业大学“哈尔科夫理工学院”，2017年10月至今担任Fackbook首席工程师和技术主管。Dzhulgakov主要对一个从事PyTorch深度学习框架（http://pytorch.org）和更广泛的Facebook AI平台的优秀工程师团队进行技术和战略领导。Dzhulgakov的工作是建立PyTorch的功能，以加快前沿的人工智能研究向生产的过渡。

- ### (emeritus) Sam Gross (Github：[colesbury](https://github.com/colesbury))

  个人主页：**http://web.mit.edu/sgross/www**

  领英：https://www.linkedin.com/in/samgross

  Gross2010年毕业于麻省理工学院，2015年3月至今任Facebook AI Research的软件工程师。

- ### (emeritus) Adam Paszke (Github：[apaszke](https://github.com/apaszke))

​		个人主页：http://apaszke.github.io/

​		领英：https://pl.linkedin.com/in/apaszke/en

​		Paszke2020年毕业于Warszawski大学，与上述几位贡献者				不同的是，Paszke2018年离开Facebook，2019年至今在				Google任高级研究员。

## 1.4 $\mathrm{CI} / \mathrm{CD}$ 的使用

CI/CD是一种通过在应用开发阶段引入自动化来频繁向客户交付应用的方法。CI/CD的核心概念是持续集成、持续交付和持续部署。在Pytorch项目中，使用CircleCI进行持续集成。

Pytorch项目的[.config.yml](https://github.com/pytorch/pytorch/blob/master/.circleci/config.yml)文件共1244行，该文件说明了：

- Pytorch同时支持windows，macos，linux系统
- Pytorch需要conda环境，并需要根据系统配置CUDA
- 提供了run_binary_tests，run_build，run_master_build,run_slow_gradcheck_build等多种build方式

## 1.5其他有价值的信息

### Pytorch与TensorFlow

由于Pytorch在模型可用性，部署基础设施，生态系统等方面的一些优势，科研界使用Pytorch较多，具体表现有：

- Huggingface的85%的模型是Pyorch专有的，即使那些不是专有的模型也有大约 50% 的机会在 PyTorch 中可用。
- 从2019年中期开始,在统计的各大顶会中，Pytorch从使用率指标上就已完成了对TensorFlow的反超。EMNLP、ACL、ICLR三家顶会的PyTorch的占比超过80%。

相关链接：https://www.assemblyai.com/blog/pytorch-vs-tensorflow-in-2022/

https://www.projectpro.io/article/pytorch-vs-tensorflow-2021-a-head-to-head-comparison/416

https://new.qq.com/omn/20220315/20220315A045GB00.html

### Pytorch与JAX

谷歌眼见Tensorflow被Meta的PyTorch击溃，为高性能数值计算而设计出了新机器学习框架JAX。在多核处理器调度问题上，JAX会自动地将若干个芯片组合而成一个小团体，而不是让一个去单打独斗，这样可以让尽可能多的TPU片刻间就能得到响应。

虽然TensorFlow和Pytorch有编译的执行模式，但这些模式是后来加入的，因此留下了伤痕。例如，TensorFlow的急切模式与图形模式并非100%兼容，这使得开发者的体验很差。Pytorch有一个糟糕的历史，它被迫使用不太直观的张量格式，因为它们是在急切模式下执行的。JAX到达时有这两种模式--专注于用于调试的eager和用于执行重型计算的JIT。但是这些模式的干净性质允许在需要时进行混合和匹配。

PyTorch和Tensorflow是深度学习库，由深度学习中现代方法的高级API组成。相比之下，JAX是一个更注重功能的库，用于任意可分的编程。

相关链接：https://www.businessinsider.com/facebook-pytorch-beat-google-tensorflow-jax-meta-ai-2022-6

https://analyticsindiamag.com/jax-vs-tensorflow-vs-pytorch-a-comparative-analysis/

https://www.assemblyai.com/blog/why-you-should-or-shouldnt-be-using-jax-in-2022/

# 三、结合期中分析的归档项目，对比分析活跃/归档项目

我们小组期中分析的项目是Upterm，Upterm是一个开源的控制台的集成开发环境（IDE），但该项目与本项目分析的Pytorch不同，Upterm是归档项目而Pytorch是活跃项目。在这一部分我们将以Upterm项目与本项目分析的Pytorch项目进行对比分析，通过分析项目基础数据（新增Star和Fork的个数，每月打开和关闭Issue个数，PR个数）与活跃开发者数量变化趋势，探究开源项目发展到活跃或归档的主要原因。

## 3.1 项目基础数据的变化趋势

项目基础数据包括：①每月新增Star和Fork个数；②每月打开 Issue 和 关闭Issue的个数；③每月打开PR和合入PR的个数。下面将之前对两个项目历史轨迹数据的分析结果拿出，分别进行对比与分析。

### 3.1.1 每月新增Star和Fork个数

项目每月新增Star和Fork个数可以一定程度上反映项目的热度，其中每月新增Star个数可以反映该项目的使用者对该项目的评价，而每月新增Fork个数反映了该项目开发者的参与程度，这是评价开源项目热度的最基本的两项指标。

经统计，2个项目每月新增Star和Fork个数的折线图对比如下：

Pytorch（活跃项目）

![fig.1-a](.\images\pytorch_fig1.png "Pytorch每月新增Star和Fork个数")

Upterm（归档项目）

![fig.1-b](.\images\upterm_fig1.png "Upterm每月新增Star和Fork个数")

> 注：由于Upterm项目每月新增Star和Fork个数最大值与最小值差异较大，为了绘制图表的美观，故使用对数坐标轴。

由折线图的变化趋势可以看出：
- 每月新增Star和Fork个数可以一定程度上反映项目的热度，且每月新增Star和Fork个数基本呈现一致的趋势，每月新增Fork个数随时间的波动较为稳定；
- 上述2个项目都曾经有过非常热门的时期。例如Pytorch在2017年1月，Upterm在2015年9月，达到热度的峰值，其每月新增Star个数分别达到3k与5k左右；
- 在达到热度的峰值之后，Pytorch（活跃项目）的热度逐渐下降但趋于稳定，其每月新增Star和Fork个数分别基本维持在1k与250左右，表明该项目长期以来均有使用者与开发者参与其中，使得其保持活跃状态；
- 在达到热度的峰值之后，Upterm（归档项目）的热度也逐渐下降，但是与活跃项目不同，其热度在之后的几年内迅速地持续下降（在对数坐标轴上这一点可以明显地看出），最终每月新增Star和Fork个数仅有几个，进而项目被归档。

### 3.1.2 每月打开Issue和关闭Issue的个数

项目每月打开和关闭Issue的个数可以一定程度上反映项目开源社区讨论的热度，通常对项目的问题或者bug反馈都是通过Issue来进行的，这是评价开源项目热度的另一项指标。

经统计，2个项目每月打开与和关闭Issue个数的折线图对比如下：

Pytorch（活跃项目）

![fig.2-a](.\images\pytorch_fig2.png "Pytorch每月打开Issue和关闭Issue的个数")

Upterm（归档项目）

![fig.2-b](.\images\upterm_fig2.png "Upterm每月打开Issue和关闭Issue的个数")

由折线图的变化趋势可以看出：
- Pytorch（活跃项目）的社区讨论热度是随着项目的发起而逐渐增长，达到峰值之后趋于稳定，截至目前该项目每月打开和关闭Issue个数基本都维持在数百条；
- Upterm（归档项目）的社区讨论热度主要存在3个高峰：2015年9月，2016年4月，2017年7月，经历这3次高峰后，该项目的社区讨论热度迅速衰减，直至最后的无人问津而被归档；

除此之外，上述折线图还能反映以下信息：
- 普遍来说，Pytorch项目在上述时间段每月打开和关闭Issue个数要比Upterm高出许多，前者大约保持在400左右而后者最高不超过100。其原因可能在于Pytorch是深度学习框架，相较于Upterm控制台集成开发环境，其功能、代码复杂程度以及使用学习成本均较高，因此社区发布的Issue个数会较多；
- 从这2个项目每月打开和关闭Issue个数的对比情况可以看出Upterm的开源社区处理Issue的效率比较高，几乎所有发出的Issue都能够及时得到处理，而Pytorch可能由于Issue数量多，涉及内容复杂困难等原因，导致大约每个月只有7成左右的Issue得到处理；
- 每月打开和关闭Issue个数与每月新增Star和Fork个数都可以一定程度反映开源项目的热度，结合这2个指标的对比情况，可以发现当一个项目每月新增Star和Fork个数较高时，其每月打开和关闭Issue个数也较高，表明这2个指标都能够反映的特征是一致的。

### 3.1.3 每月打开PR和合入PR的个数

项目每月打开PR和合入PR的个数可以一定程度上反映项目开发者、管理者更新项目的活跃程度，通常对项目的更新或者bug修复，是开源项目的开发者通过签出分支并提交PR的方式进行的，项目管理者会对PR进行审核，审核通过后进行合并。这是评价开源项目热度的另一项指标。

经统计，2个项目每月打开PR和合入PR的个数的折线图对比如下：

Pytorch（活跃项目）

![fig.3-a](.\images\pytorch_fig3.png "Pytorch每月打开PR和合入PR的个数")

Upterm（归档项目）

![fig.3-b](.\images\upterm_fig3.png "Upterm每月打开PR和合入PR的个数")

由折线图的变化趋势可以看出：
- Pytorch（活跃项目）每月打开PR的个数从项目的发起开始逐渐稳步上升，达到一定数量后在一定范围内波动，总体而言维持在1k左右的水平，表明参与该项目开发者的活跃程度长时间稳定在一定水平；而每月合入PR的个数，在项目发起的初始阶段基本与打开PR的个数呈现一样的趋势，待项目发起1年左右后到达稳定阶段后，每月合入PR的个数大幅减少，后续每月合入PR的个数仅占每月打开PR的个数的很小一部分；
- Upterm（归档项目）每月打开与合入PR的个数大部分时间一直维持在较低水平，且打开与合入PR的个数具有相同的变化趋势，即大部分发起的PR操作最后都被合入了，其中该项目打开与合入PR的热点主要由2个，2015年9月与2016年7月，表明该项目在这两段时间内进行了多次更新，并且在相邻的时间范围内，每月合入PR的个数占打开PR的个数的比例有所下降。

## 3.2 项目每月活跃开发者数量变化趋势

项目活跃开发者也能够反映开源项目的热度，活跃开发者越多，说明能够说明开源项目具有的影响范围更大，也说明项目对开源社区开发者的吸引程度越大。这里统计的活跃开发者数量指的是在统计周期（一个月）内，在项目日志中出现的不同开发者的总数。

经统计，2个项目活跃开发者数量变化趋势的折线图对比如下：

Pytorch（活跃项目）

![fig.4-a](.\images\pytorch_fig4.png "Pytorch活跃开发者数量变化趋势")

Upterm（归档项目）

![fig.4-b](.\images\upterm_fig4.png "Upterm活跃开发者数量变化趋势")

> 注：同样的原因，此处折线图使用对数坐标轴。另外还需特别说明，从数据库查询得到的数据该项目最大的每月活跃开发者可达5k，这与先前的调查分析存在出入，可能是数据库的原始数据存在问题。

由折线图的变化趋势可以看出：
- Pytorch（活跃项目）每月活跃开发者数量从项目的发起开始持续稳步上升，达到一定数量（大约为200人左右）后长时间维持在该水平，存在一定波动，说明该项目长时间以来有一定数量的开发者持续参与；
- Upterm（归档项目）每月活跃的开发者数量一直处于较少水平，大部分情况下活跃开发者数量不超过10人，事实上通过该项目的主要贡献者可以得知该项目基本上由项目拥有者本人独立开发，因此会产生这样的现象。除此之外，该项目也有过数次活跃开发者数量的高峰，分别在2015年9月，2016年7月，2017年7月，在这几段时间内有较多的开发者参与该项目。从这之后，该项目的活跃开发者就逐渐降低，之后长时间维持在个位数的级别。

## 3.3 项目发展到活跃/归档的主要影响因素探究

通过2个开源项目的比较，可以发现它们从项目发起开始之后的一段时间都迎来了一个上升期，在上升期有许多开发者参与开源项目的开发，有许多使用者参与开源社区的讨论，其项目的热度都在这一段时间不断上升，然而这2个项目却有了不同的发展结果，Pytorch一直保持活跃并成为了目前主流的深度学习框架；而Upterm并没有成为目前广为使用的控制台集成开发环境，被大量同类型应用替代，最终项目被归档而无人问津。这其中的原因值得分析。

在期中报告与期末报告的第一部分我们归纳总结了这2个开源项目的基本信息，在报告的第三部分我们通过数据分析，对比了这2个开源项目基础数据（新增Star和Fork的个数，每月打开和关闭Issue个数，PR个数）与活跃开发者数量变化趋势，从中推断开源项目发展到活跃/归档的最主要因素，归纳如下：

### 因素1：开源项目本身的应用场景与应用价值

开源项目本身的应用场景与应用价值是否能够吸引开发者与使用者，是开源项目能否持续发展的重要因素。Pytorch之所以能够长久保持活跃，是因为这是一个深度学习框架，相较于主流的tensorflow具有更好的易用性和可编程性，因而具有广泛的应用场景与较高的应用价值，这是该项目能够吸引开发者与使用者共同壮大开源社区的重要成因。

相较于Upterm，虽然该项目实现了一个易用性较强的、跨平台的控制台终端，但是相较于深度学习框架，其应用场景似乎没有那么广泛，一方面操作系统通常自带原生的控制台终端（例如Windows的PowerShell等），其功能也较为完备且无需额外安装；另一方面对于熟练用户而言，Upterm的重要“卖点”——命令提示似乎没有足够强的吸引力。

因此，开源项目本身的应用场景与应用价值是一个重要的因素，正如一篇文章的立意是否深远决定了一篇文章的高度，开源项目想要保持活跃与持续发展，在发起时需要考虑其是否具有较为广泛的应用场景，是否具有良好的应用价值（例如契合当前学术界、工业界的研究需要）。

### 因素2：现实的不可抗力

Upterm项目最终被归档的一个重要原因是项目的拥有者兼主要贡献者Vlad Shatskyi因意外离世，而该项目的大部分代码几乎都是这位编写的，且后续也没有其他开发者接力维护后续项目，进而社区发布的Issue，提交的PR无人处理，最终导致项目的热度逐渐下降最终归档。

实际上除了该项目以外也有类似的项目因显示世界的种种因素，例如政治、疫情等，进而停止项目开发、维护。因此现实世界的不可抗力可能也会影响开源项目及其社区的发展。

除此之外，Upterm项目大部分工作是由一位开发者独立完成的，协作在这个项目中并没有得到很好的体现，因此当这一位开发者发生变故时，会对项目本身产生毁灭性影响。但如果项目由世界各地的开发者共同维护，对项目的发展而言可能更为有利，也更加符合开源世界的精神。

### 因素3：开源社区治理能力

开源社区的治理能力至关重要，具体来说可以包括：开源项目的推广与传播，社区Issue的及时回复与处理，提交PR请求的处理。

Pytorch项目在开源社区治理上有着良好的表现：在项目启动时，逐渐吸引开发者与使用者参与项目，使得项目的Star数量与Fork数量逐步提升，增加项目的影响力；项目开发初期，大量地合入PR请求完善项目，使得框架的功能与成熟度逐渐提到，进而促进吸引更多开发者参与开发；项目日渐成熟时，及时对社区内使用者发出的Issue进行回复与处理，使得社区的热度维持在较高水平，同时为了保证项目的稳定性，不再大量合入PR，保证了项目的整体质量。最终使得Pytorch成为了目前主流的深度学习框架。而Upterm项目在其生命周期内大部分工作由一个开发者独立完成，在社区治理方面做的工作显然不够充足，尽管可能存在其他因素的影响，但不可否认这是该项目最后被归档的一个成因。

因此开源项目要长久维持活跃状态，需要特别考虑开源社区的治理能力，，有意识地加强开源项目的推广与传播，提升社区Issue的及时回复与处理与PR请求的处理等方面的能力。