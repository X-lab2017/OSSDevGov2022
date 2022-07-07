#                              开源课程期末作业

**小组成员：**

**卢皙钰51215903011，负责第二部分**

**李雪51215903030，负责第二部分**

**阎松 51215903029，负责一、三部分**

# 一、项目的基本背景和发展历程介绍

通过项目仓库的查阅，以及搜索引擎上项目的相关资料，给出项目一些基本的介绍：

## 技术类型：



![image-20220628151740964](assets\image-20220628151740964.png)



.NET 编译器平台（“Roslyn”）为开源 C# 和 Visual Basic 编译器提供了丰富的代码分析 API。Roslyn 是 C# 和 Visual Basic 编译器的开源实现，具有用于构建代码分析工具的 API 接口。

编译器按照结构化规则处理您编写的代码，这些规则通常与人类阅读和理解代码的方式不同。对编译器使用的模型有基本的了解，对于理解构建基于 Roslyn 的工具时使用的 API 至关重要。

.NET 编译器平台 SDK 通过提供反映传统编译器管道的 API 层，向消费者公开 C# 和 Visual Basic 编译器的代码分析。

![image-20220628154437070](assets\image-20220628154437070.png)

该管道的每个阶段都是一个单独的组件。首先，解析阶段将源文本标记化并解析为遵循语言语法的语法。其次，声明阶段分析源和导入的元数据以形成命名符号。接下来，绑定阶段将代码中的标识符与符号进行匹配。最后，发射阶段发出一个程序集，其中包含编译器构建的所有信息。

![image-20220628154509638](assets\image-20220628154509638.png)

与这些阶段中的每一个相对应，.NET 编译器平台 SDK 公开了一个对象模型，允许访问该阶段的信息。解析阶段暴露了语法树，声明阶段暴露了分层符号表，绑定阶段暴露了编译器语义分析的结果，发出阶段是产生IL字节码的API。

![image-20220628154541442](assets\image-20220628154541442.png)

每个编译器将这些组件组合在一起作为一个端到端的整体。

这些 API 与 Visual Studio 使用的相同。例如，代码大纲和格式化功能使用语法树，**对象浏览器**和导航功能使用符号表，重构和**转到定义**使用语义模型，**编辑和继续**使用所有这些，包括 Emit API。

### API 层

.NET 编译器 SDK 由多个 API 层组成：编译器 API、诊断 API、脚本 API 和工作区 API。

#### 编译器 API

编译器层包含与在编译器管道的每个阶段（句法和语义）公开的信息相对应的对象模型。编译器层还包含编译器单次调用的不可变快照，包括程序集引用、编译器选项和源代码文件。有两种不同的 API 分别代表 C# 语言和 Visual Basic 语言。这两个 API 的形状相似，但针对每种单独的语言进行了高保真度的定制。该层不依赖于 Visual Studio 组件。

#### 诊断 API

作为其分析的一部分，编译器可能会生成一组诊断，涵盖从语法、语义和明确的赋值错误到各种警告和信息诊断的所有内容。Compiler API 层通过可扩展的 API 公开诊断，允许将用户定义的分析器插入编译过程。它允许与编译器定义的诊断一起生成用户定义的诊断，例如由 StyleCop 等工具生成的诊断。以这种方式生成诊断具有与 MSBuild 和 Visual Studio 等工具自然集成的优势，这些工具依赖于诊断来获得体验，例如根据策略停止构建并在编辑器中显示实时曲线和建议代码修复。

#### 脚本 API

托管和脚本 API 是编译器层的一部分。您可以使用它们来执行代码片段并累积运行时执行上下文。C# 交互式 REPL（读取-评估-打印循环）使用这些 API。REPL 使您能够将 C# 用作脚本语言，在编写代码时以交互方式执行代码。

#### 工作区 API

Workspaces 层包含 Workspace API，它是对整个解决方案进行代码分析和重构的起点。它帮助您将解决方案中有关项目的所有信息组织到单个对象模型中，让您可以直接访问编译器层对象模型，而无需解析文件、配置选项或管理项目到项目的依赖关系。

此外，Workspaces 层还展示了一组 API，这些 API 在实现代码分析和重构工具时使用，这些工具在 Visual Studio IDE 等宿主环境中运行。示例包括查找所有引用、格式化和代码生成 API。

该层不依赖于 Visual Studio 组件。

下图是他们的开发博客。

![image-20220628155133301](assets\image-20220628155133301.png)





## 版本发布历史：

The Roslyn .NET compiler在其github网站上面共发布58次releases，但目前是更新到了.NET 7.0版本，大的版本更新有7次。

![image-20220628154948363](assets\image-20220628154948363.png)

- 最新的一次更新是2022年6月14日：.NET 7.0.0 Preview 5 和 .NET SDK 7.0.100-preview.5.22307.18 版本可供下载。最新的 7.0 版本始终列在.NET 7.0 Releases中。

  .NET 7将是当前版本，支持 18 个月，从 2022 年 11 月到 2024 年 5 月 14 日。Microsoft在多个操作系统上支持它。

  .NET 7 Preview 5 现已推出，其中包括对 ASP.NET Core 的许多重大新改进。

  以下是此预览版中新增功能的摘要：

  1.JWT 身份验证改进和自动身份验证配置；

  2.Minimal API 对参数列表简化的参数绑定支持。

  ### .NET 7 Releases

  | Date       | Release                                                      |
  | ---------- | ------------------------------------------------------------ |
  | 2022/06/14 | [7.0.0 Preview 5](https://github.com/dotnet/core/blob/main/release-notes/7.0/preview/7.0.0-preview.5.md) |
  | 2022/05/10 | [7.0.0 Preview 4](https://github.com/dotnet/core/blob/main/release-notes/7.0/preview/7.0.0-preview.4.md) |
  | 2022/04/13 | [7.0.0 Preview 3](https://github.com/dotnet/core/blob/main/release-notes/7.0/preview/7.0.0-preview.3.md) |
  | 2022/03/15 | [7.0.0 Preview 2](https://github.com/dotnet/core/blob/main/release-notes/7.0/preview/7.0.0-preview.2.md) |
  | 2022/02/17 | [7.0.0 Preview 1](https://github.com/dotnet/core/blob/main/release-notes/7.0/preview/7.0.0-preview.1.md) |

- 2021年12月15日正式发布了.NET 6.0.1版本，之前的迭代是从2021年2.18到2021年12.15。.NET 6是LTS 版本，将支持三年，从 2021 年 11 月到 2024 年 11 月。它在多个操作系统上受 Microsoft 支持。

  .NET 6 版本包括对 macOS 和 Windows Arm64 操作系统的支持。

  ### .NET 6 Releases

  | Date       | Release                                                      |
  | ---------- | ------------------------------------------------------------ |
  | 2022/06/14 | [6.0.6](https://github.com/dotnet/core/blob/main/release-notes/6.0/6.0.6/6.0.6.md) |
  | 2022/05/10 | [6.0.5](https://github.com/dotnet/core/blob/main/release-notes/6.0/6.0.5/6.0.5.md) |
  | 2022/04/12 | [6.0.4](https://github.com/dotnet/core/blob/main/release-notes/6.0/6.0.4/6.0.4.md) |
  | 2022/03/08 | [6.0.3](https://github.com/dotnet/core/blob/main/release-notes/6.0/6.0.3/6.0.3.md) |
  | 2022/02/08 | [6.0.2](https://github.com/dotnet/core/blob/main/release-notes/6.0/6.0.2/6.0.2.md) |
  | 2021/12/14 | [6.0.1](https://github.com/dotnet/core/blob/main/release-notes/6.0/6.0.1/6.0.1.md) |
  | 2021/11/08 | [6.0.0](https://github.com/dotnet/core/blob/main/release-notes/6.0/6.0.0/6.0.0.md) |
  | 2021/10/12 | [6.0.0 RC 2](https://github.com/dotnet/core/blob/main/release-notes/6.0/preview/6.0.0-rc.2.md) |
  | 2021/09/14 | [6.0.0 RC 1](https://github.com/dotnet/core/blob/main/release-notes/6.0/preview/6.0.0-rc.1.md) |
  | 2021/08/10 | [6.0.0 Preview 7](https://github.com/dotnet/core/blob/main/release-notes/6.0/preview/6.0.0-preview.7.md) |
  | 2021/07/14 | [6.0.0 Preview 6](https://github.com/dotnet/core/blob/main/release-notes/6.0/preview/6.0.0-preview.6.md) |
  | 2021/06/17 | [6.0.0 Preview 5](https://github.com/dotnet/core/blob/main/release-notes/6.0/preview/6.0.0-preview.5.md) |
  | 2021/05/25 | [6.0.0 Preview 4](https://github.com/dotnet/core/blob/main/release-notes/6.0/preview/6.0.0-preview.4.md) |
  | 2021/04/08 | [6.0.0 Preview 3](https://github.com/dotnet/core/blob/main/release-notes/6.0/preview/6.0.0-preview.3.md) |
  | 2021/03/11 | [6.0.0 Preview 2](https://github.com/dotnet/core/blob/main/release-notes/6.0/preview/6.0.0-preview.2.md) |
  | 2021/02/17 | [6.0.0 Preview 1](https://github.com/dotnet/core/blob/main/release-notes/6.0/preview/6.0.0-preview.1.md) |

- 2021年3.10日进行了最后一次.NET5.0.4的更新。.NET 5于 2020 年 5 月 10 日发布。该版本是许多贡献者的协作努力。.NET 5 于 2022 年 5 月 10 日终止支持| 它在多个操作系统上得到 Microsoft的支持。

  ### .NET 5 Releases

  | Date       | Release                                                      |
  | ---------- | ------------------------------------------------------------ |
  | 2020/05/10 | Out of Support                                               |
  | 2022/05/10 | [5.0.17](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.17/5.0.17.md) |
  | 2022/04/12 | [5.0.16](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.16/5.0.16.md) |
  | 2022/03/08 | [5.0.15](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.15/5.0.15.md) |
  | 2022/02/08 | [5.0.14](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.14/5.0.14.md) |
  | 2021/12/14 | [5.0.13](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.13/5.0.13.md) |
  | 2021/11/08 | [5.0.12](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.12/5.0.12.md) |
  | 2021/10/12 | [5.0.11](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.11/5.0.11.md) |
  | 2021/09/14 | [5.0.10](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.10/5.0.10.md) |
  | 2021/08/10 | [5.0.9](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.9/5.0.9.md) |
  | 2021/07/13 | [5.0.8](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.8/5.0.8.md) |
  | 2021/06/08 | [5.0.7](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.7/5.0.7.md) |
  | 2021/05/25 | [5.0.300](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.6/5.0.300-sdk.md) |
  | 2021/05/11 | [5.0.6](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.6/5.0.6.md) |
  | 2021/04/06 | [5.0.5](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.5/5.0.5.md) |
  | 2021/03/09 | [5.0.4](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.4/5.0.4.md) |
  | 2021/03/02 | [5.0.200](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.3/5.0.200-sdk.md) |
  | 2021/02/09 | [5.0.3](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.3/5.0.3.md) |
  | 2021/01/12 | [5.0.2](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.2/5.0.2.md) |
  | 2020/12/08 | [5.0.1](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.1/5.0.1.md) |
  | 2020/11/10 | [5.0.0](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0.0/5.0.0.md) |





## 主要贡献者的构成（国家、区域和组织等）：

![image-20220628160915428](assets\image-20220628160915428.png)



The Roslyn .NET compiler 有4.3K的人在使用，然后有514位贡献者。

近一周的PR请求情况是：

![image-20220628161324352](assets\image-20220628161324352.png)



CyrusNajmabadi 有15,982次commits,是最多的一个贡献者。

![image-20220628161619361](assets\image-20220628161619361.png)



sharwell有3,143次 commits，来自加利福尼亚州圣地亚哥。在Microsoft工作。

jaredpar有2,487次commits，也是一位主要贡献者。同样在Microsoft工作。

mavasani有2,170次commits。 同样在Microsoft工作。

其他的贡献者或多或少的进行了1-2,000次以内的commits。

## CI/CD 的使用：

CI/CD 是一种持续开发软件的方法，可以不断的进行构建、测试和部署代码迭代更改。这种迭代有助于减少基于错误或失败的版本进行开发新代码的可能性。使用这种方法，从新代码开发到部署，可以减少人工干预甚至不用干预。

达到持续的方法主要是：持续集成，持续交付，持续部署。

CI（Continuous Integration）：持续集成，也就是当每一次更改的代码被推送到远程分支后，可以创建一组脚本来自动地构建和测试这些更改，确保这些更改可以通过一些基本的准则，减少引入错误的机会。

CD :

Continuous Delivery：持续交付，在持续集成的基础上更进一步，当每一次更改的代码落库后，不仅会构建和测试，也会进行部署，但是部署需要人工干预，手动的有目的进行部署。
Continuous Deployment：持续部署，持续集成之外的另一个步骤，类似于持续交付。不同之处在于，它不是手动部署应用程序，而是将其设置为自动部署。不需要人为干预。

在项目迭代过程，可能有一个专门负责 CI/CD 的人员，但当想做一些静态代码检查，依赖检查，图片大小检查等事情的时候，就自己需要了解 CI/CD，编写特定 Pipeline Job。

在实际项目中，CI 主要是提交或合并代码的时候触发，负责一些基本规则的检查，如果检查遇到失败，那么回滚或修改代码后再提交或合并，降低代码风险；CD 主要手动的触发，在CI的基础上，还负责功能检查，如果功能符合验收标准，那么就可以交付或部署。



通过一个工具，我们可以看到其使用情况。

在Github上增加了一个第三方的插件一Appveyor ，来简单的实现了CI/CD 操作,通过注册账号, 然后各种配置以后,可以实现每次向Github提交,会自动编译，然后生成报告。

![image-20220628164527504](assets\image-20220628164527504.png)

下面是roslyn-CI。![image-20220628164900016](assets\image-20220628164900016.png)

![image-20220628164941323](assets\image-20220628164941323.png)

![image-20220628164953041](assets\image-20220628164953041.png)

## 其他有价值的信息：

![image-20220628170527485](assets\image-20220628170527485.png)

有人提出：一个API方案，提供了这个方案，就能够更好的方法公开功能。

但这样做会导致：内部 API 由 Roslyn 本身的一些代码修复使用，这会阻止将这些代码修复移动到共享的分析器层。

因此这个提出的方案不可以。

另外，这个工作也用到了语法树。

“语法树”是一种由编译器 API 公开的基础的不可变数据结构。 这些树表示源代码的词法和语法结构。 它们有两个重要用途：

- 支持使用工具（如 IDE、加载项、代码分析工具和重构）查看和处理用户项目中源代码的语法结构。
- 支持使用工具（如重构和 IDE）以自然的方式创建、修改和重新排列源代码，而无需直接编辑文本。 通过创建和操作语法树，可轻松使用工具创建和重新排列源代码。

# 二、项目的历史轨迹分析

见Sourcetrail.ipynb。

# 三、结合期中分析的归档项目，对比分析活跃/归档项目



## 期中期末项目数据对比分析

- 项目基础数据（2.1/2.2/2.3）的变化趋势

  1. 每月新增 Star 和 Frok 

     Sourcetrail的Star 和 Frok ：（项目刚开始是增长迅速，后来直到归档每月趋于下降）

     ![image-20220628172113899](assets\image-20220628172113899.png)

     The Roslyn .NET compiler （roslyn）的Star 和 Frok ：（保持平稳递进）

     ![image-20220628172209856](assets\image-20220628172209856.png)

  2. 每月打开 Issue 和 关闭 Issue 

     Sourcetrail每月打开和关闭Issue量：（项目开始缓慢增长，但每月打开Issue最高数量仅为62，每月关闭Issue最高数量为38.最后每月Issue打开和关闭数量几乎为0）

     <img src="assets\image-20220628185129262.png" alt="image-20220628185129262" style="zoom:33%;" />

     <img src="assets\image-20220628185203311.png" alt="image-20220628185203311" style="zoom:33%;" />

     The Roslyn .NET compiler （roslyn）每月打开和关闭issue量：（项目开始增长速度较快，后段时间增长较慢，但每月打开Issue最高数量为493，每月关闭Issue最高数量为625.后来Issue打开和关闭数量都不为0）

     <img src="assets\image-20220628181653943.png" alt="image-20220628181653943" style="zoom: 33%;" />

     <img src="assets\image-20220628181752813.png" alt="image-20220628181752813" style="zoom:33%;" />

  3. 每月打开 PR 和**合入** PR 

     Sourcetrail 每月打开 PR 和合入 PR量：（不断下降，最后几乎为0）

     <img src="assets\image-20220628191340338.png" alt="image-20220628191340338" style="zoom:33%;" />

     

     <img src="assets\image-20220628191418241.png" alt="image-20220628191418241" style="zoom:33%;" />

     The Roslyn .NET compiler （roslyn）每月打开 PR 和合入 PR量：（数量不断波动，但都不为0）

     <img src="assets\image-20220628181851316.png" alt="image-20220628181851316" style="zoom:33%;" />

     <img src="assets\image-20220628181819767.png" alt="image-20220628181819767" style="zoom:33%;" />

     

- 开发者数量（2.4）变化趋势

  Sourcetrail 只有36位开发者。说明大家对这个项目并不感冒。

  The Roslyn .NET compiler （roslyn）目前有514位贡献开发者。以后还会有更多的开发者加入。

- 其他你感兴趣的对比方向

  两个项目的延续时间，可以看到：

  Sourcetrail 是从2014年开始，但到2021年就归档了。

  ![image-20220628171816077](assets\image-20220628171816077.png)

  The Roslyn .NET compiler （roslyn）是从2015年发表了第一个版本，但一直到现在（2022年）还在延续。

  ![image-20220628171719743](assets\image-20220628171719743.png)

## 项目发展到活跃/归档的主要影响因素及原因

最后，给出我们小组认为的项目发展到活跃/归档的主要影响因素及原因：

### 期中作业分析：归档项目-Sourcetrail

该项目由 Sourcetrail 的原始作者和维护者于 2021 年底存档。

在 2019 年秋季将 Sourcetrail 转换为开源项目后，他们的这个项目最初得到了很多关注，并且非常有动力继续开展该项目。在他们的前几个季度发布时保持了良好的时间表，但很快进展变得缓慢，最终不再对电子邮件、新问题和拉取请求（PR）做出响应。

有几个原因：

1.关闭他们的初创公司后，他们将每天的工作时间投入到新工作中。

2.然后在 2020 年春季，公司的老板从萨尔茨堡搬到了维也纳，这使得合作变得更加困难，因为他们的成员不再同处一地。

3.慢慢地，重新开始该项目的工作也成为一项挑战。毕竟，它一直是一个雄心勃勃的软件，具有许多技术依赖项，需要不断关注以保持最新版本的最新状态。

4.特别是考虑到 Sourcetrail 在多个平台上运行，支持多种语言和构建系统，并与不同的 3rd 方工具集成。总而言之，这使得维护和恢复变得相当困难。



最终，他们的创始者也失去了在语言分析和软件可视化领域工作的兴趣，并开始将重点放在新的领域。虽然他们所取得的成就感到自豪，但在了解了创建开发工具的现实挑战，并且知道它需要大量的工作，这些工作往往令人沮丧，而且根本不好玩。

由于所有这些原因，他们决定停止该项目。

但他们在2021年秋季发布 Sourcetrail 2021.4 的最终版本。之后，将网站离线并将存储库存档在 GitHub 上，这实际上冻结了git 存储库、问题列表和 wiki。但是，它仍然允许任何人查看存储库、分叉并下载任何托管版本。

究其原因，我认为是开源项目最需要的是大家的共同合作，一个人很难完成一个巨大的工作，因此，合作共赢是一个团队应该做的事情。

### 期末作业分析：活跃项目-The Roslyn .NET compiler （roslyn）

综上所述，该项目一直在活跃，而且就在刚刚还有新的CI/CD。这就足以证明该项目的一个活跃性。

![image-20220628165804490](assets\image-20220628165804490.png)

我们认为该项目可以一直活跃的原因是：

- .NET Compiler Platform SDK 极大地降低了创建以代码为中心的工具和应用的门槛。 它将在元编程、代码生成和转换、C# 和 Visual Basic 语言的交互式使用，以及在域特定语言中嵌入 C# 和 Visual Basic 等方面，创造许多创新的机遇。
- .NET Compiler Platform SDK 使你能够生成分析器和代码修补程序，用于发现和更正编码错误。 分析器可理解语法（代码的结构）和语义，从而检测应更正的做法。 代码修补程序建议一处或多处修复，以修复分析器或编译器诊断发现的编码错误。 通常情况下，分析器和关联的代码修补程序一起打包在一个项目中。
- 分析器和代码修补程序通过静态分析来理解代码。 它们既不运行代码，也未带来其他测试方面的好处。 但是，它们可以指出经常导致 bug 的做法、无法维护的代码或标准原则冲突。
- 除了分析器和代码修补程序外，.NET Compiler Platform SDK 还允许你生成代码重构。 它还提供了一组 API，可便于检查和理解 C# 或 Visual Basic 代码库。 由于可以使用这一基准代码，因此能够利用 .NET Compiler Platform SDK 提供的语法和语义分析 API，更轻松地编写分析器和代码修补程序。 从复制由编译器执行的分析的繁重任务中解放出来，可以将精力放在为项目或库查找常见编码错误并进行修复的更为重要的任务上。
- 这带来的一个小小的好处是，分析器和代码修补程序较小，在 Visual Studio 中加载时占用的内存比为了理解项目中的代码而编写自己的基准代码占用的内存少得多。 利用编译器和 Visual Studio 使用的相同类，可以创建自己的静态分析工具。 也就是说，团队可以使用分析器和代码修补程序，而不会对 IDE 的性能造成显著影响。





