# 开源软件开发与社区治理期末作业

## 基本信息

**小组成员：**

镜像仓库搭建与数据源配置：郑泽洪（ 51215903109）；

仓库数据分析：杜方芮（51215903075），谭可人（51215903054），郑泽洪（ 51215903109）；

文档撰写：谭可人（51215903054），杜方芮（51215903075），郑泽洪（ 51215903109）。

**项目序号：**175

**项目id：**22442668

**项目名称：**openshift/origin

## 一、项目的基本背景和发展历程介绍

### 1. 技术类型

**OpenShift **是红帽 Red Hat 公司基于开源的云平台，是平台即服务（PaaS），它是一种容器应用平台。允许开发人员构建、测试和部署云应用。该系统是在 K8S 核心之上添加工具，从而实现更快的应用开发、部署及扩展。
在 OpenShift 上可以进行**开发、测试、部署、运维全流程**，实现高度的自动化，满足企业中的应用持续集成和交付及部署的需求，同时也满足企业对于容器管理（Docker）、容器编排（K8S）的需求。Openshift 是首个支持企业级 Java 的 PaaS 平台，支持 JEE6 与 JBoss 和其 Eclipse 集成开发环境以及 Maven 和 Jenkins 自动化。

### 2. 版本发布历史

1. v4.1.0 - 2019.05.02    &emsp;  &emsp;    &emsp; &emsp;      8. v3.6.0 - 2017.07.31
2. v3.11.0 - 2018.10.11   &emsp;    &emsp;     &emsp; &emsp;  9. v1.5.0 - 2017.04.21
3. v4.0.0 - 2018.09.13   &emsp;       &emsp; &emsp; &emsp;   10. v1.4.0 - 2017.01.19
4. v3.10.0 - 2018.08.03   &emsp;    &emsp;   &emsp; &emsp;  11. v1.3.0 - 2016.09.16
5. v3.9.0 - 2018.03.31   &emsp;     &emsp; &emsp; &emsp;     12. v1.2.0 - 2016.05.25
6. v3.8.0 - 2018.03.14   &emsp;   &emsp;    &emsp; &emsp;    13. v1.1.0 - 2015.12.03
7. v3.7.0 - 2017.11.30   &emsp;   &emsp; &emsp; &emsp;       14. v1.0.0 - 2015.06.19

* 注：仅包含部分重要版本发布历史。

### 3. 主要贡献者的构成

| 国家 | 贡献者姓名                                                   | 人数 |
| :--- | :----------------------------------------------------------- | :--: |
| 美国 | David Eads, Raleigh, NC，Jordan Liggitt，Ben Parees，Dan Winship，Michalis Kargakis，Steve Kuznetsov，Juan Vallejo，Sam Padgett，Cesar Wong，Mo Khan，Fabiano Franz，Jessica Forrester，Dan Mace，Jan Šafránek，Dan Williams，Seth Jennings，Derek Carr，Paul Morie |  19  |
| 波兰 | Maciej Szulik，Lukasz Szaszkiewicz                           |  2   |
| 捷克 | Michal Fojtik                                                |  1   |
| 德国 | Stefan Schimanski                                            |  1   |
| 巴西 | Fabiano Franz                                                |  1   |
| 英国 | Paul Weil                                                    |  1   |
| 总计 |                                                              |  25  |

* 在25个主要贡献者中，绝大多数（76%）的贡献者来自**美国**，其余贡献者来自波兰、捷克、德国、巴西、英国。

| 公司         | 贡献者姓名                                                   | 人数 |
| ------------ | ------------------------------------------------------------ | ---- |
| Red Hat, Inc | David Eads, Raleigh, NC，Ben Parees，Dan Winship，Michalis Kargakis，Steve Kuznetsov，Juan Vallejo，Sam Padgett，Cesar Wong，Fabiano Franz，Jessica Forrester，Dan Mace，Jan Šafránek，Dan Williams，Seth Jennings，Derek Carr，Maciej Szulik，Lukasz Szaszkiewicz，Michal Fojtik，Stefan Schimanski，Fabiano Franz，Paul Weil | 22   |
| Google       | Jordan Liggitt                                               | 1    |
| VMware       | Mo Khan                                                      | 1    |
| Apple        | Paul Morie                                                   | 1    |
| 总计         |                                                              | 25   |

* 在25个主要贡献者中，绝大多数（88%）的贡献者来自**红帽 Red Hat 公司**，其余也有来自Google、VMware、Apple的贡献者。

### 4. CI/CD的使用

未使用CI/CD。

### 5. 其他有价值的信息

* 该仓库的总Fork数量为4.7k，总Star数量为8.1k；共有49个branches，72个tags；共有Issues8935个，其中8806个已经被关闭；共有Pull Requests18322个，其中18236个已经被合入。

* 在仓库主页中提供了**openshift的官方网站**：<www.openshift.org>。网站中详细介绍了openshift的介绍、使用指南、帮助文档、博客、使用者社区、开发者社区等相关信息。
