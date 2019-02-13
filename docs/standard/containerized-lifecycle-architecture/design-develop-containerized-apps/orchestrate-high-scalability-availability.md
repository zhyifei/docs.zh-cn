---
title: 协调安排微服务和多容器应用程序，实现高可伸缩性和高可用性
description: 实际的生产应用程序必须部署和使用业务流程协调程序处理的运行状况、 工作负荷和所有容器的生命周期管理。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 749b613ac847c57eb993bff90b36f02a0b39477f
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221155"
---
# <a name="orchestrating-microservices-and-multicontainer-applications-for-high-scalability-and-availability"></a>安排微服务和多容器应用程序的高可伸缩性和可用性

如果应用程序基于微服务或只是跨多个容器拆分，则必须使用适用于生产就绪应用程序的业务流程协调程序。 如前所述，在基于微服务的方法中，每个微服务均拥有其模型和数据，如此从开发和部署的角度来看，它便是具有自主性。 但即使有更传统的应用程序，其中包含的多个服务 （如 SOA)，您还将具有多个容器或包含需要部署为分布式系统中的单个业务应用程序的服务。 这类系统是复杂，无法横向扩展和管理;因此，如果你想要拥有生产就绪且可缩放的多容器应用程序绝对需要业务流程协调程序。

图 4-6 说明了部署到多个微服务 （容器） 组成的应用程序的群集。

![](./media/image6.png)

图 4-6:容器群集

它看上去类似于逻辑方法。 但是，您怎样处理负载平衡、 路由和安排这些组合式应用程序？

Docker 命令行接口 (CLI) 满足需求的管理一台主机上的一个容器，但管理多个容器的更复杂的分布式应用程序的多个主机上部署时，这个过程很短。 在大多数情况下，您需要一个管理平台，将自动启动容器、 挂起，或需要时，关闭它们和理想情况下还控制对网络和数据存储等资源的访问。

如果不仅要管理个别容器或非常简单的组合式应用，还要进一步管理使用微服务的较大型企业应用程序，则必须转向业务流程和群集平台。

从体系结构和开发的角度看，你是否构建大，企业，基于微服务的应用程序，务必了解以下平台和产品的支持高级的方案：

-   **群集和业务流程协调程序** 当需要进行缩放的跨多个 Docker 主机的应用程序，如使用大型基于微服务的应用程序，很重要能够管理所有这些主机作为单个的群集抽象化基础平台的复杂性。 这就是容器群集和业务流程协调程序提供的内容。 业务流程协调程序的示例包括 Docker Swarm、 Mesosphere DC/OS、 Kubernetes （前三个可通过 Azure 容器服务） 和 Azure Service Fabric。

-   **计划程序** *计划*意味着管理员能够启动群集中的容器，以便它们还提供用户界面的功能。 群集计划程序具有多个职责：高效使用群集资源、设置用户提供的约束、有效负载均衡节点或主机间的容器，以及在提供高可用性的同时强力解决错误。

群集和计划程序的概念密切相关，因此不同供应商提供的产品通常具有这两套功能。 表 4-1 列出了最重要的平台和软件可供选择群集和计划程序。 这些群集通常是按 Azure 等公有云提供的。

表 4-1:适用于容器群集、业务流程和计划的软件平台

| 平台 | 描述 |
|---|---|
| Docker Swarm<br/> ![Docker Swarm 徽标](./media/image7.png) | Docker Swarm 为您提供了群集和计划 Docker 容器的功能。 通过使用 Swarm，可以将多个 Docker 主机转换味单个虚拟 Docker 主机。 客户端可以向 Swarm 发出 API 请求，在相同的方式与它们到主机，这意味着 Swarm 可以使其应用程序轻松地扩展到多个主机中。 <br /><br /> Docker Swarm 是来自 Docker 公司 的产品。 <br /><br /> Docker v1.12 或更高版本可以运行本机内置 Swarm 模式。 |
| Mesosphere DC/OS<br/>![Mesosphere DC/OS 徽标](./media/image8.png) |  Mesosphere Enterprise DC/OS（基于 Apache Mesos）是用于运行容器和分布式应用程序的生产就绪平台。 <br /><br /> DC/OS 的工作方式是提取群集中的可用资源集合，并使这些资源可用于在其上构建的组件。 Marathon 通常用作与 DC/OS 集成的计划程序。 |
| Google Kubernetes<br />![Google Kubernetes 徽标](./media/image9.png) | Kubernetes 是一款开源产品，提供各种功能，从群集基础结构和容器计划到安排功能均涵盖在内。 使用它，可以跨主机群集自动部署、 缩放和操作的应用程序容器。 <br /><br /> Kubernetes 提供以容器为中心的基础结构，将应用程序容器分组为逻辑单元，以便管理和发现。 |
| Azure Service Fabric<br />![Azure Service Fabric 徽标](./media/image10.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) 是用于生成应用程序的 Microsoft 微服务平台。 它是服务的[业务流程协调程序](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction)，可创建计算机群集。 默认情况下，Service Fabric 部署和激活这些服务作为进程，但 Service Fabric 可部署 Docker 容器映像中的服务。 更重要的是，您可以使用同一个应用程序中的容器中的服务中混合进程中的服务。 <br /><br /> 截至 2017 年 5 月，Service Fabric 支持为 Docker 容器部署服务的功能处于预览状态。 <br /><br /> 你可以开发在许多方面，从使用 Service Fabric 服务[Service Fabric 编程模型](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework)部署[来宾可执行文件](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-existing-app)以及容器。 Service Fabric 支持规定性应用程序模型，如同[有状态服务](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction)并[Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)。

## <a name="using-container-based-orchestrators-in-azure"></a>在 Azure 中使用基于容器的业务流程协调程序

多个云供应商提供 Docker 容器支持以及 Docker 群集和业务流程支持，包括 Azure、 Amazon EC2 容器服务和 Google 容器引擎。 下一节中所述，azure 将提供 Docker 群集和业务流程协调程序支持通过 Azure 容器服务。

另一种选择是使用 Azure Service Fabric，它还支持基于 Linux 和 Windows 容器的 Docker。 在 Azure 或任何其他云上运行 Service Fabric，以及[的本地](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)。

## <a name="using-azure-container-service"></a>使用 Azure 容器服务

Docker 群集汇集多个 Docker 主机，并将它们作为单个虚拟 Docker 主机公开，因此可以将多个容器部署到群集。 该群集将处理可伸缩性和运行状况等所有复杂的管理任务。 图 4-7 表示组成应用程序的 Docker 群集如何映射到容器服务。

容器服务提供了一种简化创建、 配置和管理预配置为运行容器化应用程序的 Vm 的群集的方法。 使用热门开源计划和业务流程工具的优化的配置，容器服务使你能够使用现有技能或大量不断增长的社区专业知识部署和管理基于容器上绘制在 Azure 中的应用程序。

容器服务优化了专门针对 Azure 常用 Docker 聚类分析的开源工具和技术的配置。 可以获得一个开放的解决方案，该解决方案为容器和应用程序配置提供可移植性。 用户选择主机的大小和数量以及业务流程协调程序工具，然后容器服务可处理其他操作。

容器服务使用的 Docker 映像以确保应用程序容器完全可移植。 它支持所选的开源业务流程平台，如 DC/OS、 Kubernetes 和 Docker Swarm，以确保这些应用程序可以扩展到数千或甚至数万个容器。

借助 Azure 容器服务，您可以利用 Azure 的企业级功能的同时仍维护应用程序可移植性，包括业务流程层。

![](./media/image11.png)

图 4-7:Azure 容器服务中的群集选项

如所示图 4-8，容器服务是只是为了部署 DC/OS、 Kubernetes 或 Docker Swarm，Azure 提供的基础结构，但它不实现任何其他业务流程协调程序。 因此，容器服务是不业务流程协调程序，在这种情况下;它是利用现有开放源业务流程协调程序用于容器的基础结构。

![](./media/image12.png)

图 4-8:在容器服务中的业务流程协调程序

从使用情况的角度，容器服务的目标是通过使用常用的开源工具和技术提供容器托管环境。 为此，它为选择的业务流程协调程序公开标准 API 终结点。 通过使用这些终结点，可以使用可与这些终结点通信的任何软件。 例如，对于 Docker Swarm 终结点，您可能选择使用 Docker CLI。 对于 DC/OS，可选择使用 DC/OS CLI。

### <a name="getting-started-with-container-service"></a>如何开始使用容器服务

若要开始使用容器服务，你将在 Azure 门户中的容器服务群集部署使用 Azure 资源管理器模板或[CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)。 可用模板包括 [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm)、[Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) 和 [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos)。 可以修改快速入门模板以包括其他或高级 Azure 配置。

**详细信息** 若要详细了解如何部署容器服务群集，Azure 网站上的阅读[部署 Azure 容器服务群集](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment)。

作为 ACS 的一部分，默认安装的任何软件都不收费。 所有默认选项都通过开源软件实现。

容器服务是目前适用于标准 A、 D、 DS、 G 和 GS 系列 Linux Vm 在 Azure 中。 您仅支付你选择以及其他基础结构使用基础资源，如存储和网络的计算实例。 没有增量费用的容器服务本身。

### <a name="additional-resources"></a>其他资源

以下是在哪里可以找到其他信息的位置：

-   Docker 容器托管解决方案容器服务简介：  
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

Service Fabric 源于从提供的服务交付"盒子"产品，通常是单一式样式中，Microsoft 的转换。 构建和运营大型服务规模，如 Azure SQL 数据库、 Azure Document DB、 Azure 服务总线或 Cortana 的后端的体验成就了 Service Fabric。 越来越多的服务采用了该平台，它随着时间不断演变。 Service Fabric 不仅需要在 Azure 上运行，还需在独立的 Windows Server 部署上运行，这一点十分重要。

Service Fabric 旨在解决构建和运行服务和有效地利用基础结构资源，以便团队可以解决业务问题使用微服务方法的困难的问题。

Service Fabric 提供了两个宽广区域，可帮助构建使用微服务方法的应用程序：

-   提供各种系统服务的平台，可用于部署、缩放、升级、检测、重新启动失败的服务、发现服务位置、管理状态和监视健康状况。 这些系统服务实际上提供了多种前面所述的微服务的特征。

-   有助于将应用程序构建为微服务的编程 API 或框架：[Reliable Actors 和 Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework)。 当然，开发人员可选择任何代码来构建微服务，但这些 API 可简化构建工作，且更深入地与平台集成。 这样开发人员就可获得运行状况信息和诊断信息，也可利用可靠的状态管理。

Service Fabric 未指定服务构建方式，开发人员可使用任何技术。 但它内置了编程 API，可简化微服务的构建。

图 4-9 演示如何创建和运行 Service Fabric 中的微服务，作为简单进程也作为 Docker 容器。 此外还可在同一 Service Fabric 群集中混合基于容器的微服务与基于进程的微服务。

![](./media/image13.png)

图 4-9:在 Azure Service Fabric 中将微服务部署为进程或容器

基于 Linux 和 Windows 主机上的 Service Fabric 群集可运行 Docker Linux 容器和 Windows 容器。

**详细信息** 有关 Service Fabric 中容器支持的最新信息，Azure 网站上阅读[Service Fabric 和容器](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)。

Service Fabric 是一个平台，可以使用该定义的不同逻辑体系结构 （业务微服务或界定的上下文） 与物理实现一个很好示例。 例如，如果您实现[有状态 Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction)中[Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview)，在下一部分介绍"[无状态与有状态微服务](#stateless-versus-stateful-microservices)，"有多个物理服务具有一个业务微服务概念。

如图 4-10，并从逻辑/业务微服务角度看，实现 Service Fabric 有状态可靠服务时的考虑中所示，您通常需要实现两个层的服务。 第一个是后端有状态可靠服务，用于处理多个分区。 第二个是前端服务或网关服务，负责跨多个分区或有状态服务实例的路由和数据聚合。 该网关服务还使用重试循环访问后端服务与 Service Fabric 配合使用可以处理客户端的通信[反向代理](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy)。

![](./media/image14.png)

图 4-10:使用 Service Fabric 中的多个有状态和无状态服务的业务微服务

在任何情况下，使用 Service Fabric 有状态可靠服务时，都伴有逻辑或业务微服务（边界上下文），二者通常由多个物理服务组成。 每个这些、 网关服务和分区服务就可以实现为 ASP.NET Web API 服务，图 4-10 所示。

在 Service Fabric 中，可对成组服务进行分组，并将其部署为 [Service Fabric 应用程序](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model)，即业务流程协调程序或群集的打包和部署单元。 因此，Service Fabric 应用程序无法映射到该自治业务和逻辑微服务边界或界定的上下文，以及。

### <a name="service-fabric-and-containers"></a>Service Fabric 和容器

有关 Service Fabric 中的容器，您还可以部署在 Service Fabric 群集中的容器映像中的服务。 图 4-11 说明了该大多数情况下将每个服务只有一个容器。

![](./media/image15.png)

图 4-11:Service Fabric 中具有多个服务（容器）的业务微服务

但是，Service Fabric 中也可能有所谓的“sidecar”容器（两个容器必须一同部署为逻辑服务）。 重要的是，业务微服务是多个内聚元素的逻辑边界。 在许多情况下，可能会具有单个数据模型的单个服务，但在某些其他情况下可能具有多个物理服务，以及。

截至本文 (2017 年 4 月)，在 Service Fabric 中不能部署在容器上 SF 可靠有状态服务，你可以部署仅来宾容器、 无状态服务或在容器中的执行组件服务。 但请注意，可以混合进程中的服务和在同一 Service Fabric 应用程序的容器服务中图 4-12 所示。

![](./media/image16.png)

图 4 到 12 个：映射到含容器和有状态服务的 Service Fabric 应用程序的业务微服务

对支持还正在不同，具体取决于是否正在使用 Docker 容器在 Linux 或 Windows 容器上。 将在即将发布的版本中展开对 Service Fabric 中容器的支持。 有关在 Azure 网站上的 Service Fabric 中容器支持的最新新闻阅读[Service Fabric 和容器](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)。

## <a name="stateless-versus-stateful-microservices"></a>无状态微服务与有状态微服务

如前所述，每个微服务（逻辑边界上下文）必须有其域模型（数据和逻辑）。 对于无状态微服务，数据库将位于外部，采用 SQL Server 等关系选项或 MongoDB 或 Azure DocumentDB 等 NoSQL 选项。

但是，服务本身也可以是有状态的这意味着数据驻留在微服务。 此数据可能存在不只是在同一服务器上，但在微服务进程中，在内存中，并保留在驱动器上，复制到其他节点。 图 4-13 显示了不同的方法。

![](./media/image17.png)

图 4 月 13 日：无状态微服务与有状态微服务

无状态方法是完全有效，并更轻松地实现比有状态微服务，因为方法是类似于传统的已知模式。 但无状态微服务会在进程和数据源之间产生延迟。 若要试图增加缓存和队列来提高性能，该方法会涉及更多要移动的内容。 结果就是，最终会得到具有许多层级的复杂体系结构。

与此相反，[有状态微服务](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis)可以 excel 在高级方案中，因为域逻辑和数据之间没有延迟。 处理繁重数据、 游戏后端、 数据库即服务和其他所有受益于有状态服务，可更快地访问本地状态的低延迟方案。

无状态服务和有状态服务相辅相成。 例如，有状态服务可拆分为多个分区。 若要访问这些分区，可能需要无状态服务充当网关服务，该服务了解如何基于分区键处理每个分区。

有状态服务确实存在缺点。 它们会施加的复杂性，允许他们向外扩展。完成跨有状态微服务和数据分区复制数据等任务时，必须解决通常由外部数据库系统实现的功能。 但是，这是一个业务流程协调程序喜欢其中方面[Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture)使用其[有状态 reliable services](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis)最多可以帮助 — 通过简化的开发和有状态的生命周期微服务使用[Reliable Services API](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections)并[Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)。

其他允许有状态微服务，支持 Actor 模式，提高业务逻辑和数据之间的容错、缩短延迟的微服务框架有来自 Microsoft Research 的 Microsoft [Orleans](https://github.com/dotnet/orleans) 和 [Akka.NET](https://getakka.net/)。 这两个框架目前都在改善其对 Docker 的支持。

请注意，Docker 容器本身是无状态的。 若要实现有状态服务，需到前面提到的某个级别更高的规范框架。 但是，在撰写本文时，Service Fabric 中的有状态服务不支持作为容器，只能用作普通微服务。 在容器中的 reliable services 支持将在即将推出的 Service Fabric 版本中可用。

>[!div class="step-by-step"]
>[上一页](soa-applications.md)
>[下一页](deploy-azure-kubernetes-service.md)
