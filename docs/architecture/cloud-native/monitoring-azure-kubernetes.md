---
title: 在 Azure Kubernetes 服务中进行监视
description: 在 Azure Kubernetes 服务中进行监视
ms.date: 09/23/2019
ms.openlocfilehash: 71192601eac2169db188b25da3dc91b71b860903
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841125"
---
# <a name="monitoring-in-azure-kubernetes-services"></a><span data-ttu-id="16981-103">在 Azure Kubernetes 服务中进行监视</span><span class="sxs-lookup"><span data-stu-id="16981-103">Monitoring in Azure Kubernetes Services</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="16981-104">Kubernetes 中的内置日志记录为基元。</span><span class="sxs-lookup"><span data-stu-id="16981-104">The built-in logging in Kubernetes is primitive.</span></span> <span data-ttu-id="16981-105">但是，有一些极佳的选项可让你从 Kubernetes 中取出日志，并将其放在正确分析的位置。</span><span class="sxs-lookup"><span data-stu-id="16981-105">However, there are some great options for getting the logs out of Kubernetes and into a place where they can be properly analyzed.</span></span> <span data-ttu-id="16981-106">如果需要监视 AKS 群集，为 Kubernetes 配置弹性堆栈是一种很好的解决方案。</span><span class="sxs-lookup"><span data-stu-id="16981-106">If you need to monitor your AKS clusters, configuring Elastic Stack for Kubernetes is a great solution.</span></span>

## <a name="elastic-stack"></a><span data-ttu-id="16981-107">弹性堆栈</span><span class="sxs-lookup"><span data-stu-id="16981-107">Elastic Stack</span></span>

<span data-ttu-id="16981-108">弹性堆栈是一个功能强大的选项，可用于从 Kubernetes 群集中收集信息。</span><span class="sxs-lookup"><span data-stu-id="16981-108">The Elastic Stack is a powerful option for gathering information from a Kubernetes cluster.</span></span> <span data-ttu-id="16981-109">Kubernetes 支持将日志发送到 Elasticsearch 终结点，而在[大多数情况](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/)下，你只需设置环境变量，如图7-5 所示：</span><span class="sxs-lookup"><span data-stu-id="16981-109">Kubernetes supports sending logs to an Elasticsearch endpoint, and for the [most part](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), all you need to get started is to set the environment variables as shown in Figure 7-5:</span></span>

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

<span data-ttu-id="16981-110">**图 7-5** -Kubernetes 的配置变量</span><span class="sxs-lookup"><span data-stu-id="16981-110">**Figure 7-5** - Configuration variables for Kubernetes</span></span>

<span data-ttu-id="16981-111">这会在群集上安装 Elasticsearch，并将所有群集日志发送到该群集。</span><span class="sxs-lookup"><span data-stu-id="16981-111">This will install Elasticsearch on the cluster and target sending all the cluster logs to it.</span></span>

<span data-ttu-id="16981-112">![一个 Kibana 仪表板示例，其中显示了引入 from Kubernetes **7-6**](./media/kibana-dashboard.png)
的针对日志的查询结果。</span><span class="sxs-lookup"><span data-stu-id="16981-112">![An example of a Kibana dashboard showing the results of a query against logs ingested from Kubernetes](./media/kibana-dashboard.png)
**Figure 7-6**.</span></span> <span data-ttu-id="16981-113">Kibana 仪表板的一个示例，显示针对引入 from Kubernetes 中的日志查询的结果</span><span class="sxs-lookup"><span data-stu-id="16981-113">An example of a Kibana dashboard showing the results of a query against logs that are ingested from Kubernetes</span></span>

## <a name="azure-container-monitoring"></a><span data-ttu-id="16981-114">Azure 容器监视</span><span class="sxs-lookup"><span data-stu-id="16981-114">Azure Container Monitoring</span></span>

<span data-ttu-id="16981-115">Azure 容器监视不仅支持从 Kubernetes 使用日志，还支持从其他业务流程引擎（例如 DC/OS、Docker Swarm 和 Red Hat OpenShift）使用日志。</span><span class="sxs-lookup"><span data-stu-id="16981-115">Azure Container Monitoring supports consuming logs from not just Kubernetes but also from other orchestration engines such as DC/OS, Docker Swarm, and Red Hat OpenShift.</span></span>

<span data-ttu-id="16981-116">![从不同容器使用日志](./media/containers-diagram.png)
**图 7-7**。</span><span class="sxs-lookup"><span data-stu-id="16981-116">![Consuming logs from various containers](./media/containers-diagram.png)
**Figure 7-7**.</span></span>  <span data-ttu-id="16981-117">使用不同容器中的日志</span><span class="sxs-lookup"><span data-stu-id="16981-117">Consuming logs from various containers</span></span>

<span data-ttu-id="16981-118">日志和指标信息不只是从群集中运行的容器中收集，而是由群集本身进行收集。</span><span class="sxs-lookup"><span data-stu-id="16981-118">Log and metric information is gathered not just from the containers running in the cluster but also from the cluster hosts themselves.</span></span> <span data-ttu-id="16981-119">它允许将日志信息与这两者进行关联，这使得跟踪错误变得更加容易。</span><span class="sxs-lookup"><span data-stu-id="16981-119">It allows correlating log information from the two making it much easier to track down an error.</span></span>

<span data-ttu-id="16981-120">安装日志收集器不同于[Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes)和[Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes)群集。</span><span class="sxs-lookup"><span data-stu-id="16981-120">Installing the log collectors differs on [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) and [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) clusters.</span></span> <span data-ttu-id="16981-121">但在这两种情况下，日志集合都作为 Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)实现，这意味着日志收集器将作为容器在每个节点上运行。</span><span class="sxs-lookup"><span data-stu-id="16981-121">But in both cases the log collection is implemented as a Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), meaning that the log collector is run as a container on each of the nodes.</span></span>

<span data-ttu-id="16981-122">无论哪个协调器或操作系统运行 Azure Monitor 守护程序，日志信息都将转发到与用户熟悉的 Azure Monitor 工具。</span><span class="sxs-lookup"><span data-stu-id="16981-122">No matter which orchestrator or operating system is running the Azure Monitor daemon, the log information is forwarded to the same Azure Monitor tools with which users are familiar.</span></span> <span data-ttu-id="16981-123">这可确保在混合不同的日志源（如混合 Kubernetes/Azure Functions 环境）的环境中获得并行体验。</span><span class="sxs-lookup"><span data-stu-id="16981-123">This ensures a parallel experience in environments that mix different log sources such as a hybrid Kubernetes/Azure Functions environment.</span></span>

<span data-ttu-id="16981-124">![一个示例仪表板，其中显示了多个正在运行的容器中的日志记录和指标信息。](./media/containers-dashboard.png)
**图 7-8**。</span><span class="sxs-lookup"><span data-stu-id="16981-124">![A sample dashboard showing logging and metric information from a number of running containers.](./media/containers-dashboard.png)
**Figure 7-8**.</span></span> <span data-ttu-id="16981-125">显示多个正在运行的容器中的日志记录和指标信息的示例仪表板。</span><span class="sxs-lookup"><span data-stu-id="16981-125">A sample dashboard showing logging and metric information from a number of running containers.</span></span>

## <a name="logfinalize"></a><span data-ttu-id="16981-126">Log Finalize （）</span><span class="sxs-lookup"><span data-stu-id="16981-126">Log.Finalize()</span></span>

<span data-ttu-id="16981-127">日志记录是在大规模部署任何应用程序时最忽略但最重要的部分之一。</span><span class="sxs-lookup"><span data-stu-id="16981-127">Logging is one of the most overlooked and yet most important parts of deploying any application at scale.</span></span> <span data-ttu-id="16981-128">随着应用程序的大小和复杂程度的增加，调试它们的难度也很大。</span><span class="sxs-lookup"><span data-stu-id="16981-128">As the size and complexity of applications increase, then so does the difficulty of debugging them.</span></span> <span data-ttu-id="16981-129">可用的高质量日志使调试变得更加简单，并将其从 "几乎不可能" 领域移到 "令人愉快的体验"。</span><span class="sxs-lookup"><span data-stu-id="16981-129">Having top quality logs available makes debugging much easier and moves it from the realm of "nearly impossible" to "a pleasant experience".</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="16981-130">[上一页](logging-with-elastic-stack.md)
>[下一页](azure-monitor.md)</span><span class="sxs-lookup"><span data-stu-id="16981-130">[Previous](logging-with-elastic-stack.md)
[Next](azure-monitor.md)</span></span>
