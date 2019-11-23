---
title: 其他容器部署选项
description: 使用 Azure 的其他容器部署选项
ms.date: 06/30/2019
ms.openlocfilehash: 1fcb57eedec8c9f5574fffcf409b316332032062
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "73841161"
---
# <a name="other-container-deployment-options"></a><span data-ttu-id="6af57-103">其他容器部署选项</span><span class="sxs-lookup"><span data-stu-id="6af57-103">Other container deployment options</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="6af57-104">除了部署到 AKS 以外，还可以为容器和 Azure 容器实例将容器部署到 Azure App Service。</span><span class="sxs-lookup"><span data-stu-id="6af57-104">In addition to deploying to AKS, you can also deploy containers to Azure App Service for Containers and Azure Container Instances.</span></span>

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a><span data-ttu-id="6af57-105">部署到容器的应用服务有何意义？</span><span class="sxs-lookup"><span data-stu-id="6af57-105">When does it make sense to deploy to App Service for Containers?</span></span>

<span data-ttu-id="6af57-106">不需要业务流程的简单生产应用程序非常适合用于容器 Azure App Service。</span><span class="sxs-lookup"><span data-stu-id="6af57-106">Simple production applications that don't require orchestration are well-suited to Azure App Service for Containers.</span></span>

## <a name="how-to-deploy-to-app-service-for-containers"></a><span data-ttu-id="6af57-107">如何部署到容器的应用服务</span><span class="sxs-lookup"><span data-stu-id="6af57-107">How to deploy to App Service for Containers</span></span>

<span data-ttu-id="6af57-108">若要部署到[容器 Azure App Service](https://azure.microsoft.com/services/app-service/containers/)，需要配置 Azure 容器注册表（ACR）和凭据，以便对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="6af57-108">To deploy to [Azure App Service for Containers](https://azure.microsoft.com/services/app-service/containers/), you need to have configured an Azure Container Registry (ACR) and credentials for accessing it.</span></span> <span data-ttu-id="6af57-109">将你要承载的容器推送到注册表，以便可以将其推送到你的 Azure App Service。</span><span class="sxs-lookup"><span data-stu-id="6af57-109">Push the container you intend to host to the registry so it's available to pull into your Azure App Service.</span></span> <span data-ttu-id="6af57-110">创建后，可以将应用程序配置为持续部署，这会在更新其对应的映像时，自动将更新部署到该应用。</span><span class="sxs-lookup"><span data-stu-id="6af57-110">Once created, you can configure the app for Continuous Deployment, which will automatically deploy updates to the app whenever you update its corresponding image in ACR.</span></span>

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a><span data-ttu-id="6af57-111">部署到 Azure 容器实例时有何意义？</span><span class="sxs-lookup"><span data-stu-id="6af57-111">When does it make sense to deploy to Azure Container Instances?</span></span>

<span data-ttu-id="6af57-112">Azure 容器实例最适合用于测试方案。</span><span class="sxs-lookup"><span data-stu-id="6af57-112">Azure Container Instances are best used for testing scenarios.</span></span> <span data-ttu-id="6af57-113">它们提供了一种快速、简单的方式将应用程序部署到云托管的容器实例。</span><span class="sxs-lookup"><span data-stu-id="6af57-113">They provide a fast, simple way to deploy an application to a cloud-hosted container instance.</span></span> <span data-ttu-id="6af57-114">当你不需要 Azure Kubernetes 服务提供的缩放和业务流程功能时，可以使用它们来测试或演示应用程序。</span><span class="sxs-lookup"><span data-stu-id="6af57-114">Use them to test or demo applications when you don't require scaling and orchestration features offered by Azure Kubernetes Service.</span></span>

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a><span data-ttu-id="6af57-115">如何将应用部署到 Azure 容器实例</span><span class="sxs-lookup"><span data-stu-id="6af57-115">How to deploy an app to Azure Container Instances</span></span>

<span data-ttu-id="6af57-116">若要部署到[Azure 容器实例（ACI）](https://docs.microsoft.com/azure/container-instances/)，需要配置 Azure 容器注册表（ACR）和凭据，以便对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="6af57-116">To deploy to [Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/), you need to have configured an Azure Container Registry (ACR) and credentials for accessing it.</span></span> <span data-ttu-id="6af57-117">你还必须将容器映像推送到注册表，以便将其提取到 ACI。</span><span class="sxs-lookup"><span data-stu-id="6af57-117">You must also have previously pushed your container image to the registry, so it's available to pull into ACI.</span></span> <span data-ttu-id="6af57-118">可以使用 Azure CLI 或通过门户来使用 ACI。</span><span class="sxs-lookup"><span data-stu-id="6af57-118">You can work with ACI using the Azure CLI or through the portal.</span></span> <span data-ttu-id="6af57-119">Azure 容器注册表使你可以轻松地直接从注册表内将各个容器实例部署到 ACI，如图3-14 所示。</span><span class="sxs-lookup"><span data-stu-id="6af57-119">Azure Container Registries make it easy to deploy individual container instances to ACI directly from within the registry, as shown in Figure 3-14.</span></span>

![Azure 容器注册表运行实例](./media/acr-runinstance-contextmenu.png)

<span data-ttu-id="6af57-121">**图 3-14**。</span><span class="sxs-lookup"><span data-stu-id="6af57-121">**Figure 3-14**.</span></span> <span data-ttu-id="6af57-122">Azure 容器注册表运行实例</span><span class="sxs-lookup"><span data-stu-id="6af57-122">Azure Container Registry Run Instance</span></span>

<span data-ttu-id="6af57-123">通过注册表创建容器实例只需指定常用的 Azure 设置（名称、订阅、资源组和位置）、要分配给容器的内存量以及应侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="6af57-123">Creating a container instance from the registry just requires you to specify the usual Azure settings (name, subscription, resource group, and location), how much memory to allocate to the container, and which port it should listen on.</span></span> <span data-ttu-id="6af57-124">本[快速入门演示如何使用 Azure 门户将容器实例部署到 ACI](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal)。</span><span class="sxs-lookup"><span data-stu-id="6af57-124">This [quickstart shows how to deploy a container instance to ACI using the Azure portal](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal).</span></span>

<span data-ttu-id="6af57-125">部署完成后，查找新部署的容器的 IP 地址，并通过指定的端口与它进行通信。</span><span class="sxs-lookup"><span data-stu-id="6af57-125">Once the deployment completes, find the newly deployed container's IP address and communicate with it over the port you specified.</span></span>

<span data-ttu-id="6af57-126">Azure 容器实例提供了在 Azure 中运行容器的最简单、最简单的方法。</span><span class="sxs-lookup"><span data-stu-id="6af57-126">Azure Container Instances offers the fastest, simplest way to run a container in Azure.</span></span> <span data-ttu-id="6af57-127">无需配置应用服务或 orchestrator 或处理虚拟机。</span><span class="sxs-lookup"><span data-stu-id="6af57-127">There's no need to configure an app service or an orchestrator or to deal with virtual machines.</span></span> <span data-ttu-id="6af57-128">然而，由于其简易性，ACI 应该主要用于测试目的。</span><span class="sxs-lookup"><span data-stu-id="6af57-128">However, because of its simplicity, ACI should primarily be used for testing purposes.</span></span> <span data-ttu-id="6af57-129">如果你的应用程序需要自动可伸缩性、配置为一起使用的多个容器或任何其他复杂的功能，则可以使用其他更适合的 Azure 服务来托管你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6af57-129">If your application requires automatic scalability, multiple containers configured to work together, or any additional complex features, there are other better-suited Azure services available to host your app.</span></span>

## <a name="references"></a><span data-ttu-id="6af57-130">参考</span><span class="sxs-lookup"><span data-stu-id="6af57-130">References</span></span>

- [<span data-ttu-id="6af57-131">Azure 容器实例文档</span><span class="sxs-lookup"><span data-stu-id="6af57-131">Azure Container Instances Docs</span></span>](https://docs.microsoft.com/azure/container-instances/)
- [<span data-ttu-id="6af57-132">从 ACR 部署容器实例</span><span class="sxs-lookup"><span data-stu-id="6af57-132">Deploy Container Instance from ACR</span></span>](https://docs.microsoft.com/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
><span data-ttu-id="6af57-133">[上一页](scale-containers-serverless.md)
>[下一页](communication-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="6af57-133">[Previous](scale-containers-serverless.md)
[Next](communication-patterns.md)</span></span>
