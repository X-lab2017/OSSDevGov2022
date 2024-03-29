# 期末报告 ([flutter/flutter](https://github.com/flutter/flutter))

**小组成员**:

* 杨珂（学号：51215903064，完成任务三）
* 张凌峰（学号：51215903067，完成任务二）
* 贺惠惠（学号：51215903015，完成任务一）

## 一、项目的基本背景和发展历程介绍

1. 技术类型

本项目是由谷歌公司开源的SDK框架。

本项目使用的语言有：Dart,Objective-C,Java,C++,Shell,CMake

2. 版本发布历史

从github上看，本项目采取了按版本建立不同分支进行开发的开发思路，并没有在github上进行release的整合发布，始终处于快速迭代中。从其仓库的分支历史以及read me中的框架官方网站中可以得知，版本发布历史如下：

| **Flutter version**                                          | **Architecture** | **Ref** | **Release Date** | **Dart version** |
| ------------------------------------------------------------ | ---------------- | ------- | ---------------- | ---------------- |
| [3.0.3](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_3.0.3-stable.zip) | x64              | 676cefa | 2022/6/23        | 2.17.5           |
| [3.0.2](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_3.0.2-stable.zip) | x64              | cd41fdd | 2022/6/11        | 2.17.3           |
| [3.0.1](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_3.0.1-stable.zip) | x64              | fb57da5 | 2022/5/20        | 2.17.1           |
| [3.0.0](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_3.0.0-stable.zip) | x64              | ee4e09c | 2022/5/12        | 2.17.0           |
| [2.10.5](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.10.5-stable.zip) | x64              | 5464c5b | 2022/4/19        | 2.16.2           |
| [2.10.4](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.10.4-stable.zip) | x64              | c860cba | 2022/3/29        | 2.16.2           |
| [2.10.3](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.10.3-stable.zip) | x64              | 7e9793d | 2022/3/3         | 2.16.1           |
| [2.10.2](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.10.2-stable.zip) | x64              | 097d331 | 2022/2/19        | 2.16.1           |
| [2.10.1](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.10.1-stable.zip) | x64              | db747aa | 2022/2/10        | 2.16.1           |
| [2.10.0](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.10.0-stable.zip) | x64              | 5f105a6 | 2022/2/4         | 2.16.0           |
| [2.8.1](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.8.1-stable.zip) | x64              | 77d935a | 2021/12/17       | 2.15.1           |
| [2.8.0](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.8.0-stable.zip) | x64              | cf44000 | 2021/12/9        | 2.15.0           |
| [2.5.3](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.5.3-stable.zip) | x64              | 1811693 | 2021/10/16       | 2.14.4           |
| [2.5.2](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.5.2-stable.zip) | x64              | 3595343 | 2021/10/1        | 2.14.3           |
| [2.5.1](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.5.1-stable.zip) | x64              | ffb2ece | 2021/9/18        | 2.14.2           |
| [2.5.0](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.5.0-stable.zip) | x64              | 4cc385b | 2021/9/8         | 2.14.0           |
| [2.2.3](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.2.3-stable.zip) | x64              | f4abaa0 | 2021/7/2         | 2.13.4           |
| [2.2.2](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.2.2-stable.zip) | x64              | d79295a | 2021/6/12        | 2.13.3           |
| [2.2.1](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.2.1-stable.zip) | x64              | 02c026b | 2021/5/28        | 2.13.1           |
| [2.2.0](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.2.0-stable.zip) | x64              | b227420 | 2021/5/19        | 2.13.0           |
| [2.0.6](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.0.6-stable.zip) | x64              | 1d9032c | 2021/5/1         | 2.12.3           |
| [2.0.5](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.0.5-stable.zip) | x64              | adc6878 | 2021/4/17        | 2.12.3           |
| [2.0.4](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.0.4-stable.zip) | x64              | b139559 | 2021/4/3         | 2.12.2           |
| [2.0.3](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.0.3-stable.zip) | x64              | 4d7946a | 2021/3/20        | 2.12.2           |
| [2.0.2](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.0.2-stable.zip) | x64              | 8962f6d | 2021/3/13        | 2.12.1           |
| [2.0.1](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.0.1-stable.zip) | x64              | c5a4b40 | 2021/3/5         | 2.12.0           |
| [2.0.0](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_2.0.0-stable.zip) | x64              | 60bd88d | 2021/3/4         | 2.12.0           |
| [1.22.6](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.22.6-stable.zip) | x64              | 9b2d32b | 2021/1/26        | -                |
| [1.22.5](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.22.5-stable.zip) | x64              | 7891006 | 2020/12/11       | -                |
| [1.22.4](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.22.4-stable.zip) | x64              | 1aafb3a | 2020/11/14       | 2.10.4           |
| [1.22.3](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.22.3-stable.zip) | x64              | 8874f21 | 2020/10/31       | 2.10.3           |
| [1.22.2](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.22.2-stable.zip) | x64              | 84f3d28 | 2020/10/17       | 2.10.2           |
| [1.22.1](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.22.1-stable.zip) | x64              | f30b7f4 | 2020/10/9        | 2.10.1           |
| [1.22.0](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.22.0-stable.zip) | x64              | d408d30 | 2020/10/1        | 2.10.0           |
| [1.20.4](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.20.4-stable.zip) | x64              | fba99f6 | 2020/9/16        | 2.9.2            |
| [1.20.3](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.20.3-stable.zip) | x64              | 216dee6 | 2020/9/3         | 2.9.2            |
| [1.20.2](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.20.2-stable.zip) | x64              | bbfbf17 | 2020/8/14        | 2.9.1            |
| [1.20.1](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.20.1-stable.zip) | x64              | 2ae3451 | 2020/8/7         | 2.9.0            |
| [1.20.0](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.20.0-stable.zip) | x64              | 840c920 | 2020/8/5         | 2.9.0            |
| [1.17.5](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.17.5-stable.zip) | x64              | 8af6b2f | 2020/7/2         | -                |
| [1.17.4](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.17.4-stable.zip) | x64              | 1ad9baa | 2020/6/19        | -                |
| [1.17.3](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.17.3-stable.zip) | x64              | b041144 | 2020/6/6         | -                |
| [1.17.2](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.17.2-stable.zip) | x64              | 5f21edf | 2020/5/29        | -                |
| [1.17.1](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.17.1-stable.zip) | x64              | f7a6a79 | 2020/5/14        | -                |
| [1.17.0](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_1.17.0-stable.zip) | x64              | e6b34c2 | 2020/5/6         | -                |
| [v1.12.13+hotfix.9](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.12.13+hotfix.9-stable.zip) | x64              | f139b11 | 2020/4/18        | -                |
| [v1.12.13+hotfix.8](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.12.13+hotfix.8-stable.zip) | x64              | 0b8abb4 | 2020/2/12        | -                |
| [v1.12.13+hotfix.7](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.12.13+hotfix.7-stable.zip) | x64              | 9f5ff23 | 2020/1/27        | -                |
| [v1.12.13+hotfix.5](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.12.13+hotfix.5-stable.zip) | x64              | 27321eb | 2019/12/11       | -                |
| [v1.9.1+hotfix.6](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.9.1+hotfix.6-stable.zip) | x64              | 68587a0 | 2019/10/24       | -                |
| [v1.9.1+hotfix.5](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.9.1+hotfix.5-stable.zip) | x64              | 1aedbb1 | 2019/10/18       | -                |
| [v1.9.1+hotfix.4](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.9.1+hotfix.4-stable.zip) | x64              | cc949a8 | 2019/10/2        | -                |
| [v1.9.1+hotfix.2](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.9.1+hotfix.2-stable.zip) | x64              | 2d2a1ff | 2019/9/10        | -                |
| [v1.7.8+hotfix.4](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.7.8+hotfix.4-stable.zip) | x64              | 20e5931 | 2019/7/25        | -                |
| [v1.7.8+hotfix.3](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.7.8+hotfix.3-stable.zip) | x64              | b712a17 | 2019/7/10        | -                |
| [v1.7.8+hotfix.2](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.7.8+hotfix.2-stable.zip) | x64              | 2e54093 | 2019/7/9         | -                |
| [v1.5.4-hotfix.2](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.5.4-hotfix.2-stable.zip) | x64              | 7a4c334 | 2019/5/8         | -                |
| [v1.2.1](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.2.1-stable.zip) | x64              | 8661d8a | 2019/2/27        | -                |
| [v1.0.0](https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_v1.0.0-stable.zip) | x64              | 5391447 | 2018/12/5        | -                |

3.主要贡献者构成

| 贡献者         | 区域              | 组织   |
| -------------- | ----------------- | ------ |
| Jonah Williams | Mountain View, CA | Google |
| Adam Barth     | San Francisco, CA |        |
| Ian Hickson    |                   | Google |

4. CI/CD的使用

1）使用Cirrus CI进行自动构建

2）通过Scorecards平台进行安全分析：checkout code，执行分析，上传符号表，代码扫描。以上步骤执行完毕将已checkout的代码进行上传。

3）进行镜像保存。

同时我们在活跃贡献者以及commit列表中得知，存在着若干的账户运行脚本，他们也是整个CI/CD过程中不可或缺的部分。[engine-flutter-autoroll](https://github.com/flutter/flutter/commits?author=engine-flutter-autoroll)的主要功能是逐条提交更新引擎的插件版本号；Dependabot的功能是维护CI/CD脚本；Fluttergithubbot的主要功能是自动标记重要功能的修复。以上所有内容以及脚本账号构成项目自动化流程。

## 二、项目历史轨迹分析

详见flutter.ipynb。

## 三、结合期中分析的归档项目，对比分析活跃/归档项目

其中分析的归档项目为` RXJS`。

+ 项目基础数据（2.1/2.2/2.3）变化趋势

![幻灯片1](img/幻灯片1.png)

通过对比图可知：

（1）归档项目` RxJs` 与项目` flutter`相比，在这基础数据这三个维度，前者比后者都要差上1-2 个量级。

（2）虽然两者基础数据变化趋势都是先升高至峰值然后再降低，但是`RxJs`峰值之后不断降低直至趋于零，` flutter`的数据则下降到一定程度呈平稳态势。

+ 开发者数量（2.4）变化趋势

![幻灯片2](img/幻灯片2.png)

通过对比图可知：

`RxJs`的活跃开发者总数相较` flutter`要小一个量级。与基础数据类似，项目`RxJs`的开发者总数至峰值之后不断降低直至趋于零，` flutter`的开发者至峰值后，略有下降，之后呈平稳态势。

+ 其他感兴趣的对比方向

比较两个项目PR 从打开到合入的平均时长，项目` RxJs`的值为11.6天，项目`flutter`的值为3.4天，可见` flutter`的维护者处理PR更加及时，可以得出后者比前者社区活跃度更高这一结论。

+ 给出你认为的项目发展到活跃/归档的主要影响因素及原因

社区活跃度是影响开源项目发展的重要指标。一个健康的项目应当具有相当的社区活跃度，这体现在项目的提交数、 拉取请求数和贡献者数（其它数据，如代码行数、文件数、issue 数、 fork 数、star 数）等，当一个项目社区活跃度趋于0，则代表该项目趋于归档。

