---
title: 监视容器化应用程序服务
description: 了解监视容器体系结构的一些重要层面
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 4553a35c8db6cfc46187525ef2ffc65cb3ba07c9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922741"
---
# <a name="monitor-containerized-application-services"></a>监视容器化应用程序服务

很重要的拆分为多个容器和微服务的应用程序具有一种方法来监视和分析整个应用程序的行为。

## <a name="azure-monitor"></a>Azure Monitor

[Azure 监视器](https://azure.microsoft.com/services/monitor/)是一项可扩展分析服务，用于监视实时应用程序。 它可帮助你检测和诊断性能问题以及了解用户实际使用你的应用。 它专为开发人员的意图是为了帮助您不断提高的性能和可用性的服务或应用程序。 Azure 监视器适用于 web/服务和独立上各种不同的平台，如.NET、 Java、 Node.js 和许多其他平台，托管在本地或云中的应用程序。

### <a name="additional-resources"></a>其他资源

- **Azure Monitor 概述** \
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- **什么是 Application Insights？** \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **什么是 Azure Monitor 指标？** \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- **Azure Monitor 中的容器监视解决方案** \
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a>安全和备份服务

有许多支持零碎工作具有大量你需要处理以确保你的应用程序和基础结构中前陷波条件，以支持业务需求的详细信息，这种情况变得更加复杂的微服务领域，因此您需要一种方法当您需要采取措施时具有高级别和详细视图。

Azure 提供的工具来管理并提供在云中和本地资源的四个关键方面的统一的视图：

- **安全**。 与[Azure 安全中心](https://azure.microsoft.com/services/security-center/)。
  - 获取完整的可见性和控制虚拟机、 应用和工作负荷的安全性。
  - 集中你的安全策略的管理，并集成现有流程和工具。
  - 检测到使用高级分析真正的威胁。

- **备份**。 与[Azure 备份](https://azure.microsoft.com/services/backup/)。
  - 避免成本高昂的业务中断，满足符合性目标，并保护数据免受勒索软件和人为错误。
  - 保留备份数据在传输过程中和静止加密。
  - 请确保访问基于多重身份验证，以防止未经授权的使用。

- **本地资源**。 与[真正一致的混合云](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/)。

>[!div class="step-by-step"]
>[上一页](manage-production-docker-environments.md)
>[下一页](../key-takeaways/index.md)
