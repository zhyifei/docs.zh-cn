---
title: 何时部署到 Azure 容器实例 (ACI) 的 Windows 容器
description: 更新现有的.NET 应用程序与 Azure 云和 Windows 容器 |何时部署到 Azure 容器实例 (ACI) 的 Windows 容器
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 3dc23c96543d9611763b571105f52b150dfec06f
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="62254-103">何时部署到 Azure 容器实例 (ACI) 的 Windows 容器</span><span class="sxs-lookup"><span data-stu-id="62254-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="62254-104">主要价值主张是你可以立即部署到它的容器，并且无需维护该环境的 azure 容器实例，你无需升级/修补程序的其中操作系统或 Vm，来说，是透明的只需部署到准备就绪，可以使用环境的容器。</span><span class="sxs-lookup"><span data-stu-id="62254-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlaying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="62254-105">当你使用 Azure Vm 时容器，因此基本上的原因和方案时要使用 ACI 是类似于主要方案，有关使用 Azure 容器实例的主要方案是：</span><span class="sxs-lookup"><span data-stu-id="62254-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

-   <span data-ttu-id="62254-106">**开发/测试方案**</span><span class="sxs-lookup"><span data-stu-id="62254-106">**Dev/Test scenarios**</span></span>
-   <span data-ttu-id="62254-107">**任务自动化**</span><span class="sxs-lookup"><span data-stu-id="62254-107">**Task automation**</span></span>
-   <span data-ttu-id="62254-108">**CI/CD 代理**</span><span class="sxs-lookup"><span data-stu-id="62254-108">**CI/CD agents**</span></span>
-   <span data-ttu-id="62254-109">**小型/横向批处理**</span><span class="sxs-lookup"><span data-stu-id="62254-109">**Small/scale batch processing**</span></span>
-   <span data-ttu-id="62254-110">**简单的 web 应用**</span><span class="sxs-lookup"><span data-stu-id="62254-110">**Simple web apps**</span></span>

<span data-ttu-id="62254-111">简单的 web 应用方案是 ACI 公平方案，但会考虑，因为在 ACI 只能有每个容器图像的单个容器实例，您将不具有高可用性，并且仅具有有限的可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="62254-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="62254-112">但是，即使 ACI 被认为基础结构，因为它仅提供单个容器实例，没有与正则与 Windows Server 的 Azure Vm 相比是非常有用。</span><span class="sxs-lookup"><span data-stu-id="62254-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="62254-113">与 ACI，只需部署到自我维护的环境的容器和你只需支付这些容器。</span><span class="sxs-lookup"><span data-stu-id="62254-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="62254-114">你无需维护/更新/修补 Vm，因此它是一个多更好的平台，在大多数情况下，你可能正在使用虚拟机与容器。</span><span class="sxs-lookup"><span data-stu-id="62254-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="62254-115">使用 ACI 是一个直截了当，只需部署一个容器，则无需创建虚拟机环境只需部署容器。</span><span class="sxs-lookup"><span data-stu-id="62254-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="62254-116">Azure 容器实例 (ACI) 的主要优点有：</span><span class="sxs-lookup"><span data-stu-id="62254-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

-   <span data-ttu-id="62254-117">无需管理服务器运行容器</span><span class="sxs-lookup"><span data-stu-id="62254-117">Run containers without managing servers</span></span>
-   <span data-ttu-id="62254-118">提高了灵活性与按需容器</span><span class="sxs-lookup"><span data-stu-id="62254-118">Increase agility with containers on demand</span></span>
-   <span data-ttu-id="62254-119">将容器部署到通过前所未有的简单快速地云 — 使用单个命令。</span><span class="sxs-lookup"><span data-stu-id="62254-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span> 
-   <span data-ttu-id="62254-120">保护虚拟机监控程序隔离的应用程序</span><span class="sxs-lookup"><span data-stu-id="62254-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="62254-121">简而言之，使用 ACI 可以快速而无需管理虚拟机或无需学习新工具开发应用。</span><span class="sxs-lookup"><span data-stu-id="62254-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="62254-122">它是只是你应用程序，在云中运行的容器中。</span><span class="sxs-lookup"><span data-stu-id="62254-122">It's just your application, in a container, running in the cloud.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="62254-123">[上一页](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[下一页](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="62254-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
