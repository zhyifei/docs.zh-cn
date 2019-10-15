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
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="d5fc5-103">迁移到混合云方案</span><span class="sxs-lookup"><span data-stu-id="d5fc5-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="d5fc5-104">某些组织和企业不能将其某些应用程序迁移到 Microsoft Azure 或任何其他公有云（如法规或其自己的策略）的公有云。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="d5fc5-105">但是，可能任何组织都可以受益于在公有云中和其他本地应用程序中应用某些应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="d5fc5-106">但混合环境可能会导致在环境中出现过多的复杂性，因为公有云和本地环境中使用不同的平台和技术。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="d5fc5-107">Microsoft 提供了最佳的混合云解决方案，在此解决方案中，你可以在本地和公有云中优化现有资产，同时确保 Azure 混合云中的一致性。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="d5fc5-108">你可以最大限度地利用现有技能，并获得一种灵活的统一方法来生成可在云中或本地运行的应用，这归功于 Azure Stack （本地）和 Azure （公有云）。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="d5fc5-109">在安全方面，你可以在混合云中集中管理和安全。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="d5fc5-110">可以通过提供对本地和云应用程序的单一登录，来控制从数据中心到云的所有资产。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="d5fc5-111">为此，可将 Active Directory 扩展到混合云，并使用标识管理。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="d5fc5-112">最后，你可以无缝分发和分析数据，对云和本地资产使用相同的查询语言，并在 Azure 中应用分析和深度学习来丰富数据，而不考虑数据源。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="d5fc5-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="d5fc5-113">Azure Stack</span></span>

<span data-ttu-id="d5fc5-114">Azure Stack 是一种混合云平台，可让你从组织的数据中心提供 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="d5fc5-115">Azure Stack 旨在支持关键方案（如边缘和未连接环境）的新选项，或者满足特定的安全性和符合性要求。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="d5fc5-116">图4-13 显示了 Microsoft 提供的真正混合云平台的概述。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![与 Azure Stack 和 Azure 的 Microsoft 混合云平台关系图。](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

<span data-ttu-id="d5fc5-118">**图4-13。**</span><span class="sxs-lookup"><span data-stu-id="d5fc5-118">**Figure 4-13.**</span></span> <span data-ttu-id="d5fc5-119">具有 Azure Stack 和 Azure 的 Microsoft 混合云平台</span><span class="sxs-lookup"><span data-stu-id="d5fc5-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="d5fc5-120">Azure Stack 提供了两个部署选项，以满足你的需求：</span><span class="sxs-lookup"><span data-stu-id="d5fc5-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="d5fc5-121">Azure Stack 集成系统</span><span class="sxs-lookup"><span data-stu-id="d5fc5-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="d5fc5-122">Azure Stack 开发工具包</span><span class="sxs-lookup"><span data-stu-id="d5fc5-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="d5fc5-123">Azure Stack 集成系统</span><span class="sxs-lookup"><span data-stu-id="d5fc5-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="d5fc5-124">Azure Stack 集成系统通过 Microsoft 和硬件合作伙伴的合作关系提供。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="d5fc5-125">合作关系创建了一个解决方案，它提供了云进度的创新，与管理中的简单性进行平衡。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="d5fc5-126">由于 Azure Stack 是作为硬件和软件的集成系统提供的，因此你可以获得正确的灵活性和控制能力，同时还会采用云中的创新。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="d5fc5-127">Azure Stack 集成系统范围为4到12个节点，由硬件合作伙伴和 Microsoft 共同支持。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="d5fc5-128">使用 Azure Stack 集成系统来实现生产工作负荷的新方案。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="d5fc5-129">Azure Stack 开发工具包</span><span class="sxs-lookup"><span data-stu-id="d5fc5-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="d5fc5-130">Microsoft Azure Stack 开发工具包是单节点部署的 Azure Stack，可用于评估和了解 Azure Stack。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="d5fc5-131">你还可以将 Azure Stack 开发工具包用作开发人员环境，可在其中使用与 Azure 一致的 Api 和工具进行开发。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="d5fc5-132">Azure Stack 开发工具包不能用作生产环境。</span><span class="sxs-lookup"><span data-stu-id="d5fc5-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d5fc5-133">其他资源</span><span class="sxs-lookup"><span data-stu-id="d5fc5-133">Additional resources</span></span>

- <span data-ttu-id="d5fc5-134">**Azure 混合云**</span><span class="sxs-lookup"><span data-stu-id="d5fc5-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="d5fc5-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="d5fc5-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="d5fc5-136">**Active Directory Windows 容器的服务帐户**</span><span class="sxs-lookup"><span data-stu-id="d5fc5-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="d5fc5-137">**创建支持 Active Directory 的容器**</span><span class="sxs-lookup"><span data-stu-id="d5fc5-137">**Create a container with Active Directory support**</span></span>

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- <span data-ttu-id="d5fc5-138">**Azure 混合权益许可**</span><span class="sxs-lookup"><span data-stu-id="d5fc5-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="d5fc5-139">[上一页](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[下一页](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d5fc5-139">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
