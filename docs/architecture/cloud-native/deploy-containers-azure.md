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
# <a name="deploying-containers-in-azure"></a>在 Azure 中部署容器

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

容器提供了许多好处，其中之一是可移植性。 可以轻松地获取在本地开发和测试的相同容器，并将其部署到 Azure，以便在过渡环境和生产环境中运行应用。 Azure 为基于容器的应用程序托管提供了许多选项，同样支持多种不同的部署方法。 最常见和最灵活的方法是将容器部署到 Azure 容器注册表（ACR），在该容器中，你希望使用哪些服务来承载它们。 Azure 用于容器的 Web 应用、Azure Kubernetes Services （AKS）和 Azure 容器实例（ACI）都可以访问已推送到 ACR 的容器映像。

## <a name="azure-container-registry"></a>Azure 容器注册表

Azure 容器注册表（ACR）允许您为所有容器部署生成、存储和管理映像。 可以向其部署容器的其他容器注册表（公用和专用）。 ACR 与其他选项的好处是，您可以将图像与生产环境保持接近，从而缩短生成和部署时间。 你还可以使用用于其他 Azure 资源的相同安全过程来保护这些资源，从而提高安全性并降低资产管理工作量。

使用 Azure 门户或[Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli)或[PowerShell 工具](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell)[创建容器注册表](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal)。 创建新的容器注册表只需要 Azure 订阅、资源组和唯一名称。 图3-11 显示了用于创建注册表的基本选项，这些选项将*托管在 azurecr.io。*

![创建容器注册表](./media/create-container-registry.png)
**图 3-11**。 创建容器注册表

创建注册表后，需要先对其进行身份验证，然后才能使用。 通常，你将使用 Azure CLI 命令登录到注册表：

```azurecli
az acr login --name *registryname*
```

在 Azure 容器注册表中创建注册表后，可以使用 docker 命令将容器映像推送到其中。 但是，必须先用 ACR 登录服务器的完全限定名称（URL）标记映像，然后才能执行此操作。 这将采用*registryname*. azurecr.io 格式。

```console
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

标记该映像后，使用 `docker push` 命令将该映像推送到 ACR 实例。

```console
docker push myregistry.azurecr.io/mycontainer:v1
```

将映像推送到注册表后，最好使用以下命令从本地 Docker 环境中删除映像：

```console
docker rmi myregistry.azurecr.io/mycontainer:v1
```

开发人员很少直接从其计算机推送到容器注册表。 相反，在 Azure DevOps 之类的工具中定义的生成管道应负责执行此过程。 有关详细信息，请参阅[云-Native DevOps 章节](devops.md)。

## <a name="azure-kubernetes-service"></a>Azure Kubernetes 服务

如果基于容器的应用程序涉及多个容器，则很可能需要使用 Kubernetes 等*orchestrator*来定义和管理容器之间的交互。 将容器映像部署到 ACR 后，可以轻松地将 Azure Kubernetes 服务配置为从 ACR 自动部署更新后的映像。 使用完整的 CI/CD 管道，你可以配置一个有空间的[发布](https://martinfowler.com/bliki/CanaryRelease.html)策略，以最大程度地减少快速部署更新时所涉及的风险。 新版本的应用程序最初在生产环境中进行了配置，但未将流量路由到该应用程序，然后将少量用户路由到新部署的应用程序版本。 随着团队在软件的新版本中取得自信，新版本的更多实例将推出，而以前版本的实例将被停用。 AKS 轻松支持这种部署样式。

与 Azure 中的大多数资源一样，你可以使用门户或使用命令行工具或 Helm 或 Terraform 等基础结构自动化工具来创建 Azure Kubernetes 群集。 若要开始使用新群集，需要提供以下信息：

- Azure 订阅
- 资源组
- Kubernetes 群集名称
- Region
- Kubernetes 版本
- DNS 名称前缀
- 节点大小
- 节点计数

此信息足以开始。 作为 Azure 门户中创建过程的一部分，你还可以配置以下群集功能的选项：

- 缩放
- 身份验证
- 联网
- 监视
- Tags

本[快速入门演示如何使用 Azure 门户部署 AKS 群集](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal)。

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

复杂的 Kubernetes 群集可能需要大量资源来托管，这会使开发人员难以在一台计算机上运行整个应用程序（尤其是便携式计算机）。 Azure Dev Spaces 通过允许开发人员使用 Azure 中托管的 Azure Kubernetes 群集的自己版本来提供此解决方案。 Azure Dev Spaces 旨在使用 AKS 简化基于微服务的应用程序的开发。

为了理解 Azure Dev Spaces 的价值，让我在 Microsoft Azure 的容器的 Gabe Monroy 中共享此报价：

"假设您是一名新员工，尝试修复由数十个组件组成的复杂的微服务应用程序中的 bug，每个组件都有其自己的配置和支持服务。 若要开始，必须配置本地开发环境，使其可以模拟生产环境，包括设置 IDE、构建工具链、容器化服务依赖项、本地 Kubernetes 环境、模拟用于支持服务等。 在设置开发环境的过程中，解决第一个 bug 可能需要数天的时间。

> 或者，可以使用 Dev Spaces 和 AKS。 "

使用 Azure Dev Spaces 的过程涉及以下步骤：

1. 创建 dev 空间。
2. 配置根开发人员空间。
3. 配置子开发人员空间（适用于你自己的系统版本）。
4. 连接到 dev 空间。

所有这些步骤都可以使用 Azure CLI 和新的 `azds` 命令行工具来执行。 例如，若要为给定的 Kubernetes 群集创建新的 Azure Dev 空间，请使用如下所示的命令：

```azurecli
az aks use-dev-spaces -g my-aks-resource-group -n MyAKSCluster
```

接下来，可以使用 `azds prep` 命令生成运行应用程序所需的 Docker 和 Helm 图表资产。 然后，使用 `azds up`在 AKS 中运行你的代码。 首次运行此命令时，将安装 Helm 图表，并将根据说明生成和部署容器。 首次运行时可能需要几分钟时间。 但是，在进行更改后，可以使用 `azds space select` 连接到自己的子开发人员空间，然后在隔离的子开发人员空间中部署和调试更新。 开发人员空间启动并运行后，可以通过重新发出 `azds up` 命令向其发送更新，也可以使用 Visual Studio 中的内置工具或 Visual Studio Code。 使用 VS Code，可以使用命令面板连接到开发环境。 图3-12 演示了如何使用 Visual Studio 中的 Azure Dev Spaces 启动 web 应用程序。

![连接到 Visual Studio 中的 Azure Dev Spaces](./media/azure-dev-spaces-visual-studio-launchsettings.png)
**图 3-12**。 在 Visual Studio 中连接到 Azure Dev Spaces

## <a name="references"></a>参考

- [未的版本](https://martinfowler.com/bliki/CanaryRelease.html)
- [Azure Dev Spaces 与 VS Code](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore)
- [与 Visual Studio Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore-visualstudio)

>[!div class="step-by-step"]
>[上一页](combine-containers-serverless-approaches.md)
>[下一页](scale-containers-serverless.md)
