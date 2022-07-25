# 项目基本背景和发展历程

## 1.项目基本背景与版本发布历史

CDAP 是适用于 Hadoop 生态系统的集成式开源应用程序开发平台，为开发人员提供数据和应用程序抽象，以简化和加速应用程序开发，解决更广泛的实时和批处理用例，并将应用程序部署到生产中，同时满足企业需求。

CDAP发布了开发者API，用于创建应用程序和访问核心 CDAP 服务。CDAP 定义并实现了多样化的服务集合，这些服务将应用程序和数据放在现有的Hadoop基础架构上，例如HBase,HDFS,YARN,MapReduce,Hive和Spark。

CDAP现在是Google Cloud的一部分，项目主要使用Java语言。从2014年至今发布了76个版本。项目有644个Star数和307Fork数，50k+的Commits数量。CDAP仓库并没有Issue，而是提供了user和dev两个邮件列表便于使用者与开发者进行反馈与讨论。

## 2.主要贡献者构成

Github上该仓库共记录有151名贡献者，选取Commits数量在1000以上的贡献者作为主要贡献者进行介绍，总共7名。

### 1.Ajai（@ ajainarayanan）

Ajai在CDAP仓库上共有2790个Commits，时间跨度为2014年至2021年，且这段时间内Ajai的主要贡献均在CDAP相关仓库上，2021下半年开始不在Github上活跃。Ajai现今从事于Google公司，居于Santa Clara, CA。

### 2.Terence Yim（@chtyim）

Terence Yim在CDAP上从2013年开始至今持续进行贡献，共有2591个Commits。现今从事于Google公司，并未表明居住地区，常用语言为Java。

### 3.Edwin Elia（@elfenheart）

Edwin Eila从2015年起至2022年初在CDAP上持续贡献，2015指2017年贡献次数较多，共有2135次Commits。现从事于Netfilx公司，居于San Francisco Bay Area, California。

### 4.Andreas Neumann（@anew）

Andreas Neumann在CDAP上的主要贡献时间为2012下半年至2019年初，活跃期间在2012年至2015年间，共有1741个Commits。现从事于Databricks公司，居于San Francisco, CA。

### 5.albertshau

albertshau在CDAP上从2013年开始至今一直持续贡献，共有1209个Commits。其余信息并未表明。

### 6.Joltie Root（@nitinmotgi）

Joltie Root在CDAP上的主要活跃时间为2012下半年至2013上半年，之后虽有贡献但时间较为分散，一共有1046个Commits。居于Palo Alto，并未表明组织。

### 7.poornachandra

poornachandra在CDAP上的主要活跃时间为2013年至2017上半年，之后偶尔有少量贡献，一共有1026个Commits。并未表明所属组织与所在地。

## 3.CI/CD的使用

以下图为例，根据PR内容的不同，使用了不同的测试流程

![image-20220629221443388](..\pic\9.png)

![所有贡献者都受 Google 的 CLA 保护](..\pic\10.png)

其中单元测试和确认所有贡献者都受 Google 的 CLA 保护是必须的。

## 4.其余信息

CDAP最初由Cask公司开发，后被Google收购。虽然相较于其他top项目，CDAP的Star数和Fork数量较少，但PR数量多达1w。由于CDAP是公司组织开发，各项设施包括文档，贡献手册之类的都比较完备。