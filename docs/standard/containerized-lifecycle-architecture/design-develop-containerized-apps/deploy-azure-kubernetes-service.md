---
title: 协调安排微服务和多容器应用程序，实现高可伸缩性和高可用性
description: 了解如何使用 Azure Kubernetes 服务部署应用。
ms.date: 02/15/2019
ms.openlocfilehash: 88e76b4b0a3686f4227a6aee1b7fbd2bfe55fdcc
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644656"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a>部署到 Azure Kubernetes 服务 (AKS)

可以使用首选的客户端操作系统与 AKS 进行交互，此处使用 Bash 命令介绍如何使用 Microsoft Windows 和 Windows 中的 Ubuntu Linux 内嵌版本执行该操作。

使用 AKS 之前，需具备以下先决条件：

- Linux 或 Mac 开发计算机
- Windows 开发计算机
  - 在 Windows 上启用“开发人员模式”
  - 适用于 Linux 的 Windows 子系统
- 在 [Windows、Mac 或 Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) 上安装 Azure CLI

> [!NOTE]
> 查找有关以下内容的完整信息：
>
> Azure-CLI：<https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest>
>
> 适用于 Linux 的 Windows 子系统：<https://docs.microsoft.com/windows/wsl/about>

## <a name="create-the-aks-environment-in-azure"></a>在 Azure 中创建 AKS 环境

有多种方法可创建 AKS 环境。 可以使用 Azure-CLI 命令或使用 Azure 门户来完成此操作。

此处是有关使用 Azure-CLI 创建群集和通过 Azure 门户查看结果的一些示例。 还需要在开发计算机中安装 Kubectl 和 Docker。  

## <a name="create-the-aks-cluster"></a>创建 AKS 群集

使用此命令创建 AKS 群集：

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

创建作业完成后，可以在 Azure 门户中看到创建的 AKS：

资源组：

![Azure AKS 资源组的浏览器视图。](media/aks-resource-group-view.png)

**图 4-17**。 Azure 的 AKS 资源组视图。

AKS 群集：

![AKS 资源组的浏览器视图。](media/aks-cluster-view.png)

**图 4-18**. Azure 的 AKS 视图。

还可以查看使用 `Azure-CLI` 和 `Kubectl` 创建的节点。

首先，获取凭据：

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![来自上述命令的控制台输出：将“MsSampleK8Cluster”合并为 /root/.kube/config 中的当前上下文。](media/get-credentials-command-result.png)

**图 4-19**. `aks get-credentials` 命令结果。

然后，从 Kubectl 获取节点：

```console
kubectl get nodes
```

![来自上述命令的控制台输出：包括状态、时限（运行时间）和版本的节点列表](media/kubectl-get-nodes-command-result.png)

图 4-20  。 `kubectl get nodes` 命令结果。

>[!div class="step-by-step"]
>[上一页](orchestrate-high-scalability-availability.md)
>[下一页](docker-apps-development-environment.md)
