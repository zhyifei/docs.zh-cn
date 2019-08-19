---
title: 何时将 Windows 容器部署到 Azure 容器服务 (即, Kubernetes)
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |何时将 Windows 容器部署到 Azure 容器服务 (即, Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577940"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="157dd-103">何时将 Windows 容器部署到 Azure 容器服务 (即, Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="157dd-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="157dd-104">Azure 容器服务专门为 Azure 优化了常用开源工具和技术的配置。</span><span class="sxs-lookup"><span data-stu-id="157dd-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="157dd-105">你将获得一个开放式解决方案, 该解决方案可为你的容器和应用程序配置提供可移植性。</span><span class="sxs-lookup"><span data-stu-id="157dd-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="157dd-106">选择大小、主机数和 orchestrator 工具。</span><span class="sxs-lookup"><span data-stu-id="157dd-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="157dd-107">Azure 容器服务可处理基础结构。</span><span class="sxs-lookup"><span data-stu-id="157dd-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="157dd-108">如果你已使用开源协调器 (如 Kubernetes、Docker Swarm 或 DC/OS), 则无需更改现有的管理实践即可将容器工作负荷迁移到云。</span><span class="sxs-lookup"><span data-stu-id="157dd-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="157dd-109">使用你已熟悉的应用程序管理工具, 并通过所选 orchestrator 的标准 API 终结点进行连接。</span><span class="sxs-lookup"><span data-stu-id="157dd-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="157dd-110">如果你使用的是 Linux Docker 容器, 但可能只是 Windows 容器的预览状态, 则所有这些协调器都是成熟环境。</span><span class="sxs-lookup"><span data-stu-id="157dd-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="157dd-111">例如, 在 Kubernetes 中, 对容器的支持是本机 (第一类公民), 因此, 在 Kubernetes 上使用 Windows 容器也是有效的 (在 ACS 中, 从2018年初开始)。</span><span class="sxs-lookup"><span data-stu-id="157dd-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="157dd-112">重要说明:适用于 Kubernetes 的 ACS (Azure 容器服务) 的发展和 "更多 PaaS" 版本为 AKS (Azure Kubernetes Service), 但是, 在第 2 2018 季度仍不支持 Windows 容器, 但不久就会受支持。</span><span class="sxs-lookup"><span data-stu-id="157dd-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="157dd-113">[上一页](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[下一页](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="157dd-113">[Previous](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
