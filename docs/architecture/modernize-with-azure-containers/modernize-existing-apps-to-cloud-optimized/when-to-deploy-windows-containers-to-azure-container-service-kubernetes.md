---
title: 何时将 Windows 容器部署到 Azure 容器服务（即 Kubernetes）
description: 通过 Azure 云和 Windows 容器现代化现有 .NET 应用程序 | 何时将 Windows 容器部署到 Azure 容器服务（即 Kubernetes）
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577940"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="dcead-103">何时将 Windows 容器部署到 Azure 容器服务（即 Kubernetes）</span><span class="sxs-lookup"><span data-stu-id="dcead-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="dcead-104">Azure 容器服务优化了专门针对 Azure 的常用开源工具和技术的配置。</span><span class="sxs-lookup"><span data-stu-id="dcead-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="dcead-105">你可以获得一个开放的解决方案，该解决方案为容器和应用程序配置提供可移植性。</span><span class="sxs-lookup"><span data-stu-id="dcead-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="dcead-106">你选择主机的大小和数量以及业务流程协调程序工具。</span><span class="sxs-lookup"><span data-stu-id="dcead-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="dcead-107">Azure 容器服务可为你处理基础结构。</span><span class="sxs-lookup"><span data-stu-id="dcead-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="dcead-108">如果你已使用开源业务流程协调程序（如 Kubernetes、Docker Swarm 或 DC/OS），则无需更改现有的管理实践即可将容器工作负载迁移到云。</span><span class="sxs-lookup"><span data-stu-id="dcead-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="dcead-109">针对所选的业务流程协调程序，使用熟悉的应用程序管理工具并通过标准 API 终结点连接。</span><span class="sxs-lookup"><span data-stu-id="dcead-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="dcead-110">如果你使用的是 Linux Docker 容器，则所有这些业务流程协调程序都是成熟环境；但对于 Windows 容器，它们可能只是处于预览版状态。</span><span class="sxs-lookup"><span data-stu-id="dcead-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="dcead-111">例如，在 Kubernetes 中，对容器的支持是本机的（一等公民），因此，在 Kubernetes 上使用 Windows 容器也是有效的（截止到 2018 年初在 ACS 中处于预览版状态）。</span><span class="sxs-lookup"><span data-stu-id="dcead-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="dcead-112">重要说明：AKS（Azure Kubernetes 服务）是适用于 Kubernetes 的 ACS（Azure 容器服务）的进化和“更多 PaaS”版本，不过，截止到 2018 年第 2 季度 Windows 容器仍不受支持，但不久就会受支持。</span><span class="sxs-lookup"><span data-stu-id="dcead-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dcead-113">[上一页](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[下一页](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="dcead-113">[Previous](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
