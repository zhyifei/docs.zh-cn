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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3dc30100cb134740f51e6b2b38c00b2054d2ab0a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="64069-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="64069-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="64069-103">属性</span><span class="sxs-lookup"><span data-stu-id="64069-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64069-104">ID</span><span class="sxs-lookup"><span data-stu-id="64069-104">ID</span></span>|<span data-ttu-id="64069-105">1021</span><span class="sxs-lookup"><span data-stu-id="64069-105">1021</span></span>|  
|<span data-ttu-id="64069-106">关键字</span><span class="sxs-lookup"><span data-stu-id="64069-106">Keywords</span></span>|<span data-ttu-id="64069-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="64069-107">WFRuntime</span></span>|  
|<span data-ttu-id="64069-108">级别</span><span class="sxs-lookup"><span data-stu-id="64069-108">Level</span></span>|<span data-ttu-id="64069-109">详细</span><span class="sxs-lookup"><span data-stu-id="64069-109">Verbose</span></span>|  
|<span data-ttu-id="64069-110">通道</span><span class="sxs-lookup"><span data-stu-id="64069-110">Channel</span></span>|<span data-ttu-id="64069-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="64069-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="64069-112">描述</span><span class="sxs-lookup"><span data-stu-id="64069-112">Description</span></span>  
 <span data-ttu-id="64069-113">指示已安排 BookmarkWorkItem。</span><span class="sxs-lookup"><span data-stu-id="64069-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="64069-114">消息</span><span class="sxs-lookup"><span data-stu-id="64069-114">Message</span></span>  
 <span data-ttu-id="64069-115">已为 Activity"%1"、 DisplayName 安排 BookmarkWorkItem:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="64069-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="64069-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="64069-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="64069-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="64069-117">Details</span></span>  
  
|<span data-ttu-id="64069-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="64069-118">Data Item Name</span></span>|<span data-ttu-id="64069-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="64069-119">Data Item Type</span></span>|<span data-ttu-id="64069-120">描述</span><span class="sxs-lookup"><span data-stu-id="64069-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="64069-121">Activity</span><span class="sxs-lookup"><span data-stu-id="64069-121">Activity</span></span>|<span data-ttu-id="64069-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="64069-122">xs:string</span></span>|<span data-ttu-id="64069-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="64069-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="64069-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="64069-124">DisplayName</span></span>|<span data-ttu-id="64069-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="64069-125">xs:string</span></span>|<span data-ttu-id="64069-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="64069-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="64069-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="64069-127">InstanceId</span></span>|<span data-ttu-id="64069-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="64069-128">xs:string</span></span>|<span data-ttu-id="64069-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="64069-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="64069-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="64069-130">BookmarkName</span></span>|<span data-ttu-id="64069-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="64069-131">xs:string</span></span>|<span data-ttu-id="64069-132">书签的名称。</span><span class="sxs-lookup"><span data-stu-id="64069-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="64069-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="64069-133">BookmarkScope</span></span>|<span data-ttu-id="64069-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="64069-134">xs:string</span></span>|<span data-ttu-id="64069-135">书签的范围。</span><span class="sxs-lookup"><span data-stu-id="64069-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="64069-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="64069-136">AppDomain</span></span>|<span data-ttu-id="64069-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="64069-137">xs:string</span></span>|<span data-ttu-id="64069-138">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="64069-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
