---
title: 何时将 Windows 容器部署到 Azure 容器实例 (ACI)
description: 通过 Azure 云和 Windows 容器现代化现有 .NET 应用程序 | 何时将 Windows 容器部署到 Azure 容器实例 (ACI)
ms.date: 04/29/2018
ms.openlocfilehash: 3b6ae1ced9c4e01f5ab400e2575947a396064ebd
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577930"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="3621b-103">何时将 Windows 容器部署到 Azure 容器实例 (ACI)</span><span class="sxs-lookup"><span data-stu-id="3621b-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="3621b-104">Azure 容器实例的主要价值主张是，你可以立即将容器部署到该环境中，而无需维护该环境，无需升级/修补基础操作系统或 VM，所有这些都是透明的，你只需将容器部署到随时可用的环境中即可。</span><span class="sxs-lookup"><span data-stu-id="3621b-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="3621b-105">想要使用 ACI 的原因和方案类似于将 Azure VM 与容器一起使用时的主要方案，因此，使用 Azure 容器实例的主要方案基本如下：</span><span class="sxs-lookup"><span data-stu-id="3621b-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="3621b-106">**开发/测试方案**</span><span class="sxs-lookup"><span data-stu-id="3621b-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="3621b-107">**任务自动化**</span><span class="sxs-lookup"><span data-stu-id="3621b-107">**Task automation**</span></span>
- <span data-ttu-id="3621b-108">**CI/CD 代理**</span><span class="sxs-lookup"><span data-stu-id="3621b-108">**CI/CD agents**</span></span>
- <span data-ttu-id="3621b-109">**小/大规模批处理**</span><span class="sxs-lookup"><span data-stu-id="3621b-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="3621b-110">**简单的 Web 应用**</span><span class="sxs-lookup"><span data-stu-id="3621b-110">**Simple web apps**</span></span>

<span data-ttu-id="3621b-111">简单的 Web 应用方案是一种公平的 ACI 方案，但请考虑这一点：因为在 ACI 中，每个容器映像只能有一个容器实例，你没有高可用性，并且仅具有有限的可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="3621b-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="3621b-112">不过，即使 ACI 被视为基础结构，因为它只提供单个容器实例，与使用 Windows Server 的常规 Azure VM 相比，具有巨大的优势。</span><span class="sxs-lookup"><span data-stu-id="3621b-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="3621b-113">使用 ACI，只需将容器部署到自行维护的环境中即可，只需为这些容器付费。</span><span class="sxs-lookup"><span data-stu-id="3621b-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="3621b-114">你无需维护/更新/修补 VM，因此，在大多数你可能会将 VM 与容器一起使用的情况下，这是一个更好的平台。</span><span class="sxs-lookup"><span data-stu-id="3621b-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="3621b-115">使用 ACI 相当直接，只需部署容器，无需创建仅部署容器的 VM 环境。</span><span class="sxs-lookup"><span data-stu-id="3621b-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="3621b-116">Azure 容器实例 (ACI) 的主要优点是：</span><span class="sxs-lookup"><span data-stu-id="3621b-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="3621b-117">在不管理服务器的情况下运行容器</span><span class="sxs-lookup"><span data-stu-id="3621b-117">Run containers without managing servers</span></span>
- <span data-ttu-id="3621b-118">根据需要提高容器的灵活性</span><span class="sxs-lookup"><span data-stu-id="3621b-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="3621b-119">使用单一命令将容器部署到具有空前简易性和速度的云。</span><span class="sxs-lookup"><span data-stu-id="3621b-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="3621b-120">通过虚拟机监控程序隔离保护应用程序</span><span class="sxs-lookup"><span data-stu-id="3621b-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="3621b-121">简而言之，借助 ACI，可以快速开发应用，无需管理虚拟机，也无需了解新的工具。</span><span class="sxs-lookup"><span data-stu-id="3621b-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="3621b-122">它只是在云中运行的容器中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3621b-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="3621b-123">[上一页](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [下一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="3621b-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span></span>
