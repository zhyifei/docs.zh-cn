---
title: 在 Azure 中部署容器
description: 在 Azure 中通过 Azure 容器注册表、Azure Kubernetes 服务和 Azure Dev Spaces 部署容器。
ms.date: 06/30/2019
ms.openlocfilehash: 6d95db26b6a45dd6825c88693308ffe90d1ed071
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840483"
---
# <a name="deploying-containers-in-azure"></a><span data-ttu-id="b1ef3-103">在 Azure 中部署容器</span><span class="sxs-lookup"><span data-stu-id="b1ef3-103">Deploying containers in Azure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="b1ef3-104">容器提供了许多好处，其中之一是可移植性。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-104">Containers provide many benefits, one of which is portability.</span></span> <span data-ttu-id="b1ef3-105">可以轻松地获取在本地开发和测试的相同容器，并将其部署到 Azure，以便在过渡环境和生产环境中运行应用。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-105">You can easily take the same container you've developed and tested locally and deploy it to Azure where it can run your app in staging and production environments.</span></span> <span data-ttu-id="b1ef3-106">Azure 为基于容器的应用程序托管提供了许多选项，同样支持多种不同的部署方法。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-106">Azure provides a number of options for container-based app hosting and likewise supports several different means of deployment.</span></span> <span data-ttu-id="b1ef3-107">最常见和最灵活的方法是将容器部署到 Azure 容器注册表（ACR），在该容器中，你希望使用哪些服务来承载它们。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-107">The most common and most flexible approach is to deploy your containers to Azure Container Registry (ACR), where they're accessible by whatever services you wish to use to host them.</span></span> <span data-ttu-id="b1ef3-108">Azure 用于容器的 Web 应用、Azure Kubernetes Services （AKS）和 Azure 容器实例（ACI）都可以访问已推送到 ACR 的容器映像。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-108">Azure Web App for Containers, Azure Kubernetes Services (AKS), and Azure Container Instance (ACI) all can access container images that have been pushed to ACR.</span></span>

## <a name="azure-container-registry"></a><span data-ttu-id="b1ef3-109">Azure 容器注册表</span><span class="sxs-lookup"><span data-stu-id="b1ef3-109">Azure Container Registry</span></span>

<span data-ttu-id="b1ef3-110">Azure 容器注册表（ACR）允许您为所有容器部署生成、存储和管理映像。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-110">Azure Container Registry (ACR) lets you build, store, and manage images for all of your container deployments.</span></span> <span data-ttu-id="b1ef3-111">可以向其部署容器的其他容器注册表（公用和专用）。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-111">There are other container registries, both public and private, to which you can deploy containers.</span></span> <span data-ttu-id="b1ef3-112">ACR 与其他选项的好处是，您可以将图像与生产环境保持接近，从而缩短生成和部署时间。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-112">The benefit of ACR over other options is that you can keep your images close to your production environment, improving build and deployment times.</span></span> <span data-ttu-id="b1ef3-113">你还可以使用用于其他 Azure 资源的相同安全过程来保护这些资源，从而提高安全性并降低资产管理工作量。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-113">You can also secure them using the same security procedures you use for the rest of your Azure resources, improving security and reducing asset management effort.</span></span>

<span data-ttu-id="b1ef3-114">使用 Azure 门户或[Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli)或[PowerShell 工具](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell)[创建容器注册表](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal)。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-114">You [create a container registry using the Azure Portal](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal) or [using the Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli) or [PowerShell tools](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell).</span></span> <span data-ttu-id="b1ef3-115">创建新的容器注册表只需要 Azure 订阅、资源组和唯一名称。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-115">Creating a new container registry just requires an Azure subscription, a resource group, and a unique name.</span></span> <span data-ttu-id="b1ef3-116">图3-11 显示了用于创建注册表的基本选项，这些选项将*托管在 azurecr.io。*</span><span class="sxs-lookup"><span data-stu-id="b1ef3-116">Figure 3-11 shows the basic options for creating a registry, which will be hosted at *registryname*.azurecr.io.</span></span>

<span data-ttu-id="b1ef3-117">![创建容器注册表](./media/create-container-registry.png)
**图 3-11**。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-117">![Create container registry](./media/create-container-registry.png)
**Figure 3-11**.</span></span> <span data-ttu-id="b1ef3-118">创建容器注册表</span><span class="sxs-lookup"><span data-stu-id="b1ef3-118">Create container registry</span></span>

<span data-ttu-id="b1ef3-119">创建注册表后，需要先对其进行身份验证，然后才能使用。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-119">Once you've created a registry, you'll need to authenticate with it before you can use it.</span></span> <span data-ttu-id="b1ef3-120">通常，你将使用 Azure CLI 命令登录到注册表：</span><span class="sxs-lookup"><span data-stu-id="b1ef3-120">Typically, you'll log into the registry using the Azure CLI command:</span></span>

```azurecli
az acr login --name *registryname*
```

<span data-ttu-id="b1ef3-121">在 Azure 容器注册表中创建注册表后，可以使用 docker 命令将容器映像推送到其中。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-121">Once you've created a registry in Azure Container Registry, you can use docker commands to push container images to it.</span></span> <span data-ttu-id="b1ef3-122">但是，必须先用 ACR 登录服务器的完全限定名称（URL）标记映像，然后才能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-122">Before you can do so, however, you must first tag your image with the fully qualified name (URL) of your ACR login server.</span></span> <span data-ttu-id="b1ef3-123">这将采用*registryname*. azurecr.io 格式。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-123">This will have the format *registryname*.azurecr.io.</span></span>

```console
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="b1ef3-124">标记该映像后，使用 `docker push` 命令将该映像推送到 ACR 实例。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-124">After you've tagged the image, you use the `docker push` command to push the image to your ACR instance.</span></span>

```console
docker push myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="b1ef3-125">将映像推送到注册表后，最好使用以下命令从本地 Docker 环境中删除映像：</span><span class="sxs-lookup"><span data-stu-id="b1ef3-125">After you push an image to the registry, it's a good idea to remove the image from your local Docker environment, using this command:</span></span>

```console
docker rmi myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="b1ef3-126">开发人员很少直接从其计算机推送到容器注册表。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-126">Developers should rarely push directly from their machines to a container registry.</span></span> <span data-ttu-id="b1ef3-127">相反，在 Azure DevOps 之类的工具中定义的生成管道应负责执行此过程。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-127">Instead, a build pipeline defined in a tool like Azure DevOps should be responsible for this process.</span></span> <span data-ttu-id="b1ef3-128">有关详细信息，请参阅[云-Native DevOps 章节](devops.md)。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-128">Learn more in the [Cloud-Native DevOps chapter](devops.md).</span></span>

## <a name="azure-kubernetes-service"></a><span data-ttu-id="b1ef3-129">Azure Kubernetes 服务</span><span class="sxs-lookup"><span data-stu-id="b1ef3-129">Azure Kubernetes Service</span></span>

<span data-ttu-id="b1ef3-130">如果基于容器的应用程序涉及多个容器，则很可能需要使用 Kubernetes 等*orchestrator*来定义和管理容器之间的交互。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-130">If your container-based application involves multiple containers, you'll most likely want to define and manage the interactions between the containers using an *orchestrator* like Kubernetes.</span></span> <span data-ttu-id="b1ef3-131">将容器映像部署到 ACR 后，可以轻松地将 Azure Kubernetes 服务配置为从 ACR 自动部署更新后的映像。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-131">Once you've deployed your container images to ACR, you can easily configure Azure Kubernetes Services to automatically deploy updated images from ACR.</span></span> <span data-ttu-id="b1ef3-132">使用完整的 CI/CD 管道，你可以配置一个有空间的[发布](https://martinfowler.com/bliki/CanaryRelease.html)策略，以最大程度地减少快速部署更新时所涉及的风险。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-132">With a full CI/CD pipeline in place, you can configure a [canary release](https://martinfowler.com/bliki/CanaryRelease.html) strategy to minimize the risk involved when rapidly deploying updates.</span></span> <span data-ttu-id="b1ef3-133">新版本的应用程序最初在生产环境中进行了配置，但未将流量路由到该应用程序，然后将少量用户路由到新部署的应用程序版本。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-133">The new version of the app is initially configured in production with no traffic routed to it, and then a small number of users are routed to the newly-deployed version of the app.</span></span> <span data-ttu-id="b1ef3-134">随着团队在软件的新版本中取得自信，新版本的更多实例将推出，而以前版本的实例将被停用。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-134">As the team gains confidence in the new version of the software, more instances of the new version are rolled out and the previous version's instances are retired.</span></span> <span data-ttu-id="b1ef3-135">AKS 轻松支持这种部署样式。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-135">AKS easily supports this style of deployment.</span></span>

<span data-ttu-id="b1ef3-136">与 Azure 中的大多数资源一样，你可以使用门户或使用命令行工具或 Helm 或 Terraform 等基础结构自动化工具来创建 Azure Kubernetes 群集。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-136">As with most resources in Azure, you can create Azure Kubernetes clusters using the portal or using command line tools or infrastructure automation tools like Helm or Terraform.</span></span> <span data-ttu-id="b1ef3-137">若要开始使用新群集，需要提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="b1ef3-137">To get started with a new cluster, you need to provide the following information:</span></span>

- <span data-ttu-id="b1ef3-138">Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="b1ef3-138">Azure subscription</span></span>
- <span data-ttu-id="b1ef3-139">资源组</span><span class="sxs-lookup"><span data-stu-id="b1ef3-139">Resource group</span></span>
- <span data-ttu-id="b1ef3-140">Kubernetes 群集名称</span><span class="sxs-lookup"><span data-stu-id="b1ef3-140">Kubernetes cluster name</span></span>
- <span data-ttu-id="b1ef3-141">Region</span><span class="sxs-lookup"><span data-stu-id="b1ef3-141">Region</span></span>
- <span data-ttu-id="b1ef3-142">Kubernetes 版本</span><span class="sxs-lookup"><span data-stu-id="b1ef3-142">Kubernetes version</span></span>
- <span data-ttu-id="b1ef3-143">DNS 名称前缀</span><span class="sxs-lookup"><span data-stu-id="b1ef3-143">DNS name prefix</span></span>
- <span data-ttu-id="b1ef3-144">节点大小</span><span class="sxs-lookup"><span data-stu-id="b1ef3-144">Node size</span></span>
- <span data-ttu-id="b1ef3-145">节点计数</span><span class="sxs-lookup"><span data-stu-id="b1ef3-145">Node count</span></span>

<span data-ttu-id="b1ef3-146">此信息足以开始。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-146">This information is sufficient to get started.</span></span> <span data-ttu-id="b1ef3-147">作为 Azure 门户中创建过程的一部分，你还可以配置以下群集功能的选项：</span><span class="sxs-lookup"><span data-stu-id="b1ef3-147">As part of the creation process in the Azure Portal, you can also configure options for the following features of your cluster:</span></span>

- <span data-ttu-id="b1ef3-148">缩放</span><span class="sxs-lookup"><span data-stu-id="b1ef3-148">Scale</span></span>
- <span data-ttu-id="b1ef3-149">身份验证</span><span class="sxs-lookup"><span data-stu-id="b1ef3-149">Authentication</span></span>
- <span data-ttu-id="b1ef3-150">联网</span><span class="sxs-lookup"><span data-stu-id="b1ef3-150">Networking</span></span>
- <span data-ttu-id="b1ef3-151">监视</span><span class="sxs-lookup"><span data-stu-id="b1ef3-151">Monitoring</span></span>
- <span data-ttu-id="b1ef3-152">Tags</span><span class="sxs-lookup"><span data-stu-id="b1ef3-152">Tags</span></span>

<span data-ttu-id="b1ef3-153">本[快速入门演示如何使用 Azure 门户部署 AKS 群集](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal)。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-153">This [quickstart walks through deploying an AKS cluster using the Azure portal](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).</span></span>

## <a name="azure-dev-spaces"></a><span data-ttu-id="b1ef3-154">Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="b1ef3-154">Azure Dev Spaces</span></span>

<span data-ttu-id="b1ef3-155">复杂的 Kubernetes 群集可能需要大量资源来托管，这会使开发人员难以在一台计算机上运行整个应用程序（尤其是便携式计算机）。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-155">Complex Kubernetes clusters can require significant resources to host, which can make it difficult for developers to run the entire application on a single machine (especially a laptop).</span></span> <span data-ttu-id="b1ef3-156">Azure Dev Spaces 通过允许开发人员使用 Azure 中托管的 Azure Kubernetes 群集的自己版本来提供此解决方案。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-156">Azure Dev Spaces offers a solution to this by allowing developers to work with their own versions of Azure Kubernetes clusters hosted in Azure.</span></span> <span data-ttu-id="b1ef3-157">Azure Dev Spaces 旨在使用 AKS 简化基于微服务的应用程序的开发。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-157">Azure Dev Spaces is designed to ease development of microservice-based applications using AKS.</span></span>

<span data-ttu-id="b1ef3-158">为了理解 Azure Dev Spaces 的价值，让我在 Microsoft Azure 的容器的 Gabe Monroy 中共享此报价：</span><span class="sxs-lookup"><span data-stu-id="b1ef3-158">To understand the value of Azure Dev Spaces, let me share this quotation from Gabe Monroy, PM Lead of Containers at Microsoft Azure:</span></span>

<span data-ttu-id="b1ef3-159">"假设您是一名新员工，尝试修复由数十个组件组成的复杂的微服务应用程序中的 bug，每个组件都有其自己的配置和支持服务。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-159">"Imagine you are a new employee trying to fix a bug in a complex microservices application consisting of dozens of components, each with their own configuration and backing services.</span></span> <span data-ttu-id="b1ef3-160">若要开始，必须配置本地开发环境，使其可以模拟生产环境，包括设置 IDE、构建工具链、容器化服务依赖项、本地 Kubernetes 环境、模拟用于支持服务等。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-160">To get started, you must configure your local development environment so that it can mimic production including setting up your IDE, building tool chain, containerized service dependencies, a local Kubernetes environment, mocks for backing services, and more.</span></span> <span data-ttu-id="b1ef3-161">在设置开发环境的过程中，解决第一个 bug 可能需要数天的时间。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-161">With all the time involved setting up your development environment, fixing that first bug could take days.</span></span>

> <span data-ttu-id="b1ef3-162">或者，可以使用 Dev Spaces 和 AKS。 "</span><span class="sxs-lookup"><span data-stu-id="b1ef3-162">Or you could use Dev Spaces and AKS."</span></span>

<span data-ttu-id="b1ef3-163">使用 Azure Dev Spaces 的过程涉及以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b1ef3-163">The process for working with Azure Dev Spaces involves the following steps:</span></span>

1. <span data-ttu-id="b1ef3-164">创建 dev 空间。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-164">Create the dev space.</span></span>
2. <span data-ttu-id="b1ef3-165">配置根开发人员空间。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-165">Configure the root dev space.</span></span>
3. <span data-ttu-id="b1ef3-166">配置子开发人员空间（适用于你自己的系统版本）。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-166">Configure a child dev space (for your own version of the system).</span></span>
4. <span data-ttu-id="b1ef3-167">连接到 dev 空间。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-167">Connect to the dev space.</span></span>

<span data-ttu-id="b1ef3-168">所有这些步骤都可以使用 Azure CLI 和新的 `azds` 命令行工具来执行。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-168">All of these steps can be performed using the Azure CLI and new  `azds` command line tools.</span></span> <span data-ttu-id="b1ef3-169">例如，若要为给定的 Kubernetes 群集创建新的 Azure Dev 空间，请使用如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="b1ef3-169">For example, to create a new Azure Dev Space for a given Kubernetes cluster, you would use a command like this one:</span></span>

```azurecli
az aks use-dev-spaces -g my-aks-resource-group -n MyAKSCluster
```

<span data-ttu-id="b1ef3-170">接下来，可以使用 `azds prep` 命令生成运行应用程序所需的 Docker 和 Helm 图表资产。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-170">Next, you can use the `azds prep` command to generate the necessary Docker and Helm chart assets for running the application.</span></span> <span data-ttu-id="b1ef3-171">然后，使用 `azds up`在 AKS 中运行你的代码。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-171">Then you run your code in AKS using `azds up`.</span></span> <span data-ttu-id="b1ef3-172">首次运行此命令时，将安装 Helm 图表，并将根据说明生成和部署容器。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-172">The first time you run this command, the Helm chart will be installed, and the container(s) will be built and deployed according to your instructions.</span></span> <span data-ttu-id="b1ef3-173">首次运行时可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-173">This may take a few minutes the first time it's run.</span></span> <span data-ttu-id="b1ef3-174">但是，在进行更改后，可以使用 `azds space select` 连接到自己的子开发人员空间，然后在隔离的子开发人员空间中部署和调试更新。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-174">However, after you make changes, you can connect to your own child dev space using `azds space select` and then deploy and debug your updates in your isolated child dev space.</span></span> <span data-ttu-id="b1ef3-175">开发人员空间启动并运行后，可以通过重新发出 `azds up` 命令向其发送更新，也可以使用 Visual Studio 中的内置工具或 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-175">Once you have your dev space up and running, you can send updates to it by re-issuing the `azds up` command or you can use built-in tooling in Visual Studio or Visual Studio Code.</span></span> <span data-ttu-id="b1ef3-176">使用 VS Code，可以使用命令面板连接到开发环境。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-176">With VS Code, you use the command palette to connect to your dev space.</span></span> <span data-ttu-id="b1ef3-177">图3-12 演示了如何使用 Visual Studio 中的 Azure Dev Spaces 启动 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-177">Figure 3-12 shows how to launch your web application using Azure Dev Spaces in Visual Studio.</span></span>

<span data-ttu-id="b1ef3-178">![连接到 Visual Studio 中的 Azure Dev Spaces](./media/azure-dev-spaces-visual-studio-launchsettings.png)
**图 3-12**。</span><span class="sxs-lookup"><span data-stu-id="b1ef3-178">![Connect to Azure Dev Spaces in Visual Studio](./media/azure-dev-spaces-visual-studio-launchsettings.png)
**Figure 3-12**.</span></span> <span data-ttu-id="b1ef3-179">在 Visual Studio 中连接到 Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="b1ef3-179">Connect to Azure Dev Spaces in Visual Studio</span></span>

## <a name="references"></a><span data-ttu-id="b1ef3-180">参考</span><span class="sxs-lookup"><span data-stu-id="b1ef3-180">References</span></span>

- [<span data-ttu-id="b1ef3-181">未的版本</span><span class="sxs-lookup"><span data-stu-id="b1ef3-181">Canary Release</span></span>](https://martinfowler.com/bliki/CanaryRelease.html)
- [<span data-ttu-id="b1ef3-182">Azure Dev Spaces 与 VS Code</span><span class="sxs-lookup"><span data-stu-id="b1ef3-182">Azure Dev Spaces with VS Code</span></span>](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore)
- [<span data-ttu-id="b1ef3-183">与 Visual Studio Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="b1ef3-183">Azure Dev Spaces with Visual Studio</span></span>](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore-visualstudio)

>[!div class="step-by-step"]
><span data-ttu-id="b1ef3-184">[上一页](combine-containers-serverless-approaches.md)
>[下一页](scale-containers-serverless.md)</span><span class="sxs-lookup"><span data-stu-id="b1ef3-184">[Previous](combine-containers-serverless-approaches.md)
[Next](scale-containers-serverless.md)</span></span>
