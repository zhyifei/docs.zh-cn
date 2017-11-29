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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1ba1ae69caff2e08da58e824d35341d3781ea8ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="753ea-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="753ea-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="753ea-103">属性</span><span class="sxs-lookup"><span data-stu-id="753ea-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="753ea-104">ID</span><span class="sxs-lookup"><span data-stu-id="753ea-104">ID</span></span>|<span data-ttu-id="753ea-105">1029</span><span class="sxs-lookup"><span data-stu-id="753ea-105">1029</span></span>|  
|<span data-ttu-id="753ea-106">关键字</span><span class="sxs-lookup"><span data-stu-id="753ea-106">Keywords</span></span>|<span data-ttu-id="753ea-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="753ea-107">WFRuntime</span></span>|  
|<span data-ttu-id="753ea-108">级别</span><span class="sxs-lookup"><span data-stu-id="753ea-108">Level</span></span>|<span data-ttu-id="753ea-109">详细</span><span class="sxs-lookup"><span data-stu-id="753ea-109">Verbose</span></span>|  
|<span data-ttu-id="753ea-110">通道</span><span class="sxs-lookup"><span data-stu-id="753ea-110">Channel</span></span>|<span data-ttu-id="753ea-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="753ea-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="753ea-112">描述</span><span class="sxs-lookup"><span data-stu-id="753ea-112">Description</span></span>  
 <span data-ttu-id="753ea-113">指示已安排 FaultWorkItem。</span><span class="sxs-lookup"><span data-stu-id="753ea-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="753ea-114">消息</span><span class="sxs-lookup"><span data-stu-id="753ea-114">Message</span></span>  
 <span data-ttu-id="753ea-115">已为 Activity"%1"、 DisplayName 安排 FaultWorkItem:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="753ea-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="753ea-116">异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。</span><span class="sxs-lookup"><span data-stu-id="753ea-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="753ea-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="753ea-117">Details</span></span>  
  
|<span data-ttu-id="753ea-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="753ea-118">Data Item Name</span></span>|<span data-ttu-id="753ea-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="753ea-119">Data Item Type</span></span>|<span data-ttu-id="753ea-120">描述</span><span class="sxs-lookup"><span data-stu-id="753ea-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="753ea-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="753ea-121">FaultActivity</span></span>|<span data-ttu-id="753ea-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="753ea-122">xs:string</span></span>|<span data-ttu-id="753ea-123">错误活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="753ea-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="753ea-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="753ea-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="753ea-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="753ea-125">xs:string</span></span>|<span data-ttu-id="753ea-126">错误活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="753ea-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="753ea-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="753ea-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="753ea-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="753ea-128">xs:string</span></span>|<span data-ttu-id="753ea-129">错误活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="753ea-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="753ea-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="753ea-130">ExceptionActivity</span></span>|<span data-ttu-id="753ea-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="753ea-131">xs:string</span></span>|<span data-ttu-id="753ea-132">引发了异常的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="753ea-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="753ea-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="753ea-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="753ea-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="753ea-134">xs:string</span></span>|<span data-ttu-id="753ea-135">引发了异常的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="753ea-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="753ea-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="753ea-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="753ea-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="753ea-137">xs:string</span></span>|<span data-ttu-id="753ea-138">引发了异常的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="753ea-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="753ea-139">例外</span><span class="sxs-lookup"><span data-stu-id="753ea-139">Exception</span></span>|<span data-ttu-id="753ea-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="753ea-140">xs:string</span></span>|<span data-ttu-id="753ea-141">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="753ea-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="753ea-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="753ea-142">AppDomain</span></span>|<span data-ttu-id="753ea-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="753ea-143">xs:string</span></span>|<span data-ttu-id="753ea-144">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="753ea-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
