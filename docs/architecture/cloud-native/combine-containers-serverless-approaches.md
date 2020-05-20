---
title: 将容器和无服务器方法与云本机服务组合在一起
description: 将容器和 Kubernetes 与无服务器方法结合起来
ms.date: 05/13/2020
ms.openlocfilehash: 67eee89659026db06eb16ef6f1154ab6935725a4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614196"
---
# <a name="combining-containers-and-serverless-approaches"></a><span data-ttu-id="a3413-103">合并容器和无服务器方法</span><span class="sxs-lookup"><span data-stu-id="a3413-103">Combining containers and serverless approaches</span></span>

<span data-ttu-id="a3413-104">云本机应用程序通常实现利用容器和业务流程的服务。</span><span class="sxs-lookup"><span data-stu-id="a3413-104">Cloud-native applications typically implement services leveraging containers and orchestration.</span></span> <span data-ttu-id="a3413-105">通常会有机会将一些应用程序的服务作为 Azure Functions 公开。</span><span class="sxs-lookup"><span data-stu-id="a3413-105">There are often opportunities to expose some of the application's services as Azure Functions.</span></span> <span data-ttu-id="a3413-106">但是，在部署到 Kubernetes 的云本机应用程序中，充分利用此相同工具集中的 Azure Functions 是非常好的做法。</span><span class="sxs-lookup"><span data-stu-id="a3413-106">However, with a cloud-native app deployed to Kubernetes, it would be nice to leverage Azure Functions within this same toolset.</span></span> <span data-ttu-id="a3413-107">幸运的是，您可以将 Azure Functions 包装在 Docker 容器内，并使用与 Kubernetes 的其他应用程序相同的过程和工具进行部署。</span><span class="sxs-lookup"><span data-stu-id="a3413-107">Fortunately, you can wrap Azure Functions inside Docker containers and deploy them using the same processes and tools as the rest of your Kubernetes-based app.</span></span>

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a><span data-ttu-id="a3413-108">使用无服务器的容器有何意义？</span><span class="sxs-lookup"><span data-stu-id="a3413-108">When does it make sense to use containers with serverless?</span></span>

<span data-ttu-id="a3413-109">你的 Azure 函数不知道部署它的平台。</span><span class="sxs-lookup"><span data-stu-id="a3413-109">Your Azure Function has no knowledge of the platform on which it's deployed.</span></span> <span data-ttu-id="a3413-110">在某些情况下，你可能有特定的要求，并且需要自定义运行函数代码的环境。</span><span class="sxs-lookup"><span data-stu-id="a3413-110">For some scenarios, you may have specific requirements and need to customize the environment on which your function code will run.</span></span> <span data-ttu-id="a3413-111">你将需要一个支持依赖项的自定义映像或默认映像不支持的配置。</span><span class="sxs-lookup"><span data-stu-id="a3413-111">You'll need a custom image that supports dependencies or a configuration not supported by the default image.</span></span> <span data-ttu-id="a3413-112">在这些情况下，在自定义 Docker 容器中部署函数是有意义的。</span><span class="sxs-lookup"><span data-stu-id="a3413-112">In these cases, it makes sense to deploy your function in a custom Docker container.</span></span>

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a><span data-ttu-id="a3413-113">何时应避免使用带有 Azure Functions 的容器？</span><span class="sxs-lookup"><span data-stu-id="a3413-113">When should you avoid using containers with Azure Functions?</span></span>

<span data-ttu-id="a3413-114">如果要使用消耗计费，将无法在容器中运行函数。</span><span class="sxs-lookup"><span data-stu-id="a3413-114">If you want to use consumption billing, you won't be able to run your function in a container.</span></span> <span data-ttu-id="a3413-115">此外，如果将函数部署到 Kubernetes 群集，将不再受益于 Azure Functions 提供的内置缩放。</span><span class="sxs-lookup"><span data-stu-id="a3413-115">What's more, if you deploy your function to a Kubernetes cluster, you'll no longer benefit from the built-in scaling provided by Azure Functions.</span></span> <span data-ttu-id="a3413-116">你需要使用 Kubernetes 的缩放功能，详见本章前面所述。</span><span class="sxs-lookup"><span data-stu-id="a3413-116">You'll need to use Kubernetes' scaling features, described earlier in this chapter.</span></span>

## <a name="how-to-combine-serverless-and-docker-containers"></a><span data-ttu-id="a3413-117">如何组合无服务器和 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="a3413-117">How to combine serverless and Docker containers</span></span>

<span data-ttu-id="a3413-118">若要将 Azure 函数包装在 Docker 容器中，请安装[Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools) ，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a3413-118">To wrap an Azure Function in a Docker container, install the [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools) and then run the following command:</span></span>

```console
func init ProjectName --worker-runtime dotnet --docker
```

<span data-ttu-id="a3413-119">当创建项目时，它将包括 Dockerfile 和配置为的辅助运行时 `dotnet` 。</span><span class="sxs-lookup"><span data-stu-id="a3413-119">When the project is created, it will include a Dockerfile and the worker runtime configured to `dotnet`.</span></span> <span data-ttu-id="a3413-120">现在，你可以在本地创建和测试函数。</span><span class="sxs-lookup"><span data-stu-id="a3413-120">Now, you can create and test your function locally.</span></span> <span data-ttu-id="a3413-121">使用和命令生成并运行 `docker build` 它 `docker run` 。</span><span class="sxs-lookup"><span data-stu-id="a3413-121">Build and run it using the  `docker build` and `docker run` commands.</span></span> <span data-ttu-id="a3413-122">有关使用 Docker 支持构建 Azure Functions 的详细步骤，请参阅在[Linux 上使用自定义映像创建函数](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)教程。</span><span class="sxs-lookup"><span data-stu-id="a3413-122">For detailed steps to get started building Azure Functions with Docker support, see the [Create a function on Linux using a custom image](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) tutorial.</span></span>

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a><span data-ttu-id="a3413-123">如何将无服务器和 Kubernetes 与 KEDA 结合</span><span class="sxs-lookup"><span data-stu-id="a3413-123">How to combine serverless and Kubernetes with KEDA</span></span>

<span data-ttu-id="a3413-124">在本章中，你已了解到 Azure Functions 的平台会自动扩大以满足需求。</span><span class="sxs-lookup"><span data-stu-id="a3413-124">In this chapter, you've seen that the Azure Functions' platform automatically scales out to meet demand.</span></span> <span data-ttu-id="a3413-125">但是，在将容器化函数部署到 AKS 时，会丢失内置缩放功能。</span><span class="sxs-lookup"><span data-stu-id="a3413-125">When deploying containerized functions to AKS, however, you lose the built-in scaling functionality.</span></span> <span data-ttu-id="a3413-126">[Kubernetes 是基于事件驱动的（KEDA）](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)。</span><span class="sxs-lookup"><span data-stu-id="a3413-126">To the rescue comes [Kubernetes-based Event Driven (KEDA)](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).</span></span> <span data-ttu-id="a3413-127">它实现了包含容器化函数的精细自动缩放 `event-driven Kubernetes workloads,` 。</span><span class="sxs-lookup"><span data-stu-id="a3413-127">It enables fine-grained autoscaling for `event-driven Kubernetes workloads,` including containerized functions.</span></span>

<span data-ttu-id="a3413-128">KEDA 为 Docker 容器中的函数运行时提供事件驱动的缩放功能。</span><span class="sxs-lookup"><span data-stu-id="a3413-128">KEDA provides event-driven scaling functionality to the Functions' runtime in a Docker container.</span></span> <span data-ttu-id="a3413-129">KEDA 可以根据负载从零个实例（没有事件发生时）扩展到 `n instances` 。</span><span class="sxs-lookup"><span data-stu-id="a3413-129">KEDA can scale from zero instances (when no events are occurring) out to `n instances`, based on load.</span></span> <span data-ttu-id="a3413-130">它通过向 Kubernetes 自动缩放程序（水平 Pod 自动缩放程序）公开自定义指标来启用自动缩放。</span><span class="sxs-lookup"><span data-stu-id="a3413-130">It enables autoscaling by exposing custom metrics to the Kubernetes autoscaler (Horizontal Pod Autoscaler).</span></span> <span data-ttu-id="a3413-131">将函数容器与 KEDA 结合使用，可以在任何 Kubernetes 群集中复制无服务器函数功能。</span><span class="sxs-lookup"><span data-stu-id="a3413-131">Using Functions containers with KEDA makes it possible to replicate serverless function capabilities in any Kubernetes cluster.</span></span>

<span data-ttu-id="a3413-132">值得注意的是，KEDA 项目现在由云本机计算基础（CNCF）进行管理。</span><span class="sxs-lookup"><span data-stu-id="a3413-132">It is worth noting that the KEDA project is now managed by the Cloud Native Computing Foundation (CNCF).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a3413-133">[上一页](leverage-serverless-functions.md)
>[下一页](deploy-containers-azure.md)</span><span class="sxs-lookup"><span data-stu-id="a3413-133">[Previous](leverage-serverless-functions.md)
[Next](deploy-containers-azure.md)</span></span>
