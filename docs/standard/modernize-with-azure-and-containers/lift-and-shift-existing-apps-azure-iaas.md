---
title: 提升和移动现有应用 Azure IaaS
description: 更新现有的.NET 应用程序与 Azure 云和 Windows 容器。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d7922ad3a3cd5346f81008e1841a55b5e3663832
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="lift-and-shift-existing-apps-azure-iaas"></a>提升和移动现有应用 Azure IaaS

> 设想： 作为第一个步骤，以降低本地投资和总成本的硬件和网络维护，只需 rehost 在云中的现有应用程序。

在获取到之前*如何*若要迁移到 Azure 基础结构即服务 (IaaS) 平台的现有应用程序，务必分析原因*为什么*你想要迁移直接到 IaaS在 Azure 中。 在此现代化成熟度级别方案实质上是若要开始使用虚拟机在云中，而不是继续使用最新状态，本地基础结构。

若要分析的另一点是*为什么*可能想要迁移到纯的 IaaS 云，而不是仅仅增加了更高级的 Azure 中的托管的服务。 你需要确定情况下可能首先需要 IaaS。

图 2-1 定位现代化成熟度级别中的云基础结构的通用应用程序：

![定位云基础结构的通用应用程序](./media/image2-1.png)

> **图 2-1.** 定位云基础结构的通用应用程序

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>为什么现有.NET web 应用程序迁移到 Azure IaaS

若要迁移到云中，甚至在初始 IaaS 级别的主要原因是降低成本。 通过使用更多的托管的基础结构服务，你的组织可能会降低其在硬件维护、 服务器或 VM 设置和部署和基础结构管理方面的投资。

做出决策，以将你的应用程序移到云中后，将更熟悉为什么你可能选择 IaaS 而不是更多高级选项，如 PaaS 只需进行的 IaaS 环境的主要原因。 将移动到类似于你当前的环境，在本地环境提供较低的学习曲线，这样就最快的途径到云。

但是，将最快的路径发送到云中并不意味着，你会获得最大益处，无需你在云中运行的应用程序。 任何组织将获得从云迁移在已引入的云就绪 DevOps 和 PaaS （云进行优化） 的成熟度级别最重要的好处。

它也具有变得非常明显应用程序是更轻松地更新和重新构建的体系结构将来时它们已在云中，即使在 IaaS 上运行。 此 true 的部分是因为已达到应用程序数据迁移。 已此外，获得技能所需的工作在云中，并对在"云区域性"。 操作进行移位你的组织

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>何时将迁移到 PaaS 到而不是 IaaS

下一步的各节讨论主要基于 PaaS 平台和服务的云就绪 DevOps 应用程序。 这些应用为您提供的大多数好处迁移到云。

如果你的目标是只需将移到云的现有应用程序，首先，确定现有应用程序将需要进行大量修改，以在 Azure App Service 中运行。 这些应用程序应为第一个候选项。

然后，如果你不希望或仍不能移动到 Windows 容器和/或 Azure Service Fabric 或 Kubernetes 等 orchestrators，尚未，则当你将使用纯 Vm (IaaS)。

但是，请记住，正确配置、 保护和维护 Vm 需要更多时间和 IT 专业人员相比于在 Azure 中使用 PaaS 服务。 如果你正在考虑 Azure 虚拟机，请确保修补程序、 更新和管理 VM 环境所需的持续不断的维护工作将其考虑到帐户。 Azure 虚拟机是 IaaS。

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>使用 Azure 迁移来分析和迁移到 Azure 的现有应用程序

迁移到云不一定是困难。 但是，许多组织很困难，若要开始-以深入了解到的环境和应用程序、 工作负荷和数据之间紧密相互依赖关系。 如果该可见性，没有它可能很难计划，转发的路径。 如果没有什么已成功迁移所需的详细信息，不能在你的组织内有右对话。 你不知道足够有关的潜在成本效益，或工作负荷可能只需提起并移动还是需要重大改进，才能成功迁移。 也就不足为奇对于许多组织将有所顾虑。

[Azure 迁移](https://aka.ms/azuremigrate)是一种新的服务，提供的指导，见解和帮助您迁移到 Azure 所需的机制。 Azure 迁移提供：

- 发现和评估的本地虚拟机

- 内置的依赖项的多层应用程序的高置信度发现映射

- 智能向右大小调整到 Azure 虚拟机

- 兼容性报告与修正的潜在问题的指南

- 数据库发现和迁移与 Azure 数据库管理服务集成

Azure 迁移可保证你的工作负荷可以迁移对业务影响最小并按预期方式在 Azure 中运行。 使用合适的工具和指南中，你可以实现最大同时确保该关键的性能的投资回报和满足可靠性需求。

图 2-2 显示了由 Azure 迁移的所有服务器和应用程序连接的内置的依赖项映射。

![定位云基础结构的通用应用程序](./media/image2-2.png)

> **图 2-2。** 定位云基础结构的通用应用程序

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>使用 Azure Site Recovery，以将你现有的虚拟机迁移到 Azure Vm

端到端的一部分[Azure 迁移](https://aka.ms/azuremigrate)， [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)是一个工具，可用于轻松地将你的 web 应用迁移到 Azure 中的 Vm。 可以使用 Site Recovery 将本地虚拟机和物理服务器复制到 Azure，或将其复制到辅助本地位置。 你甚至可以复制的受支持的 Azure vm，在本地上运行工作负荷*HYPER-V* VM，请在*VMware* VM，或在 Windows 或 Linux 的物理服务器上。 复制到 Azure 消除了的成本和维护辅助数据中心的复杂性。

专门为混合环境，部分也进行站点恢复本地和部分上的 Azure。 站点恢复可帮助确保业务连续性通过让你在 Vm 运行的应用和本地可用的物理服务器如果站点出现故障。 它将复制，以便它们仍然可用在辅助位置中，如果主站点不可用的虚拟机和物理服务器运行的工作负荷。 它将恢复到主站点时，再次运行的工作负荷。

图 2-3 说明多个 VM 迁移的执行使用 Azure Site Recovery。

![定位云基础结构的通用应用程序](./media/image2-3.png)

> **图 2-3。** 定位云基础结构的通用应用程序

### <a name="additional-resources"></a>其他资源

- **Azure 迁移数据表**

    [https://aka.ms/azuremigration\_数据表](https://aka.ms/azuremigration\_datasheet)

- **Azure 迁移**

    [http://azuremigrationcenter.com/](http://azuremigrationcenter.com/)

- **将迁移到 Azure 站点恢复**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure)

- **Azure Site Recovery 服务概述**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-overview](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)

- **在 AWS 到 Azure Vm 中的迁移 Vm**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure)

>[!div class="step-by-step"]
[上一页](index.md)
[下一页](migrate-your-relational-databases-to-azure.md)
