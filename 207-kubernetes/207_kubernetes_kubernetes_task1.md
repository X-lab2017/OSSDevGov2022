

## 二、项目的历史轨迹分析

基于给出的数据，完成项目 **2015年/创建 - 2021** 期间的以下数据分析任务：

*PS：给出的数据包含2022年的日志，但数据分析的时间节点只到2021年年底，2022年的不纳入统计范围*

1. 每月新增 Star 和 Fork 的个数

 ![image-20220629220053409](https://raw.githubusercontent.com/dcxr969/picgooo/master/img/202206292201998.png)

2. 每月打开 Issue 和 关闭 Issue 的个数

![image-20220629220110475](https://raw.githubusercontent.com/dcxr969/picgooo/master/img/202206292201955.png)

3. 每月打开 PR 和**合入** PR 的个数（注意，关闭 PR 不等于合入）

![image-20220629220132933](https://raw.githubusercontent.com/dcxr969/picgooo/master/img/202206292201789.png)

4. 每月在仓库中活跃（只要有日志产生就算）的不同开发者（也就是一个GitHub账号）总数

![image-20220629220152680](https://raw.githubusercontent.com/dcxr969/picgooo/master/img/202206292201402.png)

5. Issue 从打开到关闭的平均时长和中位数（单位：天)

![image-20220629220229470](https://raw.githubusercontent.com/dcxr969/picgooo/master/img/202206292202355.png)

6. PR 从打开到合入的平均时长和中位数（单位：天）

![image-20220629220248835](https://raw.githubusercontent.com/dcxr969/picgooo/master/img/202206292202980.png)

7. Issue和PR从打开到第一次有人回复（非本人回复）的平均时长和中位数（单位：天）

![image-20220629220312738](https://raw.githubusercontent.com/dcxr969/picgooo/master/img/202206292203737.png)





## 三、结合期中分析的归档项目，对比分析活跃/归档项目

期中分析的归档项目为Marp，是一个简单的Markdown演示文稿编写器。

- 项目基础数据（2.1/2.2/2.3）的变化趋势

**Marp每月新增 Star 和 Fork 的个数**

  

  ![image-20220515144149013](https://raw.githubusercontent.com/dcxr969/OSSDev2022/main/img/202205151442207.png)

**kubernetes每月新增 Star 和 Fork 的个数**

  ![image-20220629190733778](https://raw.githubusercontent.com/dcxr969/picgooo/master/img/202206291907657.png)

**Marp**：star和fork数呈现出一致性，在2016年5月创始之初到2016年7月之间呈现出一个激增的趋势，并在2016年7月达到顶峰。在此之后star个数在100左右，fork数在10左右，大体呈现出缓慢下降的趋势，仅在2016年11月和2019年2月出现了小的峰值波动。从中可以看出该项目的受关注程度在不断下降。

**kubernetes**：star数波动较为明显，fork数基本保持稳定，在2015年1月到2019年3月之间，star数呈现波动上涨，由500上涨到1500左右。在2019年3月之后，呈现出波动下降的趋势，并在2021年9月出现明细下跌。但整体来看，star数基本保持的500以上。该波动基本符合Kubernetes每3个月发布一次新版本的更新记录，每次版本的更新都会带来star个数的增加。



**Marp每月打开 Issue 和 关闭 Issue 的个数**

![image-20220515144657977](https://raw.githubusercontent.com/dcxr969/OSSDev2022/main/img/202205151449638.png)

**kubernetes每月打开 Issue 和 关闭 Issue 的个数**

![image-20220629190814889](https://raw.githubusercontent.com/dcxr969/picgooo/master/img/202206291908371.png)

**Marp**：2016年7月打开Issue和关闭Issue出现了一个峰值，2018年10月关闭Issue出现了一个峰值，其他时间的打开和关闭Issue个数基本在20以下，2019年9月项目归档后，大量Issue被关闭。可以看出其实长期以来该项目的Issue数量均不是很多。

**kubernetes**：该项目的Issue打开和关闭数量变化分为两个较为明显的阶段。在2015年1月到2018年5月之间，该项目讨论的热度很高，几乎每月都有超过500个Issue被提出，关闭的Issue数量基本随着打开的Issue数量变化，说明绝大多数Issue都得到了解决。2018年2月，大量Issue被关闭。2018年5月之后，打开和关闭的Issue个数基本在400左右波动，关闭的Issue数量基本大于打开的Issue数量。考虑到这个明显的时间节点分水岭，可能是因为项目的稳定性和成熟性上已经达到了一定的高度。



**Marp每月打开PR和合入PR的个数**

![image-20220515144754761](https://raw.githubusercontent.com/dcxr969/OSSDev2022/main/img/202205152124715.png)

**kubernetes每月打开PR和合入PR的个数**

![image-20220629190842824](https://raw.githubusercontent.com/dcxr969/picgooo/master/img/202206291908117.png)

**Marp**：该项目于2016年7月打开PR的最高个数为15，2016年7月和2016年10月合入PR的个数最高，为8左右，2016年 11月之后打开和合入PR的每个月个数基本不超过5个，且经常出现为零的情况，可以看出该项目的开源参与热度不是很高，热度的持续时间也比较短。

**kubernetes**：在2015年1月到2019年10月之间，该项目每个月打开和合入PR的个数基本在500-1000之间波动。2019年10月之后，项目的打开和合入PR个数出现下降趋势，并在2021年10月出现一个小的低谷，这一小的低谷与前面star、fork、issue的变化数量时间上具有一致性。总体可以看出，开源贡献者对该项目的关注度较高。



- 开发者数量（2.4）变化趋势

**Marp每月在仓库中活跃的不同开发者总数**

![image-20220515144946920](https://raw.githubusercontent.com/dcxr969/OSSDev2022/main/img/202205151449244.png)

**kubernetes每月在仓库中活跃的不同开发者总数**

![image-20220629190952759](C:\Users\ymyymyymy\AppData\Roaming\Typora\typora-user-images\image-20220629190952759.png)

**Marp**：该项目的活跃开发者人数呈现出明显的激增和骤降，与2016年7月达到一个峰值，约为3000人左右，之后一直稳定在100人左右，并在2019年3月之后出现持续减少直至归档。

**kubernetes**：该项目的活跃开发者人数一直呈现出上涨的趋势，最高于2019年4月达到3364人，之后稳定在2000人左右，于2021年10月出现一个低点，活跃开发者降至1021人，出现了开发者的流失。



- 其他你感兴趣的对比方向

  **Issue从打开到关闭的平均时长**

  Marp中Issue从打开到关闭的平均时长为557天，kubernetes为160天，可以看出在这一方面，kubernetes对于Issue的解决速度有明显的优势，既是项目人力资源的体现，也是吸引更多开发者的重要因素。

  **PR从打开到合入的平均时长**

  Marp中PR从打开到合入的平均时长为17天，kubernetes为13天，两者在这一方面基本相同，但考虑到Marp项目PR数量较少，而kubernetes的PR数量较多，从而体现出kubernetes项目开发者对PR处理的高效性。

  **Issue和PR从打开到第一次有人回复的平均时长**

  Marp中Issue和PR从打开到第一次有人回复的平均时长为83天，kubernetes为8天，可以看出kubernetes的平均回复时长远短于Marp，从侧面体现出了kubernetes对于Issue和PR的关注度高，从而促进了项目的更新迭代。

  

我认为项目发展到活跃/归档的主要影响因素有以下几点：

1. 市场需要

在实际的生产型应用中会涉及到多个容器跨越多个服务器主机进行部署的情况，其中涉及到容器的部署、拓展和安全性等问题。kubernetes针对这一问题提出了有效的解决方案，实现了构建跨多个容器的应用服务、跨集群调度、扩展这些容器，并长期持续管理这些容器的健康状况。因此，kubernetes抓住了市场需要的风口，极大满足了企业的需要。

2. 项目本身的完整度

Kubernetes 的前身是Google内部的Borg项目，Google 作为最早研发 Linux 容器技术的企业之一，使得Kubernetes项目本身就具有极高的系统性和完整度。Kubernetes 极大推动了云原生领域的发展，被称为影响云计算未来 10 年的技术。

3. 经济资源

Kubernetes项目有大厂背书，诞生在一个云服务供应商的内部，所以一开始就知道它将来会有怎样的发展潜力，应该向什么方向发展，它本身就具有充足的经济资源支撑它的发展。一线大厂与 Kubernetes 可以说是利益共同体，Kubernetes 的成功可以让企业快速推出产品变现，商业成功后反哺社区，进一步繁荣社区。

4. 人力资源

Kubernetes创始于Google，在该项目开源后，RedHat、华为、IBM、微软、VMware等企业迅速加入社区贡献者行列，为Kubernetes提供了丰富的人力资源，众多优秀工程师的加入也促进了Kubernetes的飞速发展。据Kubernetes创始人介绍，在 Kubernetes 项目早期，社区有很多来自不同方向的、伟大的创新想法。他们专注于构建可扩展性的机会，这意味着人们可以构建和扩展 Kubernetes，无需与 Kubernetes 项目本身进行协调。这在很大程度上推动了更广泛生态系统的发展。

6. 项目的设计理念

Kubernetes在设计之初就避免了和Docker Swarm、Apache Mesos等产品的同质化，作为一个以API为中心、面向应用的容器调度平台，它让用户参与到了容器管理的各个阶段，同时也吸引了大量的社区贡献者。Marp项目本身确实具有轻便性、易上手等特性，但在市场的同类型产品较多，不能体现其优越性和创新性。

5. 丰富的社区活动

Kubernetes社区每年都会组织 2~3 场全球性的技术峰会 KubeCon，从历年会议情况来看，会议议题数和参数人数均成爆发式增长态势。除了 KubeCon 这种全球性的峰会外，还有很多自发的 Meetup 活动，比如 Cloud Native Days China、Cloud Native Days India 等。跟据 CNCF 官方统计数据，2017 年各类 Meetup 参会人数为 53925 人，而 2018 年参数人数增长了 60%达到 89112 人。除了线下聚会，还有线上的活动来传播 Kubernetes 相关知识，比如"Cloud Native Lives"。