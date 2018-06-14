---
title: 何时部署到 Azure 容器实例 (ACI) 的 Windows 容器
description: 更新现有的.NET 应用程序与 Azure 云和 Windows 容器 |何时部署到 Azure 容器实例 (ACI) 的 Windows 容器
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 3dc23c96543d9611763b571105f52b150dfec06f
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957947"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>何时部署到 Azure 容器实例 (ACI) 的 Windows 容器

主要价值主张是你可以立即部署到它的容器，并且无需维护该环境的 azure 容器实例，你无需升级/修补程序的其中操作系统或 Vm，来说，是透明的只需部署到准备就绪，可以使用环境的容器。

当你使用 Azure Vm 时容器，因此基本上的原因和方案时要使用 ACI 是类似于主要方案，有关使用 Azure 容器实例的主要方案是：

-   **开发/测试方案**
-   **任务自动化**
-   **CI/CD 代理**
-   **小型/横向批处理**
-   **简单的 web 应用**

简单的 web 应用方案是 ACI 公平方案，但会考虑，因为在 ACI 只能有每个容器图像的单个容器实例，您将不具有高可用性，并且仅具有有限的可伸缩性。

但是，即使 ACI 被认为基础结构，因为它仅提供单个容器实例，没有与正则与 Windows Server 的 Azure Vm 相比是非常有用。 与 ACI，只需部署到自我维护的环境的容器和你只需支付这些容器。 你无需维护/更新/修补 Vm，因此它是一个多更好的平台，在大多数情况下，你可能正在使用虚拟机与容器。 使用 ACI 是一个直截了当，只需部署一个容器，则无需创建虚拟机环境只需部署容器。

Azure 容器实例 (ACI) 的主要优点有：

-   无需管理服务器运行容器
-   提高了灵活性与按需容器
-   将容器部署到通过前所未有的简单快速地云 — 使用单个命令。 
-   保护虚拟机监控程序隔离的应用程序

简而言之，使用 ACI 可以快速而无需管理虚拟机或无需学习新工具开发应用。 它是只是你应用程序，在云中运行的容器中。

>[!div class="step-by-step"]
[上一页](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[下一页](when-to-deploy-windows-containers-to-service-fabric.md)
