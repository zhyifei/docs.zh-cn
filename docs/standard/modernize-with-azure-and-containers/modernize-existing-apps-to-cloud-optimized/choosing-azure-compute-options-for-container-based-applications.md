---
title: 为基于容器的应用程序选择 Azure 计算平台
description: 更新现有.NET 应用程序与 Azure 云和 Windows 容器 |选择基于容器的应用程序的 Azure 计算平台
ms.date: 05/04/2018
ms.openlocfilehash: d91cd279402dc24beb5f766c06cb85ac8d74f482
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758831"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>为基于容器的应用程序选择 Azure 计算平台

阅读前面的部分后，您已经注意到，Azure 是开放的云，提供多个选项。 可以根据需要使用最合适，但是，它还会呈现为容器化应用程序应使用何种产品/技术有关的问题。

作为*默认情况下*建议，下面是本指南中建议主要的准则：

- **单个整体式应用程序：** 选择 Azure 应用服务
- **N 层应用程序：** 如果你有一个或几个后端服务，请选择业务流程协调程序，如 Azure Kubernetes 服务 (AKS) 或应用服务
- **Linux 微服务：** 选择 AKS/Kubernetes
- **Windows 微服务：** 为容器选择 Azure Web 应用
- **无服务器函数 （&) 事件处理程序：** 选择 Azure 函数
- **大规模批处理：** 选择 Azure Batch

但是，此建议应使用盐，片段执行如产品的选择将取决于特定应用程序的需求和特征。 即使最初它们可能看起来类似的类型，并非所有应用程序都是相同的。

在应用程序的需求的更深入地分析之后, 选择产品可能会有所不同。 但是，作为起点，最好能够从您可以开始评估的初步指导和测试基于针对特定的优先级。

在下图中，可以看到不同类型的应用程序和托管方案，其非常适合 Azure 的细分。

![](./media/image8.5.png)

> [!div class="step-by-step"]
> [上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [下一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
