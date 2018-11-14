---
title: 协调安排微服务和多容器应用程序，实现高可伸缩性和高可用性
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 协调安排微服务和多容器应用程序，实现高可伸缩性和高可用性
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 25175e2a4409d53be412ae72be5af1c07c3ec68d
ms.sourcegitcommit: 296183dbe35077b5c5e5e74d5fbe7f399bc507ee
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "50982771"
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>协调安排微服务和多容器应用程序，实现高可伸缩性和高可用性

如果应用程序基于微服务或只是跨多个容器拆分，则必须使用适用于生产就绪应用程序的业务流程协调程序。 如前所述，在基于微服务的方法中，每个微服务均拥有其模型和数据，如此从开发和部署的角度来看，它便是具有自主性。 但即使拥有由多个服务组成的更传统的应用程序（如 SOA），也将拥有多个容器或服务，这些容器或服务中包含需要作为分布式系统部署的单个业务应用程序。 这类系统的扩展和管理非常复杂；因此，如果想要拥有生产就绪且可缩放的多容器应用程序，则必须使用业务流程协调程序。

图 4-23 介绍如何部署到由多个微服务（容器）组成的应用程序群集。

![](./media/image23.PNG)

图 4-23。 容器群集

它看上去类似于逻辑方法。 但是如何处理负载均衡、路由以及如何协调安排这些组合式应用程序呢？

单个 Docker 主机中的普通 Docker 引擎能够满足在一台主机上管理单映像实例的需求，但若要管理针对更复杂的分布式应用程序而部署在多个主机上的多个容器，则无法满足需求。 大多数情况下，需要一个管理平台，该平台能自动启动容器、扩展容器（每个映像具有多个实例）、必要时暂停或关闭，并且在理想情况下还能控制资源（如网络和数据存储）访问方式。

如果不仅要管理个别容器或非常简单的组合式应用，还要进一步管理使用微服务的较大型企业应用程序，则必须转向业务流程和群集平台。

从体系结构和开发的角度来看，如果要生成由基于微服务的应用程序组成的大型企业应用程序，则务必了解清楚下面列出的支持高级方案的平台和产品：

**群集和业务流程协调程序**。 如果需要跨多个 Docker 主机扩展应用程序例如生成基于微服务的大型应用程序时，能够通过抽象化基础平台的复杂性来将所有主机作为单个群集管理是至关重要的。 这就是容器群集和业务流程协调程序所提供的功能。 业务流程协调程序示例包括 Azure Service Fabric、Kubernetes、Docker Swarm 和 Mesosphere DC/OS。 通过 Azure 容器服务，可在 Azure 中获取最后三个开源业务流程协调程序。

**计划程序**。 计划意味着管理员能够在群集中启动容器，如此这些容器也可提供 UI。 群集计划程序具有多个职责：高效使用群集资源、设置用户提供的约束、有效负载均衡节点或主机间的容器，以及在提供高可用性的同时强力解决错误。

群集和计划程序的概念密切相关，因此不同供应商提供的产品通常具有这两套功能。 下表显示了适用于群集和计划程序的最重要的平台和软件选项。 通常在公有云（如 Azure）中提供这些业务流程协调程序。

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>适用于容器群集、业务流程和计划的软件平台

Kubernetes

![Kubernetes 徽标](./media/image24.png)

> Kubernetes 是一款开源产品，提供各种功能，从群集基础结构和容器计划到安排功能均涵盖在内。 它能实现跨主机群集自动部署、缩放以及执行各种应用程序容器操作。
>
> Kubernetes 提供以容器为中心的基础结构，将应用程序容器分组为逻辑单元，以便管理和发现。
>
> Kubernetes 在 Linux 中的运用已发展成熟，但在 Windows 中相对较弱。

Docker Swarm

![Docker Swarm 徽标](./media/image25.png)

> Docker Swarm 能够对 Docker 容器进行聚类分析和计划。 通过使用 Swarm，可以将多个 Docker 主机转换味单个虚拟 Docker 主机。 客户端可以向 Swarm 发出 API 请求（方法同其向主机发出请求），这意味着 Swarm 可以使应用程序轻松地扩展到多个主机。
>
> Docker Swarm 是来自 Docker 公司 的产品。
>
> Docker v1.12 或更高版本可以运行本机内置 Swarm 模式。

Mesosphere DC/OS

![Mesosphere DC/OS 徽标](./media/image26.png)

> Mesosphere Enterprise DC/OS（基于 Apache Mesos）是用于运行容器和分布式应用程序的生产就绪平台。
>
> DC/OS 的工作方式是提取群集中的可用资源集合，并使这些资源可用于在其上构建的组件。 Marathon 通常用作与 DC/OS 集成的计划程序。
>
> DC/OS 在 Linux 中的运用已发展成熟，但在 Windows 中相对较弱。

Azure Service Fabric

![Azure Service Fabric 徽标](./media/image27.png)

> [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) 是用于生成应用程序的 Microsoft 微服务平台。 它是服务的 [业务流程协调程序](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) ，可创建计算机群集。 Service Fabric 可将服务作为容器或纯进程进行部署。 它甚至可以在同一应用程序和群集中将进程中的服务与容器中的服务进行组合。
>
> Service Fabric 提供其他可选的规定  [Service Fabric 编程模型 ](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework)（如[有状态服务](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction)和 [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)）。
>
> Service Fabric 在 Windows 中的运用已经成熟（已在 Windows 中发展多年），但在 Linux 中相对较弱。 
> 自 2017 年以来，Service Fabric 同时支持 Linux 和 Windows 容器。

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a>在 Microsoft Azure 中使用基于容器的业务流程协调程序

多家云供应商提供 Docker 容器支持以及 Docker 群集和业务流程支持，包括 Microsoft Azure、Amazon EC2 容器服务和 Google 容器引擎。 Microsoft Azure 通过 Azure 容器服务 (ACS) 提供 Docker 群集和业务流程协调程序支持，下一节中将详细说明。

另一个选项是使用 Microsoft Azure Service Fabric（微服务平台），它也支持基于 Linux 和 Windows 容器的 Docker。 Service Fabric 可在 Azure 或其他云上运行，也可在[本地](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)运行。

## <a name="using-azure-container-service"></a>使用 Azure 容器服务

Docker 群集汇集多个 Docker 主机，并将它们作为单个虚拟 Docker 主机公开，因此可以将多个容器部署到群集。 该群集将处理可伸缩性、运行状况等所有复杂的管理任务。 图 4-24 显示组合式应用程序的 Docker 群集如何映射到 Azure 容器服务 (ACS)。

ACS 提供了一种方法，可简化虚拟机（预配置为运行容器化应用程序）群集的创建、配置和管理。 通过使用常用开源计划和业务流程工具的优化配置，ACS 能够利用现有技能或大量不断增长的社区专业知识，在 Microsoft Azure 上部署和管理基于容器的应用程序。

Azure 容器服务优化了专门针对 Azure 的常用 Docker 群集开源和技术的配置。 可以获得一个开放的解决方案，该解决方案为容器和应用程序配置提供可移植性。 用户选择主机的大小和数量以及业务流程协调程序工具，然后容器服务可处理其他操作。

![](./media/image28.png)

图 4-24。 Azure 容器服务中的群集选项

ACS 利用 Docker 映像来确保应用程序容器是完全可移植的。 它支持选择开源业务流程平台，如 DC/OS （由 Apache Mesos 提供支持）、Kubernetes（最初由 Google 创建）和 Docker Swarm，确保这些应用程序可以扩展到数千或甚至数万个容器。

Azure 容器服务能够利用 Azure 的企业级功能，同时仍然保持应用程序的可移植性，包括业务流程层的可移植性。

![](./media/image29.png)

图 4-25。 ACS 中的业务流程协调程序

如图 4-25 所示，Azure 容器服务只是 Azure 提供的基础结构，以便部署 DC/OS、Kubernetes 或 Docker Swarm，但 ACS 不实现任何其他业务流程协调程序。 因此，ACS 本身并不是这种业务流程协调程序，只是利用容器的现有开源业务流程协调程序的基础结构。

从使用情况来看，Azure 容器服务的目标是通过使用常用的开源工具和技术提供容器的托管环境。 为此，它为选择的业务流程协调程序公开标准 API 终结点。 通过使用这些终结点，可以利用能与这些终结点通信的任何软件。 例如，对于 Docker Swarm 终结点，可选择使用 Docker 命令行接口 (CLI)。 对于 DC/OS，可选择使用 DC/OS CLI。

### <a name="getting-started-with-azure-container-service"></a>Azure 容器服务入门 

若要开始使用 Azure 容器服务，请使用 Azure 资源管理器模板或 [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli) 从 Azure 门户部署 Azure 容器服务群集。 可用模板包括 [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm)、[Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) 和 [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos)。 快速入门模板可以修改为包括其他或高级 Azure 配置。 有关部署 Azure 容器服务群集的详细信息，请参阅 Azure 网站上的[部署 Azure 容器服务群集](https://docs.microsoft.com/azure/container-service/container-service-deployment)。

作为 ACS 的一部分，默认安装的任何软件都不收费。 所有默认选项都通过开源软件实现。

ACS 当前可用于 Azure 中的标准 A、D、DS、G 和 GS 系列 Linux 虚拟机。 仅针对所选的计算实例以及使用的其他基础结构资源（如存储和网络）收取费用。 ACS 本身不会以增量方式收费。

## <a name="additional-resources"></a>其他资源

-   **使用 Azure 容器服务托管解决方案的 Docker 容器简介**
    [https://docs.microsoft.com/azure/container-service/container-service-intro](https://docs.microsoft.com/azure/container-service/container-service-intro)

-   **Docker Swarm overview**（Docker Swarm 概述）
    [https://docs.docker.com/swarm/overview/](https://docs.docker.com/swarm/overview/)

-   **Swarm mode overview**（Swarm 模式概述）
    [https://docs.docker.com/engine/swarm/](https://docs.docker.com/engine/swarm/)

-   **Mesosphere DC/OS Overview**（Mesosphere DC/OS 概述）
    [https://docs.mesosphere.com/1.7/overview/](https://docs.mesosphere.com/1.7/overview/)

-   **Kubernetes。** 官方网站。
    [*https://kubernetes.io/*](https://kubernetes.io/)


>[!div class="step-by-step"]
[上一页](resilient-high-availability-microservices.md)
[下一页](using-azure-service-fabric.md)
