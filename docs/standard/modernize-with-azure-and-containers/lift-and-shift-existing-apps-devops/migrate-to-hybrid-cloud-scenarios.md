---
title: "将迁移到混合云方案"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |将迁移到混合云方案"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/2/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 61b22e48afd543ac077ebb4fe1b7be200f9ec859
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>将迁移到混合云方案

某些组织和企业不能迁移部分其应用程序，如 Microsoft Azure 公有云或由于法规或自己的策略的任何其他公共云。 但是，很可能任何组织可能会有一些他们在公有云和其他应用程序本地的应用程序受益。 但混合的环境可以导致过多的复杂性，由于不同的平台和技术在公有云与本地环境中使用的环境中。

Microsoft 提供最佳的混合云解决方案，一个在其中你可以优化你的现有资产本地和在公有云中，同时确保 Azure 混合云的一致性。 你可以最大化现有技能，并获取构建应用程序可以在云中或本地，感谢 Azure 堆栈 （本地） 和 Azure （公有云） 中运行的灵活、 统一方法。

当涉及到安全时，您可以跨混合云集中管理和安全。 你可以控制所有资产，获得你数据中心到云，通过提供单一登录到本地和云应用。 通过将 Active Directory 扩展到混合云，以及通过使用标识管理实现此目的。

最后，你可以将分发和无缝地分析数据，请针对云和本地资产使用相同的查询语言并应用分析和深层学习 Azure 丰富您的数据，而不考虑其源中。

## <a name="azure-stack"></a>Azure Stack

Azure 堆栈是混合云平台，可让你从你的组织的数据中心提供 Azure 服务。 Azure 堆栈旨在为你在关键方案，例如边缘以及未连接的环境中或满足特定的安全和合规性要求的现代应用程序支持新的选项。

图 4-13 显示 true 混合云平台，Microsoft 提供了概述。

![Microsoft Azure 堆栈与 Azure 的混合云平台](./media/image13.jpg)

> **图 4-13。** Microsoft Azure 堆栈与 Azure 的混合云平台

Azure 堆栈将提供两个部署选项，以满足你的需求：

-   Azure 集成的堆栈系统

-   Azure 堆栈开发工具包

### <a name="azure-stack-integrated-systems"></a>Azure 集成的堆栈系统

Azure 集成的堆栈系统可以通过 Microsoft 和硬件合作伙伴合作关系。 合作关系创建一个解决方案，提供具有在管理的简便性平衡的云节控制进度创新。 由于 Azure 堆栈提供作为一个集成系统的硬件和软件，你仍采用云环境带来的创新时获取正确数量的灵活性和控制。 Azure 集成的堆栈系统范围的大小从 4 到 12 个节点，和硬件合作伙伴和 Microsoft 共同支持。 使用集成的 Azure 堆栈系统来实现的生产工作负荷的新方案。

### <a name="azure-stack-development-kit"></a>Azure 堆栈开发工具包

Microsoft Azure Stack 开发工具包是单节点部署的 Azure Stack，可用于评估和了解 Azure Stack。 作为开发人员环境，其中你可以开发使用 Api，工具的是与 Azure 一致，你还可以使用 Azure 堆栈开发工具包。 Azure Stack 开发工具包不能用作生产环境。

### <a name="additional-resources"></a>其他资源

-   **Azure 混合云**

    [https://www.microsoft.com/cloud-platform/hybrid-cloud](https://www.microsoft.com/cloud-platform/hybrid-cloud)

-   **Azure Stack**

    [https://azure.microsoft.com/overview/azure-stack/](https://azure.microsoft.com/overview/azure-stack/)

-   **Active Directory 服务帐户为 Windows 容器**

    [https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts)

-   **创建具有 Active Directory 支持的容器**

    [https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/](https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/)

-   **Azure 混合权益许可**

    [https://azure.microsoft.com/pricing/hybrid-use-benefit/](https://azure.microsoft.com/pricing/hybrid-use-benefit/)

>[!div class="step-by-step"]
[上一页](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[下一页](../walkthroughs-technical-get-started-overview.md)
