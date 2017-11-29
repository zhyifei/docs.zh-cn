---
title: 1023 - CompleteBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc5dac57-b3eb-4826-b505-c6d269e4774d
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5db5b106a6bc92c288aefe309d33625f57b0ddad
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1023---completebookmarkworkitem"></a><span data-ttu-id="25321-102">1023 - CompleteBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="25321-102">1023 - CompleteBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="25321-103">属性</span><span class="sxs-lookup"><span data-stu-id="25321-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25321-104">ID</span><span class="sxs-lookup"><span data-stu-id="25321-104">ID</span></span>|<span data-ttu-id="25321-105">1023</span><span class="sxs-lookup"><span data-stu-id="25321-105">1023</span></span>|  
|<span data-ttu-id="25321-106">关键字</span><span class="sxs-lookup"><span data-stu-id="25321-106">Keywords</span></span>|<span data-ttu-id="25321-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="25321-107">WFRuntime</span></span>|  
|<span data-ttu-id="25321-108">级别</span><span class="sxs-lookup"><span data-stu-id="25321-108">Level</span></span>|<span data-ttu-id="25321-109">详细</span><span class="sxs-lookup"><span data-stu-id="25321-109">Verbose</span></span>|  
|<span data-ttu-id="25321-110">通道</span><span class="sxs-lookup"><span data-stu-id="25321-110">Channel</span></span>|<span data-ttu-id="25321-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="25321-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="25321-112">描述</span><span class="sxs-lookup"><span data-stu-id="25321-112">Description</span></span>  
 <span data-ttu-id="25321-113">指示 BookmarkWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="25321-113">Indicates a BookmarkWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="25321-114">消息</span><span class="sxs-lookup"><span data-stu-id="25321-114">Message</span></span>  
 <span data-ttu-id="25321-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的 BookmarkWorkItem 已经完成。</span><span class="sxs-lookup"><span data-stu-id="25321-115">A BookmarkWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="25321-116">BookmarkName: %4、BookmarkScope: %5。</span><span class="sxs-lookup"><span data-stu-id="25321-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="25321-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="25321-117">Details</span></span>  
  
|<span data-ttu-id="25321-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="25321-118">Data Item Name</span></span>|<span data-ttu-id="25321-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="25321-119">Data Item Type</span></span>|<span data-ttu-id="25321-120">描述</span><span class="sxs-lookup"><span data-stu-id="25321-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="25321-121">Activity</span><span class="sxs-lookup"><span data-stu-id="25321-121">Activity</span></span>|<span data-ttu-id="25321-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="25321-122">xs:string</span></span>|<span data-ttu-id="25321-123">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="25321-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="25321-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="25321-124">DisplayName</span></span>|<span data-ttu-id="25321-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="25321-125">xs:string</span></span>|<span data-ttu-id="25321-126">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="25321-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="25321-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="25321-127">InstanceId</span></span>|<span data-ttu-id="25321-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="25321-128">xs:string</span></span>|<span data-ttu-id="25321-129">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="25321-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="25321-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="25321-130">BookmarkName</span></span>|<span data-ttu-id="25321-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="25321-131">xs:string</span></span>|<span data-ttu-id="25321-132">书签的名称。</span><span class="sxs-lookup"><span data-stu-id="25321-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="25321-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="25321-133">BookmarkScope</span></span>|<span data-ttu-id="25321-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="25321-134">xs:string</span></span>|<span data-ttu-id="25321-135">书签的范围。</span><span class="sxs-lookup"><span data-stu-id="25321-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="25321-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="25321-136">AppDomain</span></span>|<span data-ttu-id="25321-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="25321-137">xs:string</span></span>|<span data-ttu-id="25321-138">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="25321-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
