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
# <a name="combining-containers-and-serverless-approaches"></a>合并容器和无服务器方法

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

通常，基于微服务的应用程序很大程度上依赖容器、业务流程和消息传递来实现节点之间的通信。 此消息传递是 Azure Functions 的理想任务，但随着应用程序的其余部分使用 Kubernetes 和相关工具进行了配置和部署，最好能够利用此相同工具集中的 Azure Functions。 幸运的是，您可以将 Azure Functions 包装在 Docker 容器中，并使用与 Kubernetes 的其他应用程序相同的过程和工具进行部署。

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a>使用无服务器的容器有何意义？

默认情况下，无服务器函数不能识别运行它们的平台。 但是，在某些情况下，你可能有特定的要求，使你可以自定义代码将在其中运行的容器映像。 你可能想要使用自定义映像，因为函数依赖于特定语言版本，或者具有默认图像不支持的依赖项或配置要求。 在这些情况下，自定义自己的容器并在自定义 Docker 容器中部署函数可能有意义。

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a>何时应避免使用带有 Azure Functions 的容器？

如果希望从函数的消耗计划计费中获益，如果使用自己的容器，则无法这样做。 此外，如果不只使用 Docker 容器并将函数部署到自己的 Kubernetes 群集，则不会再受益于 Azure Functions 提供的内置缩放。 你将需要使用 Kubernetes 的缩放功能，如下所述。

## <a name="how-to-combine-serverless-and-docker-containers"></a>如何组合无服务器和 Docker 容器

若要将 Azure 函数包装在 Docker 容器中，请安装 Azure Functions Core Tools，并运行以下命令：

```console
func init ProjectName --docker
```

从以下选项中选择所需的辅助运行时：

- `dotnet` (C#)
- `node` (JavaScript)
- `python`

创建项目时，它将包含一个 Dockerfile。 现在，你可以在本地创建和测试函数。 使用 `docker build` 和 `docker run` 命令生成并运行该命令。 有关使用 Docker 支持构建 Azure Functions 的详细步骤，请参阅在[Linux 上使用自定义映像创建函数](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)教程。

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a>如何将无服务器和 Kubernetes 与 KEDA 结合

Azure 函数根据针对给定函数的事件速率，自动缩放以满足需求。 此外，你还可以利用 Kubernetes 来托管函数并使用基于 Kubernetes 的事件驱动自动缩放或 KEDA。 如果没有发生任何事件，KEDA 可以向下扩展到0个实例，然后在响应事件时，它可以使用其水平 pod 自动缩放程序扩展容器的数量，以满足需求。 [了解有关通过 KEDA 缩放 Azure 函数的详细信息](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)。

## <a name="references"></a>reference

- [在 Docker 容器中运行 Azure Functions](https://markheath.net/post/azure-functions-docker)
- [在 Linux 上使用自定义映像创建函数](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Azure Functions 与 Kubernetes 事件驱动的自动缩放](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)

>[!div class="step-by-step"]
>[上一页](leverage-serverless-functions.md)
>[下一页](deploy-containers-azure.md)
