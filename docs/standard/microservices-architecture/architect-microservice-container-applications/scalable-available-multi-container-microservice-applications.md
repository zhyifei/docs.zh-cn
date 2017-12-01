---
title: "协调微服务和多容器应用程序的高可伸缩性和可用性"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |协调微服务和多容器应用程序的高可伸缩性和可用性"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ec33901a0ddc9e5b58263440b0e4399e687c6904
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>协调微服务和多容器应用程序的高可伸缩性和可用性

如果你的应用程序是基于微服务或只需将拆分到多个容器，对生产就绪应用程序使用 orchestrators 就至关重要。 因为以前，在基于微服务构成的方法中，引入了每个微服务拥有的模型和数据，以便将成为自治的开发和部署的角度。 但即使你有了更传统的应用程序，其中包含多个服务 （如 SOA)，你还将具有多个容器或服务组成的单个业务应用程序需要作为分布式系统进行部署。 这些类型的系统很复杂，来向外扩展和管理;因此，如果你想要有一个生产就绪且可伸缩的多容器应用程序绝对需要编排器。

图 4-23 阐释了部署到多个微服务 （容器） 组成的应用程序的群集。

![](./media/image23.PNG)

**图 4-23**。 有个容器的群集

它看上去像逻辑的方法。 但是，如何为你处理负载平衡、 路由和协调这些组成应用程序？

单个 Docker 主机中的纯 Docker 引擎满足需要的管理一个主机上的单个映像实例，但管理更复杂的分布式应用程序的多个主机上部署的多个容器时，这个过程很短。 在大多数情况下，你需要一个管理平台，将自动启动容器，使用每个图像的多个实例的横向扩展容器挂起它们或在需要时关闭它们，理想情况下还控制访问资源，如网络和数据的方式存储。

以超出单个容器或非常简单的由应用程序和更接近微服务使用的大型企业应用程序的管理，你必须启用业务流程和群集平台。

从体系结构和开发角度来看，如果你正在构建的基于微服务应用程序，组成的大型企业务必了解以下平台和产品的支持高级的方案：

**群集和 orchestrators**。 当你需要横向扩展应用程序跨多个 Docker 主机，因为当大型基于微服务构成的应用程序，它是关键能够通过抽取基础平台的复杂性作为一个群集管理所有这些主机。 这就是容器群集和 orchestrators 的提供。 Orchestrators 的示例包括 Azure Service Fabric、 Kubernetes、 Docker Swarm 和 Mesosphere DC/OS。 最后三个开放源代码 orchestrators 是通过 Azure 容器服务的 Azure 中提供。

**计划程序**。 *计划*意味着能够使用的管理员才能启动群集中的容器，因此它们还提供 UI 的功能。 一个群集计划程序有多个职责： 以有效地使用群集的资源、 设置用户，有效地跨节点或主机的负载平衡容器提供的约束以及要同时提供高可靠针对错误可用性。

密切相关的群集，计划程序的概念，因此通常由不同供应商提供的产品提供的功能的两个集。 以下列表显示的最重要的平台和你有针对群集和计划程序的软件选择。 这些 orchestrators 通常是按如 Azure 公有云提供的。

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>对群集的容器、 编排和计划的软件平台

Kubernetes

![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image24.png)

> Kubernetes 是一种开放源代码产品，它提供功能，范围为群集基础结构和容器协调功能计划。 它使你能够自动部署、 缩放和操作的应用程序容器跨主机群集。
>
> Kubernetes 提供分组为逻辑单元轻松管理和发现的应用程序容器的容器以中心基础结构。
>
> 在 Linux 中，Windows 中不太成熟成熟 Kubernetes。

Docker Swarm

![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image25.png)

> Docker Swarm 允许群集和计划 Docker 容器。 通过使用 Swarm，便可以将转换单个、 虚拟的 Docker 主机的 Docker 主机的池。 客户端可以发出 API 请求以 Swarm 相同的方式一样主机，这意味着，Swarm 轻松地让应用程序扩展到多个主机。
>
> Docker Swarm 是从 Docker，公司的产品。
>
> Docker v1.12 或更高版本可以运行本机和内置 Swarm 模式。

Mesosphere DC/OS

![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-styled.png](./media/image26.png)

> Mesosphere 企业 DC/OS （基于 Apache Mesos） 是一个用于运行容器和分布式应用程序的生产就绪平台。
>
> DC/OS 工作方式： 它的群集中可用的资源集合，并使这些资源可用于上构建的组件。 Marathon 通常用作与 DC/OS 集成在一起的计划。
>
> DC/OS 是在 Linux 中，Windows 中不太成熟成熟。

Azure Service Fabric

![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image27.png)

> [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview)是 Microsoft 微服务平台，用于生成应用程序。 它是[orchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction)的服务，并创建群集的计算机。 为容器或纯进程，Service Fabric 可以将服务部署。 它可以甚至组合进程中的服务容器中的相同应用程序和群集中的服务。
>
> Service Fabric 提供了附加的和可选说明性[编程模型的 Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework)如[有状态服务](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction)和[Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)。
>
> 在 Windows 中 （数年时间发展 Windows 中），较成熟在 Linux 中，Service Fabric 是成熟。 
> 自 2017 年以来，在 Service Fabric 支持 Linux 和 Windows 容器。

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a>在 Microsoft Azure 中使用容器基于 orchestrators

多个云供应商都提供 Docker 容器支持以及 Docker 群集和业务流程支持，包括 Microsoft Azure、 Amazon EC2 容器服务和 Google 容器引擎。 在下一部分中所述，Microsoft Azure 将提供 Docker 群集和 orchestrator 支持通过 Azure 容器服务 (ACS)。

另一个选项是使用 Microsoft Azure Service Fabric （微服务平台），它还支持基于 Linux 和 Windows 容器的 Docker。 Service Fabric 在 Azure 或任何其他云上运行，并且还运行[本地](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)。

## <a name="using-azure-container-service"></a>使用 Azure 容器服务

Docker 群集池多个 Docker 主机，并将它们作为单个虚拟 Docker 主机时，公开，以便你可以将多个容器部署到群集。 群集将处理可伸缩性、 运行状况，等的所有复杂的管理管道。 图 4-24 表示由应用程序的 Docker 群集如何映射到 Azure 容器服务 (ACS)。

ACS 提供的方法来简化创建、 配置和管理已预先配置为运行容器化应用程序的虚拟机的群集。 使用的优化的配置的受欢迎的开源计划和协调工具，ACS，可运用现有技能，使用或在不断增长的社区专业技术来部署和管理容器基于 Microsoft Azure 上的应用程序正文上绘制.

Azure 容器服务优化了针对 Azure 的常用 Docker 聚类分析的开放源代码工具和技术配置。 获取一个打开的解决方案，它提供你的容器和应用程序配置的可移植性。 选择大小、 的主机，数量和 orchestrator 工具，并且容器服务处理其他所有内容。

![](./media/image28.png)

**图 4-24**。 Azure 容器服务中的聚类分析选项

ACS 利用以确保你的应用程序容器是完全可移植的 Docker 映像。 它支持你选择的开放源代码 orchestration 平台，如 DC/OS （电源已通过 Apache Mesos）、 Kubernetes （最初由 Google 创建），和 Docker Swarm，以确保这些应用程序可以将扩展到数千或甚至数万个容器。

Azure 容器服务使您能够同时，仍保持应用程序可移植性，包括在业务流程层充分利用 Azure 的企业级功能。

![](./media/image29.png)

**图 4-25**。 在 ACS 中的 orchestrators

所示图 4-25，Azure 容器服务都只是为了部署 DC/OS、 Kubernetes 或 Docker Swarm，提供 Azure 的基础结构，但 ACS 不实现任何其他 orchestrator。 因此，ACS 不 orchestrator 在这种情况下，利用现有的开源 orchestrators 的容器的基础结构。

从使用情况的角度，Azure 容器服务的目标是通过使用常用的开源工具和技术提供容器的宿主环境。 为此，它你选 orchestrator 公开的标准的 API 终结点。 通过使用这些终结点，你可以利用可与这些终结点的任何软件。 例如，对于 Docker Swarm 终结点，你可以选择使用 Docker 命令行界面 (CLI)。 对于 DC/OS，你可能选择使用 DC/OS CLI。

### <a name="getting-started-with-azure-container-service"></a>开始使用 Azure 容器服务 

若要开始使用 Azure 容器服务，你部署 Azure 容器服务群集在 Azure 门户中使用 Azure 资源管理器模板或[CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)。 可用模板包括[Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm)， [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes)，和[DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos)。 快速入门模板可以修改为包括其他或高级 Azure 配置。 部署 Azure 容器服务群集的详细信息，请参阅[部署 Azure 容器服务群集](https://docs.microsoft.com/azure/container-service/container-service-deployment)Azure 网站上。

没有任何默认情况下作为 ACS 的一部分安装的软件的费用。 所有默认选项是使用开放源代码软件都实现的。

ACS 是当前可用于标准 A、 D、 DS、 G 和 GS 系列 Azure 中的 Linux 虚拟机。 你要只为你选择的计算实例，以及其他基础基础结构占用的资源，例如存储和网络付费。 有 ACS 本身没有增量费用。

## <a name="additional-resources"></a>其他资源

-   **托管 Azure 容器服务使用的解决方案的 Docker 容器简介**
    [*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro)

-   **Docker Swarm 概述**
    [*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)

-   **Swarm 模式概述**
    [*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)

-   **Mesosphere DC/OS 概述**
    [*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/)

-   **Kubernetes。** 官方网站。 \
    [*http://kubernetes.io/*](http://kubernetes.io/)


>[!div class="step-by-step"]
[以前](弹性-高的可用性-microservices.md) [下一步] (使用-azure-服务-fabric.md)
