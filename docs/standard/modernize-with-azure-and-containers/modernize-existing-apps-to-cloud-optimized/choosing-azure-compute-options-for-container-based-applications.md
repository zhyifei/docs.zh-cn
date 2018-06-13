---
title: 选择容器基于应用程序的 Azure 计算平台
description: 更新现有的.NET 应用程序与 Azure 云和 Windows 容器 |选择容器基于应用程序的 Azure 计算平台
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: ebf022a52aaaf95ae335976f5e097921b0ac8006
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958007"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>选择容器基于应用程序的 Azure 计算平台

在阅读了前面的部分后，您已经注意到，Azure 将是提供多项选择打开云。 您可以使用最适合你的需求，但是，它还显示有关你容器化应用程序应使用何种产品/技术问题。

作为 *： 默认情况下*建议，以下是本指南中建议的主要条件：

  - **单个整体应用：** 选择 Azure App Service
  - **N 层应用程序：** 选择 orchestrators 如 Azure Kubernetes 服务 (AKS)、 Service Fabric (SF) 或应用程序服务，如果你有一个或几个后端服务
  - **Linux 微服务：** 选择 AKS/Kubernetes
  - **Windows 微服务：** 选择 Service Fabric
  - **无服务器函数和事件处理程序：** 选择 Azure 函数
  - **大规模批处理：** 选择 Azure 批处理

但是，此建议应采取的 salt，捏合与该产品的选择将依赖于特定应用程序的需求和特征。 即使最初它们可能看起来类似的类型，并非所有应用程序都是相同的。

在应用程序的需求的更深入地分析之后, 选择产品可能不同。 但是，作为起点，最好能够从你可以评估的初步指导，而且测试根据某些优先级。

在下一步的图中，你可以分析更具有全局性时详细的决策表。

![](./media/image8.5.png)

请注意如何基础操作系统 (Windows vs。Linux) 以及某些 orchestrators 更加成熟上 Linux 容器和其他 Windows 容器，也可以是决定因素。 例如，Linux 容器是在 Kubernetes (在 Azure 中的 AKS) 但不太成熟于 Service Fabric 非常成熟的。 另一方面，Windows 容器是在 Service Fabric 中 （在 2017 年 5 月发布） 更加成熟完善一些和较低成熟 AKS 中。

但是，在 OS 成熟度这些差异将淡入淡出将来和多个平台将具有可比较 OS 成熟度和决策的布局有关基于你的应用程序可能需要或基于每个平台的生态系统的特定功能的首选项的详细信息原因。


>[!div class="step-by-step"]
[上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[下一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
