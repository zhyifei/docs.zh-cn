---
title: "将迁移到混合云方案"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |将迁移到混合云方案"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/2/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6216068786745ac4ebc00263a14b4afe247193f5
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="30eaf-103">将迁移到混合云方案</span><span class="sxs-lookup"><span data-stu-id="30eaf-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="30eaf-104">某些组织和企业不能迁移部分其应用程序，如 Microsoft Azure 公有云或由于法规或自己的策略的任何其他公共云。</span><span class="sxs-lookup"><span data-stu-id="30eaf-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="30eaf-105">但是，很可能任何组织可能会有一些他们在公有云和其他应用程序本地的应用程序受益。</span><span class="sxs-lookup"><span data-stu-id="30eaf-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="30eaf-106">但混合的环境可以导致过多的复杂性，由于不同的平台和技术在公有云与本地环境中使用的环境中。</span><span class="sxs-lookup"><span data-stu-id="30eaf-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="30eaf-107">Microsoft 提供最佳的混合云解决方案，一个在其中你可以优化你的现有资产本地和在公有云中，同时确保 Azure 混合云的一致性。</span><span class="sxs-lookup"><span data-stu-id="30eaf-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="30eaf-108">你可以最大化现有技能，并获取构建应用程序可以在云中或本地，感谢 Azure 堆栈 （本地） 和 Azure （公有云） 中运行的灵活、 统一方法。</span><span class="sxs-lookup"><span data-stu-id="30eaf-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="30eaf-109">当涉及到安全时，您可以跨混合云集中管理和安全。</span><span class="sxs-lookup"><span data-stu-id="30eaf-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="30eaf-110">你可以控制所有资产，获得你数据中心到云，通过提供单一登录到本地和云应用。</span><span class="sxs-lookup"><span data-stu-id="30eaf-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="30eaf-111">通过将 Active Directory 扩展到混合云，以及通过使用标识管理实现此目的。</span><span class="sxs-lookup"><span data-stu-id="30eaf-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="30eaf-112">最后，你可以将分发和无缝地分析数据，请针对云和本地资产使用相同的查询语言并应用分析和深层学习 Azure 丰富您的数据，而不考虑其源中。</span><span class="sxs-lookup"><span data-stu-id="30eaf-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="30eaf-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="30eaf-113">Azure Stack</span></span>

<span data-ttu-id="30eaf-114">Azure 堆栈是混合云平台，可让你从你的组织的数据中心提供 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="30eaf-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="30eaf-115">Azure 堆栈旨在为你在关键方案，例如边缘以及未连接的环境中或满足特定的安全和合规性要求的现代应用程序支持新的选项。</span><span class="sxs-lookup"><span data-stu-id="30eaf-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="30eaf-116">图 4-13 显示 true 混合云平台，Microsoft 提供了概述。</span><span class="sxs-lookup"><span data-stu-id="30eaf-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Microsoft Azure 堆栈与 Azure 的混合云平台](./media/image13.jpg)

> <span data-ttu-id="30eaf-118">**图 4-13。**</span><span class="sxs-lookup"><span data-stu-id="30eaf-118">**Figure 4-13.**</span></span> <span data-ttu-id="30eaf-119">Microsoft Azure 堆栈与 Azure 的混合云平台</span><span class="sxs-lookup"><span data-stu-id="30eaf-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="30eaf-120">Azure 堆栈将提供两个部署选项，以满足你的需求：</span><span class="sxs-lookup"><span data-stu-id="30eaf-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

-   <span data-ttu-id="30eaf-121">Azure 集成的堆栈系统</span><span class="sxs-lookup"><span data-stu-id="30eaf-121">Azure Stack integrated systems</span></span>

-   <span data-ttu-id="30eaf-122">Azure 堆栈开发工具包</span><span class="sxs-lookup"><span data-stu-id="30eaf-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="30eaf-123">Azure 集成的堆栈系统</span><span class="sxs-lookup"><span data-stu-id="30eaf-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="30eaf-124">Azure 集成的堆栈系统可以通过 Microsoft 和硬件合作伙伴合作关系。</span><span class="sxs-lookup"><span data-stu-id="30eaf-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="30eaf-125">合作关系创建一个解决方案，提供具有在管理的简便性平衡的云节控制进度创新。</span><span class="sxs-lookup"><span data-stu-id="30eaf-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="30eaf-126">由于 Azure 堆栈提供作为一个集成系统的硬件和软件，你仍采用云环境带来的创新时获取正确数量的灵活性和控制。</span><span class="sxs-lookup"><span data-stu-id="30eaf-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="30eaf-127">Azure 集成的堆栈系统范围的大小从 4 到 12 个节点，和硬件合作伙伴和 Microsoft 共同支持。</span><span class="sxs-lookup"><span data-stu-id="30eaf-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="30eaf-128">使用集成的 Azure 堆栈系统来实现的生产工作负荷的新方案。</span><span class="sxs-lookup"><span data-stu-id="30eaf-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="30eaf-129">Azure 堆栈开发工具包</span><span class="sxs-lookup"><span data-stu-id="30eaf-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="30eaf-130">Microsoft Azure Stack 开发工具包是单节点部署的 Azure Stack，可用于评估和了解 Azure Stack。</span><span class="sxs-lookup"><span data-stu-id="30eaf-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="30eaf-131">作为开发人员环境，其中你可以开发使用 Api，工具的是与 Azure 一致，你还可以使用 Azure 堆栈开发工具包。</span><span class="sxs-lookup"><span data-stu-id="30eaf-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="30eaf-132">Azure Stack 开发工具包不能用作生产环境。</span><span class="sxs-lookup"><span data-stu-id="30eaf-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="30eaf-133">其他资源</span><span class="sxs-lookup"><span data-stu-id="30eaf-133">Additional resources</span></span>

-   <span data-ttu-id="30eaf-134">**Azure 混合云**</span><span class="sxs-lookup"><span data-stu-id="30eaf-134">**Azure hybrid cloud**</span></span>

    [<span data-ttu-id="30eaf-135">https://www.microsoft.com/cloud-platform/hybrid-cloud</span><span class="sxs-lookup"><span data-stu-id="30eaf-135">https://www.microsoft.com/cloud-platform/hybrid-cloud</span></span>](https://www.microsoft.com/cloud-platform/hybrid-cloud)

-   <span data-ttu-id="30eaf-136">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="30eaf-136">**Azure Stack**</span></span>

    [<span data-ttu-id="30eaf-137">https://azure.microsoft.com/overview/azure-stack/</span><span class="sxs-lookup"><span data-stu-id="30eaf-137">https://azure.microsoft.com/overview/azure-stack/</span></span>](https://azure.microsoft.com/overview/azure-stack/)

-   <span data-ttu-id="30eaf-138">**Active Directory 服务帐户为 Windows 容器**</span><span class="sxs-lookup"><span data-stu-id="30eaf-138">**Active Directory Service Accounts for Windows Containers**</span></span>

    [<span data-ttu-id="30eaf-139">https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts</span><span class="sxs-lookup"><span data-stu-id="30eaf-139">https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts)

-   <span data-ttu-id="30eaf-140">**创建具有 Active Directory 支持的容器**</span><span class="sxs-lookup"><span data-stu-id="30eaf-140">**Create a container with Active Directory support**</span></span>

    [<span data-ttu-id="30eaf-141">https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/</span><span class="sxs-lookup"><span data-stu-id="30eaf-141">https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/</span></span>](https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/)

-   <span data-ttu-id="30eaf-142">**Azure 混合权益许可**</span><span class="sxs-lookup"><span data-stu-id="30eaf-142">**Azure Hybrid Benefit licensing**</span></span>

    [<span data-ttu-id="30eaf-143">https://azure.microsoft.com/pricing/hybrid-use-benefit/</span><span class="sxs-lookup"><span data-stu-id="30eaf-143">https://azure.microsoft.com/pricing/hybrid-use-benefit/</span></span>](https://azure.microsoft.com/pricing/hybrid-use-benefit/)

>[!div class="step-by-step"]
<span data-ttu-id="30eaf-144">[上一页](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[下一页](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="30eaf-144">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
