---
title: 1029 - ScheduleFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c2031a86a8d46a51b65e60a63a352c56b1a3a53
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="e56de-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="e56de-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="e56de-103">属性</span><span class="sxs-lookup"><span data-stu-id="e56de-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e56de-104">ID</span><span class="sxs-lookup"><span data-stu-id="e56de-104">ID</span></span>|<span data-ttu-id="e56de-105">1029</span><span class="sxs-lookup"><span data-stu-id="e56de-105">1029</span></span>|  
|<span data-ttu-id="e56de-106">关键字</span><span class="sxs-lookup"><span data-stu-id="e56de-106">Keywords</span></span>|<span data-ttu-id="e56de-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e56de-107">WFRuntime</span></span>|  
|<span data-ttu-id="e56de-108">级别</span><span class="sxs-lookup"><span data-stu-id="e56de-108">Level</span></span>|<span data-ttu-id="e56de-109">详细</span><span class="sxs-lookup"><span data-stu-id="e56de-109">Verbose</span></span>|  
|<span data-ttu-id="e56de-110">通道</span><span class="sxs-lookup"><span data-stu-id="e56de-110">Channel</span></span>|<span data-ttu-id="e56de-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="e56de-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e56de-112">描述</span><span class="sxs-lookup"><span data-stu-id="e56de-112">Description</span></span>  
 <span data-ttu-id="e56de-113">指示已安排 FaultWorkItem。</span><span class="sxs-lookup"><span data-stu-id="e56de-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e56de-114">消息</span><span class="sxs-lookup"><span data-stu-id="e56de-114">Message</span></span>  
 <span data-ttu-id="e56de-115">已为 Activity"%1"、 DisplayName 安排 FaultWorkItem:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="e56de-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="e56de-116">异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。</span><span class="sxs-lookup"><span data-stu-id="e56de-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e56de-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="e56de-117">Details</span></span>  
  
|<span data-ttu-id="e56de-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="e56de-118">Data Item Name</span></span>|<span data-ttu-id="e56de-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="e56de-119">Data Item Type</span></span>|<span data-ttu-id="e56de-120">描述</span><span class="sxs-lookup"><span data-stu-id="e56de-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e56de-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="e56de-121">FaultActivity</span></span>|<span data-ttu-id="e56de-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="e56de-122">xs:string</span></span>|<span data-ttu-id="e56de-123">错误活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="e56de-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="e56de-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="e56de-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="e56de-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="e56de-125">xs:string</span></span>|<span data-ttu-id="e56de-126">错误活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="e56de-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="e56de-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="e56de-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="e56de-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="e56de-128">xs:string</span></span>|<span data-ttu-id="e56de-129">错误活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="e56de-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="e56de-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="e56de-130">ExceptionActivity</span></span>|<span data-ttu-id="e56de-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="e56de-131">xs:string</span></span>|<span data-ttu-id="e56de-132">引发了异常的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="e56de-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="e56de-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="e56de-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="e56de-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="e56de-134">xs:string</span></span>|<span data-ttu-id="e56de-135">引发了异常的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="e56de-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="e56de-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="e56de-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="e56de-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="e56de-137">xs:string</span></span>|<span data-ttu-id="e56de-138">引发了异常的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="e56de-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="e56de-139">例外</span><span class="sxs-lookup"><span data-stu-id="e56de-139">Exception</span></span>|<span data-ttu-id="e56de-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="e56de-140">xs:string</span></span>|<span data-ttu-id="e56de-141">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="e56de-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="e56de-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e56de-142">AppDomain</span></span>|<span data-ttu-id="e56de-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="e56de-143">xs:string</span></span>|<span data-ttu-id="e56de-144">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="e56de-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
