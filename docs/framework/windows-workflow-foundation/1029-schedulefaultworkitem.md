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
ms.workload: dotnet
ms.openlocfilehash: dfa9553c25f607ec25fd968c2e8c6db061fb49dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="2ae43-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="2ae43-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="2ae43-103">属性</span><span class="sxs-lookup"><span data-stu-id="2ae43-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ae43-104">ID</span><span class="sxs-lookup"><span data-stu-id="2ae43-104">ID</span></span>|<span data-ttu-id="2ae43-105">1029</span><span class="sxs-lookup"><span data-stu-id="2ae43-105">1029</span></span>|  
|<span data-ttu-id="2ae43-106">关键字</span><span class="sxs-lookup"><span data-stu-id="2ae43-106">Keywords</span></span>|<span data-ttu-id="2ae43-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2ae43-107">WFRuntime</span></span>|  
|<span data-ttu-id="2ae43-108">级别</span><span class="sxs-lookup"><span data-stu-id="2ae43-108">Level</span></span>|<span data-ttu-id="2ae43-109">详细</span><span class="sxs-lookup"><span data-stu-id="2ae43-109">Verbose</span></span>|  
|<span data-ttu-id="2ae43-110">通道</span><span class="sxs-lookup"><span data-stu-id="2ae43-110">Channel</span></span>|<span data-ttu-id="2ae43-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="2ae43-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2ae43-112">描述</span><span class="sxs-lookup"><span data-stu-id="2ae43-112">Description</span></span>  
 <span data-ttu-id="2ae43-113">指示已安排 FaultWorkItem。</span><span class="sxs-lookup"><span data-stu-id="2ae43-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2ae43-114">消息</span><span class="sxs-lookup"><span data-stu-id="2ae43-114">Message</span></span>  
 <span data-ttu-id="2ae43-115">已为 Activity"%1"、 DisplayName 安排 FaultWorkItem:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="2ae43-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="2ae43-116">异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。</span><span class="sxs-lookup"><span data-stu-id="2ae43-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2ae43-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="2ae43-117">Details</span></span>  
  
|<span data-ttu-id="2ae43-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="2ae43-118">Data Item Name</span></span>|<span data-ttu-id="2ae43-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="2ae43-119">Data Item Type</span></span>|<span data-ttu-id="2ae43-120">描述</span><span class="sxs-lookup"><span data-stu-id="2ae43-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2ae43-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="2ae43-121">FaultActivity</span></span>|<span data-ttu-id="2ae43-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ae43-122">xs:string</span></span>|<span data-ttu-id="2ae43-123">错误活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="2ae43-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="2ae43-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2ae43-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="2ae43-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ae43-125">xs:string</span></span>|<span data-ttu-id="2ae43-126">错误活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="2ae43-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="2ae43-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2ae43-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="2ae43-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ae43-128">xs:string</span></span>|<span data-ttu-id="2ae43-129">错误活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="2ae43-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="2ae43-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="2ae43-130">ExceptionActivity</span></span>|<span data-ttu-id="2ae43-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ae43-131">xs:string</span></span>|<span data-ttu-id="2ae43-132">引发了异常的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="2ae43-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2ae43-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2ae43-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="2ae43-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ae43-134">xs:string</span></span>|<span data-ttu-id="2ae43-135">引发了异常的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="2ae43-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2ae43-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2ae43-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="2ae43-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ae43-137">xs:string</span></span>|<span data-ttu-id="2ae43-138">引发了异常的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="2ae43-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2ae43-139">例外</span><span class="sxs-lookup"><span data-stu-id="2ae43-139">Exception</span></span>|<span data-ttu-id="2ae43-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ae43-140">xs:string</span></span>|<span data-ttu-id="2ae43-141">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="2ae43-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="2ae43-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2ae43-142">AppDomain</span></span>|<span data-ttu-id="2ae43-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ae43-143">xs:string</span></span>|<span data-ttu-id="2ae43-144">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="2ae43-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
