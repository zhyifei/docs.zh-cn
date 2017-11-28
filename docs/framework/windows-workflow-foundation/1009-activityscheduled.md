---
title: 1009 - ActivityScheduled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d9463fbf2e7f2ac3424488dc3fca322a91d11126
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="1ac5d-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="1ac5d-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="1ac5d-103">属性</span><span class="sxs-lookup"><span data-stu-id="1ac5d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ac5d-104">ID</span><span class="sxs-lookup"><span data-stu-id="1ac5d-104">ID</span></span>|<span data-ttu-id="1ac5d-105">1009</span><span class="sxs-lookup"><span data-stu-id="1ac5d-105">1009</span></span>|  
|<span data-ttu-id="1ac5d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="1ac5d-106">Keywords</span></span>|<span data-ttu-id="1ac5d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1ac5d-107">WFRuntime</span></span>|  
|<span data-ttu-id="1ac5d-108">级别</span><span class="sxs-lookup"><span data-stu-id="1ac5d-108">Level</span></span>|<span data-ttu-id="1ac5d-109">信息</span><span class="sxs-lookup"><span data-stu-id="1ac5d-109">Information</span></span>|  
|<span data-ttu-id="1ac5d-110">通道</span><span class="sxs-lookup"><span data-stu-id="1ac5d-110">Channel</span></span>|<span data-ttu-id="1ac5d-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="1ac5d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1ac5d-112">描述</span><span class="sxs-lookup"><span data-stu-id="1ac5d-112">Description</span></span>  
 <span data-ttu-id="1ac5d-113">指示正在安排某一活动的执行。</span><span class="sxs-lookup"><span data-stu-id="1ac5d-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1ac5d-114">消息</span><span class="sxs-lookup"><span data-stu-id="1ac5d-114">Message</span></span>  
 <span data-ttu-id="1ac5d-115">父 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了子 Activity“%4”、DisplayName“%5”、InstanceId“%6”。</span><span class="sxs-lookup"><span data-stu-id="1ac5d-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1ac5d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="1ac5d-116">Details</span></span>  
  
|<span data-ttu-id="1ac5d-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="1ac5d-117">Data Item Name</span></span>|<span data-ttu-id="1ac5d-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="1ac5d-118">Data Item Type</span></span>|<span data-ttu-id="1ac5d-119">描述</span><span class="sxs-lookup"><span data-stu-id="1ac5d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1ac5d-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="1ac5d-120">ParentActivity</span></span>|<span data-ttu-id="1ac5d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ac5d-121">xs:string</span></span>|<span data-ttu-id="1ac5d-122">父活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="1ac5d-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="1ac5d-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="1ac5d-123">ParentDisplayName</span></span>|<span data-ttu-id="1ac5d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ac5d-124">xs:string</span></span>|<span data-ttu-id="1ac5d-125">父活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1ac5d-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="1ac5d-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="1ac5d-126">ParentInstanceId</span></span>|<span data-ttu-id="1ac5d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ac5d-127">xs:string</span></span>|<span data-ttu-id="1ac5d-128">父活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="1ac5d-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="1ac5d-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="1ac5d-129">ChildActivity</span></span>|<span data-ttu-id="1ac5d-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ac5d-130">xs:string</span></span>|<span data-ttu-id="1ac5d-131">所安排子活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="1ac5d-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="1ac5d-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="1ac5d-132">ChildDisplayName</span></span>|<span data-ttu-id="1ac5d-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ac5d-133">xs:string</span></span>|<span data-ttu-id="1ac5d-134">所安排子活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1ac5d-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="1ac5d-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="1ac5d-135">ChildInstanceId</span></span>|<span data-ttu-id="1ac5d-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ac5d-136">xs:string</span></span>|<span data-ttu-id="1ac5d-137">所安排子活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="1ac5d-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="1ac5d-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1ac5d-138">AppDomain</span></span>|<span data-ttu-id="1ac5d-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ac5d-139">xs:string</span></span>|<span data-ttu-id="1ac5d-140">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="1ac5d-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
