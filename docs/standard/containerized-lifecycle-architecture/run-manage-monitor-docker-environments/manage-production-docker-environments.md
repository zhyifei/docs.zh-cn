---
title: 管理 Docker 生产环境
description: 初步了解用于管理基于容器的生产环境的关键点。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 54e2b999f744600d3b6853442bb9ccca004f4e76
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219485"
---
# <a name="manage-production-docker-environments"></a>管理 Docker 生产环境

群集管理和业务流程是控制的主机组的过程。 这可能涉及从添加和删除主机群集，获取有关主机和容器的当前状态的信息并开始和停止进程。 群集管理和业务流程与计划因为计划程序必须能够访问每个主机群集中以便计划服务密切相关。 出于此原因，同一个工具通常用于这两种用途。

## <a name="container-service-and-management-tools"></a>容器服务和管理工具

容器服务提供了快速部署流行的开源容器群集和业务流程解决方案。 它使用 Docker 映像以确保应用程序容器完全可移植。 通过使用容器服务，你可以部署 DC/OS （由 Mesosphere 和 Apache Mesos 提供支持） 和 Docker Swarm 群集使用 Azure 资源管理器模板或 Azure 门户，以确保你可以缩放到数千个这些应用程序 — 甚至数万个 — 的容器。

使用 Azure 虚拟机规模集，部署这些群集和群集充分利用 Azure 网络和存储产品/服务。 若要访问容器服务，你需要 Azure 订阅。 与容器服务中，可以同时仍维护应用程序可移植性，包括业务流程层充分利用 Azure 的企业级功能。

表 6-1 列出了其业务流程协调程序、 计划程序和聚类分析平台相关的常见管理工具。

表 6-1:Docker 管理工具


| 管理工具      | 描述           | 相关业务流程协调程序 |
|-----------------------|-----------------------|-----------------------|
| 容器服务\(Azure 门户中的用户界面管理) | [容器服务](https://azure.microsoft.com/services/container-service/)提供了一种易于获取启动路[部署在 Azure 中的容器群集](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment)基于 Mesosphere DC/OS、 Kubernetes 和 Docker Swarm 等常用业务流程协调程序。 <br /><br /> 容器服务优化了这些平台的配置。 只需选择大小、 主机数和 orchestrator 工具选项，容器服务可处理所有其他内容。 | Mesosphere DC/OS <br /><br /> Kubernetes <br /><br /> Docker Swarm |
| Docker 通用控制平面\(的本地或云) | [Docker 通用控制平面](https://docs.docker.com/v1.11/ucp/overview/)是从 Docker 的企业级群集管理解决方案。 它可帮助你从单个位置管理整个群集。 <br /><br /> Docker 通用控制平面是名为它提供了 Docker Swarm、 Docker 通用控制平面和 Docker 受信任注册表的 Docker 数据中心的商业产品的一部分。 <br /><br /> Docker 数据中心可以是安装在本地或从 Azure 等公有云预配。 | Docker Swarm\(容器服务支持) |
| Docker 云\(也称为 Tutum; 云 SaaS) | [Docker 云](https://docs.docker.com/docker-cloud/)是托管的管理服务 (SaaS)，提供生成和测试工具已 docker 化应用程序映像，工具来帮助你设置和管理主机基础结构，业务流程功能和 Docker 注册表和部署功能，可帮助你自动执行将映像部署到你的具体基础结构。 您可以将 SaaS Docker 云帐户连接到您在运行 Docker Swarm 群集的容器服务中的基础结构。 | Docker Swarm\(容器服务支持) |
| Mesosphere Marathon\(的本地或云) | [Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) Mesosphere 的 DC/OS 和 Apache Mesos 是生产级容器业务流程和计划程序平台。 <br /><br /> 它适用于 Mesos （DC/OS 基于 Apache Mesos） 控制长时间运行服务，并且提供[进程和容器管理的 web UI](https://mesosphere.github.io/marathon/docs/marathon-ui.html)。 它提供了 web UI 管理工具 | Mesosphere DC/OS\(基于 Apache Mesos; 支持的容器服务) |
| Google Kubernetes | [Kubernetes](https://kubernetes.io/docs/user-guide/ui/#dashboard-access)跨越协调、 计划和群集基础结构。 它是一个开放源代码平台，用于自动部署、 缩放和应用程序的容器操作的执行跨群集的主机，提供以容器为中心的基础结构。 | Google Kubernetes\(容器服务支持) |

## <a name="azure-service-fabric"></a>Azure Service Fabric

为群集部署和管理的另一个选项是 Azure Service Fabric。 [Service Fabric](https://azure.microsoft.com/services/service-fabric/)包括容器业务流程，以及开发人员的 Microsoft 微服务平台编程模型来构建高度可缩放的微服务应用程序。 Service Fabric 支持在当前 Linux 预览版本中，作为中的 Docker [Linux 上的 Service Fabric 预览版](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)，和用于 Windows 容器[中的下一个版本](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)。

以下是 Service Fabric 管理工具：

-   [Azure 门户中的为 Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal)与群集相关的操作 （创建/更新/删除） 群集或配置其基础结构 (Vm、 负载均衡器、 网络等)

-   [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster)是一个专用的 web UI 工具，提供的见解和 Service Fabric 群集从节点 /vm 的角度，并从应用程序和服务的角度上进行某些操作。

>[!div class="step-by-step"]
>[上一页](run-microservices-based-applications-in-production.md)
>[下一页](monitor-containerized-application-services.md)