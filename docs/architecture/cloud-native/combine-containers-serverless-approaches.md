---
title: 将容器和无服务器方法与云本机服务组合在一起
description: 将容器和 Kubernetes 与无服务器方法结合起来
ms.date: 04/23/2020
ms.openlocfilehash: fe9e9fd5d07132971d64bc6433a762fb7bd22048
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199659"
---
# <a name="combining-containers-and-serverless-approaches"></a><span data-ttu-id="9905d-103">合并容器和无服务器方法</span><span class="sxs-lookup"><span data-stu-id="9905d-103">Combining containers and serverless approaches</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="9905d-104">云本机应用程序通常实现利用容器和业务流程的服务。</span><span class="sxs-lookup"><span data-stu-id="9905d-104">Cloud-native applications typically implement services leveraging containers and orchestration.</span></span> <span data-ttu-id="9905d-105">通常会有机会将一些应用程序的服务作为 Azure Functions 公开。</span><span class="sxs-lookup"><span data-stu-id="9905d-105">There are often opportunities to expose some of the application's services as Azure Functions.</span></span> <span data-ttu-id="9905d-106">但是，在部署到 Kubernetes 的云本机应用程序中，充分利用此相同工具集中的 Azure Functions 是非常好的做法。</span><span class="sxs-lookup"><span data-stu-id="9905d-106">However, with a cloud-native app deployed to Kubernetes, it would be nice to leverage Azure Functions within this same toolset.</span></span> <span data-ttu-id="9905d-107">幸运的是，您可以将 Azure Functions 包装在 Docker 容器内，并使用与 Kubernetes 的其他应用程序相同的过程和工具进行部署。</span><span class="sxs-lookup"><span data-stu-id="9905d-107">Fortunately, you can wrap Azure Functions inside Docker containers and deploy them using the same processes and tools as the rest of your Kubernetes-based app.</span></span>

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a><span data-ttu-id="9905d-108">使用无服务器的容器有何意义？</span><span class="sxs-lookup"><span data-stu-id="9905d-108">When does it make sense to use containers with serverless?</span></span>

<span data-ttu-id="9905d-109">你的 Azure 函数不知道部署它的平台。</span><span class="sxs-lookup"><span data-stu-id="9905d-109">Your Azure Function has no knowledge of the platform on which it's deployed.</span></span> <span data-ttu-id="9905d-110">在某些情况下，你可能有特定的要求，并且需要自定义运行函数代码的环境。</span><span class="sxs-lookup"><span data-stu-id="9905d-110">For some scenarios, you may have specific requirements and need to customize the environment on which your function code will run.</span></span> <span data-ttu-id="9905d-111">你将需要一个支持依赖项的自定义映像或默认映像不支持的配置。</span><span class="sxs-lookup"><span data-stu-id="9905d-111">You'll need a custom image that supports dependencies or a configuration not supported by the default image.</span></span> <span data-ttu-id="9905d-112">在这些情况下，在自定义 Docker 容器中部署函数是有意义的。</span><span class="sxs-lookup"><span data-stu-id="9905d-112">In these cases, it makes sense to deploy your function in a custom Docker container.</span></span>

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a><span data-ttu-id="9905d-113">何时应避免使用带有 Azure Functions 的容器？</span><span class="sxs-lookup"><span data-stu-id="9905d-113">When should you avoid using containers with Azure Functions?</span></span>

<span data-ttu-id="9905d-114">如果要使用消耗计费，将无法在容器中运行函数。</span><span class="sxs-lookup"><span data-stu-id="9905d-114">If you want to use consumption billing, you won't be able to run your function in a container.</span></span> <span data-ttu-id="9905d-115">此外，如果将函数部署到 Kubernetes 群集，将不再受益于 Azure Functions 提供的内置缩放。</span><span class="sxs-lookup"><span data-stu-id="9905d-115">What's more, if you deploy your function to a Kubernetes cluster, you'll no longer benefit from the built-in scaling provided by Azure Functions.</span></span> <span data-ttu-id="9905d-116">你需要使用 Kubernetes 的缩放功能，详见本章前面所述。</span><span class="sxs-lookup"><span data-stu-id="9905d-116">You'll need to use Kubernetes' scaling features, described earlier in this chapter.</span></span>

## <a name="how-to-combine-serverless-and-docker-containers"></a><span data-ttu-id="9905d-117">如何组合无服务器和 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="9905d-117">How to combine serverless and Docker containers</span></span>

<span data-ttu-id="9905d-118">若要将 Azure 函数包装在 Docker 容器中，请安装[Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools) ，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9905d-118">To wrap an Azure Function in a Docker container, install the [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools) and then run the following command:</span></span>

```console
func init ProjectName --worker-runtime dotnet --docker
```

<span data-ttu-id="9905d-119">当创建项目时，它将包括 Dockerfile 和配置为`dotnet`的辅助运行时。</span><span class="sxs-lookup"><span data-stu-id="9905d-119">When the project is created, it will include a Dockerfile and the worker runtime configured to `dotnet`.</span></span> <span data-ttu-id="9905d-120">现在，你可以在本地创建和测试函数。</span><span class="sxs-lookup"><span data-stu-id="9905d-120">Now, you can create and test your function locally.</span></span> <span data-ttu-id="9905d-121">使用`docker build`和`docker run`命令生成并运行它。</span><span class="sxs-lookup"><span data-stu-id="9905d-121">Build and run it using the  `docker build` and `docker run` commands.</span></span> <span data-ttu-id="9905d-122">有关使用 Docker 支持构建 Azure Functions 的详细步骤，请参阅在[Linux 上使用自定义映像创建函数](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)教程。</span><span class="sxs-lookup"><span data-stu-id="9905d-122">For detailed steps to get started building Azure Functions with Docker support, see the [Create a function on Linux using a custom image](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) tutorial.</span></span>

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a><span data-ttu-id="9905d-123">如何将无服务器和 Kubernetes 与 KEDA 结合</span><span class="sxs-lookup"><span data-stu-id="9905d-123">How to combine serverless and Kubernetes with KEDA</span></span>

<span data-ttu-id="9905d-124">Azure 函数根据目标事件的速率，自动缩放以满足需求。</span><span class="sxs-lookup"><span data-stu-id="9905d-124">Azure functions scale automatically to meet demand based on the rate of events that are targeting it.</span></span> <span data-ttu-id="9905d-125">始终可以利用 AKS 托管函数并使用基于 Kubernetes 的事件驱动自动缩放或 KEDA。</span><span class="sxs-lookup"><span data-stu-id="9905d-125">You can always leverage AKS to host your functions and use Kubernetes-based Event Driven Autoscaling, or KEDA.</span></span> <span data-ttu-id="9905d-126">如果没有发生任何事件，KEDA 可以向下扩展到零实例。</span><span class="sxs-lookup"><span data-stu-id="9905d-126">When no events are occurring, KEDA can scale down to zero instances.</span></span> <span data-ttu-id="9905d-127">[了解有关通过 KEDA 缩放 Azure 函数的详细信息](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)。</span><span class="sxs-lookup"><span data-stu-id="9905d-127">[Learn more about scaling Azure functions with KEDA](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9905d-128">[上一页](leverage-serverless-functions.md)
>[下一页](deploy-containers-azure.md)</span><span class="sxs-lookup"><span data-stu-id="9905d-128">[Previous](leverage-serverless-functions.md)
[Next](deploy-containers-azure.md)</span></span>
