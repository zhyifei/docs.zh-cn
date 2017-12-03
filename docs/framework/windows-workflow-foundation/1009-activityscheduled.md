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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdaa8ca4efeffb3895e0056303721b13cdc1ae27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="ce244-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="ce244-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="ce244-103">属性</span><span class="sxs-lookup"><span data-stu-id="ce244-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ce244-104">ID</span><span class="sxs-lookup"><span data-stu-id="ce244-104">ID</span></span>|<span data-ttu-id="ce244-105">1009</span><span class="sxs-lookup"><span data-stu-id="ce244-105">1009</span></span>|  
|<span data-ttu-id="ce244-106">关键字</span><span class="sxs-lookup"><span data-stu-id="ce244-106">Keywords</span></span>|<span data-ttu-id="ce244-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ce244-107">WFRuntime</span></span>|  
|<span data-ttu-id="ce244-108">级别</span><span class="sxs-lookup"><span data-stu-id="ce244-108">Level</span></span>|<span data-ttu-id="ce244-109">信息</span><span class="sxs-lookup"><span data-stu-id="ce244-109">Information</span></span>|  
|<span data-ttu-id="ce244-110">通道</span><span class="sxs-lookup"><span data-stu-id="ce244-110">Channel</span></span>|<span data-ttu-id="ce244-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="ce244-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ce244-112">描述</span><span class="sxs-lookup"><span data-stu-id="ce244-112">Description</span></span>  
 <span data-ttu-id="ce244-113">指示正在安排某一活动的执行。</span><span class="sxs-lookup"><span data-stu-id="ce244-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ce244-114">消息</span><span class="sxs-lookup"><span data-stu-id="ce244-114">Message</span></span>  
 <span data-ttu-id="ce244-115">父 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了子 Activity“%4”、DisplayName“%5”、InstanceId“%6”。</span><span class="sxs-lookup"><span data-stu-id="ce244-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ce244-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="ce244-116">Details</span></span>  
  
|<span data-ttu-id="ce244-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="ce244-117">Data Item Name</span></span>|<span data-ttu-id="ce244-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="ce244-118">Data Item Type</span></span>|<span data-ttu-id="ce244-119">描述</span><span class="sxs-lookup"><span data-stu-id="ce244-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ce244-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="ce244-120">ParentActivity</span></span>|<span data-ttu-id="ce244-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ce244-121">xs:string</span></span>|<span data-ttu-id="ce244-122">父活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="ce244-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="ce244-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="ce244-123">ParentDisplayName</span></span>|<span data-ttu-id="ce244-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ce244-124">xs:string</span></span>|<span data-ttu-id="ce244-125">父活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ce244-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="ce244-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="ce244-126">ParentInstanceId</span></span>|<span data-ttu-id="ce244-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ce244-127">xs:string</span></span>|<span data-ttu-id="ce244-128">父活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="ce244-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="ce244-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="ce244-129">ChildActivity</span></span>|<span data-ttu-id="ce244-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ce244-130">xs:string</span></span>|<span data-ttu-id="ce244-131">所安排子活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="ce244-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="ce244-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="ce244-132">ChildDisplayName</span></span>|<span data-ttu-id="ce244-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="ce244-133">xs:string</span></span>|<span data-ttu-id="ce244-134">所安排子活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ce244-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="ce244-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="ce244-135">ChildInstanceId</span></span>|<span data-ttu-id="ce244-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="ce244-136">xs:string</span></span>|<span data-ttu-id="ce244-137">所安排子活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="ce244-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="ce244-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ce244-138">AppDomain</span></span>|<span data-ttu-id="ce244-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="ce244-139">xs:string</span></span>|<span data-ttu-id="ce244-140">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="ce244-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
