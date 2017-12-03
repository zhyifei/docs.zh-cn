---
title: 3503 - DuplicateCorrelationQuery
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b86289340c35d24552b1d524a3cceaacb2f0420
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="4adbe-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="4adbe-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="4adbe-103">属性</span><span class="sxs-lookup"><span data-stu-id="4adbe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4adbe-104">ID</span><span class="sxs-lookup"><span data-stu-id="4adbe-104">ID</span></span>|<span data-ttu-id="4adbe-105">3503</span><span class="sxs-lookup"><span data-stu-id="4adbe-105">3503</span></span>|  
|<span data-ttu-id="4adbe-106">关键字</span><span class="sxs-lookup"><span data-stu-id="4adbe-106">Keywords</span></span>|<span data-ttu-id="4adbe-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="4adbe-107">WFServices</span></span>|  
|<span data-ttu-id="4adbe-108">级别</span><span class="sxs-lookup"><span data-stu-id="4adbe-108">Level</span></span>|<span data-ttu-id="4adbe-109">警告</span><span class="sxs-lookup"><span data-stu-id="4adbe-109">Warning</span></span>|  
|<span data-ttu-id="4adbe-110">通道</span><span class="sxs-lookup"><span data-stu-id="4adbe-110">Channel</span></span>|<span data-ttu-id="4adbe-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="4adbe-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4adbe-112">描述</span><span class="sxs-lookup"><span data-stu-id="4adbe-112">Description</span></span>  
 <span data-ttu-id="4adbe-113">指示找到了重复 CorrelationQuery。</span><span class="sxs-lookup"><span data-stu-id="4adbe-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="4adbe-114">计算相关性时将不使用重复查询。</span><span class="sxs-lookup"><span data-stu-id="4adbe-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4adbe-115">消息</span><span class="sxs-lookup"><span data-stu-id="4adbe-115">Message</span></span>  
 <span data-ttu-id="4adbe-116">找到了含有 Where='%1' 的重复 CorrelationQuery。</span><span class="sxs-lookup"><span data-stu-id="4adbe-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="4adbe-117">计算相关性时将不使用此重复查询。</span><span class="sxs-lookup"><span data-stu-id="4adbe-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4adbe-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="4adbe-118">Details</span></span>  
  
|<span data-ttu-id="4adbe-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="4adbe-119">Data Item Name</span></span>|<span data-ttu-id="4adbe-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="4adbe-120">Data Item Type</span></span>|<span data-ttu-id="4adbe-121">描述</span><span class="sxs-lookup"><span data-stu-id="4adbe-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4adbe-122">Where</span><span class="sxs-lookup"><span data-stu-id="4adbe-122">Where</span></span>|<span data-ttu-id="4adbe-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="4adbe-123">xs:string</span></span>|<span data-ttu-id="4adbe-124">相关查询的 Where 部分。</span><span class="sxs-lookup"><span data-stu-id="4adbe-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="4adbe-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4adbe-125">AppDomain</span></span>|<span data-ttu-id="4adbe-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="4adbe-126">xs:string</span></span>|<span data-ttu-id="4adbe-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="4adbe-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
