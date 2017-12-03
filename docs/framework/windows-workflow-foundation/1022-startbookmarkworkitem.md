---
title: 1022 - StartBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d7df39bd0f6d6d4d309cf5c599ecd3795eb92067
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="b6181-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="b6181-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b6181-103">属性</span><span class="sxs-lookup"><span data-stu-id="b6181-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b6181-104">ID</span><span class="sxs-lookup"><span data-stu-id="b6181-104">ID</span></span>|<span data-ttu-id="b6181-105">1022</span><span class="sxs-lookup"><span data-stu-id="b6181-105">1022</span></span>|  
|<span data-ttu-id="b6181-106">关键字</span><span class="sxs-lookup"><span data-stu-id="b6181-106">Keywords</span></span>|<span data-ttu-id="b6181-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b6181-107">WFRuntime</span></span>|  
|<span data-ttu-id="b6181-108">级别</span><span class="sxs-lookup"><span data-stu-id="b6181-108">Level</span></span>|<span data-ttu-id="b6181-109">详细</span><span class="sxs-lookup"><span data-stu-id="b6181-109">Verbose</span></span>|  
|<span data-ttu-id="b6181-110">通道</span><span class="sxs-lookup"><span data-stu-id="b6181-110">Channel</span></span>|<span data-ttu-id="b6181-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="b6181-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b6181-112">描述</span><span class="sxs-lookup"><span data-stu-id="b6181-112">Description</span></span>  
 <span data-ttu-id="b6181-113">指示 BookmarkWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="b6181-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b6181-114">消息</span><span class="sxs-lookup"><span data-stu-id="b6181-114">Message</span></span>  
 <span data-ttu-id="b6181-115">开始执行的活动 DisplayName"%1"的 BookmarkWorkItem:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="b6181-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="b6181-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="b6181-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b6181-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="b6181-117">Details</span></span>  
  
|<span data-ttu-id="b6181-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="b6181-118">Data Item Name</span></span>|<span data-ttu-id="b6181-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="b6181-119">Data Item Type</span></span>|<span data-ttu-id="b6181-120">描述</span><span class="sxs-lookup"><span data-stu-id="b6181-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b6181-121">Activity</span><span class="sxs-lookup"><span data-stu-id="b6181-121">Activity</span></span>|<span data-ttu-id="b6181-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6181-122">xs:string</span></span>|<span data-ttu-id="b6181-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="b6181-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="b6181-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b6181-124">DisplayName</span></span>|<span data-ttu-id="b6181-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6181-125">xs:string</span></span>|<span data-ttu-id="b6181-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b6181-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="b6181-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b6181-127">InstanceId</span></span>|<span data-ttu-id="b6181-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6181-128">xs:string</span></span>|<span data-ttu-id="b6181-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="b6181-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b6181-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="b6181-130">BookmarkName</span></span>|<span data-ttu-id="b6181-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6181-131">xs:string</span></span>|<span data-ttu-id="b6181-132">书签的名称。</span><span class="sxs-lookup"><span data-stu-id="b6181-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="b6181-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="b6181-133">BookmarkScope</span></span>|<span data-ttu-id="b6181-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6181-134">xs:string</span></span>|<span data-ttu-id="b6181-135">书签的范围。</span><span class="sxs-lookup"><span data-stu-id="b6181-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="b6181-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b6181-136">AppDomain</span></span>|<span data-ttu-id="b6181-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6181-137">xs:string</span></span>|<span data-ttu-id="b6181-138">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="b6181-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
