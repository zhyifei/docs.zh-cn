---
title: 何时将 Windows 容器部署到 Azure 容器服务 (即 Kubernetes)
description: 更新现有.NET 应用程序与 Azure 云和 Windows 容器 |何时将 Windows 容器部署到 Azure 容器服务 (即 Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 0b803b104f905fddac7939d7b070c206aabffeda
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011965"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="81617-103">何时将 Windows 容器部署到 Azure 容器服务 (即 Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="81617-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="81617-104">Azure 容器服务优化了专门针对 Azure 的受欢迎的开源工具和技术配置。</span><span class="sxs-lookup"><span data-stu-id="81617-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="81617-105">获取打开的解决方案，可提供你的容器和应用程序配置的可移植性。</span><span class="sxs-lookup"><span data-stu-id="81617-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="81617-106">您选择的大小、 主机数和 orchestrator 工具。</span><span class="sxs-lookup"><span data-stu-id="81617-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="81617-107">Azure 容器服务为你处理的基础结构。</span><span class="sxs-lookup"><span data-stu-id="81617-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="81617-108">如果已在使用 Kubernetes、 Docker Swarm 或 DC/OS 等的开放源业务流程协调程序，不需要更改现有的管理措施以将容器工作负荷移动到云。</span><span class="sxs-lookup"><span data-stu-id="81617-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="81617-109">使用您已经熟悉的应用程序管理工具并通过标准 API 终结点连接的所选的业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="81617-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="81617-110">如果你正在使用 Linux Docker 容器，但可能仅在 Windows 容器的预览状态，所有这些业务流程协调程序是成熟的环境。</span><span class="sxs-lookup"><span data-stu-id="81617-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="81617-111">例如，在 Kubernetes 中，对支持容器是本机 （一流成员），因此在 Kubernetes 上使用 Windows 容器也很有效 （在预览版在 ACS 中，从 2018 年初开始）。</span><span class="sxs-lookup"><span data-stu-id="81617-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="81617-112">重要说明：改进和"多个 PaaS"适用于 Kubernetes 的 ACS （Azure 容器服务） 的版本是 AKS （Azure Kubernetes 服务），但是，Windows 容器目前尚不支持从第 2 季度 2018 起，但将很快支持。</span><span class="sxs-lookup"><span data-stu-id="81617-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="81617-113">[上一页](when-to-deploy-windows-containers-to-service-fabric.md)
>[下一页](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="81617-113">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>