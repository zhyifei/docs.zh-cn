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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f9b09001212de6d5aa4f5fde577b9eeb9d967ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="0c988-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="0c988-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0c988-103">属性</span><span class="sxs-lookup"><span data-stu-id="0c988-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0c988-104">ID</span><span class="sxs-lookup"><span data-stu-id="0c988-104">ID</span></span>|<span data-ttu-id="0c988-105">1016</span><span class="sxs-lookup"><span data-stu-id="0c988-105">1016</span></span>|  
|<span data-ttu-id="0c988-106">关键字</span><span class="sxs-lookup"><span data-stu-id="0c988-106">Keywords</span></span>|<span data-ttu-id="0c988-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0c988-107">WFRuntime</span></span>|  
|<span data-ttu-id="0c988-108">级别</span><span class="sxs-lookup"><span data-stu-id="0c988-108">Level</span></span>|<span data-ttu-id="0c988-109">详细</span><span class="sxs-lookup"><span data-stu-id="0c988-109">Verbose</span></span>|  
|<span data-ttu-id="0c988-110">通道</span><span class="sxs-lookup"><span data-stu-id="0c988-110">Channel</span></span>|<span data-ttu-id="0c988-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="0c988-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0c988-112">描述</span><span class="sxs-lookup"><span data-stu-id="0c988-112">Description</span></span>  
 <span data-ttu-id="0c988-113">指示 CompletionWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="0c988-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0c988-114">消息</span><span class="sxs-lookup"><span data-stu-id="0c988-114">Message</span></span>  
 <span data-ttu-id="0c988-115">父 Activity“%1”、DisplayName“'%2”、InstanceId“%3”已完成了 CompletionWorkItem。</span><span class="sxs-lookup"><span data-stu-id="0c988-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="0c988-116">已完成的活动“%4”、DisplayName：“%5”、InstanceId：“%6”。</span><span class="sxs-lookup"><span data-stu-id="0c988-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0c988-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="0c988-117">Details</span></span>  
  
|<span data-ttu-id="0c988-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="0c988-118">Data Item Name</span></span>|<span data-ttu-id="0c988-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="0c988-119">Data Item Type</span></span>|<span data-ttu-id="0c988-120">描述</span><span class="sxs-lookup"><span data-stu-id="0c988-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0c988-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="0c988-121">ParentActivity</span></span>|<span data-ttu-id="0c988-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c988-122">xs:string</span></span>|<span data-ttu-id="0c988-123">父活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="0c988-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="0c988-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="0c988-124">ParentDisplayName</span></span>|<span data-ttu-id="0c988-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c988-125">xs:string</span></span>|<span data-ttu-id="0c988-126">父活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="0c988-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="0c988-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="0c988-127">ParentInstanceId</span></span>|<span data-ttu-id="0c988-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c988-128">xs:string</span></span>|<span data-ttu-id="0c988-129">父活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="0c988-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="0c988-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="0c988-130">CompletedActivity</span></span>|<span data-ttu-id="0c988-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c988-131">xs:string</span></span>|<span data-ttu-id="0c988-132">已完成活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="0c988-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="0c988-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="0c988-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="0c988-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c988-134">xs:string</span></span>|<span data-ttu-id="0c988-135">已完成活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="0c988-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="0c988-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="0c988-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="0c988-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c988-137">xs:string</span></span>|<span data-ttu-id="0c988-138">已完成活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="0c988-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="0c988-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0c988-139">AppDomain</span></span>|<span data-ttu-id="0c988-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c988-140">xs:string</span></span>|<span data-ttu-id="0c988-141">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="0c988-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
