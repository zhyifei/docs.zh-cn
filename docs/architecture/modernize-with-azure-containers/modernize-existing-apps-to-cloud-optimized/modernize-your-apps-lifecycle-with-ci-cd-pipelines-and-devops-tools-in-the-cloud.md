---
title: 通过云中的 CI/CD 管道和 DevOps 工具保持对应用的生命周期进行现代化
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |在云中通过 CI/CD 管道和 DevOps 工具现代化应用程序的生命周期
ms.date: 04/30/2018
ms.openlocfilehash: 62b6c541780ed3bf82c55e576fa485f811b55b17
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374143"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="d4fbc-103">通过云中的 CI/CD 管道和 DevOps 工具保持对应用的生命周期进行现代化</span><span class="sxs-lookup"><span data-stu-id="d4fbc-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="d4fbc-104">如今的企业需要快速创新，才能在 marketplace 中获得竞争力。</span><span class="sxs-lookup"><span data-stu-id="d4fbc-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="d4fbc-105">交付高质量的新式应用程序需要 DevOps 工具和过程，这些工具和过程对于实现这一不断创新的循环至关重要。</span><span class="sxs-lookup"><span data-stu-id="d4fbc-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="d4fbc-106">借助适当的 DevOps 工具，开发人员可以简化持续部署，并更快地让用户获得创新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d4fbc-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="d4fbc-107">尽管持续集成和部署做法已建立良好的发展，但引入容器也会引入新的注意事项，尤其是在使用多容器应用程序时。</span><span class="sxs-lookup"><span data-stu-id="d4fbc-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="d4fbc-108">Azure DevOps Services 通过官方 Azure DevOps Services 部署任务支持将多容器应用程序持续集成和部署到各种环境：</span><span class="sxs-lookup"><span data-stu-id="d4fbc-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="d4fbc-109">部署到 Azure 用于容器的 Web 应用</span><span class="sxs-lookup"><span data-stu-id="d4fbc-109">Deploy to an Azure Web App for Containers</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops)

- [<span data-ttu-id="d4fbc-110">部署到 Azure 容器服务– Kubernetes</span><span class="sxs-lookup"><span data-stu-id="d4fbc-110">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="d4fbc-111">但你还可以使用基于 Azure DevOps Services 脚本的任务部署到[Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/)或 DC/OS。</span><span class="sxs-lookup"><span data-stu-id="d4fbc-111">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="d4fbc-112">为了继续促进部署灵活性，这些工具为容器工作负载提供了完美的开发到生产部署体验，同时提供了一系列开发和 CI/CD 解决方案。</span><span class="sxs-lookup"><span data-stu-id="d4fbc-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="d4fbc-113">图4-12 显示了部署到 Azure 容器服务中的 Kubernetes 群集的持续部署管道。</span><span class="sxs-lookup"><span data-stu-id="d4fbc-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Azure DevOps Services 连续部署管道，部署到 Kubernetes 群集](./media/image12.png)

<span data-ttu-id="d4fbc-115">**图4-12。**</span><span class="sxs-lookup"><span data-stu-id="d4fbc-115">**Figure 4-12.**</span></span> <span data-ttu-id="d4fbc-116">Azure DevOps Services 连续部署管道，部署到 Kubernetes 群集</span><span class="sxs-lookup"><span data-stu-id="d4fbc-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d4fbc-117">[上一页](modernize-your-apps-with-monitoring-and-telemetry.md)
>[下一页](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="d4fbc-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
