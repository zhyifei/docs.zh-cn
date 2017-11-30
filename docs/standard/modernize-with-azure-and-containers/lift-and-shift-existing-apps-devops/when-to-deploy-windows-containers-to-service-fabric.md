---
title: "何时到 Service Fabric 中部署 Windows 容器"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |何时到 Service Fabric 中部署 Windows 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 21b6c348991e07dac7dbc9d327b63fa88a588ba4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-deploy-windows-containers-to-service-fabric"></a>何时到 Service Fabric 中部署 Windows 容器

应用程序基于 Windows 容器快速将需要使用从 IaaS Vm 放下移甚至可更进一步的平台。 此内容用于改进自动的可伸缩性和高可伸缩性，并能够在部署中，完整的管理体验的重大改进升级时，版本控制、 回退和运行状况监视。 与 orchestrator Azure Service Fabric 中，可在 Microsoft Azure 云，但还在本地，或甚至在另一个云，可以实现这些目标。

许多组织抬起，然后切换到容器的现有整体应用程序有两个原因：

-   降低成本，或者由于合并和删除的现有硬件，或者在更高的密度运行应用程序。

-   一致的部署之间开发和操作协定。

按照降低成本是可以理解，并很可能所有组织都追踪这一目标。 一致的部署将更难以若要评估，但同样重要。 部署一致协定指出开发人员可自由选择使用它们，适合的技术和运营团队都可使用单一方法来部署和管理应用程序。 本协议以减少无操作处理的许多不同的技术，复杂性或强制开发人员可以仅使用某些技术难题。 从根本上来说，每个应用程序被容器中的自包含的部署映像。

某些组织将继续 modernizing 通过添加微服务 （云优化和云本机应用程序）。 许多组织将在此处停止 （已准备云 DevOps）。 如所示在图 4-8 中，这些组织不会移动到微服务体系结构，因为它们可能不需要。 在任何情况下，它们已获得的好处，使用容器以及 Service Fabric 提供了一个完整的管理体验，包括部署、 升级、 版本控制、 回滚，和运行状况监视。

> ![提升和移动到 Service Fabric 应用程序](./media/image8.png)
>
> **图 4-8。** 提升和移动到 Service Fabric 应用程序

Service Fabric 的关键方法是重复使用现有代码，只需提升和移动。 因此，你可以通过使用 Windows 容器迁移你当前的.NET Framework 应用程序，并将它们部署到 Service Fabric。 它将更容易地将转 modernizing，最后，通过添加新的微服务。

当将 Service Fabric 与其他 orchestrators 进行比较，务必突出显示 Service Fabric 是非常成熟在运行基于 Windows 的应用程序和服务。 Service Fabric 已经运行基于 Windows 的服务和应用程序，包括年 Microsoft，从第 1 层、 执行关键任务的产品。 它是用于为 Windows 容器 (5 月 2017) 具有常规可用性的第一个 orchestrator。 其他容器，如 Kubernetes、 DC/OS 和 Docker Swarm，是更加成熟完善一些在 Linux 中，但不太成熟比基于 Windows 的 Service Fabric 应用程序和 Windows 容器。

Service Fabric 的最终目标是减少使用微服务方法生成应用程序的复杂性。 这是其中最终要对于某些类型的应用程序，以避免代价高昂的重新设计。 可以启动小、 缩放需要时，弃用服务、 添加新服务，和发展客户使用的应用程序。 我们知道尚来解决为大多数开发人员进行微服务更便于访问的许多其他问题。 如果你当前是刚刚提起并移动应用程序与 Windows 容器，但你正在考虑添加微服务在将来根据容器，这是 Service Fabric 最擅长的领域。

>[!div class="step-by-step"]
[上一页](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[下一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
