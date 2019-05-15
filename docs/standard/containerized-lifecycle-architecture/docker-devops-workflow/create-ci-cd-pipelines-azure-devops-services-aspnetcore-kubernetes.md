---
title: Docker 应用程序的外部循环 DevOps 工作流步骤
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
ms.date: 02/15/2019
ms.openlocfilehash: 9fdc5acfd375e4f2266859f061ef1c854286b914
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644981"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a><span data-ttu-id="c65f7-103">在 Azure DevOps Services 中为容器中的 .NET Core 2.0 应用程序创建 CI/CD 管道并部署到 Kubernetes 群集</span><span class="sxs-lookup"><span data-stu-id="c65f7-103">Creating CI/CD pipelines in Azure DevOps Services for a .NET Core 2.0 application on Containers and deploying to a Kubernetes cluster</span></span>

<span data-ttu-id="c65f7-104">图 5-12 中可以看到的端到端 DevOps 方案中介绍的代码管理、 代码编译、 生成 Docker 映像、 Docker 映像推送到 Docker 注册表，最后部署到 Azure 中的 Kubernetes 群集。</span><span class="sxs-lookup"><span data-stu-id="c65f7-104">In Figure 5-12 you can see the end-to-end DevOps scenario covering the code management, code compilation, Docker images build, Docker images push to a Docker registry and finally the deployment to a Kubernetes cluster in Azure.</span></span>

![工作流：在开发计算机中启动。](media/docker-workflow-ci-cd-aks.png)

<span data-ttu-id="c65f7-107">**图 5-12**。</span><span class="sxs-lookup"><span data-stu-id="c65f7-107">**Figure 5-12**.</span></span> <span data-ttu-id="c65f7-108">CI/CD 方案创建 Docker 映像，部署到 Azure 中的 Kubernetes 群集</span><span class="sxs-lookup"><span data-stu-id="c65f7-108">CI/CD scenario creating Docker images and deploying to a Kubernetes cluster in Azure</span></span>

<span data-ttu-id="c65f7-109">务必以突出显示的两个管道，生成/CI 和发布/CD，通过 Docker 注册表 （如 Docker 中心或 Azure 容器注册表） 中的连接。</span><span class="sxs-lookup"><span data-stu-id="c65f7-109">It is important to highlight that the two pipelines, build/CI, and release/CD, are connected through the Docker Registry (such as Docker Hub or Azure Container Registry).</span></span> <span data-ttu-id="c65f7-110">Docker 注册表是相比传统的 CI/CD 过程不带 Docker 的主要区别之一。</span><span class="sxs-lookup"><span data-stu-id="c65f7-110">The Docker registry is one of the main differences compared to a traditional CI/CD process without Docker.</span></span>

<span data-ttu-id="c65f7-111">如所示在图 5 月 13 日，第一阶段是生成/CI 管道。</span><span class="sxs-lookup"><span data-stu-id="c65f7-111">As shown in Figure 5-13, the first phase is the build/CI pipeline.</span></span> <span data-ttu-id="c65f7-112">在 Azure DevOps 服务可以创建生成/CI 管道，请将编译的代码创建 Docker 映像，并将它们推送到 Docker 注册表，如 Docker 中心或 Azure 容器注册表。</span><span class="sxs-lookup"><span data-stu-id="c65f7-112">In Azure DevOps Services you can create build/CI pipelines that will compile the code, create the Docker images, and push them to a Docker Registry like Docker Hub or Azure Container Registry.</span></span>

![Azure DevOps，生成进程任务定义的浏览器视图。](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

<span data-ttu-id="c65f7-114">**图 5-13**。</span><span class="sxs-lookup"><span data-stu-id="c65f7-114">**Figure 5-13**.</span></span> <span data-ttu-id="c65f7-115">生成/CI 管道中 Azure DevOps 生成 Docker 映像并将映像推送到 Docker 注册表</span><span class="sxs-lookup"><span data-stu-id="c65f7-115">Build/CI pipeline in Azure DevOps building Docker images and pushing images to a Docker registry</span></span>

<span data-ttu-id="c65f7-116">第二个阶段是创建部署/发布管道。</span><span class="sxs-lookup"><span data-stu-id="c65f7-116">The second phase is to create a deployment/release pipeline.</span></span> <span data-ttu-id="c65f7-117">在 Azure DevOps 服务，可以轻松地创建适用于 Azure DevOps 服务，使用 Kubernetes 任务面向的 Kubernetes 群集中图 5-14 所示的部署管道。</span><span class="sxs-lookup"><span data-stu-id="c65f7-117">In Azure DevOps Services, you can easily create a deployment pipeline targeting a Kubernetes cluster by using the Kubernetes tasks for Azure DevOps Services, as shown in Figure 5-14.</span></span>

![Azure DevOps 的浏览器视图将部署到 Kubernetes 任务定义。](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

<span data-ttu-id="c65f7-119">**图 5-14**。</span><span class="sxs-lookup"><span data-stu-id="c65f7-119">**Figure 5-14**.</span></span> <span data-ttu-id="c65f7-120">Azure DevOps 服务部署到 Kubernetes 群集中的发布/CD 管道</span><span class="sxs-lookup"><span data-stu-id="c65f7-120">Release/CD pipeline in Azure DevOps Services deploying to a Kubernetes cluster</span></span>

> [!演练]<span data-ttu-id="c65f7-121"> 部署到 Kubernetes eShopModernized:</span><span class="sxs-lookup"><span data-stu-id="c65f7-121"> Deploying eShopModernized to Kubernetes:</span></span>
>
> <span data-ttu-id="c65f7-122">有关 Azure DevOps CI/CD 管道的详细演练部署到 Kubernetes 中，请参阅此文章: \\</span><span class="sxs-lookup"><span data-stu-id="c65f7-122">For a detailed walkthrough of Azure DevOps CI/CD pipelines deploying to Kubernetes, see this post: \\</span></span>
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
><span data-ttu-id="c65f7-123">[上一页](docker-application-outer-loop-devops-workflow.md)
>[下一页](../run-manage-monitor-docker-environments/index.md)</span><span class="sxs-lookup"><span data-stu-id="c65f7-123">[Previous](docker-application-outer-loop-devops-workflow.md)
[Next](../run-manage-monitor-docker-environments/index.md)</span></span>
