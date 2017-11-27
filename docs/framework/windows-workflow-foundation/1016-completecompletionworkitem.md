---
title: 1016 - CompleteCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a7c6b6060e8dd3256d23db7350299d2670f6caa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="c3895-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="c3895-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="c3895-103">属性</span><span class="sxs-lookup"><span data-stu-id="c3895-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3895-104">ID</span><span class="sxs-lookup"><span data-stu-id="c3895-104">ID</span></span>|<span data-ttu-id="c3895-105">1016</span><span class="sxs-lookup"><span data-stu-id="c3895-105">1016</span></span>|  
|<span data-ttu-id="c3895-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c3895-106">Keywords</span></span>|<span data-ttu-id="c3895-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c3895-107">WFRuntime</span></span>|  
|<span data-ttu-id="c3895-108">级别</span><span class="sxs-lookup"><span data-stu-id="c3895-108">Level</span></span>|<span data-ttu-id="c3895-109">详细</span><span class="sxs-lookup"><span data-stu-id="c3895-109">Verbose</span></span>|  
|<span data-ttu-id="c3895-110">通道</span><span class="sxs-lookup"><span data-stu-id="c3895-110">Channel</span></span>|<span data-ttu-id="c3895-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c3895-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c3895-112">描述</span><span class="sxs-lookup"><span data-stu-id="c3895-112">Description</span></span>  
 <span data-ttu-id="c3895-113">指示 CompletionWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="c3895-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c3895-114">消息</span><span class="sxs-lookup"><span data-stu-id="c3895-114">Message</span></span>  
 <span data-ttu-id="c3895-115">父 Activity“%1”、DisplayName“'%2”、InstanceId“%3”已完成了 CompletionWorkItem。</span><span class="sxs-lookup"><span data-stu-id="c3895-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="c3895-116">已完成的活动“%4”、DisplayName：“%5”、InstanceId：“%6”。</span><span class="sxs-lookup"><span data-stu-id="c3895-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c3895-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="c3895-117">Details</span></span>  
  
|<span data-ttu-id="c3895-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c3895-118">Data Item Name</span></span>|<span data-ttu-id="c3895-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c3895-119">Data Item Type</span></span>|<span data-ttu-id="c3895-120">描述</span><span class="sxs-lookup"><span data-stu-id="c3895-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c3895-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="c3895-121">ParentActivity</span></span>|<span data-ttu-id="c3895-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3895-122">xs:string</span></span>|<span data-ttu-id="c3895-123">父活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="c3895-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="c3895-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="c3895-124">ParentDisplayName</span></span>|<span data-ttu-id="c3895-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3895-125">xs:string</span></span>|<span data-ttu-id="c3895-126">父活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c3895-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="c3895-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="c3895-127">ParentInstanceId</span></span>|<span data-ttu-id="c3895-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3895-128">xs:string</span></span>|<span data-ttu-id="c3895-129">父活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="c3895-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="c3895-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="c3895-130">CompletedActivity</span></span>|<span data-ttu-id="c3895-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3895-131">xs:string</span></span>|<span data-ttu-id="c3895-132">已完成活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="c3895-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="c3895-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c3895-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="c3895-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3895-134">xs:string</span></span>|<span data-ttu-id="c3895-135">已完成活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c3895-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="c3895-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c3895-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="c3895-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3895-137">xs:string</span></span>|<span data-ttu-id="c3895-138">已完成活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="c3895-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="c3895-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c3895-139">AppDomain</span></span>|<span data-ttu-id="c3895-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3895-140">xs:string</span></span>|<span data-ttu-id="c3895-141">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c3895-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
