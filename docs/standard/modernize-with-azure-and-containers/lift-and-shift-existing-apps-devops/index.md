---
title: 直接迁移现有应用 DevOps
description: 使用 Azure 云和 Windows 容器更新现有 .NET 应用程序。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5229e6c9a63e5adf76c7a893a49a8a55633fa621
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="lift-and-shift-existing-apps-devops"></a><span data-ttu-id="40ab3-103">直接迁移现有应用 DevOps</span><span class="sxs-lookup"><span data-stu-id="40ab3-103">Lift and shift existing apps DevOps</span></span>

> <span data-ttu-id="40ab3-104">愿景：将现有 .NET Framework 应用程序直接迁移到云 DevOps 就绪应用程序以显著提高部署敏捷性，以加快交付速度，降低应用交付成本。</span><span class="sxs-lookup"><span data-stu-id="40ab3-104">Vision: Lift and shift your existing .NET Framework applications to Cloud DevOps-Ready applications to drastically improve your deployment agility, so you can ship faster and lower app delivery costs.</span></span>

<span data-ttu-id="40ab3-105">若要利用云和新技术（如容器）的优势，至少应部分更新现有 .NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="40ab3-105">To take advantage of the benefits of the cloud and new technologies like containers, you should at least partially modernize your existing .NET applications.</span></span> <span data-ttu-id="40ab3-106">最终，更新企业应用程序将降低总拥有成本。</span><span class="sxs-lookup"><span data-stu-id="40ab3-106">Ultimately, modernizing your enterprise applications will lower your total cost of ownership.</span></span>

<span data-ttu-id="40ab3-107">部分更新应用不需要完全迁移和重新构建。</span><span class="sxs-lookup"><span data-stu-id="40ab3-107">Partially modernizing an app doesn't necessarily mean a full migration and re-architecture.</span></span> <span data-ttu-id="40ab3-108">首先可以通过简单快速的直接迁移进程来更新现有应用程序。</span><span class="sxs-lookup"><span data-stu-id="40ab3-108">You can initially modernize your existing applications by using a lift and shift process that's easy and fast.</span></span> <span data-ttu-id="40ab3-109">可以维护当前基本代码，这些代码使用现有.NET Framework 版本编写并具有任意 Windows 和 IIS 依赖项。</span><span class="sxs-lookup"><span data-stu-id="40ab3-109">You can maintain your current code base, written in existing .NET Framework versions, with any Windows and IIS dependencies.</span></span> <span data-ttu-id="40ab3-110">图 4-1 突出显示了如何在 Azure 应用程序更新成熟度模型中定位云 DevOps 就绪应用。</span><span class="sxs-lookup"><span data-stu-id="40ab3-110">Figure 4-1 highlights how Cloud DevOps-Ready apps are positioned in Azure application modernization maturity models.</span></span>

![定位 DevOps 就绪应用程序](./media/image1.png)

> <span data-ttu-id="40ab3-112">**图 4-1**。</span><span class="sxs-lookup"><span data-stu-id="40ab3-112">**Figure 4-1.**</span></span> <span data-ttu-id="40ab3-113">定位 DevOps 就绪应用程序</span><span class="sxs-lookup"><span data-stu-id="40ab3-113">Positioning Cloud DevOps-Ready applications</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="40ab3-114">[上一页](../migrate-your-relational-databases-to-azure.md)
[下一页](reasons-to-lift-and-shift-existing-net-apps-to-cloud-devops-ready-applications.md)</span><span class="sxs-lookup"><span data-stu-id="40ab3-114">[Previous](../migrate-your-relational-databases-to-azure.md)
[Next](reasons-to-lift-and-shift-existing-net-apps-to-cloud-devops-ready-applications.md)</span></span>
