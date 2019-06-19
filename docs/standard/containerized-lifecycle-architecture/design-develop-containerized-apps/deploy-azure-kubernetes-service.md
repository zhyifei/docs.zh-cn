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
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="55291-103">部署到 Azure Kubernetes 服务 (AKS)</span><span class="sxs-lookup"><span data-stu-id="55291-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="55291-104">可以使用首选的客户端操作系统与 AKS 进行交互，此处使用 Bash 命令介绍如何使用 Microsoft Windows 和 Windows 中的 Ubuntu Linux 内嵌版本执行该操作。</span><span class="sxs-lookup"><span data-stu-id="55291-104">You can interact with AKS using your preferred client operating system, here we show how to do it with Microsoft Windows and an embedded version of Ubuntu Linux in Windows, using Bash commands.</span></span>

<span data-ttu-id="55291-105">使用 AKS 之前，需具备以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="55291-105">Prerequisites to have before using AKS are:</span></span>

- <span data-ttu-id="55291-106">Linux 或 Mac 开发计算机</span><span class="sxs-lookup"><span data-stu-id="55291-106">Linux or Mac development machine</span></span>
- <span data-ttu-id="55291-107">Windows 开发计算机</span><span class="sxs-lookup"><span data-stu-id="55291-107">Windows development machine</span></span>
  - <span data-ttu-id="55291-108">在 Windows 上启用“开发人员模式”</span><span class="sxs-lookup"><span data-stu-id="55291-108">Developer Mode enabled on Windows</span></span>
  - <span data-ttu-id="55291-109">适用于 Linux 的 Windows 子系统</span><span class="sxs-lookup"><span data-stu-id="55291-109">Windows Subsystem for Linux</span></span>
- <span data-ttu-id="55291-110">在 [Windows、Mac 或 Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) 上安装 Azure CLI</span><span class="sxs-lookup"><span data-stu-id="55291-110">Azure-CLI installed on [Windows, Mac or Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span></span>

> [!NOTE]
> <span data-ttu-id="55291-111">查找有关以下内容的完整信息：</span><span class="sxs-lookup"><span data-stu-id="55291-111">To find complete information about:</span></span>
>
> <span data-ttu-id="55291-112">Azure-CLI：<https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span><span class="sxs-lookup"><span data-stu-id="55291-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span></span>
>
> <span data-ttu-id="55291-113">适用于 Linux 的 Windows 子系统：<https://docs.microsoft.com/windows/wsl/about></span><span class="sxs-lookup"><span data-stu-id="55291-113">Windows Subsystem for Linux: <https://docs.microsoft.com/windows/wsl/about></span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="55291-114">在 Azure 中创建 AKS 环境</span><span class="sxs-lookup"><span data-stu-id="55291-114">Create the AKS environment in Azure</span></span>

<span data-ttu-id="55291-115">有多种方法可创建 AKS 环境。</span><span class="sxs-lookup"><span data-stu-id="55291-115">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="55291-116">可以使用 Azure-CLI 命令或使用 Azure 门户来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="55291-116">It can be done by using Azure-CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="55291-117">此处是有关使用 Azure-CLI 创建群集和通过 Azure 门户查看结果的一些示例。</span><span class="sxs-lookup"><span data-stu-id="55291-117">Here you can explore some examples using the Azure-CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="55291-118">还需要在开发计算机中安装 Kubectl 和 Docker。</span><span class="sxs-lookup"><span data-stu-id="55291-118">You also need to have Kubectl and Docker in your development machine.</span></span>  

## <a name="create-the-aks-cluster"></a><span data-ttu-id="55291-119">创建 AKS 群集</span><span class="sxs-lookup"><span data-stu-id="55291-119">Create the AKS cluster</span></span>

<span data-ttu-id="55291-120">使用此命令创建 AKS 群集：</span><span class="sxs-lookup"><span data-stu-id="55291-120">Create the AKS cluster using this command:</span></span>

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

<span data-ttu-id="55291-121">创建作业完成后，可以在 Azure 门户中看到创建的 AKS：</span><span class="sxs-lookup"><span data-stu-id="55291-121">After the creation job finishes, you can see the AKS created in the Azure portal:</span></span>

<span data-ttu-id="55291-122">资源组：</span><span class="sxs-lookup"><span data-stu-id="55291-122">The resource group:</span></span>

![Azure AKS 资源组的浏览器视图。](media/aks-resource-group-view.png)

<span data-ttu-id="55291-124">**图 4-17**。</span><span class="sxs-lookup"><span data-stu-id="55291-124">**Figure 4-17**.</span></span> <span data-ttu-id="55291-125">Azure 的 AKS 资源组视图。</span><span class="sxs-lookup"><span data-stu-id="55291-125">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="55291-126">AKS 群集：</span><span class="sxs-lookup"><span data-stu-id="55291-126">The AKS cluster:</span></span>

![AKS 资源组的浏览器视图。](media/aks-cluster-view.png)

<span data-ttu-id="55291-128">**图 4-18**.</span><span class="sxs-lookup"><span data-stu-id="55291-128">**Figure 4-18**.</span></span> <span data-ttu-id="55291-129">Azure 的 AKS 视图。</span><span class="sxs-lookup"><span data-stu-id="55291-129">AKS view from Azure.</span></span>

<span data-ttu-id="55291-130">还可以查看使用 `Azure-CLI` 和 `Kubectl` 创建的节点。</span><span class="sxs-lookup"><span data-stu-id="55291-130">You can also view the node created using `Azure-CLI` and `Kubectl`.</span></span>

<span data-ttu-id="55291-131">首先，获取凭据：</span><span class="sxs-lookup"><span data-stu-id="55291-131">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![来自上述命令的控制台输出：将“MsSampleK8Cluster”合并为 /root/.kube/config 中的当前上下文。](media/get-credentials-command-result.png)

<span data-ttu-id="55291-133">**图 4-19**.</span><span class="sxs-lookup"><span data-stu-id="55291-133">**Figure 4-19**.</span></span> <span data-ttu-id="55291-134">`aks get-credentials` 命令结果。</span><span class="sxs-lookup"><span data-stu-id="55291-134">`aks get-credentials` command result.</span></span>

<span data-ttu-id="55291-135">然后，从 Kubectl 获取节点：</span><span class="sxs-lookup"><span data-stu-id="55291-135">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![来自上述命令的控制台输出：包括状态、时限（运行时间）和版本的节点列表](media/kubectl-get-nodes-command-result.png)

<span data-ttu-id="55291-137">图 4-20  。</span><span class="sxs-lookup"><span data-stu-id="55291-137">**Figure 4-20**.</span></span> <span data-ttu-id="55291-138">`kubectl get nodes` 命令结果。</span><span class="sxs-lookup"><span data-stu-id="55291-138">`kubectl get nodes` command result.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="55291-139">[上一页](orchestrate-high-scalability-availability.md)
>[下一页](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="55291-139">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
