---
title: "更新使用 CI/CD 管道和 DevOps 工具在云中的应用程序的生命周期"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |更新使用 CI/CD 管道和 DevOps 工具在云中的应用程序的生命周期"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 668c48b64cab964da65625ef5326fb75e133b3b9
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="8eaf9-103">更新使用 CI/CD 管道和 DevOps 工具在云中的应用程序的生命周期</span><span class="sxs-lookup"><span data-stu-id="8eaf9-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="8eaf9-104">如今的企业需要在较快的速度要应用商店中竞争对手创新。</span><span class="sxs-lookup"><span data-stu-id="8eaf9-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="8eaf9-105">提供高质量，现代应用程序要求的都是关键实现创新此常量周期 DevOps 工具和过程。</span><span class="sxs-lookup"><span data-stu-id="8eaf9-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="8eaf9-106">使用适当的 DevOps 工具，开发人员可以简化连续部署和更快速地获取的用户到手中的创新应用程序。</span><span class="sxs-lookup"><span data-stu-id="8eaf9-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="8eaf9-107">虽然连续集成和部署实践成熟，但容器简介引入了新的注意事项，尤其是在你正在使用多容器应用程序时。</span><span class="sxs-lookup"><span data-stu-id="8eaf9-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="8eaf9-108">Visual Studio Team Services 支持持续集成和部署多容器应用程序到各种环境中完成的正式的 Team Services 部署任务：</span><span class="sxs-lookup"><span data-stu-id="8eaf9-108">Visual Studio Team Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Team Services deployment tasks:</span></span>

-   <span data-ttu-id="8eaf9-109">[将部署到独立的 Docker 主机 VM](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) （Linux 或 Windows Server 2016 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="8eaf9-109">[Deploy to standalone Docker Host VM](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux or Windows Server 2016 or later)</span></span>

-   [<span data-ttu-id="8eaf9-110">将部署到 Service Fabric</span><span class="sxs-lookup"><span data-stu-id="8eaf9-110">Deploy to Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [<span data-ttu-id="8eaf9-111">将部署到 Azure 容器服务 – Kubernetes</span><span class="sxs-lookup"><span data-stu-id="8eaf9-111">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/vsts/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="8eaf9-112">但你也可以部署到[Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/)或 DC/OS 使用 Team Services 基于脚本的任务。</span><span class="sxs-lookup"><span data-stu-id="8eaf9-112">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Team Services script-based tasks.</span></span>

<span data-ttu-id="8eaf9-113">若要继续推进部署灵活性，这些工具提供出色开发到测试到生产部署遇到对于容器的工作负荷，通过选择的开发和 CI/CD 解决方案。</span><span class="sxs-lookup"><span data-stu-id="8eaf9-113">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="8eaf9-114">图 4-12 显示将部署到 Azure 容器服务中的实现 Kubernetes 群集的连续部署管道。</span><span class="sxs-lookup"><span data-stu-id="8eaf9-114">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Visual Studio Team Services 连续部署管道，到 Kubernetes 群集部署](./media/image12.png)

> <span data-ttu-id="8eaf9-116">**图 4-12。**</span><span class="sxs-lookup"><span data-stu-id="8eaf9-116">**Figure 4-12.**</span></span> <span data-ttu-id="8eaf9-117">Visual Studio Team Services 连续部署管道，到 Kubernetes 群集部署</span><span class="sxs-lookup"><span data-stu-id="8eaf9-117">Visual Studio Team Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="8eaf9-118">[上一页](modernize-your-apps-with-monitoring-and-telemetry.md)
[下一页](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="8eaf9-118">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
