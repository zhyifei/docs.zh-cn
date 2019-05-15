---
title: 何时将 Windows 容器部署到 Azure VM（IaaS 云）
description: 更新现有.NET 应用程序与 Azure 云和 Windows 容器 |何时将 Windows 容器部署到 Azure Vm （IaaS 云）
ms.date: 04/28/2018
ms.openlocfilehash: e9a2903662306b607977a7751018e24161ab80ab
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639000"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a><span data-ttu-id="4f7fc-103">何时将 Windows 容器部署到 Azure VM（IaaS 云）</span><span class="sxs-lookup"><span data-stu-id="4f7fc-103">When to deploy Windows Containers to Azure VMs (IaaS cloud)</span></span>

<span data-ttu-id="4f7fc-104">如果你的组织使用 Azure 虚拟机，即使您还在使用 Windows 容器，您依然是使用 IaaS 时的处理。</span><span class="sxs-lookup"><span data-stu-id="4f7fc-104">If your organization is using Azure VMs, even if you are also using Windows Containers, you are still dealing with IaaS.</span></span> <span data-ttu-id="4f7fc-105">这意味着该处理基础结构操作、 VM OS 修补程序和基础结构的复杂性的高度可缩放的应用程序需要将部署到负载平衡基础结构中的多个 Vm。</span><span class="sxs-lookup"><span data-stu-id="4f7fc-105">That means that dealing with infrastructure operations, VM OS patches, and infrastructure complexity for highly scalable applications when you need to deploy to multiple VMs in a load balanced infrastructure.</span></span> <span data-ttu-id="4f7fc-106">在 Azure VM 中使用 Windows 容器的主要方案是：</span><span class="sxs-lookup"><span data-stu-id="4f7fc-106">The main scenarios for using Windows Containers in an Azure VM are:</span></span>

- <span data-ttu-id="4f7fc-107">**开发/测试环境**:云中的 VM 非常适合用于开发和测试在云中。</span><span class="sxs-lookup"><span data-stu-id="4f7fc-107">**Dev/test environment**: A VM in the cloud is perfect for development and testing in the cloud.</span></span> <span data-ttu-id="4f7fc-108">您可以快速创建或根据需要停止环境。</span><span class="sxs-lookup"><span data-stu-id="4f7fc-108">You can rapidly create or stop the environment depending on your needs.</span></span>

- <span data-ttu-id="4f7fc-109">**小型和中型可伸缩性需要**:在其中为生产环境可能需要几个 Vm 的情况下，管理少量的虚拟机可能是经济实惠直到可以将它们移动到更高级的 PaaS 环境，如业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="4f7fc-109">**Small and medium scalability needs**: In scenarios where you might need just a couple of VMs for your production environment, managing a small number of VMs might be affordable until you can move to more advanced PaaS environments, like orchestrators.</span></span>

- <span data-ttu-id="4f7fc-110">**生产环境中的现有部署工具**:您可能会将移动从您已经投资的工具来对虚拟机或裸机服务器 （如 Puppet 或类似工具） 进行复杂的部署在本地环境。</span><span class="sxs-lookup"><span data-stu-id="4f7fc-110">**Production environment with existing deployment tools**: You might be moving from an on-premises environment in which you have invested in tools to make complex deployments to VMs or bare-metal servers (like Puppet or similar tools).</span></span> <span data-ttu-id="4f7fc-111">若要移动到云进行少量的更改到生产环境部署过程，您可能会继续使用这些工具来部署到 Azure Vm。</span><span class="sxs-lookup"><span data-stu-id="4f7fc-111">To move to the cloud with minimal changes to production environment deployment procedures, you might continue to use those tools to deploy to Azure VMs.</span></span> <span data-ttu-id="4f7fc-112">但是，你将想要使用 Windows 容器作为部署单元，以改善部署体验。</span><span class="sxs-lookup"><span data-stu-id="4f7fc-112">However, you'll want to use Windows Containers as the unit of deployment to improve the deployment experience.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4f7fc-113">[上一页](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[下一页](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span><span class="sxs-lookup"><span data-stu-id="4f7fc-113">[Previous](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Next](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span></span>
