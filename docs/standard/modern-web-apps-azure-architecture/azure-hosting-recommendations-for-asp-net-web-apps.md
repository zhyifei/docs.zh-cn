---
title: "Azure 托管的 ASP.NET 核心 web 应用的建议"
description: "设计使用 ASP.NET Core 和 Azure 的现代 Web 应用程序 |Azure 托管的 ASP.NET web 应用程序的建议"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 868f1b7ce452be9e29b921888f90d128e074ba13
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>Azure 托管的 ASP.NET 核心 Web 应用的建议

> "业务线领导者，这些 everywhere 是绕过 IT 部门以获取从云中 (又称 SaaS) 应用程序，并像杂志订阅为它们付费。 并且不再需要该服务时，他们可以取消订阅保留在角中未使用任何设备。"  
> _\- Daryl Plummer，Gartner 分析师_

## <a name="summary"></a>摘要

任何应用程序的需求和体系结构，Azure 可以支持它。 你托管的需求可以很简单，只需为静态网站的多个服务组成的非常复杂应用程序。 对于 ASP.NET Core 整体 web 应用程序和支持服务，有几种已知配置，这建议。 根据要托管、 是否完整应用程序、 单个进程或数据资源的种类，以下建议进行分组。

## <a name="web-applications"></a>Web 应用程序

可以使用托管 web 应用程序：

-   App Service Web Apps

-   容器

-   Azure Service Fabric

-   虚拟机 (Vm)

其中，App Service Web Apps 是在大多数情况下建议的方法。 对于微服务体系结构，请考虑基于容器的方法或从服务构造。 如果你需要更好地控制运行你的应用程序的计算机，考虑 Azure 虚拟机。

### <a name="app-service-web-apps"></a>App Service Web Apps

App Service Web Apps 提供完全托管的平台来托管 web 应用程序优化。 它是 platform-as-a-service(PaaS) 产品使您能够关注你的业务逻辑，而 Azure 负责的基础结构所需的运行和缩放应用程序。 App Service Web Apps 一些关键功能：

-   DevOps 优化 (持续集成和传递，多个环境，A / B 测试、 脚本支持)

-   全球缩放和高可用性

-   连接到 SaaS 平台和你的本地数据

-   安全和合规性

-   Visual Studio 集成

Azure App Service 是大多数 web 应用的最佳选择。 部署和管理集成到平台，站点可以快速缩放以应对高流量负载，以及内置的负载平衡和流量管理器提供高可用性。 你可以移动到 Azure App Service 轻松使用的联机迁移工具的现有站点使用开放源代码应用 Web 应用程序库中，或创建新站点使用的框架和所选的工具。 Web 作业功能，可轻松地为你的 App Service web 应用添加后台作业处理。

### <a name="containers-and-azure-container-service"></a>容器和 Azure 容器服务

Azure 容器服务使您创建、 配置和管理的已预先配置为运行容器化应用程序的虚拟机群集更容易。 它使用的优化的配置的受欢迎的开源计划和协调工具。 这使你使用现有技能，或利用社区专业技能，来部署和管理容器基于 Microsoft Azure 上的应用程序不断增长的正文。

Azure 容器服务使您创建、 配置和管理的已预先配置为运行容器化应用程序的虚拟机群集更容易。 它使用的优化的配置的受欢迎的开源计划和协调工具。 这使你使用现有技能，或利用社区专业技能，来部署和管理容器基于 Microsoft Azure 上的应用程序不断增长的正文。

Azure 容器服务的一个目标是提供了容器宿主环境中使用开放源代码工具和目前在 Microsoft 的客户之间常用的技术。 为此，Azure 容器服务你选 orchestrator （DC/OS、 Docker Swarm，或 Kubernetes） 公开的标准的 API 终结点。 通过使用这些终结点，你可以利用任何能够与这些终结点通信的软件。 例如，对于 Docker Swarm 终结点，你可以选择使用 Docker 命令行界面 (CLI)。 对于 DC/OS，你可能选择 DCOS CLI。 对于 Kubernetes，你可能选择 kubectl。 图 11-1 显示了如何将使用这些终结点来管理你的容器群集。

![](./media/image11-1.png)

**图 11-1。** 使用 Docker、 Kubernetes 或 DC/OS 终结点的 azure 容器服务管理。

### <a name="azure-service-fabric"></a>Azure Service Fabric

如果你要创建新的应用程序或重写现有应用程序以使用微服务体系结构，Service Fabric 是一个不错的选择。 应用程序，它在机的共享池上运行，可以启动小并到大规模具有数百或数千台计算机根据需要增长。 有状态服务让你轻松一致而可靠地存储应用程序的状态，并 Service Fabric 自动管理服务分区、 缩放和可用性为你。 Service Fabric 还支持用于.NET (OWIN) 和 ASP.NET Core 的 WebAPI 打开 Web 界面。 与 App Service 相比，Service Fabric 还提供了更多控制或直接访问，底层基础结构。 你可以远程连接到你的服务器或配置服务器启动任务。

### <a name="azure-virtual-machines"></a>Azure 虚拟机

如果你有现有的应用程序需要进行大幅修改才能在 App Service 或 Service Fabric 中运行程序，你可以选择虚拟机来简化迁移到云。 不过，正确配置、 保护和维护 Vm 需要更多的时间和 IT 专业知识与 Azure App Service 和 Service Fabric 的比较。 如果你正在考虑 Azure 虚拟机，请确保你考虑到修补程序、 更新和管理 VM 环境所需的持续不断的维护工作。 Azure 虚拟机是基础结构作为-服务 (IaaS)，虽然 App Service 和 Service Fabric 平台作为-服务 (Paas)。

#### <a name="feature-comparison"></a>功能比较

| 功能 App Service | Service Fabric | 虚拟机 |
|---------|----------|----------|
| 接近即时的部署 | X | X | |
| 向上扩展到更大的计算机，无需重新部署 | X | X | |
| 实例共享内容和配置;无需重新部署或重新配置在缩放时 | X | X | |
| 多个部署环境 （生产，过渡） | X | X | |
| 自动操作系统更新管理 | X | | |
| 无缝 32/64 位平台之间切换 | X | | |
| 使用 Git、 FTP 部署代码 | X | | X |
| WebDeploy 使用部署代码 | X | | X |
| 使用 TFS 部署代码 | X | X | X |
| 主机 web 或 web 服务层的多层体系结构 | X | X | X |
| 访问 Service Bus、 存储、 SQL 数据库这样的 Azure 服务 | X | X | X |
| 安装任何自定义 MSI | | X | X |

## <a name="logical-processes"></a>逻辑进程

可以从应用程序的其余部分相互脱耦的单独逻辑进程可能被部署独立到 Azure 函数中的"无服务器"的方式。 Azure 函数允许你只需编写为给定的问题，而无需担心要运行它的应用程序或基础结构所需的代码。 你可以选择使用不同的编程语言，包括 C\#，F\#，Node.js、 Python 和 PHP，允许你手头选取任务最为高效的语言。 类似于大多数基于云的解决方案，你付费的时间内仅供使用，并且可以信任 Azure 函数，以根据需要向上扩展。

## <a name="data"></a>数据

Azure 提供了各种数据存储选项，因此你的应用程序可以使用适当的数据提供程序相关数据的。

有关事务的关系数据，Azure SQL 数据库是最佳选项。 对于高性能读取主要数据，Azure SQL 数据库支持的 Redis 缓存是一个不错的解决方案。

非结构化的 JSON 数据可以存储在 DocumentDB 设为的方式，从 SQL 数据库对 Blob 或 Azure 存储中的表的列多。 其中，DocumentDB 提供最佳查询功能，并且是大量的查询必须支持的基于 JSON 的文档的建议的选项。

Azure Service Bus 或 Azure 存储队列，可以使用用于安排应用程序行为的暂时性命令或基于事件的数据。 Azure 存储总线提供更大的灵活性，是以非普通消息传递服务内部或之间应用程序建议的服务。

## <a name="architecture-recommendations"></a>体系结构的建议

应用程序的要求应指明及其体系结构。 有许多不同的 Azure 服务可用，选择正确一项重要决策。 Microsoft 提供的参考体系结构，以帮助识别针对常见方案进行了优化的典型体系结构的库。 你可能绑定映射适合你的应用程序的要求，或在至少提供一个起始点参考体系结构。

图 11-2 显示的示例引用体系结构。 下图描述了优化用于营销 Sitecore 内容管理系统网站的建议体系结构方法。

![](./media/image11-2.png)

**图 11-2。** Sitecore 市场营销网站参考体系结构。

**引用 – Azure 托管的建议**

-   Azure 解决方案 Architectures\
    <https://azure.microsoft.com/solutions/architecture/>

-   Azure 开发人员 Guide\
    <https://azure.microsoft.com/campaigns/developer-guide/>

-   什么是 Azure App Service？ \
    <https://docs.microsoft.com/azure/app-service/app-service-value-prop-what-is>

-   Azure App Service、 虚拟机、 Service Fabric 和云服务比较 \
    <https://docs.microsoft.com/azure/app-service-web/choose-web-site-cloud-service-vm>

>[!div class="step-by-step"]
[Previous] (development-process-for-azure.md)
