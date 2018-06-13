---
title: 管理生产 Docker 环境
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 5ecf1fbc164ff4170951894abc071908f45178d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573876"
---
# <a name="manage-production-docker-environments"></a>管理生产 Docker 环境

群集管理和业务流程是控制的主机组的过程。 这可能涉及中添加或删除主机群集，获取有关主机和容器的当前状态的信息和开始和停止进程。 因为计划程序必须能够访问每个主机群集中以便计划服务执行计划密切相关群集管理和业务流程。 因此，相同的工具通常用于这两种用途。

## <a name="container-service-and-management-tools"></a>容器服务和管理工具

容器服务提供受欢迎的开源容器聚类分析和业务流程解决方案的快速的部署。 它使用 Docker 映像以确保你的应用程序容器是完全可移植。 通过使用容器服务，你可以部署 （由 Mesosphere 和 Apache Mesos 提供支持） 的 DC/OS 和 Docker Swarm 群集与 Azure 资源管理器模板或 Azure 门户，以确保你可以扩展到数千这些应用程序 — 即使数万个-的容器。

使用 Azure 虚拟机缩放集，部署这些群集和群集充分利用 Azure 的网络和存储产品。 若要访问容器服务，你需要 Azure 订阅。 借助容器 Service，你可以利用 Azure 的企业级功能的同时，仍保持应用程序可移植性，包括在业务流程层。

表 6-1 列出其 orchestrators、 计划程序时和聚类分析的平台与相关的常见管理工具。

表 6-1: Docker 管理工具


| 管理工具      | 描述           | 相关的 orchestrators |
|-----------------------|-----------------------|-----------------------|
| 容器服务\(在 Azure 门户中的用户界面管理) | [容器服务](https://azure.microsoft.com/en-us/services/container-service/)提供一种易于获取启动往[部署在 Azure 中的容器群集](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment)基于流行 orchestrators Mesosphere DC/OS、 Kubernetes 和 Docker Swarm 等。 <br /><br /> 容器服务优化这些平台的配置。 你只需选择的大小、 的主机，数量和所选的 orchestrator 工具，并且容器服务处理其他所有内容。 | Mesosphere DC/OS <br /><br /> Kubernetes <br /><br /> Docker Swarm |
| Docker 通用控制平面\(本地或云) | [Docker 通用控制平面](https://docs.docker.com/v1.11/ucp/overview/)是从 Docker 的企业级群集管理解决方案。 它可帮助你从单个位置管理整个群集。 <br /><br /> Docker 通用控制平面是名为 Docker 数据中心，它提供 Docker Swarm、 Docker 通用控制平面和 Docker 受信任注册表商业产品的一部分包括。 <br /><br /> Docker 数据中心可以是在本地安装，或从如 Azure 公共云预配。 | Docker Swarm\(容器服务支持) |
| Docker 云\(也称为 Tutum; 云 SaaS) | [Docker 云](https://docs.docker.com/docker-cloud/)是一种托管的管理服务 (SaaS)，它提供生成和测试功能，Dockerized 应用程序映像，工具来帮助你设置和管理主机基础结构，业务流程功能和 Docker 注册表和部署功能，可帮助你自动执行将映像部署到你的具体基础结构。 你可以连接到你在运行 Docker Swarm 群集的容器服务的基础结构的 SaaS Docker 云帐户。 | Docker Swarm\(容器服务支持) |
| Mesosphere Marathon\(本地或云) | [Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) Mesosphere 的 DC/OS 和 Apache Mesos 是一个生产级容器业务流程和计划程序的平台。 <br /><br /> 它适用于 Mesos （DC/OS 基于 Apache Mesos） 控制长时间运行服务，并且提供[的过程和容器管理 web UI](https://mesosphere.github.io/marathon/docs/marathon-ui.html)。 它提供了一个 web UI 管理工具 | Mesosphere DC/OS\(基于 Apache Mesos; 支持的容器服务) |
| Google Kubernetes | [Kubernetes](http://kubernetes.io/docs/user-guide/ui/#dashboard-access)跨越协调、 计划和群集基础结构。 它是一个开源平台，用于跨群集主机，提供以容器为中心的基础结构自动部署、 缩放和操作的应用程序容器。 | Google Kubernetes\(容器服务支持) |

## <a name="azure-service-fabric"></a>Azure Service Fabric

为群集部署和管理的另一个选项是 Azure Service Fabric。 [Service Fabric](https://azure.microsoft.com/en-us/services/service-fabric/)一个 Microsoft 微服务平台，包括容器业务流程，以及开发人员编程模型来生成高度可缩放的微服务应用程序。 Service Fabric 支持 Docker 在当前的 Linux 预览版本，如[在 Linux 上的 Service Fabric 预览](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)，和为 Windows 容器[下一个版本中](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)。

以下是 Service Fabric 管理工具：

-   [适用于 Service Fabric 的 azure 门户](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal)与群集相关的操作 （创建/更新/删除） 群集或配置其基础结构 (例如其 Vm、 负载平衡器、 网络等)

-   [Azure Service Fabric 资源管理器](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster)是一个专用的 web UI 工具，提供了见解和 Service Fabric 群集从节点/Vm 角度来看，并从应用程序和服务的角度来看某些操作。


>[!div class="step-by-step"]
[以前] (run-microservices-based-applications-in-production.md) [下一步] (monitor-containerized-application-services.md)
