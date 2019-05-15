---
title: 协调安排微服务和多容器应用程序，实现高可伸缩性和高可用性
description: 了解如何使用 Azure Kubernetes 服务部署应用。
ms.date: 02/15/2019
ms.openlocfilehash: 88e76b4b0a3686f4227a6aee1b7fbd2bfe55fdcc
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644656"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="63bd0-103">部署到 Azure Kubernetes 服务 (AKS)</span><span class="sxs-lookup"><span data-stu-id="63bd0-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="63bd0-104">可以与 AKS 使用您首选的客户端的操作系统进行交互，下面我们介绍如何使用 Microsoft Windows 和 Windows，在 Ubuntu Linux 的嵌入式的版本使用 Bash 命令。</span><span class="sxs-lookup"><span data-stu-id="63bd0-104">You can interact with AKS using your preferred client operating system, here we show how to do it with Microsoft Windows and an embedded version of Ubuntu Linux in Windows, using Bash commands.</span></span>

<span data-ttu-id="63bd0-105">使用 AKS 之前，有的先决条件是：</span><span class="sxs-lookup"><span data-stu-id="63bd0-105">Prerequisites to have before using AKS are:</span></span>

- <span data-ttu-id="63bd0-106">Linux 或 Mac 开发计算机</span><span class="sxs-lookup"><span data-stu-id="63bd0-106">Linux or Mac development machine</span></span>
- <span data-ttu-id="63bd0-107">Windows 开发计算机</span><span class="sxs-lookup"><span data-stu-id="63bd0-107">Windows development machine</span></span>
  - <span data-ttu-id="63bd0-108">在 Windows 上启用了开发人员模式</span><span class="sxs-lookup"><span data-stu-id="63bd0-108">Developer Mode enabled on Windows</span></span>
  - <span data-ttu-id="63bd0-109">适用于 Linux 的 Windows 子系统</span><span class="sxs-lookup"><span data-stu-id="63bd0-109">Windows Subsystem for Linux</span></span>
- <span data-ttu-id="63bd0-110">Azure CLI 上安装[Windows、 Mac 或 Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span><span class="sxs-lookup"><span data-stu-id="63bd0-110">Azure-CLI installed on [Windows, Mac or Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span></span>

> [!NOTE]
> <span data-ttu-id="63bd0-111">若要查找有关完整信息：</span><span class="sxs-lookup"><span data-stu-id="63bd0-111">To find complete information about:</span></span>
>
> <span data-ttu-id="63bd0-112">Azure CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span><span class="sxs-lookup"><span data-stu-id="63bd0-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span></span>
>
> <span data-ttu-id="63bd0-113">适用于 Linux 的 Windows 子系统： <https://docs.microsoft.com/windows/wsl/about></span><span class="sxs-lookup"><span data-stu-id="63bd0-113">Windows Subsystem for Linux: <https://docs.microsoft.com/windows/wsl/about></span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="63bd0-114">在 Azure 中创建的 AKS 环境</span><span class="sxs-lookup"><span data-stu-id="63bd0-114">Create the AKS environment in Azure</span></span>

<span data-ttu-id="63bd0-115">有几种方法来创建 AKS 环境。</span><span class="sxs-lookup"><span data-stu-id="63bd0-115">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="63bd0-116">它可以通过使用 Azure CLI 命令或使用 Azure 门户完成。</span><span class="sxs-lookup"><span data-stu-id="63bd0-116">It can be done by using Azure-CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="63bd0-117">这里，可以探讨一些示例使用 Azure CLI 创建群集和 Azure 门户以查看结果。</span><span class="sxs-lookup"><span data-stu-id="63bd0-117">Here you can explore some examples using the Azure-CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="63bd0-118">此外需要具有 Kubectl 和 Docker 在开发计算机。</span><span class="sxs-lookup"><span data-stu-id="63bd0-118">You also need to have Kubectl and Docker in your development machine.</span></span>  

## <a name="create-the-aks-cluster"></a><span data-ttu-id="63bd0-119">创建 AKS 群集</span><span class="sxs-lookup"><span data-stu-id="63bd0-119">Create the AKS cluster</span></span>

<span data-ttu-id="63bd0-120">创建 AKS 群集使用此命令：</span><span class="sxs-lookup"><span data-stu-id="63bd0-120">Create the AKS cluster using this command:</span></span>

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

<span data-ttu-id="63bd0-121">创建作业完成后，可以看到在 Azure 门户中创建 AKS:</span><span class="sxs-lookup"><span data-stu-id="63bd0-121">After the creation job finishes, you can see the AKS created in the Azure portal:</span></span>

<span data-ttu-id="63bd0-122">资源组中：</span><span class="sxs-lookup"><span data-stu-id="63bd0-122">The resource group:</span></span>

![Azure AKS 资源组的浏览器视图。](media/aks-resource-group-view.png)

<span data-ttu-id="63bd0-124">**图 4-17**。</span><span class="sxs-lookup"><span data-stu-id="63bd0-124">**Figure 4-17**.</span></span> <span data-ttu-id="63bd0-125">从 Azure AKS 资源组视图。</span><span class="sxs-lookup"><span data-stu-id="63bd0-125">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="63bd0-126">AKS 群集：</span><span class="sxs-lookup"><span data-stu-id="63bd0-126">The AKS cluster:</span></span>

![AKS 资源组的浏览器视图。](media/aks-cluster-view.png)

<span data-ttu-id="63bd0-128">**图 4-18**.</span><span class="sxs-lookup"><span data-stu-id="63bd0-128">**Figure 4-18**.</span></span> <span data-ttu-id="63bd0-129">从 Azure AKS 视图。</span><span class="sxs-lookup"><span data-stu-id="63bd0-129">AKS view from Azure.</span></span>

<span data-ttu-id="63bd0-130">你还可以查看使用创建的节点`Azure-CLI`和`Kubectl`。</span><span class="sxs-lookup"><span data-stu-id="63bd0-130">You can also view the node created using `Azure-CLI` and `Kubectl`.</span></span>

<span data-ttu-id="63bd0-131">首先，获取凭据：</span><span class="sxs-lookup"><span data-stu-id="63bd0-131">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![控制台输出从上面的命令：合并"作为当前上下文中 /root/.kube/config MsSampleK8Cluster。](media/get-credentials-command-result.png)

<span data-ttu-id="63bd0-133">**图 4-19**.</span><span class="sxs-lookup"><span data-stu-id="63bd0-133">**Figure 4-19**.</span></span> <span data-ttu-id="63bd0-134">`aks get-credentials` 命令的结果。</span><span class="sxs-lookup"><span data-stu-id="63bd0-134">`aks get-credentials` command result.</span></span>

<span data-ttu-id="63bd0-135">然后，从 Kubectl 获取节点：</span><span class="sxs-lookup"><span data-stu-id="63bd0-135">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![控制台输出通过命令：包括状态、 年龄 （运行的时间） 和版本的节点的列表](media/kubectl-get-nodes-command-result.png)

<span data-ttu-id="63bd0-137">图 4-20。</span><span class="sxs-lookup"><span data-stu-id="63bd0-137">**Figure 4-20**.</span></span> <span data-ttu-id="63bd0-138">`kubectl get nodes` 命令的结果。</span><span class="sxs-lookup"><span data-stu-id="63bd0-138">`kubectl get nodes` command result.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="63bd0-139">[上一页](orchestrate-high-scalability-availability.md)
>[下一页](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="63bd0-139">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
