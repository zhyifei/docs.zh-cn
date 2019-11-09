---
title: 合并容器和无服务器方法
description: 将容器和 Kubernetes 与无服务器方法结合起来
ms.date: 06/30/2019
ms.openlocfilehash: 58aff43adbdd2e629370cc685f32c7b61c25f85e
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840591"
---
# <a name="combining-containers-and-serverless-approaches"></a><span data-ttu-id="eee3f-103">合并容器和无服务器方法</span><span class="sxs-lookup"><span data-stu-id="eee3f-103">Combining containers and serverless approaches</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="eee3f-104">通常，基于微服务的应用程序很大程度上依赖容器、业务流程和消息传递来实现节点之间的通信。</span><span class="sxs-lookup"><span data-stu-id="eee3f-104">Frequently, microservices-based applications rely heavily on containers, orchestration, and message-passing for communication between nodes.</span></span> <span data-ttu-id="eee3f-105">此消息传递是 Azure Functions 的理想任务，但随着应用程序的其余部分使用 Kubernetes 和相关工具进行了配置和部署，最好能够利用此相同工具集中的 Azure Functions。</span><span class="sxs-lookup"><span data-stu-id="eee3f-105">This messaging is an ideal task for Azure Functions, but with the rest of the application configured and deployed using Kubernetes and related tools, it would be nice to be able to leverage Azure Functions within this same toolset.</span></span> <span data-ttu-id="eee3f-106">幸运的是，您可以将 Azure Functions 包装在 Docker 容器中，并使用与 Kubernetes 的其他应用程序相同的过程和工具进行部署。</span><span class="sxs-lookup"><span data-stu-id="eee3f-106">Fortunately, you can wrap Azure Functions in Docker containers and deploy them using the same processes and tools as the rest of your Kubernetes-based app.</span></span>

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a><span data-ttu-id="eee3f-107">使用无服务器的容器有何意义？</span><span class="sxs-lookup"><span data-stu-id="eee3f-107">When does it make sense to use containers with serverless?</span></span>

<span data-ttu-id="eee3f-108">默认情况下，无服务器函数不能识别运行它们的平台。</span><span class="sxs-lookup"><span data-stu-id="eee3f-108">By default, your serverless functions have no knowledge of the platform on which they'll run.</span></span> <span data-ttu-id="eee3f-109">但是，在某些情况下，你可能有特定的要求，使你可以自定义代码将在其中运行的容器映像。</span><span class="sxs-lookup"><span data-stu-id="eee3f-109">However, in some cases you may have specific requirements that make it important for you to customize the container image in which your code will run.</span></span> <span data-ttu-id="eee3f-110">你可能想要使用自定义映像，因为函数依赖于特定语言版本，或者具有默认图像不支持的依赖项或配置要求。</span><span class="sxs-lookup"><span data-stu-id="eee3f-110">You may want to use a custom image because your function relies on a specific language version or has dependencies or configuration requirements that aren't supported by the default image.</span></span> <span data-ttu-id="eee3f-111">在这些情况下，自定义自己的容器并在自定义 Docker 容器中部署函数可能有意义。</span><span class="sxs-lookup"><span data-stu-id="eee3f-111">In these cases, it may make sense to customize your own container and deploy your function in a custom Docker container.</span></span>

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a><span data-ttu-id="eee3f-112">何时应避免使用带有 Azure Functions 的容器？</span><span class="sxs-lookup"><span data-stu-id="eee3f-112">When should you avoid using containers with Azure Functions?</span></span>

<span data-ttu-id="eee3f-113">如果希望从函数的消耗计划计费中获益，如果使用自己的容器，则无法这样做。</span><span class="sxs-lookup"><span data-stu-id="eee3f-113">If you're expecting to benefit from the consumption plan billing for your function, you won't be able to do so if you're using your own container.</span></span> <span data-ttu-id="eee3f-114">此外，如果不只使用 Docker 容器并将函数部署到自己的 Kubernetes 群集，则不会再受益于 Azure Functions 提供的内置缩放。</span><span class="sxs-lookup"><span data-stu-id="eee3f-114">What's more, if you go beyond just using a Docker container and deploy your functions to your own Kubernetes cluster, you'll no longer benefit from the built-in scaling provided by Azure Functions.</span></span> <span data-ttu-id="eee3f-115">你将需要使用 Kubernetes 的缩放功能，如下所述。</span><span class="sxs-lookup"><span data-stu-id="eee3f-115">You'll need to use Kubernetes' scaling features, described below.</span></span>

## <a name="how-to-combine-serverless-and-docker-containers"></a><span data-ttu-id="eee3f-116">如何组合无服务器和 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="eee3f-116">How to combine serverless and Docker containers</span></span>

<span data-ttu-id="eee3f-117">若要将 Azure 函数包装在 Docker 容器中，请安装 Azure Functions Core Tools，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="eee3f-117">To wrap an Azure Function in a Docker container, install the Azure Functions Core Tools and then run the following command:</span></span>

```console
func init ProjectName --docker
```

<span data-ttu-id="eee3f-118">从以下选项中选择所需的辅助运行时：</span><span class="sxs-lookup"><span data-stu-id="eee3f-118">Choose which worker runtime you want from the following options:</span></span>

- <span data-ttu-id="eee3f-119">`dotnet` (C#)</span><span class="sxs-lookup"><span data-stu-id="eee3f-119">`dotnet` (C#)</span></span>
- <span data-ttu-id="eee3f-120">`node` (JavaScript)</span><span class="sxs-lookup"><span data-stu-id="eee3f-120">`node` (JavaScript)</span></span>
- `python`

<span data-ttu-id="eee3f-121">创建项目时，它将包含一个 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="eee3f-121">When the project is created, it will include a Dockerfile.</span></span> <span data-ttu-id="eee3f-122">现在，你可以在本地创建和测试函数。</span><span class="sxs-lookup"><span data-stu-id="eee3f-122">Now, you can create and test your function locally.</span></span> <span data-ttu-id="eee3f-123">使用 `docker build` 和 `docker run` 命令生成并运行该命令。</span><span class="sxs-lookup"><span data-stu-id="eee3f-123">Build and run it using the  `docker build` and `docker run` commands.</span></span> <span data-ttu-id="eee3f-124">有关使用 Docker 支持构建 Azure Functions 的详细步骤，请参阅在[Linux 上使用自定义映像创建函数](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)教程。</span><span class="sxs-lookup"><span data-stu-id="eee3f-124">For detailed steps to get started building Azure Functions with Docker support, see the [Create a function on Linux using a custom image](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) tutorial.</span></span>

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a><span data-ttu-id="eee3f-125">如何将无服务器和 Kubernetes 与 KEDA 结合</span><span class="sxs-lookup"><span data-stu-id="eee3f-125">How to combine serverless and Kubernetes with KEDA</span></span>

<span data-ttu-id="eee3f-126">Azure 函数根据针对给定函数的事件速率，自动缩放以满足需求。</span><span class="sxs-lookup"><span data-stu-id="eee3f-126">Azure functions scale automatically to meet demand based on the rate of events that are targeting a given function.</span></span> <span data-ttu-id="eee3f-127">此外，你还可以利用 Kubernetes 来托管函数并使用基于 Kubernetes 的事件驱动自动缩放或 KEDA。</span><span class="sxs-lookup"><span data-stu-id="eee3f-127">Additionally, you can leverage Kubernetes to host your functions and use Kubernetes-based Event Driven Autoscaling, or KEDA.</span></span> <span data-ttu-id="eee3f-128">如果没有发生任何事件，KEDA 可以向下扩展到0个实例，然后在响应事件时，它可以使用其水平 pod 自动缩放程序扩展容器的数量，以满足需求。</span><span class="sxs-lookup"><span data-stu-id="eee3f-128">When no events are occurring, KEDA can scale down to 0 instances, and then in response to events it can scale up the number of containers to meet the demand using its horizontal pod autoscaler.</span></span> <span data-ttu-id="eee3f-129">[了解有关通过 KEDA 缩放 Azure 函数的详细信息](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)。</span><span class="sxs-lookup"><span data-stu-id="eee3f-129">[Learn more about scaling Azure functions with KEDA](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).</span></span>

## <a name="references"></a><span data-ttu-id="eee3f-130">reference</span><span class="sxs-lookup"><span data-stu-id="eee3f-130">References</span></span>

- [<span data-ttu-id="eee3f-131">在 Docker 容器中运行 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="eee3f-131">Run Azure Functions in a Docker Container</span></span>](https://markheath.net/post/azure-functions-docker)
- [<span data-ttu-id="eee3f-132">在 Linux 上使用自定义映像创建函数</span><span class="sxs-lookup"><span data-stu-id="eee3f-132">Create a function on Linux using a custom image</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [<span data-ttu-id="eee3f-133">Azure Functions 与 Kubernetes 事件驱动的自动缩放</span><span class="sxs-lookup"><span data-stu-id="eee3f-133">Azure Functions with Kubernetes Event Driven Autoscaling</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)

>[!div class="step-by-step"]
><span data-ttu-id="eee3f-134">[上一页](leverage-serverless-functions.md)
>[下一页](deploy-containers-azure.md)</span><span class="sxs-lookup"><span data-stu-id="eee3f-134">[Previous](leverage-serverless-functions.md)
[Next](deploy-containers-azure.md)</span></span>
