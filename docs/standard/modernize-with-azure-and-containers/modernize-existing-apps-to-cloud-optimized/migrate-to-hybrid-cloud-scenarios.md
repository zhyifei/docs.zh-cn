---
title: 迁移到混合云方案
description: 更新现有.NET 应用程序与 Azure 云和 Windows 容器 |将迁移到混合云方案
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 6cba29ad654b09b01f9b6969fa6688dd5f165fbb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64636594"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="18194-103">迁移到混合云方案</span><span class="sxs-lookup"><span data-stu-id="18194-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="18194-104">某些组织和企业不能将其某些应用程序到 Microsoft Azure 等公有云或由于法规或他们自己的策略的任何其他公有云迁移。</span><span class="sxs-lookup"><span data-stu-id="18194-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="18194-105">但是，可能是任何组织可能具有一些在公有云与其他应用程序的本地应用程序受益。</span><span class="sxs-lookup"><span data-stu-id="18194-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="18194-106">但在环境中由于不同的平台和技术在公有云与本地环境中使用过多的复杂性可能会导致混合的环境。</span><span class="sxs-lookup"><span data-stu-id="18194-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="18194-107">Microsoft 提供了最佳的混合云解决方案，其中一个可以在其中优化现有资产的本地和公有云中，确保 Azure 混合云的一致性。</span><span class="sxs-lookup"><span data-stu-id="18194-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="18194-108">你可以最大程度提高现有技能，并获取一种灵活、 统一的方法，来生成可在云中或本地，得益于 Azure Stack （内部） 和 Azure （公有云） 中运行的应用。</span><span class="sxs-lookup"><span data-stu-id="18194-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="18194-109">谈到安全性，您可以跨混合云来集中管理和安全。</span><span class="sxs-lookup"><span data-stu-id="18194-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="18194-110">你可以通过单一登录方式登录到在本地提供从数据中心到云，获取对所有资产的控制和云应用。</span><span class="sxs-lookup"><span data-stu-id="18194-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="18194-111">通过将 Active Directory 扩展到混合云，并使用标识管理实现此目的。</span><span class="sxs-lookup"><span data-stu-id="18194-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="18194-112">最后，可以将分发和无缝地分析数据、 对在本地和云资产，使用相同的查询语言和应用分析和深度学习来丰富您的数据，而不考虑其源。</span><span class="sxs-lookup"><span data-stu-id="18194-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="18194-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="18194-113">Azure Stack</span></span>

<span data-ttu-id="18194-114">Azure Stack 是一种混合云平台，可从组织的数据中心交付 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="18194-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="18194-115">Azure Stack 旨在支持现代应用程序中关键方案，如边缘和未连接的环境中或满足特定安全性和符合性要求的新选项。</span><span class="sxs-lookup"><span data-stu-id="18194-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="18194-116">图 4-13 显示了 Microsoft 提供的真正的混合云平台的概述。</span><span class="sxs-lookup"><span data-stu-id="18194-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![使用 Azure Stack 和 Azure 的 Microsoft 混合云平台](./media/image13.jpg)

> <span data-ttu-id="18194-118">**图 4 月 13 日。**</span><span class="sxs-lookup"><span data-stu-id="18194-118">**Figure 4-13.**</span></span> <span data-ttu-id="18194-119">使用 Azure Stack 和 Azure 的 Microsoft 混合云平台</span><span class="sxs-lookup"><span data-stu-id="18194-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="18194-120">Azure Stack 中两个部署选项，以满足你的需求提供：</span><span class="sxs-lookup"><span data-stu-id="18194-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="18194-121">Azure Stack 集成系统</span><span class="sxs-lookup"><span data-stu-id="18194-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="18194-122">Azure Stack 开发工具包</span><span class="sxs-lookup"><span data-stu-id="18194-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="18194-123">Azure Stack 集成系统</span><span class="sxs-lookup"><span data-stu-id="18194-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="18194-124">Azure Stack 集成系统将通过 Microsoft 和硬件合作伙伴提供的合作关系提供。</span><span class="sxs-lookup"><span data-stu-id="18194-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="18194-125">合作关系创建一个解决方案，提供了与管理的简化保持平衡的兼顾云时代的创新。</span><span class="sxs-lookup"><span data-stu-id="18194-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="18194-126">由于 Azure Stack 作为集成系统的硬件和软件提供，您将获取适量的灵活性和控制，时仍采用云环境带来的创新。</span><span class="sxs-lookup"><span data-stu-id="18194-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="18194-127">Azure Stack 集成系统范围的大小从 4 到 12 个节点，由硬件合作伙伴和 Microsoft 共同提供支持。</span><span class="sxs-lookup"><span data-stu-id="18194-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="18194-128">使用 Azure Stack 集成系统来实现生产工作负荷的新方案。</span><span class="sxs-lookup"><span data-stu-id="18194-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="18194-129">Azure Stack 开发工具包</span><span class="sxs-lookup"><span data-stu-id="18194-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="18194-130">Microsoft Azure Stack 开发工具包是单节点部署的 Azure Stack，可用于评估和了解 Azure Stack。</span><span class="sxs-lookup"><span data-stu-id="18194-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="18194-131">作为开发人员环境，其中您可以使用 Api 进行开发和工具，是与 Azure 一致，您还可以使用 Azure Stack 开发工具包。</span><span class="sxs-lookup"><span data-stu-id="18194-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="18194-132">Azure Stack 开发工具包不能用作生产环境。</span><span class="sxs-lookup"><span data-stu-id="18194-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="18194-133">其他资源</span><span class="sxs-lookup"><span data-stu-id="18194-133">Additional resources</span></span>

- <span data-ttu-id="18194-134">**Azure 混合云**</span><span class="sxs-lookup"><span data-stu-id="18194-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="18194-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="18194-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="18194-136">**Active Directory 服务帐户用于 Windows 容器**</span><span class="sxs-lookup"><span data-stu-id="18194-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="18194-137">**创建具有 Active Directory 支持的容器**</span><span class="sxs-lookup"><span data-stu-id="18194-137">**Create a container with Active Directory support**</span></span>

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- <span data-ttu-id="18194-138">**Azure 混合权益许可**</span><span class="sxs-lookup"><span data-stu-id="18194-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="18194-139">[上一页](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[下一页](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="18194-139">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
