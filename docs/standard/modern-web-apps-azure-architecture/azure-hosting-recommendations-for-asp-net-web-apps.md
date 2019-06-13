---
title: 关于 ASP.NET Core Web 应用的 Azure 托管建议
description: 使用 ASP.NET Core 和 Azure 构建新式 Web 应用程序 | 关于 ASP.NET Web 应用的 Azure 托管建议
author: ardalis
ms.author: wiwagn
ms.date: 06/06/2019
ms.openlocfilehash: 7cfb9ada4f963aa392a41cfb9f1b2df22f542d41
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758669"
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>关于 ASP.NET Core Web 应用的 Azure 托管建议

> "业务线领导者无处不在绕过 IT 部门获取从云 (也称为 SaaS) 应用程序，并且它们像订阅杂志一样为它们付费。 不再需要服务时，他们可取消订阅，不会出现设备闲置的情况。”  
> \-Gartner 分析师 Daryl Plummer 

任何应用程序的需求和体系结构，Microsoft Azure 可以支持它。 托管需求可以很简单，只需为静态网站或数十种服务组成的复杂应用程序。 对于 ASP.NET Core 整体 Web 应用程序和支持服务，推荐以下几种常见配置。 无论是完整应用程序、单个进程或数据，本文中的建议配置均按待托管资源的类型分组。

## <a name="web-applications"></a>Web 应用程序

可通过以下方式托管 Web 应用程序：

- 应用服务 Web 应用

- 容器 （几个选项）

- 虚拟机 (VM)

其中，应用服务 Web 应用是推荐用于大多数方案，包括简单的基于容器的应用程序的方法。 对于微服务体系结构，请考虑使用基于容器的方法。 如果需要更好地控制运行应用程序的计算机，请考虑使用 Azure 虚拟机。

### <a name="app-service-web-apps"></a>应用服务 Web 应用

应用服务 Web 应用提供的完全托管平台针对托管 Web 应用程序进行了优化。 它是一种平台即服务 (PaaS) 产品/服务，可使你专注于业务逻辑，而由 Azure 负责维护应用运行和缩放所需的基础结构。 应用服务 Web 应用的一些关键功能：

- DevOps 优化（持续集成和交付、多环境、A/B 测试和脚本支持）。

- 全球缩放和高可用性。

- 可连接至 SaaS 平台和本地数据。

- 安全性和符合性。

- Visual Studio 集成。

Azure 应用服务是适合大多数 Web 应用的最佳选择。 该平台集成部署与管理，站点可快速缩放以处理高流量负载，内置负载均衡和流量管理器提供高可用性。 可通过在线迁移工具将现有站点轻松移动到 Azure 应用服务、使用 Web 应用程序库中的开源应用或使用框架和你选择的工具创建新的站点。 通过 WebJobs 功能可将后台作业处理轻松添加到应用服务 Web 应用。 如果你有一个现成的 ASP.NET 应用程序托管在本地使用的本地数据库，则途径，若要将应用迁移到应用服务 Web 应用与 Azure SQL 数据库 （或安全访问你的本地数据库服务器，如果愿意）。

![推荐的迁移策略的本地到 Azure 应用服务的.NET 应用程序](./media/image1-6.png)

在大多数情况下，将从本地托管的 ASP.NET 应用程序移至应用服务 Web 应用是一个简单的过程。 很少或没有修改应需要的应用程序本身，并且它可以快速开始充分利用 Azure 应用服务 Web 应用提供的许多功能。

除了不针对云优化的应用，Azure 应用服务 Web 应用还有许多简单整体式 （非分布式） 应用程序，例如多个 ASP.NET Core 应用的优异解决方案。 在这种方法，体系结构是基本的简单了解和管理：

![基本 Azure 体系结构](./media/image1-5.png)

少量的单个资源组中的资源是通常不足以管理此类应用。 应用程序通常部署为单个单元，而不是由组成的多个单独的进程，这些应用程序非常适合进行这[基本体系结构方法](https://docs.microsoft.com/azure/architecture/reference-architectures/app-service-web-app/basic-web-app)。 这种方法很简单，但仍允许托管的应用缩放两者了 （更多资源，每个节点） 和输出 （更多托管的节点） 以满足任何增加的需求。 使用自动缩放，应用程序可以配置为自动调整的托管应用程序根据需求和平均负载跨节点的节点数。

### <a name="app-service-web-apps-for-containers"></a>用于容器的应用服务 Web 应用

除了支持直接，托管 web 应用[用于容器的应用服务 Web 应用](https://azure.microsoft.com/services/app-service/containers/)可用于 Windows 和 Linux 上运行容器化应用程序。 使用此服务，你可以轻松地部署和运行容器化应用程序可以与你的业务一起缩放的。 应用具有的所有上面列出的应用服务 Web 应用的功能。 此外，适用于容器支持的 Web 应用，可以简化 CI/CD 用于 Docker 中心、 Azure 容器注册表和 GitHub。 Azure DevOps 可用于定义将更改发布到注册表的生成和部署管道。 这些更改可以随后可在过渡环境中测试并自动部署到生产环境使用部署槽位，从而允许零停机时间升级。 可以很容易地回滚到以前的版本。

有几种方案用于容器的 Web 应用在其中进行的最大价值。 如果在 Windows 或 Linux 容器中是否有你可以容器化的现有应用，可以托管这些轻松地使用此工具集。 只需将发布你的容器，然后配置要从所选的注册表中拉取该映像的最新版本的容器的 Web 应用。 这是从托管到云优化模型的模型的经典应用程序迁移到的"提升和 shift"方法。

![本地容器化的.NET 应用程序迁移到用于容器的 Azure Web 应用](./media/image1-8.png)

如果您的开发团队是能够将移动到基于容器的开发过程，此方法也适用。 开发使用容器的应用的"内部循环"包括构建应用程序与容器。 为代码，也适用容器配置所做的更改推送到源代码管理和自动的生成负责将新容器映像发布到如 Docker Hub 注册表或 Azure 容器注册表。 这些映像是然后用作额外的开发，以及部署到生产环境，如以下关系图中所示：

![端到端 Docker DevOps 生命周期工作流](./media/image1-7.png)

使用容器开发提供了很多优点，尤其是在生产环境中使用容器。 相同的容器配置用于托管该应用程序在每个环境中运行，从本地开发计算机以生成和测试系统到生产。 这极大地降低了缺陷导致的计算机配置或软件版本之间的差异的可能性。 开发人员还可以使用任何工具，它们最高效地使用，包括操作系统，因为容器可以在任何操作系统上运行。 在某些情况下，涉及多个容器的分布式应用程序可能是非常耗费资源的单个开发计算机上运行。 在此方案中，它可能请升级到使用 Kubernetes 和 Azure 开发人员空间，在下一节中介绍。

因为较大型应用程序的某些部分被拆分成多自己较小独立*微服务*，可以使用额外的设计模式以提高应用程序的行为。 而不是直接与单个服务处理*API 网关*可以简化访问，并将其后端中的客户端中分离出来。 具有单独的服务后端的不同前端还允许以配合其使用者的服务。 常见服务可以访问通过单独*挎斗*容器，这可能包括使用的常见客户端连接库*代表*模式。

![微服务与所述的几种常见设计模式的示例体系结构。](./media/image1-10.png)

[了解有关构建基于微服务的系统时需要考虑的设计模式的详细信息。](https://docs.microsoft.com/azure/architecture/microservices/design/patterns)

### <a name="azure-kubernetes-service"></a>Azure Kubernetes 服务

Azure Kubernetes 服务 (AKS) 管理托管的 Kubernetes 环境，即使没有容器业务流程专业知识，也可快速轻松地部署和管理容器化应用程序。 此外，它还通过预配、升级和按需缩放资源，消除了持续操作和维护的负担，而无需应用程序脱机。

通过将大量责任转移至 Azure，AKS 降低了管理 Kubernetes 群集的复杂性和运营开销。 作为一项托管的 Kubernetes 服务，Azure 将为你处理运行状况监视和维护等关键任务。 并且，你仅需支付群集中的代理节点，而无需支付主节点。 作为一项托管的 Kubernetes 服务，AKS 提供以下功能：

- 自动化的 Kubernetes 版本升级和修补。
- 轻松的群集缩放。
- 自我修复型托管控制平面（主节点）。
- 节省成本：仅支付运行的代理池节点。

由于 Azure 会负责管理 AKS 群集中的节点，因此，很多任务（例如群集升级）不再需要手动执行。 由于 Azure 会处理这些关键维护任务，因此，AKS 不提供对群集的直接访问（例如使用 SSH）。

团队利用 AKS 还可以利用 Azure 开发人员空格。 Azure 开发人员空间可帮助团队通过允许团队成员要直接使用其整个微服务体系结构或在 AKS 中运行的应用程序集中于开发和微服务应用程序的快速迭代。 Azure 开发人员空间还提供了独立更新的微服务体系结构中隔离的部分而不会影响在 AKS 群集或其他开发人员的其余部分的方法。

![Azure 开发人员空间工作流示例](./media/image1-9.gif)

Azure 开发人员空间：

- 本地计算机安装时间和资源需求降至最低
- 允许团队能够更快速地循环访问
- 减少所需的团队的集成环境的数量
- 需要开发/测试时，模拟某些服务在分布式系统中删除

[了解有关 Azure 开发人员空间的详细信息](https://docs.microsoft.com/azure/dev-spaces/about)

### <a name="azure-virtual-machines"></a>Azure 虚拟机

如果现有应用程序需要经过大量修改才可在应用服务中运行，为简化迁移到云的操作，可选择虚拟机。 然而，与 Azure 应用服务相比，正确配置、保护和维护 VM 需要更多时间和 IT 专业知识。 如要使用 Azure 虚拟机，请务必考虑到 VM 环境的修补、更新和管理所需的持续性维护工作。 Azure 虚拟机属于基础结构即服务 (IaaS)，而应用服务属于 PaaS。 还应考虑将应用作为 Windows 容器部署到用于容器的 Web 应用是否可能成为方案的可行选项。

## <a name="logical-processes"></a>逻辑进程

对于可从应用程序的剩余部分分离的单独逻辑进程，可以“无服务器”方式将其独立部署到 Azure Functions。 通过 Azure Functions 可编写解决特定问题所需的代码，无需担心运行它的应用程序或基础结构。 可选择各种编程语言，包括 C\#、F\#、Node.js、Python 和 PHP，以便你选择一种最高效语言来处理手头任务。 与多数基于云的解决方案一样，仅需为使用的时间量支付费用，而且 Azure Functions 按需扩展非常可靠。

## <a name="data"></a>数据

Azure 提供多种数据存储选择，以便应用程序可使用恰当的数据提供程序处理相关数据。

对于事务和关系数据，Azure SQL 数据库是最佳选择。 对于以读取为主的高性能数据，受 Azure SQL 数据库支持的 Redis 缓存是一个不错的解决方案。

可使用多种方式存储非结构化 JSON 数据，包括 SQL 数据库列、Blob、Azure 存储中的表以及 Cosmos DB。 其中，Cosmos DB 提供最佳查询功能，建议用于必须支持查询的大量基于 JSON 的文档。

暂时命令或者用于安排应用程序行为的基于事件的数据可使用 Azure 服务总线或 Azure 存储队列。 Azure 存储总线具有更强的灵活性，建议将该服务用于处理应用程序内和应用程序间的非普通消息传递。

## <a name="architecture-recommendations"></a>体系结构建议

应用程序要求应决定其体系结构。 有多种不同的 Azure 服务可供使用。 选择正确的服务是一项重要决定。 Microsoft 提供一系列参考体系结构，帮助用户确定针对常见方案优化的典型体系结构。 可找到一个与应用程序要求高度契合或至少提供一个出发点的参考体系结构。

图 11-2 显示了一个示例参考体系结构。 该图介绍了一个建议用于为市场营销而优化的 Sitecore 内容管理系统网站的体系结构方式。

![](./media/image11-2.png)

**Figure 11-1**。 Sitecore 市场营销网站参考体系结构。

**参考：Azure 托管建议**

- Azure解决方案体系结构\
  <https://azure.microsoft.com/solutions/architecture/>

- Azure 基本 Web 应用程序 Architecture\
  <https://docs.microsoft.com/azure/architecture/reference-architectures/app-service-web-app/basic-web-app>

- Microservices\ 的设计模式
  <https://docs.microsoft.com/azure/architecture/microservices/design/patterns>

- Azure 开发人员指南\
  <https://azure.microsoft.com/campaigns/developer-guide/>

- Web 应用概述\
  <https://docs.microsoft.com/azure/app-service/app-service-web-overview>

- 用于容器的 Web 应用\
  <https://azure.microsoft.com/services/app-service/containers/>

- Azure Kubernetes 服务 (AKS) 简介\
  <https://docs.microsoft.com/azure/aks/intro-kubernetes>

>[!div class="step-by-step"]
>[上一篇](development-process-for-azure.md)
