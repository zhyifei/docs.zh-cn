---
title: "使用 Azure Service Fabric"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |使用 Azure Service Fabric"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: aa15f9cf9bc60e9e70607da921f2ce2c75e39ec2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="using-azure-service-fabric"></a>使用 Azure Service Fabric

Azure Service Fabric 产生从将框产品不同，后者是通常整体样式，传送到提供服务的 Microsoft 的转换。 构建并运行大型大规模情况下，如 Azure SQL 数据库、 Azure Cosmos DB、 Azure Service Bus 或 Cortana 的后端服务的体验调整 Service Fabric。 随着越来越多的服务采用它，通过逐步发展平台。 重要的是，Service Fabric 必须在运行不仅在 Azure 中，还在独立 Windows 服务器部署。

Service Fabric 的目的是为了解决难题的生成和运行服务并有效地，利用基础结构资源，以便团队可以解决业务问题使用微服务方法。

Service Fabric 提供了两个广泛的区域，可帮助你构建的应用程序使用微服务方法：

-   提供用于部署、 缩放、 升级、 检测，并重新启动失败的服务，发现服务位置、 管理状态，和监视运行状况的系统服务的平台。 实际上，这些系统服务启用的许多微服务前面所述的特性。

-   编程 Api 或框架，可帮助你构建微服务的应用程序： [reliable actors 和 reliable services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework)。 当然，你可以选择任何代码，以创建你的 microservice，这些 Api 使您的工作更简单，但他们与平台级别更深入地集成。 这样就可以运行状况和诊断信息，也可以利用可靠状态管理。

Service Fabric 是不可知方面如何生成你的服务，并且可以使用任何技术。 但是，它提供内置的编程 Api，使其更轻松地生成微服务。

如所示在图 4-26 日，你可以创建和运行在 Service Fabric 微服务，作为简单的流程或 Docker 容器。 还有可能混合使用与过程基于同一 Service Fabric 群集中的微服务容器基于微服务。

![](./media/image30.png)

**图 4-26**。 部署微服务作为流程或 Azure Service Fabric 中的容器

基于 Linux 和 Windows 的主机上的 Service Fabric 群集可以分别运行 Docker Linux 容器和 Windows 容器。

有关 Azure Service Fabric 中的容器支持的最新信息，请参阅[Service Fabric 和容器](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)。

Service Fabric 是一个平台，一个好例子，你可以在其中定义另一个逻辑体系结构 （业务微服务或绑定上下文） 中引入的物理实现比[而不是物理的逻辑体系结构体系结构](#logical-architecture-versus-physical-architecture)部分。 例如，如果你实现[有状态 Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction)中[Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview)，其中的部分中引入[与有状态微服务 Stateless](#stateless-versus-stateful-microservices)更高版本，你可以具有与多个物理服务业务微服务概念。

如图 4-27 和从逻辑/业务 microservice 角度看，在实现 Service Fabric 有状态 Reliable Service 时的考虑中所示，你通常需要实现两个级别的服务。 第一个是后端有状态 reliable service，用于处理 （每个分区是一个有状态服务） 的多个分区。 第二个是指前端服务或网关服务，负责跨多个分区或有状态服务实例的路由和数据聚合。 该网关服务还使用重试循环访问后端服务可以处理客户端通信。
如果实现自定义服务或你也可以使用全新的 Service Fabric 的 alternatevely，称为网关服务[反向代理服务](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy)。

![](./media/image31.png)

**图 4-27**。 与几个有状态服务实例和自定义网关前端的业务微服务

在任何情况下，当你使用 Service Fabric 有状态 Reliable Services 时，还必须由通常多个物理服务组成的逻辑或业务 microservice （界定上下文）。 每个它们、 网关服务和分区服务无法作为 ASP.NET Web API 服务，在图 4-26 中所示实现。

可在 Service Fabric 中，组和部署的服务作为组[Service Fabric 应用程序](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model)，即打包和部署 orchestrator 或群集的单位。 因此，Service Fabric 应用程序可以映射到此自治业务和逻辑 microservice 边界或绑定上下文中，同样，以便可以自主部署这些服务。

## <a name="service-fabric-and-containers"></a>Service Fabric 和容器

关于在 Service Fabric 中的容器，也可以部署在 Service Fabric 群集中的容器映像中的服务。 如图 4-28 所示，大多数情况下将仅有一个容器，每个服务。

![](./media/image32.png)

**图 4-28**。 业务微服务与 Service Fabric 中的多个服务 （容器）

但是，所谓的"实现 sidecar"容器 （必须在作为逻辑服务的一部分一起部署的两个容器） 也是 Service Fabric 中可能的。 重要的是业务微服务是在多个凝聚力元素周围的逻辑边界。 在许多情况下，它可能是单个服务具有单个数据模型，但在某些其他情况下，你可能必须物理多个服务。

截至中旬 2017年在 Service Fabric 中不能将部署在容器上 SF 可靠有状态服务-你可以仅部署无状态服务和容器中的参与者服务。 但请注意，可以混合在同一 Service Fabric 应用程序的容器中进程中的服务和服务在图 4-29 中所示。

![](./media/image33.png)

**图 4-29 个**。 映射到具有容器和有状态服务的 Service Fabric 应用程序的业务微服务

有关 Azure Service Fabric 中的容器支持的详细信息，请参阅[Service Fabric 和容器](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)。

## <a name="stateless-versus-stateful-microservices"></a>与有状态微服务无状态

如前所述，每个微服务 （逻辑绑定上下文） 必须拥有其域模型 （数据和逻辑）。 对于无状态微服务，数据库就会外部，采用类似于 SQL Server 的关系选项或 NoSQL 选项，如 MongoDB 或 Azure Cosmos DB。

但服务本身也可以是有状态 Service Fabric 中，这意味着数据位于内微服务中。 此数据可能存在不只是在同一服务器上，但在微服务过程中，在内存中和在硬盘驱动器上保留和复制到其他节点。 图 4-30 显示不同的方法。

![](./media/image34.png)

**图 4-30**。 与有状态微服务无状态

无状态的方法完全有效，且可以更轻松地实现都比有状态微服务，因为这种方法是类似于传统和已知模式。 但无状态微服务施加的进程和数据源之间的延迟。 当你尝试通过其他缓存和队列提高性能时，它们还会涉及更移动片段。 结果是，你可以得到复杂的体系结构具有太多层。

与此相反，[有状态微服务](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis)可以在高级方案中，excel，因为没有在域逻辑和数据之间的滞后时间。 大量的数据处理，返回游戏结束，数据库作为一种服务，并受益于有状态服务，启用更快的访问权限的本地状态的所有其他低延迟方案。

无状态和有状态服务是补充。 例如，你可以在正确的图中，有状态服务，无法拆分为多个分区看到图 4-30。 若要访问这些分区，可能需要充当一个知道如何解决每个分区基于分区键的网关服务的无状态服务。

有状态服务有缺点。 施加的横向扩展允许的复杂性。跨有状态微服务和分区的数据，通常会由外部数据库系统实现的功能必须解决的任务，例如数据复制。 但是，这是一个其中 orchestrator 喜欢方面[Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture)与其[有状态 reliable services](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis)有助于最大 — 通过简化开发和有状态的生命周期微服务使用[Reliable Services API](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections)和[Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)。

允许有状态服务，支持 Actor 模式，并可提高程度的容错和业务逻辑和数据之间的延迟其他微服务框架是 Microsoft[奥尔良](https://github.com/dotnet/orleans)，请从 Microsoft Research [Akka.NET](http://getakka.net/)。 这两种框架当前改善它们对 Docker 的支持。

请注意，Docker 容器本身无状态。 如果你想要实现一个有状态服务，你需要一个前文所述的其他说明性和较高级别的框架。 

>[!div class="step-by-step"]
[以前](scalable-available-multi-container-microservice-applications.md) [下一步] (.../docker-application-development-process/index.md)
