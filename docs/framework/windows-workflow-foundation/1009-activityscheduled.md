---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 0e3ea53a7b0509fcb8b73b61193742d615ac7e91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="24ab2-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="24ab2-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="24ab2-103">属性</span><span class="sxs-lookup"><span data-stu-id="24ab2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24ab2-104">ID</span><span class="sxs-lookup"><span data-stu-id="24ab2-104">ID</span></span>|<span data-ttu-id="24ab2-105">1009</span><span class="sxs-lookup"><span data-stu-id="24ab2-105">1009</span></span>|  
|<span data-ttu-id="24ab2-106">关键字</span><span class="sxs-lookup"><span data-stu-id="24ab2-106">Keywords</span></span>|<span data-ttu-id="24ab2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="24ab2-107">WFRuntime</span></span>|  
|<span data-ttu-id="24ab2-108">级别</span><span class="sxs-lookup"><span data-stu-id="24ab2-108">Level</span></span>|<span data-ttu-id="24ab2-109">信息</span><span class="sxs-lookup"><span data-stu-id="24ab2-109">Information</span></span>|  
|<span data-ttu-id="24ab2-110">通道</span><span class="sxs-lookup"><span data-stu-id="24ab2-110">Channel</span></span>|<span data-ttu-id="24ab2-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="24ab2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="24ab2-112">描述</span><span class="sxs-lookup"><span data-stu-id="24ab2-112">Description</span></span>  
 <span data-ttu-id="24ab2-113">指示正在安排某一活动的执行。</span><span class="sxs-lookup"><span data-stu-id="24ab2-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="24ab2-114">消息</span><span class="sxs-lookup"><span data-stu-id="24ab2-114">Message</span></span>  
 <span data-ttu-id="24ab2-115">父 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了子 Activity“%4”、DisplayName“%5”、InstanceId“%6”。</span><span class="sxs-lookup"><span data-stu-id="24ab2-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="24ab2-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="24ab2-116">Details</span></span>  
  
|<span data-ttu-id="24ab2-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="24ab2-117">Data Item Name</span></span>|<span data-ttu-id="24ab2-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="24ab2-118">Data Item Type</span></span>|<span data-ttu-id="24ab2-119">描述</span><span class="sxs-lookup"><span data-stu-id="24ab2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="24ab2-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="24ab2-120">ParentActivity</span></span>|<span data-ttu-id="24ab2-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="24ab2-121">xs:string</span></span>|<span data-ttu-id="24ab2-122">父活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="24ab2-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="24ab2-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="24ab2-123">ParentDisplayName</span></span>|<span data-ttu-id="24ab2-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="24ab2-124">xs:string</span></span>|<span data-ttu-id="24ab2-125">父活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="24ab2-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="24ab2-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="24ab2-126">ParentInstanceId</span></span>|<span data-ttu-id="24ab2-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="24ab2-127">xs:string</span></span>|<span data-ttu-id="24ab2-128">父活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="24ab2-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="24ab2-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="24ab2-129">ChildActivity</span></span>|<span data-ttu-id="24ab2-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="24ab2-130">xs:string</span></span>|<span data-ttu-id="24ab2-131">所安排子活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="24ab2-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="24ab2-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="24ab2-132">ChildDisplayName</span></span>|<span data-ttu-id="24ab2-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="24ab2-133">xs:string</span></span>|<span data-ttu-id="24ab2-134">所安排子活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="24ab2-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="24ab2-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="24ab2-135">ChildInstanceId</span></span>|<span data-ttu-id="24ab2-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="24ab2-136">xs:string</span></span>|<span data-ttu-id="24ab2-137">所安排子活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="24ab2-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="24ab2-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="24ab2-138">AppDomain</span></span>|<span data-ttu-id="24ab2-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="24ab2-139">xs:string</span></span>|<span data-ttu-id="24ab2-140">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="24ab2-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
