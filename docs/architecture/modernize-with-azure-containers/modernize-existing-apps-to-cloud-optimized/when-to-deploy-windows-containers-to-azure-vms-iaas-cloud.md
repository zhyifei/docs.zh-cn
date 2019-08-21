---
title: 何时将 Windows 容器部署到 Azure VM（IaaS 云）
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |何时将 Windows 容器部署到 Azure Vm (IaaS 云)
ms.date: 04/28/2018
ms.openlocfilehash: e9a2903662306b607977a7751018e24161ab80ab
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577900"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>何时将 Windows 容器部署到 Azure VM（IaaS 云）

如果你的组织使用的是 Azure Vm, 即使你还使用 Windows 容器, 你仍将处理 IaaS。 这意味着, 当你需要在负载平衡基础结构中部署到多个 Vm 时, 处理适用于高度可伸缩性的应用程序的基础结构操作、VM 操作系统修补程序和基础结构复杂性。 在 Azure VM 中使用 Windows 容器的主要方案是:

- **开发/测试环境**:云中的 VM 非常适合在云中进行开发和测试。 你可以根据需要快速创建或停止环境。

- 中小型**可伸缩性需求**:对于生产环境, 可能只需要几个 Vm, 则在可以迁移到更高级的 PaaS 环境 (如协调器) 之前, 管理少量 Vm 可能会得到经济实惠。

- **包含现有部署工具的生产环境**:你可能会从本地环境迁移, 在该环境中, 你可以在其中投入工具来向 Vm 或裸机服务器 (如 Puppet 或类似的工具) 进行复杂的部署。 若要迁移到云, 只需对生产环境部署过程进行少量更改, 你就可以继续使用这些工具部署到 Azure Vm。 但是, 你需要使用 Windows 容器作为部署单元来改善部署体验。

>[!div class="step-by-step"]
>[上一页](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[下一页](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
