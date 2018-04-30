---
title: 协调微服务和以高可伸缩性和可用性的 multicontainer 应用程序
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 59c03755bebce98e018f56fc7213b00a0d3eae38
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="orchestrating-microservices-and-multicontainer-applications-for-high-scalability-and-availability"></a>协调微服务和以高可伸缩性和可用性的 multicontainer 应用程序

如果应用程序基于微服务或只是跨多个容器拆分，则必须使用适用于生产就绪应用程序的业务流程协调程序。 如前所述，在基于微服务的方法中，每个微服务均拥有其模型和数据，如此从开发和部署的角度来看，它便是具有自主性。 但即使你有了更传统的应用程序，其中包含多个服务 （如 SOA)，你还将具有多个容器或服务组成的单个业务应用程序需要作为分布式系统进行部署。 这些类型的系统很复杂，来向外扩展和管理;因此，如果你想要有一个生产就绪且可伸缩的 multicontainer 应用程序绝对需要编排器。

图 4-6 显示了为群集的多个微服务 （容器） 组成的应用程序的部署。

![](./media/image6.png)

图 4-6： 容器的群集

它看上去类似于逻辑方法。 但是，如何在处理负载平衡、 路由和协调这些组合的应用程序？

Docker 命令行界面 (CLI) 满足需要的管理一个主机上的一个容器，但管理更复杂的分布式应用程序的多个主机上部署的多个容器时，这个过程很短。 在大多数情况下，你需要一个管理平台，将自动启动容器挂起，或在需要时关闭它们，理想情况下还控制它们访问网络和数据存储空间等资源的方式。

如果不仅要管理个别容器或非常简单的组合式应用，还要进一步管理使用微服务的较大型企业应用程序，则必须转向业务流程和群集平台。

从体系结构和开发角度来看，如果要构建大型，企业中，基于微服务的应用程序，务必了解以下平台和产品的支持高级的方案：

-   **群集和 orchestrators** 需要进行缩放-出跨多个 Docker 主机的应用程序，如大型基于微服务的应用程序，与至关重要要能够作为一个群集由管理所有这些主机提取基础平台的复杂性。 这就是容器群集和业务流程协调程序所提供的功能。 Orchestrators 的示例包括 Docker Swarm、 Mesosphere DC/OS、 Kubernetes （前三个可通过 Azure 容器服务） 和 Azure Service Fabric。

-   **计划程序** *计划*意味着能够使用的管理员才能启动群集中的容器，以便它们还提供用户界面的功能。 一个群集计划程序有多个职责： 以有效地使用群集的资源、 设置用户，有效地跨节点或主机的负载平衡容器提供的约束以及要同时提供高可靠针对错误可用性。

群集和计划程序的概念密切相关，因此不同供应商提供的产品通常具有这两套功能。 最重要的平台和你有针对群集和计划程序的软件选择，将列出表 4-1。 这些群集通常是按如 Azure 公有云提供的。

表 4-1： 群集的容器、 协调和计划的软件平台

| 平台 | 描述 |
|---|---|
| Docker Swarm<br/> ![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image7.png) | Docker Swarm 提供群集和计划 Docker 容器的功能。 通过使用 Swarm，可以将多个 Docker 主机转换味单个虚拟 Docker 主机。 客户端可以进行 API 请求到 Swarm 中与它们执行的操作主机，这意味着，Swarm 轻松地让应用程序扩展到多个主机的方式相同。 <br /><br /> Docker Swarm 是来自 Docker 公司 的产品。 <br /><br /> Docker v1.12 或更高版本可以运行本机内置 Swarm 模式。 |
| Mesosphere DC/OS<br/>![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-styled.png](./media/image8.png) |  Mesosphere Enterprise DC/OS（基于 Apache Mesos）是用于运行容器和分布式应用程序的生产就绪平台。 <br /><br /> DC/OS 的工作方式是提取群集中的可用资源集合，并使这些资源可用于在其上构建的组件。 Marathon 通常用作与 DC/OS 集成的计划程序。 |
| Google Kubernetes<br />![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image9.png) | Kubernetes 是一款开源产品，提供各种功能，从群集基础结构和容器计划到安排功能均涵盖在内。 通过它，你可以跨主机群集自动执行部署、 缩放和操作的应用程序容器。 <br /><br /> Kubernetes 提供以容器为中心的基础结构，将应用程序容器分组为逻辑单元，以便管理和发现。 |
| Azure Service Fabric<br />![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image10.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) 是用于生成应用程序的 Microsoft 微服务平台。 它是服务的[业务流程协调程序](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction)，可创建计算机群集。 默认情况下，Service Fabric 部署并激活服务作为进程，但 Service Fabric 可以部署在 Docker 容器映像中的服务。 更重要的是，你可以与在同一应用程序的容器中的服务中混合进程中的服务。 <br /><br /> 截至自 2017 年 1 月，Service Fabric 支持 Docker 容器作为部署服务的功能处于预览状态。 <br /><br /> 你可以开发在许多方面，与使用的 Service Fabric 服务[编程模型的 Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework)部署[来宾可执行文件](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-existing-app)以及容器。 Service Fabric 支持说明性的应用程序模型，如同[有状态服务](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction)和[Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)。

## <a name="using-container-based-orchestrators-in-azure"></a>在 Azure 中使用容器基于 orchestrators

多个云供应商都提供 Docker 容器支持以及 Docker 群集和业务流程支持，包括 Azure、 Amazon EC2 容器服务和 Google 容器引擎。 在下一部分中所述，azure 将提供 Docker 群集和 orchestrator 支持通过 Azure 容器服务。

另一个选项是使用 Azure Service Fabric，还支持基于 Linux 和 Windows 容器的 Docker。 Service Fabric 在 Azure 或其他云上运行，以及[本地](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)。

## <a name="using-azure-container-service"></a>使用 Azure 容器服务

Docker 群集汇集多个 Docker 主机，并将它们作为单个虚拟 Docker 主机公开，因此可以将多个容器部署到群集。 群集将处理如可扩展性和运行状况的所有复杂的管理管道。 图 4-7 表示由应用程序的 Docker 群集如何映射到容器服务。

容器服务提供的方法来简化创建、 配置和管理已预先配置为运行容器化应用程序的 Vm 的群集。 使用的优化的配置的受欢迎的开源计划和协调工具，容器服务使你能够运用现有技能，使用或在不断增长的社区专业知识来部署和管理容器基于体上绘制Azure 中的应用程序。

容器服务优化了针对 Azure 的常用 Docker 聚类分析的开源工具和技术配置。 可以获得一个开放的解决方案，该解决方案为容器和应用程序配置提供可移植性。 用户选择主机的大小和数量以及业务流程协调程序工具，然后容器服务可处理其他操作。

容器服务使用 Docker 映像以确保你的应用程序容器是完全可移植。 它支持你选择的 DC/OS、 Kubernetes，和 Docker Swarm 之类的开放源代码 orchestration 平台，以确保这些应用程序可以扩展到数千或甚至数万个容器。

使用 Azure 容器服务，你可以利用 Azure 的企业级功能的同时，仍保持应用程序可移植性，包括在业务流程层。

![](./media/image11.png)

图 4-7： 群集中 Azure 容器服务的选项

所示在图 4-8 中，容器服务都只是为了部署 DC/OS、 Kubernetes，或 Docker Swarm，提供 Azure 的基础结构，但它不实现任何其他 orchestrator。 因此，容器服务是不编排器，在这种情况下;它是利用现有的开源 orchestrators 的容器的基础结构。

![](./media/image12.png)

图 4-8: Orchestrators 中容器服务

从使用情况的角度，容器服务的目标是通过使用常用的开源工具和技术提供容器的宿主环境。 为此，它为选择的业务流程协调程序公开标准 API 终结点。 通过使用这些终结点，你可以使用可与这些终结点通信的任何软件。 例如，对于 Docker Swarm 终结点，你可以选择使用 Docker CLI。 对于 DC/OS，可选择使用 DC/OS CLI。

### <a name="getting-started-with-container-service"></a>开始使用容器服务

若要开始使用容器服务，你部署一个容器服务群集在 Azure 门户中使用 Azure 资源管理器模板或[CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)。 可用模板包括 [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm)、[Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) 和 [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos)。 你可以修改以包括其他或高级 Azure 配置的快速入门模板。

**详细信息** 若要了解有关部署容器服务群集，在 Azure 网站上，阅读[部署 Azure 容器服务群集](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment)。

作为 ACS 的一部分，默认安装的任何软件都不收费。 所有默认选项都通过开源软件实现。

容器服务是当前可用于标准 A、 D、 DS、 G 和 GS 系列 Azure 中的 Linux Vm。 你仅收取你选择以及其他基础基础结构占用的资源，例如存储和网络的计算实例。 没有增量费用是容器服务本身。

### <a name="additional-resources"></a>其他资源

以下是在哪里可以找到其他信息的位置：

-   托管使用容器服务解决方案的 Docker 容器简介：  
    https://docs.microsoft.com/azure/container-service/kubernetes/container-service-intro-kubernetes>

-   Docker Swarm 概述：  
    <https://docs.docker.com/swarm/overview/>

-   Swarm 模式概述：  
    <https://docs.docker.com/engine/swarm/>

-   Mesosphere DC/OS 概述：    
    <https://docs.mesosphere.com/1.7/overview/>

-   Kubernetes （官方站点）：  
    <https://kubernetes.io/>

## <a name="using-service-fabric"></a>使用 Service Fabric

Service Fabric 产生从交付服务交付"框"产品不同，后者是通常整体样式中，Microsoft 的转换。 构建并运行大型大规模情况下，如 Azure SQL 数据库、 Azure 文档数据库、 Azure Service Bus 或 Cortana 的后端服务的体验调整 Service Fabric。 越来越多的服务采用了该平台，它随着时间不断演变。 Service Fabric 不仅需要在 Azure 上运行，还需在独立的 Windows Server 部署上运行，这一点十分重要。

Service Fabric 旨在解决的困难问题的生成和运行服务和有效地利用基础结构资源，以便团队可以解决业务问题使用微服务方法。

Service Fabric 提供了两个宽广区域，可帮助构建使用微服务方法的应用程序：

-   提供各种系统服务的平台，可用于部署、缩放、升级、检测、重新启动失败的服务、发现服务位置、管理状态和监视健康状况。 实际上，这些系统服务提供的许多微服务前面所述的特性。

-   有助于将应用程序构建为微服务的编程 API 或框架：[Reliable Actors 和 Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework)。 当然，开发人员可选择任何代码来构建微服务，但这些 API 可简化构建工作，且更深入地与平台集成。 这样开发人员就可获得运行状况信息和诊断信息，也可利用可靠的状态管理。

Service Fabric 未指定服务构建方式，开发人员可使用任何技术。 但它内置了编程 API，可简化微服务的构建。

图 4-9 演示如何创建和运行在 Service Fabric 微服务，作为简单的流程或 Docker 容器。 此外还可在同一 Service Fabric 群集中混合基于容器的微服务与基于进程的微服务。

![](./media/image13.png)

图 4-9： 部署微服务作为流程或 Azure Service Fabric 中的容器

Docker Linux 容器和 Windows 容器，可以运行 Linux 和 Windows 的主机上基于的 Service Fabric 群集。

**详细信息** 有关 Service Fabric 中的容器支持在 Azure 网站上的最新信息读取[Service Fabric 和容器](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)。

Service Fabric 是与你可以定义另一个逻辑体系结构 （业务微服务或绑定上下文） 的物理实现比平台的一个很好示例。 例如，如果你实现[有状态 Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction)中[Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview)，这在下一步的部分中，引入"[与有状态微服务Stateless](#stateless-versus-stateful-microservices)，"具有与多个物理服务业务微服务概念。

如图 4-10 和从逻辑/业务 microservice 角度看，在实现 Service Fabric 有状态 Reliable Service 时的考虑中所示，你通常需要实现两个级别的服务。 第一个是后端有状态 reliable service，用于处理多个分区。 第二层是前端服务或网关服务，负责跨多个分区或有状态服务实例进行路由，聚合数据。 该网关服务还使用重试循环访问后端服务与 Service Fabric 结合使用可以处理客户端通信[反向代理](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy)。

![](./media/image14.png)

图 4-10： 业务微服务与 Service Fabric 中的几个有状态和无状态服务

在任何情况下，使用 Service Fabric 有状态可靠服务时，都伴有逻辑或业务微服务（边界上下文），二者通常由多个物理服务组成。 每个它们、 网关服务和分区服务无法作为 ASP.NET Web API 服务，在图 4-10 中所示实现。

在 Service Fabric 中，可对成组服务进行分组，并将其部署为 [Service Fabric 应用程序](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model)，即业务流程协调程序或群集的打包和部署单元。 因此，Service Fabric 应用程序可以映射到此自治业务和逻辑 microservice 边界或绑定上下文中，以及。

### <a name="service-fabric-and-containers"></a>Service Fabric 和容器

关于在 Service Fabric 中的容器，你还可以部署在 Service Fabric 群集中的容器映像中的服务。 图 4-11 列出了该大多数情况下将每个服务只有一个容器。

![](./media/image15.png)

图 4-11： 业务微服务与 Service Fabric 中的多个服务 （容器）

但是，所谓的"实现 sidecar"容器 （必须在作为逻辑服务的一部分一起部署的两个容器） 也是 Service Fabric 中可能的。 重要的是，业务微服务是多个内聚元素的逻辑边界。 在许多情况下，它可能与单个数据模型中，单个服务，但在某些其他情况下可能具有物理多个服务，以及。

从此编写 (自 2017 年 4 月)，开始在 Service Fabric 中不能将部署在容器上 SF 可靠有状态服务-你可以部署来宾容器、 无状态服务或在容器中的参与者服务。 但请注意，可以混合在同一 Service Fabric 应用程序的容器中进程中的服务和服务在图 4-12 中所示。

![](./media/image16.png)

图 4-12： 业务微服务映射到具有容器和有状态服务的 Service Fabric 应用程序

支持也是根据你使用 Docker 容器在 Linux 或 Windows 容器上不同的。 将在即将发布的版本中展开对 Service Fabric 中的容器的支持。 有关在 Service Fabric 中，在 Azure 网站上的容器支持的最新新闻读取[Service Fabric 和容器](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)。

## <a name="stateless-versus-stateful-microservices"></a>无状态微服务与有状态微服务

如前所述，每个微服务（逻辑边界上下文）必须有其域模型（数据和逻辑）。 对于无状态微服务，数据库就会外部，采用类似于 SQL Server 的关系选项或 MongoDB 或 Azure DocumentDB 等 NoSQL 选项。

但服务本身也可以是有状态的这意味着数据位于内微服务。 此数据可能存在不只是在同一服务器上，但在微服务过程中，在内存中，并保留在驱动器复制到其他节点。 图 4-13 显示不同的方法。

![](./media/image17.png)

图 4-13： 有状态微服务与无状态

无状态的方法完全有效，且可以更轻松地实现比有状态微服务，因为这种方法是类似于传统和已知模式。 但无状态微服务会在进程和数据源之间产生延迟。 若要试图增加缓存和队列来提高性能，该方法会涉及更多要移动的内容。 结果就是，最终会得到具有许多层级的复杂体系结构。

与此相反，[有状态微服务](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis)可以 excel 高级方案中，因为没有在域逻辑和数据之间的滞后时间。 大量的数据处理，游戏后端、 数据库作为一种服务，以及其他所有受益于有状态服务，以便提供更快地访问本地状态的低延迟方案。

无状态服务和有状态服务相辅相成。 例如，有状态服务无法拆分为多个分区。 若要访问这些分区，可能需要无状态服务充当网关服务，该服务了解如何基于分区键处理每个分区。

有状态服务确实存在缺点。 施加的复杂性，允许他们向外扩展。完成跨有状态微服务和数据分区复制数据等任务时，必须解决通常由外部数据库系统实现的功能。 但是，这是一个其中 orchestrator 喜欢方面[Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture)与其[有状态 reliable services](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis)有助于最大 — 通过简化开发和有状态的生命周期微服务使用[Reliable Services API](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections)和[Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)。

其他允许有状态微服务，支持 Actor 模式，提高业务逻辑和数据之间的容错、缩短延迟的微服务框架有来自 Microsoft Research 的 Microsoft [Orleans](https://github.com/dotnet/orleans) 和 [Akka.NET](https://getakka.net/)。 这两个框架目前都在改善其对 Docker 的支持。

请注意，Docker 容器本身是无状态的。 若要实现有状态服务，需到前面提到的某个级别更高的规范框架。 但是，截至撰写本文时，Service Fabric 中的有状态服务不支持作为容器，仅为纯微服务。 将会在即将发布版本的 Service Fabric 提供容器中的可靠的服务支持。


>[!div class="step-by-step"]
[以前](soa-applications.md) [下一步] (docker-应用程序的开发-environment.md)
