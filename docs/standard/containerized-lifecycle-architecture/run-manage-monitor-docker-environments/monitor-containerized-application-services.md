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
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="0b7de-103">监视容器化应用程序服务</span><span class="sxs-lookup"><span data-stu-id="0b7de-103">Monitor containerized application services</span></span>

<span data-ttu-id="0b7de-104">很重要的拆分为多个容器和微服务的应用程序具有一种方法来监视和分析整个应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="0b7de-104">It's critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the whole application.</span></span>

## <a name="azure-monitor"></a><span data-ttu-id="0b7de-105">Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="0b7de-105">Azure Monitor</span></span>

<span data-ttu-id="0b7de-106">[Azure 监视器](https://azure.microsoft.com/services/monitor/)是一项可扩展分析服务，用于监视实时应用程序。</span><span class="sxs-lookup"><span data-stu-id="0b7de-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="0b7de-107">它可帮助你检测和诊断性能问题以及了解用户实际使用你的应用。</span><span class="sxs-lookup"><span data-stu-id="0b7de-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="0b7de-108">它专为开发人员的意图是为了帮助您不断提高的性能和可用性的服务或应用程序。</span><span class="sxs-lookup"><span data-stu-id="0b7de-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="0b7de-109">Azure 监视器适用于 web/服务和独立上各种不同的平台，如.NET、 Java、 Node.js 和许多其他平台，托管在本地或云中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0b7de-109">Azure Monitor works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0b7de-110">其他资源</span><span class="sxs-lookup"><span data-stu-id="0b7de-110">Additional resources</span></span>

- <span data-ttu-id="0b7de-111">**Azure Monitor 概述** \\</span><span class="sxs-lookup"><span data-stu-id="0b7de-111">**Overview of Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="0b7de-112">**什么是 Application Insights？**</span><span class="sxs-lookup"><span data-stu-id="0b7de-112">**What is Application Insights?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="0b7de-113">**什么是 Azure Monitor 指标？**</span><span class="sxs-lookup"><span data-stu-id="0b7de-113">**What is Azure Monitor Metrics?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- <span data-ttu-id="0b7de-114">**Azure Monitor 中的容器监视解决方案** \\</span><span class="sxs-lookup"><span data-stu-id="0b7de-114">**Container Monitoring solution in Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a><span data-ttu-id="0b7de-115">安全和备份服务</span><span class="sxs-lookup"><span data-stu-id="0b7de-115">Security and backup services</span></span>

<span data-ttu-id="0b7de-116">有许多支持零碎工作具有大量你需要处理以确保你的应用程序和基础结构中前陷波条件，以支持业务需求的详细信息，这种情况变得更加复杂的微服务领域，因此您需要一种方法当您需要采取措施时具有高级别和详细视图。</span><span class="sxs-lookup"><span data-stu-id="0b7de-116">There are many support chores with lots of details that you have to handle to ensure your applications and infrastructure are in top notch condition to support business needs, and the situation becomes more complicated in the microservices realm, so you need a way to have both high-level and detailed views when you need to take action.</span></span>

<span data-ttu-id="0b7de-117">Azure 提供的工具来管理并提供在云中和本地资源的四个关键方面的统一的视图：</span><span class="sxs-lookup"><span data-stu-id="0b7de-117">Azure has the tools to manage and provide a unified view of four critical aspects of both your cloud and on-premises resources:</span></span>

- <span data-ttu-id="0b7de-118">**安全**。</span><span class="sxs-lookup"><span data-stu-id="0b7de-118">**Security**.</span></span> <span data-ttu-id="0b7de-119">与[Azure 安全中心](https://azure.microsoft.com/services/security-center/)。</span><span class="sxs-lookup"><span data-stu-id="0b7de-119">With [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span></span>
  - <span data-ttu-id="0b7de-120">获取完整的可见性和控制虚拟机、 应用和工作负荷的安全性。</span><span class="sxs-lookup"><span data-stu-id="0b7de-120">Get full visibility and control over the security of your virtual machines, apps, and workloads.</span></span>
  - <span data-ttu-id="0b7de-121">集中你的安全策略的管理，并集成现有流程和工具。</span><span class="sxs-lookup"><span data-stu-id="0b7de-121">Centralize the management of your security policies and integrate existing processes and tools.</span></span>
  - <span data-ttu-id="0b7de-122">检测到使用高级分析真正的威胁。</span><span class="sxs-lookup"><span data-stu-id="0b7de-122">Detect real threats with advanced analytics.</span></span>

- <span data-ttu-id="0b7de-123">**备份**。</span><span class="sxs-lookup"><span data-stu-id="0b7de-123">**Backup**.</span></span> <span data-ttu-id="0b7de-124">与[Azure 备份](https://azure.microsoft.com/services/backup/)。</span><span class="sxs-lookup"><span data-stu-id="0b7de-124">With [Azure Backup](https://azure.microsoft.com/services/backup/).</span></span>
  - <span data-ttu-id="0b7de-125">避免成本高昂的业务中断，满足符合性目标，并保护数据免受勒索软件和人为错误。</span><span class="sxs-lookup"><span data-stu-id="0b7de-125">Avoid costly business disruptions, meet compliance goals, and protect your data against ransomware and human errors.</span></span>
  - <span data-ttu-id="0b7de-126">保留备份数据在传输过程中和静止加密。</span><span class="sxs-lookup"><span data-stu-id="0b7de-126">Keep your backup data encrypted in transit and at rest.</span></span>
  - <span data-ttu-id="0b7de-127">请确保访问基于多重身份验证，以防止未经授权的使用。</span><span class="sxs-lookup"><span data-stu-id="0b7de-127">Ensure access based on multifactor authentication to prevent unauthorized use.</span></span>

- <span data-ttu-id="0b7de-128">**本地资源**。</span><span class="sxs-lookup"><span data-stu-id="0b7de-128">**On-premises resources**.</span></span> <span data-ttu-id="0b7de-129">与[真正一致的混合云](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/)。</span><span class="sxs-lookup"><span data-stu-id="0b7de-129">With [a truly consistent hybrid cloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0b7de-130">[上一页](manage-production-docker-environments.md)
>[下一页](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="0b7de-130">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>
