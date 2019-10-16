---
title: 为基于容器的应用程序选择 Azure 计算平台
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |为基于容器的应用程序选择 Azure 计算平台
ms.date: 05/04/2018
ms.openlocfilehash: 2262d2cf4e69e19e8b78c07c239602dd5dccc3cd
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318664"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>为基于容器的应用程序选择 Azure 计算平台

正如你在阅读前面几节中所注意到的，Azure 是一个开放的云，它提供多个选择。 您可以最大程度地满足您的需求，但它还会对您应该为容器化应用程序使用的产品/技术提出问题。

作为*默认*建议，以下是本指南中建议的主要标准：

- **单一单一应用程序：** 选择 Azure App Service
- **N 层应用程序：** 如果你有单个或几个后端服务，请选择 "协调器" （如 Azure Kubernetes Service （AKS）或 "应用服务"）
- **微服务**选择 AKS 或适用于容器的 Azure Web 应用
- **& 事件处理程序的无服务器函数：** 选择 Azure Functions
- **大规模批：** 选择 Azure Batch

但是，这一建议应该用到了一把盐，因为产品的选择取决于具体的应用程序的需求和特性。 并非所有应用程序都是相同的，即使最初它们可能看起来类似。

在对应用程序的需求进行更深入的分析之后，所选产品可能会有所不同。 但作为起点，最好具有初始指导，可以根据特定优先级开始评估和测试。

在图1中，你可以看到不同种类的应用程序及其理想的 Azure 托管方案的细分。

![图 1](./media/image8.5.png)

> [!div class="step-by-step"]
> [上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [下一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
