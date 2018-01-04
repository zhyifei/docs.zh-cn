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
ms.workload: dotnet
ms.openlocfilehash: a87ecb0a50437d83dd3c80d213553c8ac2143968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="42047-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="42047-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="42047-103">属性</span><span class="sxs-lookup"><span data-stu-id="42047-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42047-104">ID</span><span class="sxs-lookup"><span data-stu-id="42047-104">ID</span></span>|<span data-ttu-id="42047-105">1031</span><span class="sxs-lookup"><span data-stu-id="42047-105">1031</span></span>|  
|<span data-ttu-id="42047-106">关键字</span><span class="sxs-lookup"><span data-stu-id="42047-106">Keywords</span></span>|<span data-ttu-id="42047-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="42047-107">WFRuntime</span></span>|  
|<span data-ttu-id="42047-108">级别</span><span class="sxs-lookup"><span data-stu-id="42047-108">Level</span></span>|<span data-ttu-id="42047-109">详细</span><span class="sxs-lookup"><span data-stu-id="42047-109">Verbose</span></span>|  
|<span data-ttu-id="42047-110">通道</span><span class="sxs-lookup"><span data-stu-id="42047-110">Channel</span></span>|<span data-ttu-id="42047-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="42047-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="42047-112">描述</span><span class="sxs-lookup"><span data-stu-id="42047-112">Description</span></span>  
 <span data-ttu-id="42047-113">指示 FaultWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="42047-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="42047-114">消息</span><span class="sxs-lookup"><span data-stu-id="42047-114">Message</span></span>  
 <span data-ttu-id="42047-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的 FaultWorkItem 已经完成。</span><span class="sxs-lookup"><span data-stu-id="42047-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="42047-116">异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。</span><span class="sxs-lookup"><span data-stu-id="42047-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="42047-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="42047-117">Details</span></span>  
  
|<span data-ttu-id="42047-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="42047-118">Data Item Name</span></span>|<span data-ttu-id="42047-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="42047-119">Data Item Type</span></span>|<span data-ttu-id="42047-120">描述</span><span class="sxs-lookup"><span data-stu-id="42047-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="42047-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="42047-121">FaultActivity</span></span>|<span data-ttu-id="42047-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="42047-122">xs:string</span></span>|<span data-ttu-id="42047-123">错误活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="42047-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="42047-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="42047-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="42047-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="42047-125">xs:string</span></span>|<span data-ttu-id="42047-126">错误活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="42047-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="42047-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="42047-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="42047-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="42047-128">xs:string</span></span>|<span data-ttu-id="42047-129">错误活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="42047-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="42047-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="42047-130">ExceptionActivity</span></span>|<span data-ttu-id="42047-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="42047-131">xs:string</span></span>|<span data-ttu-id="42047-132">引发了异常的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="42047-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="42047-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="42047-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="42047-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="42047-134">xs:string</span></span>|<span data-ttu-id="42047-135">引发了异常的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="42047-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="42047-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="42047-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="42047-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="42047-137">xs:string</span></span>|<span data-ttu-id="42047-138">引发了异常的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="42047-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="42047-139">例外</span><span class="sxs-lookup"><span data-stu-id="42047-139">Exception</span></span>|<span data-ttu-id="42047-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="42047-140">xs:string</span></span>|<span data-ttu-id="42047-141">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="42047-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="42047-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="42047-142">AppDomain</span></span>|<span data-ttu-id="42047-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="42047-143">xs:string</span></span>|<span data-ttu-id="42047-144">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="42047-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
