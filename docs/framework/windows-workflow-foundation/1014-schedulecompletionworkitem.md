---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 50b00a49ea73dcbe09e8f4c4195cbce8c1cbf615
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510362"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="dc225-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="dc225-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="dc225-103">属性</span><span class="sxs-lookup"><span data-stu-id="dc225-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dc225-104">ID</span><span class="sxs-lookup"><span data-stu-id="dc225-104">ID</span></span>|<span data-ttu-id="dc225-105">1014</span><span class="sxs-lookup"><span data-stu-id="dc225-105">1014</span></span>|  
|<span data-ttu-id="dc225-106">关键字</span><span class="sxs-lookup"><span data-stu-id="dc225-106">Keywords</span></span>|<span data-ttu-id="dc225-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="dc225-107">WFRuntime</span></span>|  
|<span data-ttu-id="dc225-108">级别</span><span class="sxs-lookup"><span data-stu-id="dc225-108">Level</span></span>|<span data-ttu-id="dc225-109">详细</span><span class="sxs-lookup"><span data-stu-id="dc225-109">Verbose</span></span>|  
|<span data-ttu-id="dc225-110">通道</span><span class="sxs-lookup"><span data-stu-id="dc225-110">Channel</span></span>|<span data-ttu-id="dc225-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="dc225-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dc225-112">描述</span><span class="sxs-lookup"><span data-stu-id="dc225-112">Description</span></span>  
 <span data-ttu-id="dc225-113">指示已安排 CompletionWorkItem。</span><span class="sxs-lookup"><span data-stu-id="dc225-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dc225-114">消息</span><span class="sxs-lookup"><span data-stu-id="dc225-114">Message</span></span>  
 <span data-ttu-id="dc225-115">CompletionWorkItem 已安排为父 Activity"%1"、 DisplayName:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="dc225-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="dc225-116">已完成的活动“%4”、DisplayName：“%5”、InstanceId：“%6”。</span><span class="sxs-lookup"><span data-stu-id="dc225-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dc225-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="dc225-117">Details</span></span>  
  
|<span data-ttu-id="dc225-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="dc225-118">Data Item Name</span></span>|<span data-ttu-id="dc225-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="dc225-119">Data Item Type</span></span>|<span data-ttu-id="dc225-120">描述</span><span class="sxs-lookup"><span data-stu-id="dc225-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dc225-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="dc225-121">ParentActivity</span></span>|<span data-ttu-id="dc225-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="dc225-122">xs:string</span></span>|<span data-ttu-id="dc225-123">父活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="dc225-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="dc225-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="dc225-124">ParentDisplayName</span></span>|<span data-ttu-id="dc225-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="dc225-125">xs:string</span></span>|<span data-ttu-id="dc225-126">父活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="dc225-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="dc225-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="dc225-127">ParentInstanceId</span></span>|<span data-ttu-id="dc225-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="dc225-128">xs:string</span></span>|<span data-ttu-id="dc225-129">父活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="dc225-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="dc225-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="dc225-130">CompletedActivity</span></span>|<span data-ttu-id="dc225-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="dc225-131">xs:string</span></span>|<span data-ttu-id="dc225-132">已完成活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="dc225-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="dc225-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="dc225-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="dc225-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="dc225-134">xs:string</span></span>|<span data-ttu-id="dc225-135">已完成活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="dc225-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="dc225-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="dc225-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="dc225-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="dc225-137">xs:string</span></span>|<span data-ttu-id="dc225-138">已完成活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="dc225-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="dc225-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="dc225-139">AppDomain</span></span>|<span data-ttu-id="dc225-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="dc225-140">xs:string</span></span>|<span data-ttu-id="dc225-141">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="dc225-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
