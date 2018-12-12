---
title: 更新运行的.NET 应用到云优化的应用程序
description: 使用 Azure 云和 Windows 容器更新现有 .NET 应用程序。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: edbffe45a2a1652ff477f9785b3afb5b0e493bc3
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151494"
---
# <a name="modernize-existing-net-apps-to-cloud-optimized-applications"></a><span data-ttu-id="6c9b0-103">更新运行的.NET 应用到云优化的应用程序</span><span class="sxs-lookup"><span data-stu-id="6c9b0-103">Modernize existing .NET apps to Cloud-Optimized applications</span></span>

> <span data-ttu-id="6c9b0-104">设想：更新现有.NET Framework 应用程序到云优化的应用程序以显著提高您的部署灵活性，从而可以更快地交付，降低应用程序的交付成本。</span><span class="sxs-lookup"><span data-stu-id="6c9b0-104">Vision: Modernize your existing .NET Framework applications to Cloud-Optimized applications to drastically improve your deployment agility, so you can ship faster and lower application’s delivery costs.</span></span>

<span data-ttu-id="6c9b0-105">若要利用云和新技术（如容器）的优势，至少应部分更新现有 .NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6c9b0-105">To take advantage of the benefits of the cloud and new technologies like containers, you should at least partially modernize your existing .NET applications.</span></span> <span data-ttu-id="6c9b0-106">最终，更新企业应用程序将降低总拥有成本。</span><span class="sxs-lookup"><span data-stu-id="6c9b0-106">Ultimately, modernizing your enterprise applications will lower your total cost of ownership.</span></span>

<span data-ttu-id="6c9b0-107">部分更新应用并不一定意味着完全迁移和体系结构重建。</span><span class="sxs-lookup"><span data-stu-id="6c9b0-107">Partially modernizing an app doesn’t necessarily mean a full migration and rearchitecture.</span></span> <span data-ttu-id="6c9b0-108">最初，你可以完成现代化重要但容易实现现代化你现有的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6c9b0-108">You can initially modernize your existing applications with important but easy to do modernization.</span></span> <span data-ttu-id="6c9b0-109">可以维护当前基本代码，这些代码使用现有.NET Framework 版本编写并具有任意 Windows 和 IIS 依赖项。</span><span class="sxs-lookup"><span data-stu-id="6c9b0-109">You can maintain your current code base, written in existing .NET Framework versions, with any Windows and IIS dependencies.</span></span> <span data-ttu-id="6c9b0-110">图 4-1 突出显示了如何云优化的应用程序在 Azure 应用程序更新成熟度模型中的位置。</span><span class="sxs-lookup"><span data-stu-id="6c9b0-110">Figure 4-1 highlights how Cloud-Optimized apps are positioned in Azure application modernization maturity models.</span></span>

![定位云优化的应用程序](./media/image1.png)

> <span data-ttu-id="6c9b0-112">**图 4-1**。</span><span class="sxs-lookup"><span data-stu-id="6c9b0-112">**Figure 4-1.**</span></span> <span data-ttu-id="6c9b0-113">定位云优化的应用程序</span><span class="sxs-lookup"><span data-stu-id="6c9b0-113">Positioning Cloud-Optimized applications</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6c9b0-114">[上一页](../migrate-your-relational-databases-to-azure.md)
>[下一页](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)</span><span class="sxs-lookup"><span data-stu-id="6c9b0-114">[Previous](../migrate-your-relational-databases-to-azure.md)
[Next](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)</span></span>