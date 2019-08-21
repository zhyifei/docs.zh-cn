---
title: 将现有 .NET 应用程序直接迁移到 Azure IaaS (云基础结构就绪)
description: 利用 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化。
ms.date: 04/28/2018
ms.openlocfilehash: e25ddbf9b6e62c264f3f4d4580d7df3553d262ea
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69660738"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a>将现有 .NET 应用程序直接迁移到 Azure IaaS (云基础结构就绪)

> 愿景：作为第一步, 若要减少本地投资和硬件和网络维护的总成本, 只需将现有应用程序 rehost 到云中。

在*介绍如何*将现有应用程序迁移到 azure 基础结构即服务 (IaaS) 平台之前, 请务必分析要直接迁移到 azure中的 IaaS 的原因。 此现代化成熟度级别的方案实质上是开始在云中使用 Vm, 而不是继续使用当前的本地基础结构。

要分析的另一点是, 可能需要迁移到纯 IaaS 云, 而不是只是在 Azure 中添加更高级的托管服务。 首先确定哪些情况下可能需要 IaaS。

图2-1 定位现代化成熟度中的云基础结构就绪应用程序:

![定位云基础结构就绪应用程序](./media/image2-1.png)

> **图 2-1.** 定位云基础结构就绪应用程序

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>为什么要将现有 .NET web 应用程序迁移到 Azure IaaS

即使在初始 IaaS 级别迁移到云的主要原因是要实现成本降低。 通过使用更多的托管基础结构服务, 你的组织可以降低其对硬件维护、服务器或 VM 预配和部署以及基础结构管理的投资。

决定将应用移到云后, 选择 IaaS 而不是更高级选项 (如 PaaS) 的主要原因就是, IaaS 环境会更熟悉。 迁移到类似于你当前的本地环境的环境提供较低的学习曲线, 使其成为云的最快途径。

但是, 将最快的途径带入云并不意味着你可以从在云中运行应用程序获得最大的好处。 任何组织都将从已推出的云优化和云本机成熟度级别的云迁移中获得最大的好处。

它还明显表明, 如果应用程序已在云中运行, 甚至在 IaaS 上运行, 就更容易实现现代化和重塑。 已实现应用程序数据迁移。 此外, 你的组织将获得在云中工作所需的技能, 并使班次成为 "云文化"。

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>何时迁移到 IaaS 而不是迁移到 PaaS

接下来的部分讨论基于 PaaS 平台和服务的云优化应用程序。 这些应用为你带来了迁移到云的最大好处。 

如果你的目标只是将现有应用程序迁移到云, 请先确定现有应用程序, 这些应用程序不需要进行大量修改即可在 Azure App Service 中运行。 这些应用应是云优化的第一个候选项。 

然后, 对于仍无法移至 Windows 容器和 PaaS 的应用 (如 Azure Kubernetes Service), 请将其迁移到简单的普通 Vm (IaaS)。 

但请记住, 正确配置、保护和维护 Vm 需要比在 Azure 中使用 PaaS 服务更多的时间和 IT 专业知识。 如果考虑使用 Azure 虚拟机, 请确保将修补、更新和管理 VM 环境所需的日常维护工作纳入考虑。 Azure 虚拟机为 IaaS。

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>使用 Azure Migrate 分析现有应用程序并将其迁移到 Azure

迁移到云不一定很困难。 但许多组织都在努力开始-深入了解环境以及应用程序、工作负荷和数据之间的紧密相关性。 如果没有该可见性, 则很难规划转发的路径。 如果没有关于成功迁移所需内容的详细信息, 你的组织中将无法进行正确的对话。 您并不知道可能的成本优势, 或者工作负荷是只需要直接迁移, 还是需要大量返工才能成功迁移。 不是很多人都想。

[Azure Migrate](https://aka.ms/azuremigrate)是一项新服务, 提供帮助你迁移到 Azure 所需的指导、见解和机制。 Azure Migrate 提供:

- 发现和评估本地虚拟机

- 用于多层应用程序的高可信度发现的内置依赖项映射

- 向 Azure 虚拟机智能地调整大小

- 兼容性报告与补救潜在问题的指南

- 与 Azure 数据库管理服务集成以实现数据库发现和迁移

Azure Migrate 使你确信工作负荷可以在最小程度上进行迁移, 并在 Azure 中按预期运行。 利用正确的工具和指南, 你可以实现最大投资回报, 同时确保满足关键的性能和可靠性需求。

图2-2 显示了 Azure Migrate 执行的所有服务器和应用程序连接的内置依赖项映射。

![定位云基础结构就绪应用程序](./media/image2-2.png)

> **图 2-2。** 定位云基础结构就绪应用程序

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>使用 Azure Site Recovery 将现有 Vm 迁移到 Azure Vm

作为端到端[Azure Migrate](https://aka.ms/azuremigrate)的一部分, [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)是一个工具, 可用于轻松地将 Web 应用迁移到 Azure 中的 vm。 你可以使用 Site Recovery 将本地 Vm 和物理服务器复制到 Azure, 或将其复制到辅助本地位置。 甚至可以复制在受支持的 Azure VM、本地*Hyper-v* Vm、 *VMware* Vm 或 Windows 或 Linux 物理服务器上运行的工作负荷。 复制到 Azure 消除了维护辅助数据中心的成本和复杂性。

对于部分本地和 Azure 上部分的混合环境, Site Recovery 也是专门提供的。 Site Recovery 通过将运行于 Vm 和本地物理服务器上的应用程序保持在站点出现故障的情况下, 帮助确保业务连续性。 它复制在 Vm 和物理服务器上运行的工作负荷, 以便在主站点不可用时, 它们仍可用于辅助位置。 当主站点重新启动并运行时, 它会将工作负荷恢复到主站点。

图2-3 显示了如何使用 Azure Site Recovery 执行多个 VM 迁移。

![定位云基础结构就绪应用程序](./media/image2-3.png)

> **图2-3。** 定位云基础结构就绪应用程序

### <a name="additional-resources"></a>其他资源

- **Azure Migrate 数据表**

    <https://aka.ms/azuremigration\_datasheet>

- **Azure Migrate**

    <https://aka.ms/azuremigrate>

- **Azure 迁移中心**

    <https://azure.microsoft.com/migration/>

- **通过 Site Recovery 迁移到 Azure**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- **Azure Site Recovery 服务概述**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- **将 AWS 中的 Vm 迁移到 Azure Vm**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
>[上一页](index.md)
>[下一页](migrate-your-relational-databases-to-azure.md) <!-- Next Chapter -->
