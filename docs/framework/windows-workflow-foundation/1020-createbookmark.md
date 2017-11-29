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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d0584c6eeaf0e08e92ad94e01e1fca765616440f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1020---createbookmark"></a><span data-ttu-id="2d138-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="2d138-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="2d138-103">属性</span><span class="sxs-lookup"><span data-stu-id="2d138-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2d138-104">ID</span><span class="sxs-lookup"><span data-stu-id="2d138-104">ID</span></span>|<span data-ttu-id="2d138-105">1020</span><span class="sxs-lookup"><span data-stu-id="2d138-105">1020</span></span>|  
|<span data-ttu-id="2d138-106">关键字</span><span class="sxs-lookup"><span data-stu-id="2d138-106">Keywords</span></span>|<span data-ttu-id="2d138-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2d138-107">WFRuntime</span></span>|  
|<span data-ttu-id="2d138-108">级别</span><span class="sxs-lookup"><span data-stu-id="2d138-108">Level</span></span>|<span data-ttu-id="2d138-109">详细</span><span class="sxs-lookup"><span data-stu-id="2d138-109">Verbose</span></span>|  
|<span data-ttu-id="2d138-110">通道</span><span class="sxs-lookup"><span data-stu-id="2d138-110">Channel</span></span>|<span data-ttu-id="2d138-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="2d138-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2d138-112">描述</span><span class="sxs-lookup"><span data-stu-id="2d138-112">Description</span></span>  
 <span data-ttu-id="2d138-113">指示已为活动创建了书签。</span><span class="sxs-lookup"><span data-stu-id="2d138-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2d138-114">消息</span><span class="sxs-lookup"><span data-stu-id="2d138-114">Message</span></span>  
 <span data-ttu-id="2d138-115">已为 Activity"%1"、 DisplayName 创建书签:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="2d138-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="2d138-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="2d138-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2d138-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="2d138-117">Details</span></span>  
  
|<span data-ttu-id="2d138-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="2d138-118">Data Item Name</span></span>|<span data-ttu-id="2d138-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="2d138-119">Data Item Type</span></span>|<span data-ttu-id="2d138-120">描述</span><span class="sxs-lookup"><span data-stu-id="2d138-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2d138-121">Activity</span><span class="sxs-lookup"><span data-stu-id="2d138-121">Activity</span></span>|<span data-ttu-id="2d138-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d138-122">xs:string</span></span>|<span data-ttu-id="2d138-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="2d138-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="2d138-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2d138-124">DisplayName</span></span>|<span data-ttu-id="2d138-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d138-125">xs:string</span></span>|<span data-ttu-id="2d138-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="2d138-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="2d138-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2d138-127">InstanceId</span></span>|<span data-ttu-id="2d138-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d138-128">xs:string</span></span>|<span data-ttu-id="2d138-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="2d138-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2d138-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="2d138-130">BookmarkName</span></span>|<span data-ttu-id="2d138-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d138-131">xs:string</span></span>|<span data-ttu-id="2d138-132">书签的名称。</span><span class="sxs-lookup"><span data-stu-id="2d138-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="2d138-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="2d138-133">BookmarkScope</span></span>|<span data-ttu-id="2d138-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d138-134">xs:string</span></span>|<span data-ttu-id="2d138-135">书签的范围。</span><span class="sxs-lookup"><span data-stu-id="2d138-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="2d138-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2d138-136">AppDomain</span></span>|<span data-ttu-id="2d138-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2d138-137">xs:string</span></span>|<span data-ttu-id="2d138-138">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="2d138-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
