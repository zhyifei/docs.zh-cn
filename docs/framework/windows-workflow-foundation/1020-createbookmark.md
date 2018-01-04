---
title: 1020 - CreateBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c47a5464222d12c1dba717e24606e5614e392f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1020---createbookmark"></a><span data-ttu-id="c36ad-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="c36ad-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="c36ad-103">属性</span><span class="sxs-lookup"><span data-stu-id="c36ad-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c36ad-104">ID</span><span class="sxs-lookup"><span data-stu-id="c36ad-104">ID</span></span>|<span data-ttu-id="c36ad-105">1020</span><span class="sxs-lookup"><span data-stu-id="c36ad-105">1020</span></span>|  
|<span data-ttu-id="c36ad-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c36ad-106">Keywords</span></span>|<span data-ttu-id="c36ad-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c36ad-107">WFRuntime</span></span>|  
|<span data-ttu-id="c36ad-108">级别</span><span class="sxs-lookup"><span data-stu-id="c36ad-108">Level</span></span>|<span data-ttu-id="c36ad-109">详细</span><span class="sxs-lookup"><span data-stu-id="c36ad-109">Verbose</span></span>|  
|<span data-ttu-id="c36ad-110">通道</span><span class="sxs-lookup"><span data-stu-id="c36ad-110">Channel</span></span>|<span data-ttu-id="c36ad-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c36ad-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c36ad-112">描述</span><span class="sxs-lookup"><span data-stu-id="c36ad-112">Description</span></span>  
 <span data-ttu-id="c36ad-113">指示已为活动创建了书签。</span><span class="sxs-lookup"><span data-stu-id="c36ad-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c36ad-114">消息</span><span class="sxs-lookup"><span data-stu-id="c36ad-114">Message</span></span>  
 <span data-ttu-id="c36ad-115">已为 Activity"%1"、 DisplayName 创建书签:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="c36ad-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="c36ad-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="c36ad-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c36ad-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="c36ad-117">Details</span></span>  
  
|<span data-ttu-id="c36ad-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c36ad-118">Data Item Name</span></span>|<span data-ttu-id="c36ad-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c36ad-119">Data Item Type</span></span>|<span data-ttu-id="c36ad-120">描述</span><span class="sxs-lookup"><span data-stu-id="c36ad-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c36ad-121">Activity</span><span class="sxs-lookup"><span data-stu-id="c36ad-121">Activity</span></span>|<span data-ttu-id="c36ad-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c36ad-122">xs:string</span></span>|<span data-ttu-id="c36ad-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="c36ad-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="c36ad-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c36ad-124">DisplayName</span></span>|<span data-ttu-id="c36ad-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c36ad-125">xs:string</span></span>|<span data-ttu-id="c36ad-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c36ad-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="c36ad-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c36ad-127">InstanceId</span></span>|<span data-ttu-id="c36ad-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c36ad-128">xs:string</span></span>|<span data-ttu-id="c36ad-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="c36ad-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c36ad-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="c36ad-130">BookmarkName</span></span>|<span data-ttu-id="c36ad-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c36ad-131">xs:string</span></span>|<span data-ttu-id="c36ad-132">书签的名称。</span><span class="sxs-lookup"><span data-stu-id="c36ad-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="c36ad-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="c36ad-133">BookmarkScope</span></span>|<span data-ttu-id="c36ad-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="c36ad-134">xs:string</span></span>|<span data-ttu-id="c36ad-135">书签的范围。</span><span class="sxs-lookup"><span data-stu-id="c36ad-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="c36ad-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c36ad-136">AppDomain</span></span>|<span data-ttu-id="c36ad-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="c36ad-137">xs:string</span></span>|<span data-ttu-id="c36ad-138">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c36ad-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
