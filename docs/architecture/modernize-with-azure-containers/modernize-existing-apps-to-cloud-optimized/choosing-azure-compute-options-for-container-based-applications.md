---
title: 为基于容器的应用程序选择 Azure 计算平台
description: 通过 Azure 云和 Windows 容器现代化现有 .NET 应用程序 | 为基于容器的应用程序选择 Azure 计算平台
ms.date: 05/04/2018
ms.openlocfilehash: 079c9c5ca02b6dc75214d63cb59afdead03d3190
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2019
ms.locfileid: "73737017"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>为基于容器的应用程序选择 Azure 计算平台

正如你在阅读前面章节时所注意到的，Azure 是一个提供多项选择的开放云。 你可以充分利用它来满足你的需求，但是它也提出了一些关于你应该为容器化应用程序采用哪些产品/技术的问题。

作为“默认”  建议，以下是本指南中建议的主要标准：

- **单一整体式应用：** 选择 Azure 应用服务
- **N 层应用：** 如果拥有单个或几个后端服务，请选择“业务流程协调程序”，如 Azure Kubernetes 服务 (AKS) 或应用服务
- **微服务：** 为容器选择 AKS 或 Azure Web 应用
- **无服务器函数和事件处理程序：** 选择“Azure Functions”
- **大规模 Batch：** 选择“Azure Batch”

但是，这一建议并不完全可信，因为产品的选择取决于具体的应用程序需求和特性。 并非所有的应用程序都是相同的，即使它们最初可能看起来是类似的。

在对应用程序的需求进行更深入的分析之后，所选择的产品可能会有所不同。 但最好一开始就获得初步指导，你可以基于特定的优先级从其中开始评估和测试。

在图 1 中，你可以看到不同种类应用及其理想的 Azure 托管方案的明细。

![哪些 Azure 托管方案最适合不同应用的表。](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> [上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [下一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
