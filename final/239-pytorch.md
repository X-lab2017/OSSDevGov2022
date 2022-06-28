

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