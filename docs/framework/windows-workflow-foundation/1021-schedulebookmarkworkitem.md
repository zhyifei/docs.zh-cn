---
title: 1021 - ScheduleBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61c67792f807907f58480f3bfa3d192b811766b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="c5ac8-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="c5ac8-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="c5ac8-103">属性</span><span class="sxs-lookup"><span data-stu-id="c5ac8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c5ac8-104">ID</span><span class="sxs-lookup"><span data-stu-id="c5ac8-104">ID</span></span>|<span data-ttu-id="c5ac8-105">1021</span><span class="sxs-lookup"><span data-stu-id="c5ac8-105">1021</span></span>|  
|<span data-ttu-id="c5ac8-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c5ac8-106">Keywords</span></span>|<span data-ttu-id="c5ac8-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c5ac8-107">WFRuntime</span></span>|  
|<span data-ttu-id="c5ac8-108">级别</span><span class="sxs-lookup"><span data-stu-id="c5ac8-108">Level</span></span>|<span data-ttu-id="c5ac8-109">详细</span><span class="sxs-lookup"><span data-stu-id="c5ac8-109">Verbose</span></span>|  
|<span data-ttu-id="c5ac8-110">通道</span><span class="sxs-lookup"><span data-stu-id="c5ac8-110">Channel</span></span>|<span data-ttu-id="c5ac8-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c5ac8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c5ac8-112">描述</span><span class="sxs-lookup"><span data-stu-id="c5ac8-112">Description</span></span>  
 <span data-ttu-id="c5ac8-113">指示已安排 BookmarkWorkItem。</span><span class="sxs-lookup"><span data-stu-id="c5ac8-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c5ac8-114">消息</span><span class="sxs-lookup"><span data-stu-id="c5ac8-114">Message</span></span>  
 <span data-ttu-id="c5ac8-115">已为 Activity"%1"、 DisplayName 安排 BookmarkWorkItem:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="c5ac8-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="c5ac8-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="c5ac8-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c5ac8-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="c5ac8-117">Details</span></span>  
  
|<span data-ttu-id="c5ac8-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c5ac8-118">Data Item Name</span></span>|<span data-ttu-id="c5ac8-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c5ac8-119">Data Item Type</span></span>|<span data-ttu-id="c5ac8-120">描述</span><span class="sxs-lookup"><span data-stu-id="c5ac8-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c5ac8-121">Activity</span><span class="sxs-lookup"><span data-stu-id="c5ac8-121">Activity</span></span>|<span data-ttu-id="c5ac8-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c5ac8-122">xs:string</span></span>|<span data-ttu-id="c5ac8-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="c5ac8-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="c5ac8-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c5ac8-124">DisplayName</span></span>|<span data-ttu-id="c5ac8-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c5ac8-125">xs:string</span></span>|<span data-ttu-id="c5ac8-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c5ac8-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="c5ac8-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c5ac8-127">InstanceId</span></span>|<span data-ttu-id="c5ac8-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c5ac8-128">xs:string</span></span>|<span data-ttu-id="c5ac8-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="c5ac8-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c5ac8-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="c5ac8-130">BookmarkName</span></span>|<span data-ttu-id="c5ac8-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c5ac8-131">xs:string</span></span>|<span data-ttu-id="c5ac8-132">书签的名称。</span><span class="sxs-lookup"><span data-stu-id="c5ac8-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="c5ac8-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="c5ac8-133">BookmarkScope</span></span>|<span data-ttu-id="c5ac8-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="c5ac8-134">xs:string</span></span>|<span data-ttu-id="c5ac8-135">书签的范围。</span><span class="sxs-lookup"><span data-stu-id="c5ac8-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="c5ac8-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c5ac8-136">AppDomain</span></span>|<span data-ttu-id="c5ac8-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="c5ac8-137">xs:string</span></span>|<span data-ttu-id="c5ac8-138">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c5ac8-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
