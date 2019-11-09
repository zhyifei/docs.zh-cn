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
# <a name="monitoring-in-azure-kubernetes-services"></a>在 Azure Kubernetes 服务中进行监视

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Kubernetes 中的内置日志记录为基元。 但是，有一些极佳的选项可让你从 Kubernetes 中取出日志，并将其放在正确分析的位置。 如果需要监视 AKS 群集，为 Kubernetes 配置弹性堆栈是一种很好的解决方案。

## <a name="elastic-stack"></a>弹性堆栈

弹性堆栈是一个功能强大的选项，可用于从 Kubernetes 群集中收集信息。 Kubernetes 支持将日志发送到 Elasticsearch 终结点，而在[大多数情况](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/)下，你只需设置环境变量，如图7-5 所示：

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

**图 7-5** -Kubernetes 的配置变量

这会在群集上安装 Elasticsearch，并将所有群集日志发送到该群集。

![一个 Kibana 仪表板示例，其中显示了引入 from Kubernetes **7-6**](./media/kibana-dashboard.png)
的针对日志的查询结果。 Kibana 仪表板的一个示例，显示针对引入 from Kubernetes 中的日志查询的结果

## <a name="azure-container-monitoring"></a>Azure 容器监视

Azure 容器监视不仅支持从 Kubernetes 使用日志，还支持从其他业务流程引擎（例如 DC/OS、Docker Swarm 和 Red Hat OpenShift）使用日志。

![从不同容器使用日志](./media/containers-diagram.png)
**图 7-7**。  使用不同容器中的日志

日志和指标信息不只是从群集中运行的容器中收集，而是由群集本身进行收集。 它允许将日志信息与这两者进行关联，这使得跟踪错误变得更加容易。

安装日志收集器不同于[Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes)和[Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes)群集。 但在这两种情况下，日志集合都作为 Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)实现，这意味着日志收集器将作为容器在每个节点上运行。

无论哪个协调器或操作系统运行 Azure Monitor 守护程序，日志信息都将转发到与用户熟悉的 Azure Monitor 工具。 这可确保在混合不同的日志源（如混合 Kubernetes/Azure Functions 环境）的环境中获得并行体验。

![一个示例仪表板，其中显示了多个正在运行的容器中的日志记录和指标信息。](./media/containers-dashboard.png)
**图 7-8**。 显示多个正在运行的容器中的日志记录和指标信息的示例仪表板。

## <a name="logfinalize"></a>Log Finalize （）

日志记录是在大规模部署任何应用程序时最忽略但最重要的部分之一。 随着应用程序的大小和复杂程度的增加，调试它们的难度也很大。 可用的高质量日志使调试变得更加简单，并将其从 "几乎不可能" 领域移到 "令人愉快的体验"。

>[!div class="step-by-step"]
>[上一页](logging-with-elastic-stack.md)
>[下一页](azure-monitor.md)
