---
title: 何时将 Windows 容器部署到 Azure 容器实例 (ACI)
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |何时将 Windows 容器部署到 Azure 容器实例 (ACI)
ms.date: 04/29/2018
ms.openlocfilehash: 3b6ae1ced9c4e01f5ab400e2575947a396064ebd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577930"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>何时将 Windows 容器部署到 Azure 容器实例 (ACI)

Azure 容器实例的主要价值主张是, 你可以立即将容器部署到该环境中, 而无需维护该环境, 无需升级/修补基础操作系统或 Vm, 所有这些操作都是透明的, 你只需部署容器进入随时可用的环境。

当你将 Azure Vm 与容器一起使用时, 想要使用 ACI 的原因和方案类似于主要方案, 因此, 使用 Azure 容器实例的主要方案如下:

- **开发/测试方案**
- **任务自动化**
- **CI/CD 代理**
- **小规模/缩放批处理**
- **简单的 web 应用**

简单的 web 应用方案是一种公平的 ACI 方案, 但考虑到这一点, 因为在 ACI 中, 每个容器映像只能有一个容器实例, 你没有高可用性, 并且仅具有有限的可伸缩性。

但是, 即使 ACI 被视为基础结构, 因为它只提供单个容器实例, 与使用 Windows Server 的常规 Azure Vm 相比, 具有巨大的优势。 使用 ACI, 只需将容器部署到自行维护的环境中即可, 只需为这些容器付费。 你无需维护/更新/修补 Vm, 因此, 在大多数情况下, 你可能会在容器中使用 Vm, 这是一个更好的平台。 使用 ACI 直接进行, 只需部署容器, 无需创建仅部署容器的 VM 环境。

Azure 容器实例 (ACI) 的主要优点是:

- 在不管理服务器的情况下运行容器
- 根据需要提高容器的灵活性
- 使用单个命令将容器部署到具有空前简易性和速度的云。
- 通过虚拟机监控程序隔离保护应用程序

简而言之, 借助 ACI, 可以快速开发应用而无需管理虚拟机, 也无需了解新的工具。 它只是在云中运行的应用程序。

> [!div class="step-by-step"]
> [上一页](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [下一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
