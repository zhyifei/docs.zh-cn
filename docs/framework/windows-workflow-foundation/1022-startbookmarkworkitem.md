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
ms.workload: dotnet
ms.openlocfilehash: cdb6af10c45e7a93e9a68e6150e5d239002cce04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="9c3bf-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="9c3bf-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9c3bf-103">属性</span><span class="sxs-lookup"><span data-stu-id="9c3bf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9c3bf-104">ID</span><span class="sxs-lookup"><span data-stu-id="9c3bf-104">ID</span></span>|<span data-ttu-id="9c3bf-105">1022</span><span class="sxs-lookup"><span data-stu-id="9c3bf-105">1022</span></span>|  
|<span data-ttu-id="9c3bf-106">关键字</span><span class="sxs-lookup"><span data-stu-id="9c3bf-106">Keywords</span></span>|<span data-ttu-id="9c3bf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9c3bf-107">WFRuntime</span></span>|  
|<span data-ttu-id="9c3bf-108">级别</span><span class="sxs-lookup"><span data-stu-id="9c3bf-108">Level</span></span>|<span data-ttu-id="9c3bf-109">详细</span><span class="sxs-lookup"><span data-stu-id="9c3bf-109">Verbose</span></span>|  
|<span data-ttu-id="9c3bf-110">通道</span><span class="sxs-lookup"><span data-stu-id="9c3bf-110">Channel</span></span>|<span data-ttu-id="9c3bf-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="9c3bf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9c3bf-112">描述</span><span class="sxs-lookup"><span data-stu-id="9c3bf-112">Description</span></span>  
 <span data-ttu-id="9c3bf-113">指示 BookmarkWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="9c3bf-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9c3bf-114">消息</span><span class="sxs-lookup"><span data-stu-id="9c3bf-114">Message</span></span>  
 <span data-ttu-id="9c3bf-115">开始执行的活动 DisplayName"%1"的 BookmarkWorkItem:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="9c3bf-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="9c3bf-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="9c3bf-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9c3bf-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="9c3bf-117">Details</span></span>  
  
|<span data-ttu-id="9c3bf-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="9c3bf-118">Data Item Name</span></span>|<span data-ttu-id="9c3bf-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="9c3bf-119">Data Item Type</span></span>|<span data-ttu-id="9c3bf-120">描述</span><span class="sxs-lookup"><span data-stu-id="9c3bf-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9c3bf-121">Activity</span><span class="sxs-lookup"><span data-stu-id="9c3bf-121">Activity</span></span>|<span data-ttu-id="9c3bf-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="9c3bf-122">xs:string</span></span>|<span data-ttu-id="9c3bf-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="9c3bf-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="9c3bf-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9c3bf-124">DisplayName</span></span>|<span data-ttu-id="9c3bf-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="9c3bf-125">xs:string</span></span>|<span data-ttu-id="9c3bf-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9c3bf-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="9c3bf-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="9c3bf-127">InstanceId</span></span>|<span data-ttu-id="9c3bf-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="9c3bf-128">xs:string</span></span>|<span data-ttu-id="9c3bf-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="9c3bf-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="9c3bf-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="9c3bf-130">BookmarkName</span></span>|<span data-ttu-id="9c3bf-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="9c3bf-131">xs:string</span></span>|<span data-ttu-id="9c3bf-132">书签的名称。</span><span class="sxs-lookup"><span data-stu-id="9c3bf-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="9c3bf-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="9c3bf-133">BookmarkScope</span></span>|<span data-ttu-id="9c3bf-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="9c3bf-134">xs:string</span></span>|<span data-ttu-id="9c3bf-135">书签的范围。</span><span class="sxs-lookup"><span data-stu-id="9c3bf-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="9c3bf-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9c3bf-136">AppDomain</span></span>|<span data-ttu-id="9c3bf-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="9c3bf-137">xs:string</span></span>|<span data-ttu-id="9c3bf-138">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="9c3bf-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
