---
title: 更新现有.NET 应用程序与 Azure 云和 Windows 容器 （第二版）
description: 了解如何提升和按住 shift 并更新现有应用程序到 Azure 云和与此电子书的容器。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 4/28/2018
ms.openlocfilehash: 3fcfdca68e05494785148cbbe149cdc2f812c577
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers-2nd-edition"></a>更新现有的.NET 应用程序与 Azure 云和 Windows 容器 （第二版）

![封面图像](./media/cover.png)

发布者  
Microsoft Press 和 Microsoft DevDiv  
Microsoft Corporation 的部门  
One Microsoft Way  
Redmond, Washington 98052-6399  

版权所有 © Microsoft corporation 2018  

保留所有权利。 未经发布者书面许可，不得以任何形式或任何方式复制本书中的任何内容。

本书位于免费电子书 （电子图书） 可通过 microsoft 的多个通道的形式如http://dot.net/architecture。

若要了解本书的相关问题，请发送电子邮件至 [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book)

本书“按原样”提供，表达作者的观点和看法。 视图、 观点和表示本书，包括 URL 和其他 Internet 网站引用中的信息可能会更改恕不另行通知。

本书中提及的一些示例仅用于说明，纯属虚构。 不存在任何实际关联或联系，请勿妄加推断。

Microsoft 和列在商标http://www.microsoft.com"商标"网页上是 Microsoft 公司集团的商标。 所有其他标记均为其各自所有者的财产。

作者:
> **Cesar de la Torre**，Microsoft Corp. .NET 产品团队的高级项目经理。

参与者和审阅者：
> **Scott Hunter**，Microsoft .NET 团队的合作伙伴总监项目经理  
> **Paul Yuknewicz**，Microsoft Visual Studio Tools 团队的主要项目经理  
> **Lisa Guthrie**，Microsoft Visual Studio Tools 团队的高级项目经理  
> **Ankit Asthana**，Microsoft .NET 团队的主要项目经理  
> **Unai Zorrilla**，Plain Concepts 的开发者领导  
> **Javier Valero**，Grupo Solutio 的首席运营官  

## <a name="introduction"></a>介绍

如果你决定要更新你的 web 应用程序或服务并将它们移到云，你不一定需要完全构建你的应用。 重新应用程序架构通过使用高级如微服务方法并不总是选项由于成本和时间的约束。 根据应用程序的类型，重新应用架构也可能不是必要。 为了优化组织云迁移策略的成本效益，必须考虑业务和应用的需求。 需要确定：

- 哪些应用需要转换或重新架构。

- 哪些应用只需部分更新。

- 哪些应用能直接“直接迁移”到云。

## <a name="about-this-guide"></a>关于本指南

本指南主要侧重初始现代化的现有 Microsoft.NET Framework web 服务器或面向服务的应用程序，这意味着将工作负荷移动到较新的或更现代的环境，而无需显著更改应用程序的代码的操作和基本的体系结构。 

本指南也将突出显示你的应用程序迁移到云和部分 modernizing 通过使用一组特定的新技术和方法，如 Windows 容器和 Azure 支持 Windows 容器中的相关的计算平台的应用程序的优点。

## <a name="path-to-the-cloud-for-existing-net-applications"></a>将现有 .NET 应用程序迁移到云的途径

组织通常选择移动到云来使其应用程序获得敏捷性和速度。 只需几分钟即可在云中设置数千台服务器 (VM)，而设置本地服务器通常需要数周。

将应用程序迁移到云没有普遍通用的策略。 合适的迁移方法由组织的需求和优先考虑事项，以及要迁移的应用程序种类决定。 并非所有应用程序都保证可以移动到平台即服务 ([PaaS](https://azure.microsoft.com/overview/what-is-paas/)) 模型或开发[云原生](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications)应用程序模型。 许多情况下都可根据业务需求采用阶段性或递增性方法将资产移动到云。

为具有最佳长期的灵活性和为组织的值的现代应用程序，您也可以获益那么投资于*云本机*应用程序体系结构。 但是，对于现有的应用程序或旧资产，关键是将它们移到云中，为了实现显著的好处时花费最少的时间和金钱 （无重新架构或代码更改）。

图 1-1 显示了采用递增性方法将现有 .NET 应用程序移动到云时可能使用的途径。

 ![现有 .NET 应用程序和服务的更新途径](./media/image1-1.png)

> **图 1-1**。 现有 .NET 应用程序和服务的更新途径

每种迁移方法的优点和使用原因各不相同。 可以选择一种方法将应用迁移到云，也可以从多种方法中选择某些组件。 单个应用程序不限于单一的方法或成熟度状态。 例如，常见的混合方法将包含某些本地组件以及云中的其他组件。

定义和短说明每个应用程序的成熟度级别如下所示：

**级别 1： 云基础结构已准备**应用程序： 在此迁移方法中，你只需迁移或 rehost 当前在本地应用程序到基础结构即服务 ([IaaS](https://azure.microsoft.com/overview/what-is-iaas/)) 平台。 应用的组成与之前基本一致，但现在可将它们部署到云中的 VM。
在"提升 & 位移。"行业中通常已知此简单类型的迁移

**级别 2： 云优化**应用程序： 在此级别和仍而无需重新架构或修改大量代码，你可以获得其他好处使用如容器和其他现代技术在云中运行你的应用程序云托管服务。 通过优化企业开发操作 (DevOps) 流程，可以提高应用程序的敏捷性，以实现更快交付。 通过使用基于 Docker 引擎的 Windows 容器等技术来实现此目的。 容器中删除在多个阶段中部署时，由应用程序依赖关系的摩擦。 在此成熟度模型中，你可以部署 IaaS 上的容器或 PaaS 时使用其他云托管服务相关的数据库，缓存为服务、 监视和持续集成/连续部署 (CI/CD) 管道。

第三个成熟度级别是云中的最终目标，但对于很多应用它是可选的，并不是本指南的主要重点：

**级别 3： 云本机**应用程序： 此迁移方法通常由驱动的业务需求和目标 modernizing 任务关键型应用程序。 在此级别，使用 PaaS 服务将应用移动到 PaaS 计算平台。 实现[云原生](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications)应用程序和微服务体系结构，以改进应用程序，使其具有长期的敏捷性并扩展至新的限制。 此类更新通常需要专门针对云进行构建。 通常必须编写新代码，尤其是移动到基于云原生应用程序和微服务的模型时。 此方法有助于获得一些益处，这些益处在单片和本地应用程序环境中很难实现。

表 1-1 介绍了选择每种迁移或更新方法的主要优点和原因。

| **云基础结构就绪** <br /> *直接迁移* | **云优化** <br /> *更新* | **云-本机** <br /> *现代化、 构建和重写* |
|---|---|---|
| **应用程序的计算目标** |
| 部署到 Azure 中 VM 的应用程序 | 整体或 N 层应用程序部署到 Azure App Service、 Azure 容器实例 (ACI)、 虚拟机与容器、 Azure Service Fabric 中或 AKS （Azure Kubernetes 服务） | Azure Kubernetes 服务 (AKS)，Service Fabric 和/或基于 Azure 函数的无服务器微服务上的容器化微服务。 |
| **数据目标** |
| VM 中的 SQL 或任何关系数据库 | Azure SQL 数据库托管实例或另一个在云中托管的数据库。 | 因而罚款粒度微服务，Azure SQL 数据库、 Azure Cosmos DB 或在云中托管的另一个数据库上基于每个数据库 |
| **优点**|
| <li>没有重新架构，任何新的代码 <li> 需要的工作量最少，实现快速迁移 <li> Azure 中支持最小公分母 <li> 保证基本可用性 <li> 移动到云后，更容易更新 | <li> 不重新架构 <li> 最小代码/配置更改 <li> 由于容器的原因，改进了部署和 DevOps 发布敏捷性 <li> 增加了密度，降低了部署成本 <li> 应用的可移植性和依赖项 <li> 灵活的主机目标： PaaS 方法或 IaaS | <li> 架构师云，您可以获得最佳好处从云中但需要新代码 <li> 微服务云原生方法 <li> 现代任务关键型应用程序，云弹性超可缩放 <li> 完全托管服务 <li> 优化了规模 <li> 通过子系统优化了自主敏捷性 <li> 基于部署和 DevOps |
| **挑战** |
| <li> 除了转移运营费用或关闭数据中心之外，云价值较小 <li> 很少进行管理： 没有操作系统或中间件修补;可能使用基础结构解决方案，Terraform、 Spinnaker，或 puppet 这类 | <li> Containerizing 是为开发人员和 IT 运营学习曲线中的一个额外的步骤 <li> DevOps 和 CI/CD 管道通常是必需的这种方法。 如果不是当前出现在组织的区域性中，则可能是其他质询| <li> 需要重新组织了架构的云本机应用程序和微服务体系结构，但通常需要大量代码重构或重写时 modernizing （增加的时间和预算） <li> DevOps 和 CI/CD 管道通常是必需的这种方法。 如果不是当前出现在组织的区域性中，则可能是其他质询|
> **表 1-1**。 现有 .NET 应用程序和服务的更新途径的优势和挑战

### <a name="key-technologies-and-architectures-by-maturity-level"></a>各成熟度级别使用的关键技术和体系结构

.NET Framework 应用程序的初始版本为 .NET Framework 1.0，该版本于 2001 年年底发布。 然后，公司发布了更新的版本（如 2.0、3.5 和 .NET 4.x）。 这些应用程序的大多数 Windows Server 和 Internet 信息服务器 (IIS) 上运行，并使用关系数据库中的，如 SQL Server、 Oracle、 MySQL 或任何其他 RDBMS。

当今大部分现有 .NET 应用程序可能都基于 .NET Framework 4.x，甚至 .NET Framework 3.5，并使用 Web 框架，如 ASP.NET MVC、ASP.NET Web 窗体、ASP.NET Web API、Windows Communication Foundation (WCF)、ASP.NET SignalR 和 ASP.NET 网页。 这些既定的 .NET Framework 技术都依赖于 Windows。 如果只是简单地迁移旧版应用并希望对应用程序基础结构作出最少的更改，依赖项是一项重要的考虑因素。

图 1-2 显示了三个云成熟度级别中每一个级别所使用的主要技术和体系结构样式：

![用于更新现有 .NET Web 应用程序的每个成熟度级别的主要技术](./media/image1-2.png)

> **图 1-2**。 用于更新现有 .NET Web 应用程序的每个成熟度级别的主要技术

图 1-2 强调了最常见的方案，但在体系结构方面，可能存在许多混合变体。 例如，成熟度模型不仅适用于现有 Web 应用的单片体系结构，还适用于服务方向、N 层以及其他体系结构样式变体。 更高版本的焦点或上一个或另一个体系结构类型和相关的技术的百分比确定你的应用程序的总体成熟度。

更新流程中的每个成熟度级别与以下关键技术和方法相关：

- **云基础结构已准备**（rehost 或 basic 提升和移动）： 第一步，许多组织只是想快速执行云迁移策略。 在这种情况下，应用程序是重新承载的。 大多数重新托管均可使用 [Azure Migrate](https://aka.ms/azuremigrate) 自动完成，该服务提供指南、见解和机制，帮助迁移到基于 Azure 的云工具（如 [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) 和 [Azure 数据库迁移服务](https://azure.microsoft.com/campaigns/database-migration/)）。 也可以手动设置重新托管，以便在将旧版应用移动到云时了解关于这些资产的基础结构详细信息。 例如，你可以将应用程序移到虚拟机在 Azure 中很少或者修改可能与仅次要配置更改。 这种情况下的网络类似于本地环境，尤其是在 Azure 中创建虚拟网络时。

- **云优化**（托管服务和 Windows 容器）： 此模型是如何使几个重要部署优化以获取一些显著的好处，从云中，而无需更改应用程序的核心体系结构。 此处的基本步骤是对现有 .NET Framework 应用程序增加 [Windows 容器](https://docs.microsoft.com/virtualization/windowscontainers/about/) 支持。 此重要步骤 （容器化） 不需要触及代码，以便总体提起并移动工作量较轻。 可以使用 [Image2Docker](https://github.com/docker/communitytools-image2docker-win) 或 Visual Studio 之类的工具，Visual Studio 带有适用于 [Docker](https://www.docker.com/) 的工具。 Visual Studio 自动为 ASP.NET 应用程序和 Windows 容器映像选择智能默认值。 这些工具提供快速内部循环，并提供将容器迁移到 Azure 的快速途径。 部署到多个环境中时，敏捷性得到提高。 然后，移动到生产环境，你可以部署到你 Windows 容器[容器的 Azure Web 应用](https://azure.microsoft.com/en-us/services/app-service/containers/)，[Azure 容器实例 (ACI) 和 Windows Server 2016 和容器，如果你愿意 IaaS 方法的 Azure Vm。 对于稍微复杂一些多容器应用程序，如 orchestrators 到[Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)或[Azure Kubernetes 服务 (AKS/ACS)](https://azure.microsoft.com/en-us/services/container-service/)。 初次更新期间，还可以从云中添加资产，如使用如下工具进行监视：[Azure Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview)适用于应用生命周期且带 [Visual Studio Team Services](https://www.visualstudio.com/team-services/) 的 CI/CD 管道，以及 Azure 中提供的许多其他数据资源服务。 例如，可以修改单片 Web 应用，该应用最初使用传统 [ASP.NET Web 窗体](https://www.asp.net/web-forms)或 [ASP.NET MVC](https://www.asp.net/mvc) 开发，但现在使用 Windows 容器部署。 使用 Windows 容器时，还需要将数据迁移到 [Azure SQL 数据库托管实例](https://docs.microsoft.com/azure/sql-database/)中的数据库，但不需要更改应用程序的核心体系结构。

- **云本机**： 因为引入了，你应当考虑哪些构建[云本机](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications)时你将大型和复杂的应用程序与多个独立的开发团队处理的应用程序不同的微服务可以开发和自主部署。 此外，由于每个微服务 granularized 和独立可伸缩性。 这些体系结构方法不会遇到非常重要的难题和复杂性，但可以通过使用云 PaaS 大大简化和 orchestrators 喜欢[Azure Kubernetes 服务 (AKS/ACS)](https://azure.microsoft.com/en-us/services/container-service/) （托管 Kubernetes） [Azure 服务Fabric 中，和[Azure 函数](https://azure.microsoft.com/services/functions/)有关无服务器的方法。 （例如微服务和无服务器） 的所有这些方法通常要求你为云设计和编写新代码-经过调整以适应特定的 PaaS 平台的代码或与特定的体系结构，如微服务一致的代码。

图 1-3 显示了每个成熟度级别可使用的内部技术：

![每个更新成熟度级别可使用的内部技术](./media/image1-3.png)

> **图 1-3**。 每个更新成熟度级别可使用的内部技术

## <a name="lift-and-shift-scenario"></a>提升和移动方案

对于直接迁移，请记住，在应用程序方案中可以使用很多不同的直接迁移变体。 如果仅重新托管应用程序，则可能拥有类似于图 1-4 中所示的方案，在此方案中，仅对应用程序和数据库服务器使用云中的 VM。

![云中纯 IaaS 方案的示例](./media/image1-4.png)

> **图 1-4**。 云中纯 IaaS 方案的示例

## <a name="modernization-scenarios"></a>现代化方案

对于现代化方案，你可能必须纯云优化使用的应用程序元素仅从该成熟度。 或者，你可以具有某些元素的中间状态应用程序从云就绪基础结构和从云优化的其他元素 (一个"挑选和选择"或混合的模型)，如图 1-5。

![“挑选”方案示例，使用 IaaS 数据库、DevOps 和容器化资产](./media/image1-5.png)

> **图 1-5**。 “挑选”方案示例，使用 IaaS 数据库、DevOps 和容器化资产

接下来，为许多现有的.NET Framework 应用，若要迁移，理想的方案，你无法迁移到云优化应用程序，以获取从工作少显著的好处。 此方法还将设置你注册云本机的可能的未来发展。 图 1-6 显示了一个示例。

![示例云优化应用方案中，与 Windows 容器和托管的服务](./media/image1-6.png)

> **图 1-6**。 示例云优化应用方案中，与 Windows 容器和托管的服务

将更进一步，您可以通过添加用于特定方案的几个微服务来扩展你现有的云优化应用程序。 这会移动你部分到云本机模型，这是不存在的指南的主要重点的级别。


## <a name="what-this-guide-does-not-cover"></a>本指南未涵盖的内容

本指南涵盖了一小部分特定的示例方案，如图 1-7 所示。 本指南重点介绍只能提起并移动方案，且上从根本上讲，云优化模型。 在云优化模型中，通过使用 Windows 容器，以及等监视其他组件改进.NET Framework 应用程序和 CI/CD 管道。 每个组件都是确保将应用程序更快地、敏捷地部署到云的基础。

![本指南中未涉及云本机](./media/image1-7.png)

> **图 1-7** 本指南中未涉及云本机

本指南的重点具有一定的针对性。 它将显示可用于实现提升和 shift 你现有的.NET 应用程序，重新架构，而无需进行任何代码更改的路径。 从根本上讲，它演示如何使你的应用程序云进行优化。

本指南不演示如何创建云本机应用程序，例如如何发展到微服务体系结构。 若要构建你的应用程序或创建全新的应用程序基于微服务，请参阅电子书[.NET 微服务： 为容器化的.NET 应用程序的体系结构](https://aka.ms/microservicesebook)。

### <a name="additional-resources"></a>其他资源

- **容器 Docker 应用生命周期内使用 Microsoft 平台和工具**（可下载电子图书）： [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)

- **.NET 微服务： 为容器化的.NET 应用程序的体系结构**（可下载电子图书）： [*https://aka.ms/microservicesebook*](https://aka.ms/microservicesebook)

- **构建使用 ASP.NET Core 和 Azure 的现代 web 应用程序**（可下载电子图书）： [*https://aka.ms/webappebook*](https://aka.ms/webappebook)

## <a name="who-should-use-this-guide"></a>本指南的目标读者

本指南专为开发人员和解决方案架构师想要更新现有的 ASP.NET web 应用程序或基于.NET Framework 中，为提升灵活性传送和发布应用程序中的 WCF 服务。

本指南可能也对技术决策者有帮助，例如希望大概了解使用 Windows 容器和使用 Microsoft Azure 部署到云可以获得哪些好处的企业架构师或开发负责人/主管。

## <a name="how-to-use-this-guide"></a>如何使用本指南

本指南解释了需要更新现有应用程序的原因，以及使用 Windows 容器将应用移动到云能获得的具体好处。 本指南前几章的内容适用于架构师和技术决策者，他们只需大概了解，不需要实现和技术分步细节。

本指南最后一章介绍重点针对特定部署方案的多个演练。 本指南提供较短版本的演练，来汇总多个方案和突出显示其优势。 完整演练深入到了设置和实现细节，并作为一组 [Wiki 文章](https://github.com/dotnet-architecture/eShopModernizing/wiki)在相同的公共 [GitHub 存储库](https://github.com/dotnet-architecture/eShopModernizing)中发布，该存储库中还存放着相关示例应用（将在下一节讨论）。 关注实现细节的开发者和架构师将对最后一章以及 GitHub 上的分步 Wiki 演练更感兴趣。

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>用于更新旧版应用的示例应用：eShopModernizing

GitHub 上的 [EShopModernizing](https://github.com/dotnet-architecture/eShopModernizing) 存储库提供了两个示例应用程序，用以模拟旧版单片 Web 应用程序。 通过使用 ASP.NET MVC; 开发一个 web 应用通过使用 ASP.NET Web 窗体开发第二个 web 应用和第三个应用程序是具有 WinForms 客户端桌面应用程序使用 WCF 服务后端的 N 层应用。 所有这些应用基于传统的.NET Framework。 这些示例应用不使用 .NET Core 或 ASP.NET Core，它们是要更新的现有/旧版 .NET Framework 应用程序。

这些示例应用具有现代化代码的第二个版本，并且这是非常简单。 两个应用版本之间最重要的差异是第二个版本使用 Windows 容器作为部署选项。 第二个版本中还新增了一些组件，如用于管理映像的 Azure 存储 Blobs、管理安全的 Azure Active Directory，以及用于监视和审核应用程序的 Azure Application Insights。

## <a name="send-your-feedback"></a>发送你的反馈

编写本指南旨在帮助你了解用于提高和 modernizing 现有的.NET web 应用程序的选项。 本指南以及相关示例应用程序不断更新。 你的反馈是受欢迎 ！ 如有关于本指南的改进建议，请将其发送到 [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book)。

>[!div class="step-by-step"]
[下一篇](lift-and-shift-existing-apps-azure-iaas.md)
