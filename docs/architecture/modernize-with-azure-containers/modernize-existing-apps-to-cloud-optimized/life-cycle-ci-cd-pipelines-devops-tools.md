---
title: 通过云中的 CI/CD 管道和 DevOps 工具保持对应用的生命周期进行现代化
description: 通过 Azure 云和 Windows 容器现代化现有 .NET 应用程序 | 通过云中的 CI/CD 管道和 DevOps 工具保持现代化应用的生命周期
ms.date: 04/30/2018
ms.openlocfilehash: ac2d9a1e9ab432cf69cb3da670fc91c681f802c2
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "80987850"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="1e1dc-103">通过云中的 CI/CD 管道和 DevOps 工具保持对应用的生命周期进行现代化</span><span class="sxs-lookup"><span data-stu-id="1e1dc-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="1e1dc-104">如今的企业需要快速创新，才能在市场中获得竞争力。</span><span class="sxs-lookup"><span data-stu-id="1e1dc-104">Today's businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="1e1dc-105">交付高质量的新式应用程序需要 DevOps 工具和进程，这些工具和进程对于实现这一不断创新的循环至关重要。</span><span class="sxs-lookup"><span data-stu-id="1e1dc-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="1e1dc-106">借助适当的 DevOps 工具，开发人员可以简化持续部署，并更快地让用户获得创新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e1dc-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="1e1dc-107">尽管持续集成和部署做法已建立良好的发展，但引入容器也会引入新的注意事项，尤其是在使用多容器应用程序时。</span><span class="sxs-lookup"><span data-stu-id="1e1dc-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="1e1dc-108">Azure DevOps Services 通过官方 Azure DevOps Services 部署任务支持将多容器应用程序持续集成和部署到各种环境：</span><span class="sxs-lookup"><span data-stu-id="1e1dc-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="1e1dc-109">部署到用于容器的 Azure Web 应用</span><span class="sxs-lookup"><span data-stu-id="1e1dc-109">Deploy to an Azure Web App for Containers</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?tabs=dotnet-core)

- [<span data-ttu-id="1e1dc-110">部署到 Azure Kubernetes 服务</span><span class="sxs-lookup"><span data-stu-id="1e1dc-110">Deploy to Azure Kubernetes Service</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-aks?tabs=dotnet-core)

<span data-ttu-id="1e1dc-111">但你还可以使用基于 Azure DevOps Services 脚本的任务部署到 [Docker Swarm](https://blog.jcorioland.io/archives/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services.html) 或 DC/OS。</span><span class="sxs-lookup"><span data-stu-id="1e1dc-111">But you also can deploy to [Docker Swarm](https://blog.jcorioland.io/archives/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services.html) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="1e1dc-112">为了继续促进部署灵活性，这些工具为容器工作负载提供了开发到测试到生产部署的完美体验，同时提供了一系列开发和 CI/CD 解决方案。</span><span class="sxs-lookup"><span data-stu-id="1e1dc-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="1e1dc-113">图 4-12 显示了部署到 Azure 容器服务中的 Kubernetes 群集的持续部署管道。</span><span class="sxs-lookup"><span data-stu-id="1e1dc-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Azure DevOps 服务部署到 Kubernetes 群集的屏幕截图。](./media/life-cycle-ci-cd-pipelines-devops-tools/deploy-mvc-app-container-kubernetes.png)

<span data-ttu-id="1e1dc-115">**图 4-12.**</span><span class="sxs-lookup"><span data-stu-id="1e1dc-115">**Figure 4-12.**</span></span> <span data-ttu-id="1e1dc-116">Azure DevOps Services 持续部署管道，部署到 Kubernetes 群集</span><span class="sxs-lookup"><span data-stu-id="1e1dc-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1e1dc-117">[上一页](modernize-your-apps-with-monitoring-and-telemetry.md)
>[下一页](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="1e1dc-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
