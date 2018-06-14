---
title: 何时到 Service Fabric 中部署 Windows 容器
description: 更新现有的.NET 应用程序与 Azure 云和 Windows 容器 |何时到 Service Fabric 中部署 Windows 容器
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: c41db8b37c883f9369a6b8d1f8bccbc0535f504c
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957907"
---
# <a name="when-to-deploy-windows-containers-to-service-fabric"></a>何时到 Service Fabric 中部署 Windows 容器

应用程序基于 Windows 容器快速将需要使用从 IaaS Vm 放下移甚至可更进一步的平台。 此内容用于改进自动的可伸缩性和高可伸缩性，并能够在部署中，完整的管理体验的重大改进升级时，版本控制、 回退和运行状况监视。 与 orchestrator Azure Service Fabric 中，可在 Microsoft Azure 云，但还在本地，或甚至在另一个云，可以实现这些目标。

许多组织抬起，然后切换到容器的现有整体应用程序有两个原因：

-   降低成本，或者由于合并和删除的现有硬件，或者在更高的密度运行应用程序。

-   一致的部署之间开发和操作协定。

按照降低成本是可以理解，并很可能所有组织都追踪这一目标。 一致的部署将更难以若要评估，但同样重要。 部署一致协定指出开发人员可自由选择使用它们，适合的技术和运营团队都可使用单一方法来部署和管理应用程序。 本协议以减少无操作处理的许多不同的技术，复杂性或强制开发人员可以仅使用某些技术难题。 从根本上来说，每个应用程序被容器中的自包含的部署映像。

某些组织将继续 modernizing 通过添加微服务 （云本机应用程序），但许多其他组织将在此处停止 （云优化应用程序）。 如所示在图 4-8 中，这些组织不会移动到微服务体系结构，因为它们可能不需要。 在任何情况下，它们已获得的好处，使用容器以及 Service Fabric 提供了一个完整的管理体验，包括部署、 升级、 版本控制、 回滚，和运行状况监视。

> ![提升和移动到 Service Fabric 应用程序](./media/image8.png)
>
> **图 4-8。** 提升和移动到 Service Fabric 应用程序

Service Fabric 的关键方法是重复使用现有代码和提升和移动。 因此，你可以通过使用 Windows 容器迁移你当前的.NET Framework 应用程序，并将它们部署到 Service Fabric。 它将更容易地将转 modernizing，最后，通过添加新的微服务。

时将 Service Fabric 与其他 orchestrators 进行比较，务必突出显示 Service Fabric 是成熟在运行基于 Windows 的应用程序和服务。 Service Fabric 已经运行基于 Windows 的服务和应用程序，包括年的第 1 层、 执行关键任务的 Microsoft 产品。 它是用于为 Windows 容器具有常规可用性的第一个 orchestrator。 其他容器，如 Kubernetes、 DC/OS 和 Docker Swarm，是更加成熟完善一些在 Linux 中，但不太成熟比基于 Windows 的 Service Fabric 应用程序和 Windows 容器。

Service Fabric 的最终目标是减少使用微服务方法生成应用程序的复杂性。 你最终将要用于特定类型的应用程序能够避免代价高昂的重新设计的微服务。 可以启动小、 缩放需要时，弃用服务、 添加新服务，和发展客户使用的应用程序。 有许多尚为大多数开发人员进行微服务更便于访问要解决其他问题。 如果你当前是刚刚提起并移动应用程序与 Windows 容器，但你正在考虑添加微服务在将来根据容器，这是 Service Fabric 最擅长的领域。

>[!div class="step-by-step"]
[上一页](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[下一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
