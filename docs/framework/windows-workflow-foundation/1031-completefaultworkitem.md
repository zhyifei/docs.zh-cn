---
title: 1031 - CompleteFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5173e61b2479d02dc35c5fcf9ae55634cc8dc7ba
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="dd018-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="dd018-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="dd018-103">属性</span><span class="sxs-lookup"><span data-stu-id="dd018-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dd018-104">ID</span><span class="sxs-lookup"><span data-stu-id="dd018-104">ID</span></span>|<span data-ttu-id="dd018-105">1031</span><span class="sxs-lookup"><span data-stu-id="dd018-105">1031</span></span>|  
|<span data-ttu-id="dd018-106">关键字</span><span class="sxs-lookup"><span data-stu-id="dd018-106">Keywords</span></span>|<span data-ttu-id="dd018-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="dd018-107">WFRuntime</span></span>|  
|<span data-ttu-id="dd018-108">级别</span><span class="sxs-lookup"><span data-stu-id="dd018-108">Level</span></span>|<span data-ttu-id="dd018-109">详细</span><span class="sxs-lookup"><span data-stu-id="dd018-109">Verbose</span></span>|  
|<span data-ttu-id="dd018-110">通道</span><span class="sxs-lookup"><span data-stu-id="dd018-110">Channel</span></span>|<span data-ttu-id="dd018-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="dd018-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dd018-112">描述</span><span class="sxs-lookup"><span data-stu-id="dd018-112">Description</span></span>  
 <span data-ttu-id="dd018-113">指示 FaultWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="dd018-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dd018-114">消息</span><span class="sxs-lookup"><span data-stu-id="dd018-114">Message</span></span>  
 <span data-ttu-id="dd018-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的 FaultWorkItem 已经完成。</span><span class="sxs-lookup"><span data-stu-id="dd018-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="dd018-116">异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。</span><span class="sxs-lookup"><span data-stu-id="dd018-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dd018-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="dd018-117">Details</span></span>  
  
|<span data-ttu-id="dd018-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="dd018-118">Data Item Name</span></span>|<span data-ttu-id="dd018-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="dd018-119">Data Item Type</span></span>|<span data-ttu-id="dd018-120">描述</span><span class="sxs-lookup"><span data-stu-id="dd018-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dd018-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="dd018-121">FaultActivity</span></span>|<span data-ttu-id="dd018-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd018-122">xs:string</span></span>|<span data-ttu-id="dd018-123">错误活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="dd018-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="dd018-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="dd018-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="dd018-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd018-125">xs:string</span></span>|<span data-ttu-id="dd018-126">错误活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="dd018-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="dd018-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="dd018-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="dd018-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd018-128">xs:string</span></span>|<span data-ttu-id="dd018-129">错误活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="dd018-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="dd018-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="dd018-130">ExceptionActivity</span></span>|<span data-ttu-id="dd018-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd018-131">xs:string</span></span>|<span data-ttu-id="dd018-132">引发了异常的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="dd018-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="dd018-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="dd018-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="dd018-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd018-134">xs:string</span></span>|<span data-ttu-id="dd018-135">引发了异常的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="dd018-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="dd018-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="dd018-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="dd018-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd018-137">xs:string</span></span>|<span data-ttu-id="dd018-138">引发了异常的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="dd018-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="dd018-139">例外</span><span class="sxs-lookup"><span data-stu-id="dd018-139">Exception</span></span>|<span data-ttu-id="dd018-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd018-140">xs:string</span></span>|<span data-ttu-id="dd018-141">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="dd018-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="dd018-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="dd018-142">AppDomain</span></span>|<span data-ttu-id="dd018-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd018-143">xs:string</span></span>|<span data-ttu-id="dd018-144">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="dd018-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
