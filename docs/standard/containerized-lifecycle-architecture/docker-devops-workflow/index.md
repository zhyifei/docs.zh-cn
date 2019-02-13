---
title: 使用 Microsoft 工具的 Docker 应用程序 DevOps 工作流
description: 使用 Microsoft 工具的 Microsoft 平台和工具 DevOps 工作流使用的容器化的 Docker 应用程序生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: a2d88dda9f3560675fcb6826960c6e76fa7daf92
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219070"
---
# <a name="docker-application-devops-workflow-with-microsoft-tools"></a><span data-ttu-id="d16b5-103">使用 Microsoft 工具的 Docker 应用程序 DevOps 工作流</span><span class="sxs-lookup"><span data-stu-id="d16b5-103">Docker application DevOps workflow with Microsoft tools</span></span>

<span data-ttu-id="d16b5-104">Microsoft Visual Studio、 Azure DevOps 服务、 Team Foundation Server 和 Application Insights 为开发和为你的团队提供的工具来管理项目和快速生成、 测试和部署的 IT 运营提供综合的生态系统容器化应用程序。</span><span class="sxs-lookup"><span data-stu-id="d16b5-104">Microsoft Visual Studio, Azure DevOps Services, Team Foundation Server, and Application Insights provide a comprehensive ecosystem for development and IT operations that give your team the tools to manage projects and rapidly build, test, and deploy containerized applications.</span></span>

<span data-ttu-id="d16b5-105">使用 Visual Studio 和 Azure DevOps 服务在云中，以及 Team Foundation Server 的本地开发团队还可以高效地构建、 测试和发布面向任何平台 （Windows 或 Linux） 的容器化应用程序。</span><span class="sxs-lookup"><span data-stu-id="d16b5-105">With Visual Studio and Azure DevOps Services in the cloud, along with Team Foundation Server on-premises, development teams can productively build, test, and release containerized applications directed toward any platform (Windows or Linux).</span></span>

<span data-ttu-id="d16b5-106">Microsoft 工具可以自动完成的容器化应用程序的具体实现管道-Docker、.NET Core 或与其他平台的任意组合 — 从全局生成和持续集成 (CI) 和使用 Azure DevOps 服务或团队的测试Foundation Server，到持续部署 (CD) 到 Docker 环境 （开发、 过渡、 生产），并向开发团队通过 Application Insights 服务的分析信息传输。</span><span class="sxs-lookup"><span data-stu-id="d16b5-106">Microsoft tools can automate the pipeline for specific implementations of containerized applications—Docker, .NET Core, or any combination with other platforms—from global builds and Continuous Integration (CI) and tests with Azure DevOps Services or Team Foundation Server, to Continuous Deployment (CD) to Docker environments (Development, Staging, Production), and to transmit analytics information about the services to the development team through Application Insights.</span></span> <span data-ttu-id="d16b5-107">每个代码提交都能启动生成 (CI) 过程并自动将服务部署到特定的容器化环境 (CD)。</span><span class="sxs-lookup"><span data-stu-id="d16b5-107">Every code commit can initiate a build (CI) and automatically deploy the services to specific containerized environments (CD).</span></span>

<span data-ttu-id="d16b5-108">开发者和测试者可以使用 Microsoft Azure 中的模板快速轻松地配置生产环境，如基于 Docker 的开发和测试环境。</span><span class="sxs-lookup"><span data-stu-id="d16b5-108">Developers and testers can easily and quickly provision production-like development and test environments based on Docker by using templates in Microsoft Azure.</span></span>

<span data-ttu-id="d16b5-109">容器化应用程序开发的复杂度根据业务复杂度和可伸缩性需要逐步增加。</span><span class="sxs-lookup"><span data-stu-id="d16b5-109">The complexity of containerized application development increases steadily depending on the business complexity and scalability needs.</span></span> <span data-ttu-id="d16b5-110">一个很好的示例就是基于微服务体系结构的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d16b5-110">A good example of this are applications based on microservices architectures.</span></span> <span data-ttu-id="d16b5-111">若要成功执行在此类环境中，你的项目必须自动执行整个生命周期 — 不仅生成和部署，但它还必须管理版本并收集遥测数据。</span><span class="sxs-lookup"><span data-stu-id="d16b5-111">To succeed in such an environment, your project must automate the entire life cycle—not only the build and deployment, but it also must manage versions along with the collection of telemetry.</span></span> <span data-ttu-id="d16b5-112">Azure DevOps 服务和 Azure 提供了以下功能：</span><span class="sxs-lookup"><span data-stu-id="d16b5-112">Azure DevOps Services and Azure offer the following capabilities:</span></span>

-   <span data-ttu-id="d16b5-113">Azure DevOps Services/Team Foundation Server 源代码管理 （基于 Git 或 Team Foundation 版本控制），敏捷规划 （Agile、 Scrum 和 CMMI 支持），CI、 发布管理和敏捷团队的其他工具。</span><span class="sxs-lookup"><span data-stu-id="d16b5-113">Azure DevOps Services/Team Foundation Server source code management (based on Git or Team Foundation Version Control), Agile planning (Agile, Scrum, and CMMI are supported), CI, release management, and other tools for Agile teams.</span></span>

-   <span data-ttu-id="d16b5-114">Azure DevOps Services/Team Foundation Server 包括第一个和第三方扩展与您轻松地可以构造 CI、 生成、 测试、 交付和发布管理管道微服务的一个功能强大且不断增长的生态的系统。</span><span class="sxs-lookup"><span data-stu-id="d16b5-114">Azure DevOps Services/Team Foundation Server include a powerful and growing ecosystem of first- and third-party extensions with which you easily can construct a CI, build, test, delivery, and release management pipeline for microservices.</span></span>

-   <span data-ttu-id="d16b5-115">运行自动的测试作为生成管道中 Azure DevOps 服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="d16b5-115">Run automated tests as part of your build pipeline in Azure DevOps Services.</span></span>

-   <span data-ttu-id="d16b5-116">Azure DevOps 服务可以增强 DevOps 生命周期与传递到多个环境，而不仅仅是对于生产环境，还适用于测试，包括 A / B 试验[canary 发布](https://martinfowler.com/bliki/CanaryRelease.html)，依次类推。</span><span class="sxs-lookup"><span data-stu-id="d16b5-116">Azure DevOps Services can tighten the DevOps life cycle with delivery to multiple environments, not just for production environments, but also for testing, including A/B experimentation, [canary releases](https://martinfowler.com/bliki/CanaryRelease.html), and so on.</span></span>

-   <span data-ttu-id="d16b5-117">组织可以使用 Azure 资源管理器和熟悉的工具，轻松从 Azure 容器注册表中存储的专用映像配置 Docker 容器以及 Azure 组件（数据、PaaS 等）的任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="d16b5-117">Organizations easily can provision Docker containers from private images stored in Azure Container Registry along with any dependency on Azure components (Data, PaaS, etc.) using Azure Resource Manager templates with tools with which they are already comfortable working.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d16b5-118">[上一页](../design-develop-containerized-apps/build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
>[下一页](docker-application-outer-loop-devops-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="d16b5-118">[Previous](../design-develop-containerized-apps/build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
[Next](docker-application-outer-loop-devops-workflow.md)</span></span>