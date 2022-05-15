# 开源课程期中作业

##基本信息
### 小组成员：刘鑫52215903010  刘文辉52215903014 伍志坚5221593015
### 组内分工：
项目的基本背景和发展历程介绍：刘文辉

项目的历史轨迹分析：刘鑫

洞察项目被归档的可能原因：伍志坚



###项目信息：序号26	项目ID38066334	项目名facebookarchive/caffe2



##一、项目的基本背景和发展历程介绍
* 技术类型

Caffe的全称是Convolutional Architecture for Fast Feature Embedding（译为：快速特征嵌入的卷积体系结构），其作者是贾扬清。caffe是一个清晰而高效的深度学习框架，是纯粹的C++/CUDA架构，核心语言是C++，支持命令行、python和matlab接口；可以在CPU和GPU之间无缝切换。affe的基本工作流程是设计建立在神经网络的一个简单假设，所有的计算都是层的形式表示的，网络层所做的事情就是输入数据，然后输出计算结果。

* 版本发布历史

    - **官方版本：伯克利BVLC(Berkeley Vision And Learning Center) 版**这个是Caffe的主版本，由伯克利大学维护。其他所有的Caffe版本都是由这个版本分支出去的。这个版本Caffe可以编译出Linux和Windows*版本，支持Nvidia的CUDA加速，但是对CPU的优化不好，而且有关安装和配置的文档很少。从这个版本编译Caffe，需要很强的自我学习和解决问题能力。
    - **微软的Windows版本**微软自己维护的一个版本。这个版本简化了Caffe在Windows*下的步骤，自带了一个VS的Solution项目。这个版本同样支持基于CPU和CUDA的算法实现。
    - **Intel Caffe优化版**Intel维护的另一个版本，相对于官网BVLC Caffe上的OpenCL分支，优化了基于Intel 核显GPU的OpenCL加速算法。这个版本同时支持Windows* 和Linux平台，适合在有Intel核显的CPU上做一些推理(Inference)场景的工作。
    - **Intel clCaffe 核显OpenCL优化版**Intel维护的另一个版本，相对于官网BVLC Caffe上的OpenCL分支，优化了基于Intel 核显GPU的OpenCL加速算法。这个版本同时支持Windows* 和Linux平台，适合在有Intel核显的CPU上做一些推理(Inference)场景的工作。
    


* 主要贡献者的构成（国家、区域和组织等）

根据官网显示该项目的贡献者达到258位。其中，主要贡献者有7位。注意：这里我们定义主要贡献者为commit数量不低于50的贡献者。下表列出了贡献者的详细信息。

|贡献者|Commits|Additions|Deletions|国家或区域或组织|
|-|-------:|:------:|:------:|:------:|
|Evan Shelhamer |597|1499163|2927347|英国|
|Jeff Donahue   |558|64344  |40142  |UCB|
|Yangqing Jia   |354|4365583|2892659|中国|
|longjon        |257|13887  |23259  |UCB|
|Sergio Guadarrama |154|15994  |2664   |美国|
|kloudkl        |144|6983   |4306   |未知|
|Sergey Karayev |98 |17713  |10148  |UCB|

在这些主要的贡献者中，尽管Yangqing Jia的提交数量并不是最多的，但他是该项目的创建者。从中可以看出，这些主要贡献者们都是来自于加州大学伯克利分校。

* CI/CD的使用

 CI/CD的核心概念是持续集成和持续部署。GitHub已在其流行的代码共享站点中引入了一种名为GitHub Actions的工作流工具，以允许直接从GitHub本身进行持续集成/连续部署（CI / CD） 。使用此工具（目前处于测试版） ，开发人员可以在GitHub或外部系统上构建，部署和更新软件项目，而无需自己运行代码。

 在Caffe项目中，使用Travis CI进行持续集成。Travis CI是在线托管的CI服务，通常使用GitHub托管的开源项目会使用Travis CI持续集成。Travis CI会绑定GitHub上的项目，只要有新的代码就会自动抓取，提供一个运行环境，执行测试、构建和部署。我们可以在项目仓库中找到.travis.yml文件是持续集成的配置文件，该文件定义了Travis CI的持续集成和持续交付行为，一旦项目有了新的提交，Travis CI就会根据该文件执行里面的命令。具体文件内容如下：

    dist: trusty
    sudo: required
    
    language: cpp
    compiler: gcc
    
    env:
        global:
        - NUM_THREADS=4
    matrix:
        - BUILD_NAME="default-make"
        - BUILD_NAME="no-io-make" WITH_IO=false
        - BUILD_NAME="cuda-make" WITH_CUDA=true
        - BUILD_NAME="cudnn-make" WITH_CUDA=true WITH_CUDNN=true
    
        - BUILD_NAME="default-cmake" WITH_CMAKE=true
        - BUILD_NAME="python3-cmake" WITH_CMAKE=true WITH_PYTHON3=true
        - BUILD_NAME="no-io-cmake" WITH_CMAKE=true WITH_IO=false
        - BUILD_NAME="cuda-cmake" WITH_CMAKE=true WITH_CUDA=true
        - BUILD_NAME="cudnn-cmake" WITH_CMAKE=true WITH_CUDA=true WITH_CUDNN=true
    
    cache:
    apt: true
    directories:
        - ~/protobuf3
    
    before_install:
    - source ./scripts/travis/defaults.sh
    
    install:
    - sudo -E ./scripts/travis/install-deps.sh
    - ./scripts/travis/setup-venv.sh ~/venv
    - source ~/venv/bin/activate
    - ./scripts/travis/install-python-deps.sh
    
    before_script:
    - ./scripts/travis/configure.sh
    
    script:
    - ./scripts/travis/build.sh
    - ./scripts/travis/test.sh
    
    notifications:
    email:
        on_success: always
        on_failure: always
根据该配置文件，可以获得安装依赖前的行为，定义在configure.sh文件中。另外，在script中可以获得构建和测试的脚本。

* 其他有价值的信息

本项目的创建者贾扬清，也是tensorflow、pytorch项目的创建者。这些主要贡献者中有些也参与了tensorflow或pytorch项目的开发。



##二、项目归档的可能原因
**由于Caffe2被合并入PyTorch，因此项目最终被归档。** Caffe2开发的主要重点是性能和跨平台部署，而PyTorch专注于快速原型设计和研究的灵活性。Facebook认为，为了用户的体验，有必要将两者结合到一个包内。因此，Caffe2现在作为PyTorch的一部分存在。

##项目归档后可能产生的影响
###对于用户而言
1.Caffe2仍然提供本地库和python扩展作为独立的安装选项

2.Caffe2仍然支持跨平台的编译

3.Caffe2的各种加速后端和库集成以及可拓展的图形executor基本上保持不变


**用户仍然可以使用Caffe2提供的API，此外，安装PyTorch同样可以使用Caffe2的相关功能**
###对于开发者而言
1.由于Caffe2和PyTorch有大量共享的代码和库，合并之后，能减少同时维护两个深度学习框架的成本。

2.PyTorch有优秀的前端，Caffe2有优秀的后端，合并以后可以进一步提升开发者的效率

##对开源项目如何可持续发展的理解
可持续发展被定义为"既满足当代人的需求，又不对后代人满足其自身需求的能力构成危害的发展"。我们认为，对于开源项目而言，可持续发展要求项目能负担起财务压力，同时能够持续发布代码并对产品做出改进。

很多开源项目在早期能够快速更新迭代，文档编写也很及时，然而后期缺乏经济收入，项目很容易停摆甚至中断。开源项目让很多巨头企业从中受益，但项目贡献者却无法得到有效回馈。这使得开发者缺乏持续更新迭代的动力。我们认为大型企业作为既得利益者，应该将部分经济收益回馈给贡献者，这有益于开源项目的可持续发展，同时有利于开源社区的良性循环。

开源项目的创始团队在项目创建时没有考虑可持续发展的问题，对于资金和人力没有制定合理的规划。因此项目到后期很难实现可持续性。开源项目的创始团队应该在项目初期制定长期规划，对于可以调动的资源合理评估，同时要考虑在出现资金断流、人员流失之后应该采取的相应措施。

