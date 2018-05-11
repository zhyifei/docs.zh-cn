---
title: 何时将 Windows 容器部署到 Azure Vm （IaaS 云）
description: 更新现有的.NET 应用程序与 Azure 云和 Windows 容器 |何时将 Windows 容器部署到 Azure Vm （IaaS 云）
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 7472745577f414062b460fd71ab45bae85d7a62e
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>何时将 Windows 容器部署到 Azure Vm （IaaS 云）

如果你的组织使用 Azure Vm，即使你使用 Windows 容器，则仍要处理 IaaS。 当你需要将部署到负载平衡基础结构中的多个 Vm 时，这会高度可伸缩的应用程序意味着该处理基础结构操作、 VM OS 修补程序和基础结构的复杂性。 在 Azure VM 中使用 Windows 容器功能的主要方案是：

-   **开发/测试环境**： 在云中的 VM 非常适用于开发和测试在云中。 你可以快速创建或停止环境，具体取决于你的需求。

-   **小型和中型可伸缩性需要**： 在其中你可能需要几 Vm 内的为生产环境的情况下，管理少量的 Vm 之前，可能存在实惠可以将它们移动到更高级的 PaaS 环境，类似于 orchestrators。

-   **使用现有的部署工具的生产环境**： 你可能会从你已投资工具对虚拟机或裸机服务器 （如 Puppet 或类似工具） 进行复杂的部署中的本地环境中移动。 若要进行少量的更改到生产环境部署过程迁移到云，你可能会继续使用这些工具将部署到 Azure Vm。 但是，你将想要使用 Windows 容器作为部署单元，以改进部署体验。

>[!div class="step-by-step"]
[上一页](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[下一页](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
