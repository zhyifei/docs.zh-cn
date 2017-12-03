---
title: 1030 - StartFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c639de96bd72670b2641707e7283be2642801dbe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="13da3-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="13da3-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="13da3-103">属性</span><span class="sxs-lookup"><span data-stu-id="13da3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="13da3-104">ID</span><span class="sxs-lookup"><span data-stu-id="13da3-104">ID</span></span>|<span data-ttu-id="13da3-105">1030</span><span class="sxs-lookup"><span data-stu-id="13da3-105">1030</span></span>|  
|<span data-ttu-id="13da3-106">关键字</span><span class="sxs-lookup"><span data-stu-id="13da3-106">Keywords</span></span>|<span data-ttu-id="13da3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="13da3-107">WFRuntime</span></span>|  
|<span data-ttu-id="13da3-108">级别</span><span class="sxs-lookup"><span data-stu-id="13da3-108">Level</span></span>|<span data-ttu-id="13da3-109">详细</span><span class="sxs-lookup"><span data-stu-id="13da3-109">Verbose</span></span>|  
|<span data-ttu-id="13da3-110">通道</span><span class="sxs-lookup"><span data-stu-id="13da3-110">Channel</span></span>|<span data-ttu-id="13da3-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="13da3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="13da3-112">描述</span><span class="sxs-lookup"><span data-stu-id="13da3-112">Description</span></span>  
 <span data-ttu-id="13da3-113">指示 FaultWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="13da3-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="13da3-114">消息</span><span class="sxs-lookup"><span data-stu-id="13da3-114">Message</span></span>  
 <span data-ttu-id="13da3-115">开始执行的活动 DisplayName"%1"的 FaultWorkItem:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="13da3-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="13da3-116">异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。</span><span class="sxs-lookup"><span data-stu-id="13da3-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="13da3-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="13da3-117">Details</span></span>  
  
|<span data-ttu-id="13da3-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="13da3-118">Data Item Name</span></span>|<span data-ttu-id="13da3-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="13da3-119">Data Item Type</span></span>|<span data-ttu-id="13da3-120">描述</span><span class="sxs-lookup"><span data-stu-id="13da3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="13da3-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="13da3-121">FaultActivity</span></span>|<span data-ttu-id="13da3-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="13da3-122">xs:string</span></span>|<span data-ttu-id="13da3-123">错误活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="13da3-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="13da3-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="13da3-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="13da3-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="13da3-125">xs:string</span></span>|<span data-ttu-id="13da3-126">错误活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="13da3-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="13da3-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="13da3-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="13da3-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="13da3-128">xs:string</span></span>|<span data-ttu-id="13da3-129">错误活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="13da3-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="13da3-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="13da3-130">ExceptionActivity</span></span>|<span data-ttu-id="13da3-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="13da3-131">xs:string</span></span>|<span data-ttu-id="13da3-132">引发了异常的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="13da3-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="13da3-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="13da3-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="13da3-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="13da3-134">xs:string</span></span>|<span data-ttu-id="13da3-135">引发了异常的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="13da3-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="13da3-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="13da3-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="13da3-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="13da3-137">xs:string</span></span>|<span data-ttu-id="13da3-138">引发了异常的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="13da3-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="13da3-139">例外</span><span class="sxs-lookup"><span data-stu-id="13da3-139">Exception</span></span>|<span data-ttu-id="13da3-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="13da3-140">xs:string</span></span>|<span data-ttu-id="13da3-141">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="13da3-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="13da3-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="13da3-142">AppDomain</span></span>|<span data-ttu-id="13da3-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="13da3-143">xs:string</span></span>|<span data-ttu-id="13da3-144">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="13da3-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
