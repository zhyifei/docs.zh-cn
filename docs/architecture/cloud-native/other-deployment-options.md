---
title: 其他容器部署选项
description: 使用 Azure 的其他容器部署选项
ms.date: 04/13/2020
ms.openlocfilehash: 3cae771b3877215a7fc91afd4f406fdfc9ff2771
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199997"
---
# <a name="other-container-deployment-options"></a>其他容器部署选项

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

除了 Azure Kubernetes Service （AKS）以外，还可以为容器和 Azure 容器实例将容器部署到 Azure App Service。

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a>部署到容器的应用服务有何意义？

不需要业务流程的简单生产应用程序非常适合用于容器 Azure App Service。

## <a name="how-to-deploy-to-app-service-for-containers"></a>如何部署到容器的应用服务

若要部署到[容器 Azure App Service](https://azure.microsoft.com/services/app-service/containers/)，你将需要一个 Azure 容器注册表（ACR）实例和用于访问该实例的凭据。 将容器映像推送到 ACR 存储库，以便将其提取到 Azure App Service 中。 完成后，可以将应用程序配置为连续部署。 这样做会在图像更改为 ACR 时自动部署更新。

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a>部署到 Azure 容器实例时有何意义？

使用[Azure 容器实例（ACI）](https://azure.microsoft.com/services/container-instances/) ，可以在托管的无服务器云环境中运行 Docker 容器，而无需设置虚拟机或群集。 这是一个很好的解决方案，适用于可在隔离容器中运行的短时间运行的工作负荷。 请考虑将 ACI 用于简单服务、测试方案、任务自动化和生成作业。 ACI 向上旋转容器实例，执行任务，然后将其向下旋转。

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a>如何将应用部署到 Azure 容器实例

若要部署到[Azure 容器实例（ACI）](https://docs.microsoft.com/azure/container-instances/)，需要使用 Azure 容器注册表（ACR）和凭据进行访问。 将容器映像推送到存储库后，可将其拉入 ACI。 可以使用 Azure 门户或命令行界面来处理 ACI。 ACR 提供与 ACI 的紧密集成。 图3-14 显示了如何将单个容器映像推送到 ACR。

![Azure 容器注册表运行实例](./media/acr-runinstance-contextmenu.png)

**图 3-14**。 Azure 容器注册表运行实例

可以快速完成在 ACI 中创建实例的操作。 指定映像注册表、Azure 资源组信息、要分配的内存量以及要侦听的端口。 本[快速入门演示如何使用 Azure 门户将容器实例部署到 ACI](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal)。

部署完成后，查找新部署的容器的 IP 地址，并通过指定的端口与它进行通信。

Azure 容器实例提供了在 Azure 中运行简单容器工作负荷的最快方法。 不需要配置应用服务、orchestrator 或虚拟机。 对于需要完整容器业务流程的方案、服务发现、自动缩放或协调升级，我们建议 Azure Kubernetes Service （AKS）。

## <a name="references"></a>参考

- [什么是 Kubernetes？](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [通过 Minikube 安装 Kubernetes](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [MiniKube vs Docker Desktop](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Visual Studio Tools for Docker](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)
- [了解无服务器冷启动](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)
- [准备好 Azure Functions 实例](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances)
- [在 Linux 上使用自定义映像创建函数](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [在 Docker 容器中运行 Azure Functions](https://markheath.net/post/azure-functions-docker)
- [在 Linux 上使用自定义映像创建函数](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Azure Functions 与 Kubernetes 事件驱动的自动缩放](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)
- [未的版本](https://martinfowler.com/bliki/CanaryRelease.html)
- [Azure Dev Spaces 与 VS Code](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore)
- [与 Visual Studio Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore-visualstudio)
- [AKS 多节点池](https://docs.microsoft.com/azure/aks/use-multiple-node-pools)
- [AKS 群集自动缩放程序](https://docs.microsoft.com/azure/aks/cluster-autoscaler)
- [教程：在 AKS 中缩放应用程序](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale)
- [Azure Functions 的缩放和托管](https://docs.microsoft.com/azure/azure-functions/functions-scale)
- [Azure 容器实例文档](https://docs.microsoft.com/azure/container-instances/)
- [从 ACR 部署容器实例](https://docs.microsoft.com/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
>[上一页](scale-containers-serverless.md)
>[下一页](communication-patterns.md)
