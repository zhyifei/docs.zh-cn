---
title: 何时将 Windows 容器部署到 Azure 容器实例 (ACI)
description: 更新现有.NET 应用程序与 Azure 云和 Windows 容器 |何时将 Windows 容器部署到 Azure 容器实例 (ACI)
ms.date: 04/29/2018
ms.openlocfilehash: 9bfa0688d07bd04964a1b28f688f125b5bcd2299
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638926"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="db3a9-103">何时将 Windows 容器部署到 Azure 容器实例 (ACI)</span><span class="sxs-lookup"><span data-stu-id="db3a9-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="db3a9-104">Azure 容器实例时的主要价值主张是可以立即将容器部署到它并不需要以维护该环境，您无需升级/修补基础操作系统或虚拟机，所有的是透明的并将其只需部署到随时可用的环境中的容器。</span><span class="sxs-lookup"><span data-stu-id="db3a9-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="db3a9-105">原因和方案时想要使用 ACI 是类似的主要方案基本上使用 Azure Vm 和容器时，使用 Azure 容器实例的主要方案是：</span><span class="sxs-lookup"><span data-stu-id="db3a9-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="db3a9-106">**开发/测试方案**</span><span class="sxs-lookup"><span data-stu-id="db3a9-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="db3a9-107">**任务自动化**</span><span class="sxs-lookup"><span data-stu-id="db3a9-107">**Task automation**</span></span>
- <span data-ttu-id="db3a9-108">**CI/CD 代理**</span><span class="sxs-lookup"><span data-stu-id="db3a9-108">**CI/CD agents**</span></span>
- <span data-ttu-id="db3a9-109">**小型/规模批处理**</span><span class="sxs-lookup"><span data-stu-id="db3a9-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="db3a9-110">**简单的 web 应用**</span><span class="sxs-lookup"><span data-stu-id="db3a9-110">**Simple web apps**</span></span>

<span data-ttu-id="db3a9-111">简单的 web 应用方案是公平的 ACI 方案，但请考虑在 ACI 中只能有一个容器实例，每个容器映像，因为您不具有高可用性，仅具有有限的可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="db3a9-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="db3a9-112">但是，即使 ACI 被视为基础结构，因为它只提供单个容器实例，是一个巨大的优势，比使用 Windows Server 的常规 Azure Vm。</span><span class="sxs-lookup"><span data-stu-id="db3a9-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="db3a9-113">使用 ACI，只需将容器部署到自我维护环境和您只需支付这些容器。</span><span class="sxs-lookup"><span data-stu-id="db3a9-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="db3a9-114">因此，更好平台，你可能正在使用虚拟机与容器的大多数情况下，不需要维护/更新/修补 Vm。</span><span class="sxs-lookup"><span data-stu-id="db3a9-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="db3a9-115">使用 ACI 非常简单，只需部署一个容器，则无需创建虚拟机环境只需部署容器。</span><span class="sxs-lookup"><span data-stu-id="db3a9-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="db3a9-116">Azure 容器实例 (ACI) 的主要优点是：</span><span class="sxs-lookup"><span data-stu-id="db3a9-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="db3a9-117">而无需管理服务器运行容器</span><span class="sxs-lookup"><span data-stu-id="db3a9-117">Run containers without managing servers</span></span>
- <span data-ttu-id="db3a9-118">提高灵活性的按需的容器</span><span class="sxs-lookup"><span data-stu-id="db3a9-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="db3a9-119">将容器部署到具有速度和便捷性史无前例的云-使用单个命令。</span><span class="sxs-lookup"><span data-stu-id="db3a9-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="db3a9-120">使用虚拟机监控程序隔离安全的应用程序</span><span class="sxs-lookup"><span data-stu-id="db3a9-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="db3a9-121">简单地说，使用 ACI 可以快速而无需管理虚拟机或无需学习新的工具开发应用。</span><span class="sxs-lookup"><span data-stu-id="db3a9-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="db3a9-122">它是只是你的应用程序在云中运行的容器。</span><span class="sxs-lookup"><span data-stu-id="db3a9-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="db3a9-123">[上一页](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [下一页](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="db3a9-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
