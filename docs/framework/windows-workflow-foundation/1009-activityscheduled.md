---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 0e3ea53a7b0509fcb8b73b61193742d615ac7e91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924652"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="1b256-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="1b256-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="1b256-103">属性</span><span class="sxs-lookup"><span data-stu-id="1b256-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1b256-104">Id</span><span class="sxs-lookup"><span data-stu-id="1b256-104">ID</span></span>|<span data-ttu-id="1b256-105">1009</span><span class="sxs-lookup"><span data-stu-id="1b256-105">1009</span></span>|  
|<span data-ttu-id="1b256-106">关键字</span><span class="sxs-lookup"><span data-stu-id="1b256-106">Keywords</span></span>|<span data-ttu-id="1b256-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1b256-107">WFRuntime</span></span>|  
|<span data-ttu-id="1b256-108">级别</span><span class="sxs-lookup"><span data-stu-id="1b256-108">Level</span></span>|<span data-ttu-id="1b256-109">信息</span><span class="sxs-lookup"><span data-stu-id="1b256-109">Information</span></span>|  
|<span data-ttu-id="1b256-110">通道</span><span class="sxs-lookup"><span data-stu-id="1b256-110">Channel</span></span>|<span data-ttu-id="1b256-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="1b256-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1b256-112">描述</span><span class="sxs-lookup"><span data-stu-id="1b256-112">Description</span></span>  
 <span data-ttu-id="1b256-113">指示正在安排某一活动的执行。</span><span class="sxs-lookup"><span data-stu-id="1b256-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1b256-114">消息</span><span class="sxs-lookup"><span data-stu-id="1b256-114">Message</span></span>  
 <span data-ttu-id="1b256-115">父 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了子 Activity“%4”、DisplayName“%5”、InstanceId“%6”。</span><span class="sxs-lookup"><span data-stu-id="1b256-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1b256-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="1b256-116">Details</span></span>  
  
|<span data-ttu-id="1b256-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="1b256-117">Data Item Name</span></span>|<span data-ttu-id="1b256-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="1b256-118">Data Item Type</span></span>|<span data-ttu-id="1b256-119">描述</span><span class="sxs-lookup"><span data-stu-id="1b256-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1b256-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="1b256-120">ParentActivity</span></span>|<span data-ttu-id="1b256-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1b256-121">xs:string</span></span>|<span data-ttu-id="1b256-122">父活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="1b256-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="1b256-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="1b256-123">ParentDisplayName</span></span>|<span data-ttu-id="1b256-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1b256-124">xs:string</span></span>|<span data-ttu-id="1b256-125">父活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1b256-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="1b256-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="1b256-126">ParentInstanceId</span></span>|<span data-ttu-id="1b256-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="1b256-127">xs:string</span></span>|<span data-ttu-id="1b256-128">父活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="1b256-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="1b256-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="1b256-129">ChildActivity</span></span>|<span data-ttu-id="1b256-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="1b256-130">xs:string</span></span>|<span data-ttu-id="1b256-131">所安排子活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="1b256-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="1b256-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="1b256-132">ChildDisplayName</span></span>|<span data-ttu-id="1b256-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="1b256-133">xs:string</span></span>|<span data-ttu-id="1b256-134">所安排子活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1b256-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="1b256-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="1b256-135">ChildInstanceId</span></span>|<span data-ttu-id="1b256-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="1b256-136">xs:string</span></span>|<span data-ttu-id="1b256-137">所安排子活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="1b256-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="1b256-138">应用程序域</span><span class="sxs-lookup"><span data-stu-id="1b256-138">AppDomain</span></span>|<span data-ttu-id="1b256-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="1b256-139">xs:string</span></span>|<span data-ttu-id="1b256-140">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="1b256-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
