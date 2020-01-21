---
title: 迁移到混合云方案
description: 通过 Azure 云和 Windows 容器现代化现有 .NET 应用程序 | 迁移到混合云方案
ms.date: 04/30/2018
ms.openlocfilehash: dcbb799a45609f8bb811866c4041951abf1fda8b
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937367"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="2347f-103">迁移到混合云方案</span><span class="sxs-lookup"><span data-stu-id="2347f-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="2347f-104">由于法规或其自身的策略，某些组织和企业无法将部分应用程序迁移到公有云，如 Microsoft Azure 或任何其他公有云。</span><span class="sxs-lookup"><span data-stu-id="2347f-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="2347f-105">但是，任何组织都可能从公有云中的部分应用程序和本地的其他应用程序中获益。</span><span class="sxs-lookup"><span data-stu-id="2347f-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="2347f-106">但混合环境可能会导致环境变得过度复杂，因为公有云和本地环境使用的平台和技术不同。</span><span class="sxs-lookup"><span data-stu-id="2347f-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="2347f-107">Microsoft 提供了最佳的混合云解决方案，在此解决方案中，你可以在本地和公有云中优化现有资产，同时确保 Azure 混合云中的一致性。</span><span class="sxs-lookup"><span data-stu-id="2347f-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="2347f-108">你可以最大限度地利用现有技能，并获得一种灵活的统一方法来生成可在云中或本地运行的应用，这归功于 Azure Stack（本地）和 Azure（公有云）。</span><span class="sxs-lookup"><span data-stu-id="2347f-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="2347f-109">在安全方面，你可以在混合云中集中管理和安全性。</span><span class="sxs-lookup"><span data-stu-id="2347f-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="2347f-110">可以通过提供对本地和云应用程序的单一登录，来控制从数据中心到云的所有资产。</span><span class="sxs-lookup"><span data-stu-id="2347f-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="2347f-111">为此，可将 Active Directory 扩展到混合云，并使用标识管理。</span><span class="sxs-lookup"><span data-stu-id="2347f-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="2347f-112">最后，你可以无缝分发和分析数据，对云和本地资产使用相同的查询语言，并在 Azure 中应用分析和深度学习来丰富数据，而不考虑数据源。</span><span class="sxs-lookup"><span data-stu-id="2347f-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="2347f-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="2347f-113">Azure Stack</span></span>

<span data-ttu-id="2347f-114">Azure Stack，一种混合云平台，可从组织数据中心提供 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="2347f-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="2347f-115">Azure Stack 旨在支持关键方案（如边缘和未连接环境）中现代应用程序的新选项，或者满足特定的安全性和符合性要求。</span><span class="sxs-lookup"><span data-stu-id="2347f-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="2347f-116">图 4-13 显示了 Microsoft 提供的真正混合云平台的概述。</span><span class="sxs-lookup"><span data-stu-id="2347f-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![提供 Azure Stack 和 Azure 的 Microsoft 混合云平台关系图。](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

<span data-ttu-id="2347f-118">**图 4-13.**</span><span class="sxs-lookup"><span data-stu-id="2347f-118">**Figure 4-13.**</span></span> <span data-ttu-id="2347f-119">提供 Azure Stack 和 Azure 的 Microsoft 混合云平台</span><span class="sxs-lookup"><span data-stu-id="2347f-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="2347f-120">通过两个部署选项提供 Azure Stack 来满足你的需求：</span><span class="sxs-lookup"><span data-stu-id="2347f-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="2347f-121">Azure Stack 集成系统</span><span class="sxs-lookup"><span data-stu-id="2347f-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="2347f-122">Azure Stack 开发工具包</span><span class="sxs-lookup"><span data-stu-id="2347f-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="2347f-123">Azure Stack 集成系统</span><span class="sxs-lookup"><span data-stu-id="2347f-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="2347f-124">Azure Stack 集成系统通过 Microsoft 和硬件合作伙伴的合作关系提供。</span><span class="sxs-lookup"><span data-stu-id="2347f-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="2347f-125">合作关系创建了一个解决方案，它提供了云进度的创新，与管理中的简单性进行平衡。</span><span class="sxs-lookup"><span data-stu-id="2347f-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="2347f-126">由于 Azure Stack 是作为硬件和软件的集成系统提供的，因此用户可以获得适当的灵活性和控制能力，同时仍然采用来自云的创新。</span><span class="sxs-lookup"><span data-stu-id="2347f-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="2347f-127">Azure Stack 集成系统的大小从 4 个节点到 12 个节点不等，由硬件合作伙伴和 Microsoft 共同提供支持。</span><span class="sxs-lookup"><span data-stu-id="2347f-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="2347f-128">使用 Azure Stack 集成系统可实施针对生产工作负载的新方案。</span><span class="sxs-lookup"><span data-stu-id="2347f-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="2347f-129">Azure Stack 开发工具包</span><span class="sxs-lookup"><span data-stu-id="2347f-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="2347f-130">Microsoft Azure Stack 开发工具包是 Azure Stack 的单节点部署，可用于评估和了解 Azure Stack。</span><span class="sxs-lookup"><span data-stu-id="2347f-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="2347f-131">还可以将 Azure Stack 开发工具包用作开发人员环境，在其中使用与 Azure 一致的 API 和工具进行开发。</span><span class="sxs-lookup"><span data-stu-id="2347f-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="2347f-132">Azure Stack 开发工具包不应作为生产环境使用。</span><span class="sxs-lookup"><span data-stu-id="2347f-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="2347f-133">其他资源</span><span class="sxs-lookup"><span data-stu-id="2347f-133">Additional resources</span></span>

- <span data-ttu-id="2347f-134">**Azure 混合云**</span><span class="sxs-lookup"><span data-stu-id="2347f-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="2347f-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="2347f-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="2347f-136">**Windows 容器的 Active Directory 服务帐户**</span><span class="sxs-lookup"><span data-stu-id="2347f-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="2347f-137">**借助 Active Directory 支持创建容器**</span><span class="sxs-lookup"><span data-stu-id="2347f-137">**Create a container with Active Directory support**</span></span>

    <https://docs.microsoft.com/archive/blogs/containerstuff/create-a-container-with-active-directory-support>

- <span data-ttu-id="2347f-138">**Azure 混合权益许可**</span><span class="sxs-lookup"><span data-stu-id="2347f-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="2347f-139">[上一页](life-cycle-ci-cd-pipelines-devops-tools.md)
>[下一页](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2347f-139">[Previous](life-cycle-ci-cd-pipelines-devops-tools.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
