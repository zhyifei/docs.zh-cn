---
title: 1014 - ScheduleCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a80406ce56000703555f7834714222e03d2b65f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="7891a-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="7891a-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="7891a-103">属性</span><span class="sxs-lookup"><span data-stu-id="7891a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7891a-104">ID</span><span class="sxs-lookup"><span data-stu-id="7891a-104">ID</span></span>|<span data-ttu-id="7891a-105">1014</span><span class="sxs-lookup"><span data-stu-id="7891a-105">1014</span></span>|  
|<span data-ttu-id="7891a-106">关键字</span><span class="sxs-lookup"><span data-stu-id="7891a-106">Keywords</span></span>|<span data-ttu-id="7891a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7891a-107">WFRuntime</span></span>|  
|<span data-ttu-id="7891a-108">级别</span><span class="sxs-lookup"><span data-stu-id="7891a-108">Level</span></span>|<span data-ttu-id="7891a-109">详细</span><span class="sxs-lookup"><span data-stu-id="7891a-109">Verbose</span></span>|  
|<span data-ttu-id="7891a-110">通道</span><span class="sxs-lookup"><span data-stu-id="7891a-110">Channel</span></span>|<span data-ttu-id="7891a-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="7891a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7891a-112">描述</span><span class="sxs-lookup"><span data-stu-id="7891a-112">Description</span></span>  
 <span data-ttu-id="7891a-113">指示已安排 CompletionWorkItem。</span><span class="sxs-lookup"><span data-stu-id="7891a-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7891a-114">消息</span><span class="sxs-lookup"><span data-stu-id="7891a-114">Message</span></span>  
 <span data-ttu-id="7891a-115">CompletionWorkItem 已安排为父 Activity"%1"、 DisplayName:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="7891a-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="7891a-116">已完成的活动“%4”、DisplayName：“%5”、InstanceId：“%6”。</span><span class="sxs-lookup"><span data-stu-id="7891a-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7891a-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="7891a-117">Details</span></span>  
  
|<span data-ttu-id="7891a-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="7891a-118">Data Item Name</span></span>|<span data-ttu-id="7891a-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="7891a-119">Data Item Type</span></span>|<span data-ttu-id="7891a-120">描述</span><span class="sxs-lookup"><span data-stu-id="7891a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7891a-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="7891a-121">ParentActivity</span></span>|<span data-ttu-id="7891a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="7891a-122">xs:string</span></span>|<span data-ttu-id="7891a-123">父活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="7891a-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="7891a-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="7891a-124">ParentDisplayName</span></span>|<span data-ttu-id="7891a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="7891a-125">xs:string</span></span>|<span data-ttu-id="7891a-126">父活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="7891a-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="7891a-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="7891a-127">ParentInstanceId</span></span>|<span data-ttu-id="7891a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="7891a-128">xs:string</span></span>|<span data-ttu-id="7891a-129">父活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="7891a-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="7891a-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="7891a-130">CompletedActivity</span></span>|<span data-ttu-id="7891a-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="7891a-131">xs:string</span></span>|<span data-ttu-id="7891a-132">已完成活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="7891a-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="7891a-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="7891a-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="7891a-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="7891a-134">xs:string</span></span>|<span data-ttu-id="7891a-135">已完成活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="7891a-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="7891a-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="7891a-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="7891a-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="7891a-137">xs:string</span></span>|<span data-ttu-id="7891a-138">已完成活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="7891a-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="7891a-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7891a-139">AppDomain</span></span>|<span data-ttu-id="7891a-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="7891a-140">xs:string</span></span>|<span data-ttu-id="7891a-141">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="7891a-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
