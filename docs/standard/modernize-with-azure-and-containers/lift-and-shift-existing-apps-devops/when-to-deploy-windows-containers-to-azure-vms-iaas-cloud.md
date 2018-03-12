---
title: "何时将 Windows 容器部署到 Azure Vm （IaaS 云）"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |何时将 Windows 容器部署到 Azure Vm （IaaS 云）"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 37a37f91bb910004128c96511f585bea03a51d3a
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a><span data-ttu-id="8a6a7-103">何时将 Windows 容器部署到 Azure Vm （IaaS 云）</span><span class="sxs-lookup"><span data-stu-id="8a6a7-103">When to deploy Windows Containers to Azure VMs (IaaS cloud)</span></span>

<span data-ttu-id="8a6a7-104">如果你的组织使用 Azure Vm，即使你使用 Windows 容器，则仍要处理 IaaS。</span><span class="sxs-lookup"><span data-stu-id="8a6a7-104">If your organization is using Azure VMs, even if you are also using Windows Containers, you are still dealing with IaaS.</span></span> <span data-ttu-id="8a6a7-105">当你需要将部署到负载平衡基础结构中的多个 Vm 时，这会高度可伸缩的应用程序意味着该处理基础结构操作、 VM OS 修补程序和基础结构的复杂性。</span><span class="sxs-lookup"><span data-stu-id="8a6a7-105">That means that dealing with infrastructure operations, VM OS patches, and infrastructure complexity for highly scalable applications when you need to deploy to multiple VMs in a load balanced infrastructure.</span></span> <span data-ttu-id="8a6a7-106">在 Azure VM 中使用 Windows 容器功能的主要方案是：</span><span class="sxs-lookup"><span data-stu-id="8a6a7-106">The main scenarios for using Windows Containers in an Azure VM are:</span></span>

-   <span data-ttu-id="8a6a7-107">**开发/测试环境**： 在云中的 VM 非常适用于开发和测试在云中。</span><span class="sxs-lookup"><span data-stu-id="8a6a7-107">**Dev/test environment**: A VM in the cloud is perfect for development and testing in the cloud.</span></span> <span data-ttu-id="8a6a7-108">你可以快速创建或停止环境，具体取决于你的需求。</span><span class="sxs-lookup"><span data-stu-id="8a6a7-108">You can rapidly create or stop the environment depending on your needs.</span></span>

-   <span data-ttu-id="8a6a7-109">**小型和中型可伸缩性需要**： 在其中你可能需要几 Vm 内的为生产环境的情况下，管理少量的 Vm 之前，可能存在实惠可以将它们移动到更高级的 PaaS 环境，类似于 orchestrators。</span><span class="sxs-lookup"><span data-stu-id="8a6a7-109">**Small and medium scalability needs**: In scenarios where you might need just a couple of VMs for your production environment, managing a small number of VMs might be affordable until you can move to more advanced PaaS environments, like orchestrators.</span></span>

-   <span data-ttu-id="8a6a7-110">**使用现有的部署工具的生产环境**： 你可能会从你已投资工具对虚拟机或裸机服务器 （如 Puppet 或类似工具） 进行复杂的部署中的本地环境中移动。</span><span class="sxs-lookup"><span data-stu-id="8a6a7-110">**Production environment with existing deployment tools**: You might be moving from an on-premises environment in which you have invested in tools to make complex deployments to VMs or bare-metal servers (like Puppet or similar tools).</span></span> <span data-ttu-id="8a6a7-111">若要进行少量的更改到生产环境部署过程迁移到云，你可能会继续使用这些工具将部署到 Azure Vm。</span><span class="sxs-lookup"><span data-stu-id="8a6a7-111">To move to the cloud with minimal changes to production environment deployment procedures, you might continue to use those tools to deploy to Azure VMs.</span></span> <span data-ttu-id="8a6a7-112">但是，你将想要使用 Windows 容器作为部署单元，以改进部署体验。</span><span class="sxs-lookup"><span data-stu-id="8a6a7-112">However, you'll want to use Windows Containers as the unit of deployment to improve the deployment experience.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="8a6a7-113">[上一页](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[下一页](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="8a6a7-113">[Previous](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
