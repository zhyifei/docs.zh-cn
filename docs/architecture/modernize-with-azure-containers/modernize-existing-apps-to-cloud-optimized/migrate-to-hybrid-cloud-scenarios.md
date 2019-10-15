---
title: 迁移到混合云方案
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |迁移到混合云方案
ms.date: 04/30/2018
ms.openlocfilehash: 5f0819495080bc29ed1239b4a7ab8af31141881b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318470"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>迁移到混合云方案

某些组织和企业不能将其某些应用程序迁移到 Microsoft Azure 或任何其他公有云（如法规或其自己的策略）的公有云。 但是，可能任何组织都可以受益于在公有云中和其他本地应用程序中应用某些应用程序。 但混合环境可能会导致在环境中出现过多的复杂性，因为公有云和本地环境中使用不同的平台和技术。

Microsoft 提供了最佳的混合云解决方案，在此解决方案中，你可以在本地和公有云中优化现有资产，同时确保 Azure 混合云中的一致性。 你可以最大限度地利用现有技能，并获得一种灵活的统一方法来生成可在云中或本地运行的应用，这归功于 Azure Stack （本地）和 Azure （公有云）。

在安全方面，你可以在混合云中集中管理和安全。 可以通过提供对本地和云应用程序的单一登录，来控制从数据中心到云的所有资产。 为此，可将 Active Directory 扩展到混合云，并使用标识管理。

最后，你可以无缝分发和分析数据，对云和本地资产使用相同的查询语言，并在 Azure 中应用分析和深度学习来丰富数据，而不考虑数据源。

## <a name="azure-stack"></a>Azure Stack

Azure Stack 是一种混合云平台，可让你从组织的数据中心提供 Azure 服务。 Azure Stack 旨在支持关键方案（如边缘和未连接环境）的新选项，或者满足特定的安全性和符合性要求。

图4-13 显示了 Microsoft 提供的真正混合云平台的概述。

![与 Azure Stack 和 Azure 的 Microsoft 混合云平台关系图。](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

**图4-13。** 具有 Azure Stack 和 Azure 的 Microsoft 混合云平台

Azure Stack 提供了两个部署选项，以满足你的需求：

- Azure Stack 集成系统

- Azure Stack 开发工具包

### <a name="azure-stack-integrated-systems"></a>Azure Stack 集成系统

Azure Stack 集成系统通过 Microsoft 和硬件合作伙伴的合作关系提供。 合作关系创建了一个解决方案，它提供了云进度的创新，与管理中的简单性进行平衡。 由于 Azure Stack 是作为硬件和软件的集成系统提供的，因此你可以获得正确的灵活性和控制能力，同时还会采用云中的创新。 Azure Stack 集成系统范围为4到12个节点，由硬件合作伙伴和 Microsoft 共同支持。 使用 Azure Stack 集成系统来实现生产工作负荷的新方案。

### <a name="azure-stack-development-kit"></a>Azure Stack 开发工具包

Microsoft Azure Stack 开发工具包是单节点部署的 Azure Stack，可用于评估和了解 Azure Stack。 你还可以将 Azure Stack 开发工具包用作开发人员环境，可在其中使用与 Azure 一致的 Api 和工具进行开发。 Azure Stack 开发工具包不能用作生产环境。

### <a name="additional-resources"></a>其他资源

- **Azure 混合云**

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- **Azure Stack**

    <https://azure.microsoft.com/overview/azure-stack/>

- **Active Directory Windows 容器的服务帐户**

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- **创建支持 Active Directory 的容器**

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- **Azure 混合权益许可**

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
>[上一页](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[下一页](../walkthroughs-technical-get-started-overview.md)
