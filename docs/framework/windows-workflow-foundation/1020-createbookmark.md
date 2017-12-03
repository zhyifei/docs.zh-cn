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
ms.openlocfilehash: 1a0837caa668d6395bf1551c319781934bcfecc1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1020---createbookmark"></a><span data-ttu-id="1cd4e-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="1cd4e-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="1cd4e-103">属性</span><span class="sxs-lookup"><span data-stu-id="1cd4e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1cd4e-104">ID</span><span class="sxs-lookup"><span data-stu-id="1cd4e-104">ID</span></span>|<span data-ttu-id="1cd4e-105">1020</span><span class="sxs-lookup"><span data-stu-id="1cd4e-105">1020</span></span>|  
|<span data-ttu-id="1cd4e-106">关键字</span><span class="sxs-lookup"><span data-stu-id="1cd4e-106">Keywords</span></span>|<span data-ttu-id="1cd4e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1cd4e-107">WFRuntime</span></span>|  
|<span data-ttu-id="1cd4e-108">级别</span><span class="sxs-lookup"><span data-stu-id="1cd4e-108">Level</span></span>|<span data-ttu-id="1cd4e-109">详细</span><span class="sxs-lookup"><span data-stu-id="1cd4e-109">Verbose</span></span>|  
|<span data-ttu-id="1cd4e-110">通道</span><span class="sxs-lookup"><span data-stu-id="1cd4e-110">Channel</span></span>|<span data-ttu-id="1cd4e-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="1cd4e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1cd4e-112">描述</span><span class="sxs-lookup"><span data-stu-id="1cd4e-112">Description</span></span>  
 <span data-ttu-id="1cd4e-113">指示已为活动创建了书签。</span><span class="sxs-lookup"><span data-stu-id="1cd4e-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1cd4e-114">消息</span><span class="sxs-lookup"><span data-stu-id="1cd4e-114">Message</span></span>  
 <span data-ttu-id="1cd4e-115">已为 Activity"%1"、 DisplayName 创建书签:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="1cd4e-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="1cd4e-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="1cd4e-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1cd4e-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="1cd4e-117">Details</span></span>  
  
|<span data-ttu-id="1cd4e-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="1cd4e-118">Data Item Name</span></span>|<span data-ttu-id="1cd4e-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="1cd4e-119">Data Item Type</span></span>|<span data-ttu-id="1cd4e-120">描述</span><span class="sxs-lookup"><span data-stu-id="1cd4e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1cd4e-121">Activity</span><span class="sxs-lookup"><span data-stu-id="1cd4e-121">Activity</span></span>|<span data-ttu-id="1cd4e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="1cd4e-122">xs:string</span></span>|<span data-ttu-id="1cd4e-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="1cd4e-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="1cd4e-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1cd4e-124">DisplayName</span></span>|<span data-ttu-id="1cd4e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="1cd4e-125">xs:string</span></span>|<span data-ttu-id="1cd4e-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1cd4e-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="1cd4e-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1cd4e-127">InstanceId</span></span>|<span data-ttu-id="1cd4e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="1cd4e-128">xs:string</span></span>|<span data-ttu-id="1cd4e-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="1cd4e-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="1cd4e-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="1cd4e-130">BookmarkName</span></span>|<span data-ttu-id="1cd4e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="1cd4e-131">xs:string</span></span>|<span data-ttu-id="1cd4e-132">书签的名称。</span><span class="sxs-lookup"><span data-stu-id="1cd4e-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="1cd4e-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="1cd4e-133">BookmarkScope</span></span>|<span data-ttu-id="1cd4e-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="1cd4e-134">xs:string</span></span>|<span data-ttu-id="1cd4e-135">书签的范围。</span><span class="sxs-lookup"><span data-stu-id="1cd4e-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="1cd4e-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1cd4e-136">AppDomain</span></span>|<span data-ttu-id="1cd4e-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="1cd4e-137">xs:string</span></span>|<span data-ttu-id="1cd4e-138">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="1cd4e-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
