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
ms.workload: dotnet
ms.openlocfilehash: 436a0323fcf4498a1d707f7af9bd8204885fd645
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="9488b-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="9488b-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9488b-103">属性</span><span class="sxs-lookup"><span data-stu-id="9488b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9488b-104">ID</span><span class="sxs-lookup"><span data-stu-id="9488b-104">ID</span></span>|<span data-ttu-id="9488b-105">1030</span><span class="sxs-lookup"><span data-stu-id="9488b-105">1030</span></span>|  
|<span data-ttu-id="9488b-106">关键字</span><span class="sxs-lookup"><span data-stu-id="9488b-106">Keywords</span></span>|<span data-ttu-id="9488b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9488b-107">WFRuntime</span></span>|  
|<span data-ttu-id="9488b-108">级别</span><span class="sxs-lookup"><span data-stu-id="9488b-108">Level</span></span>|<span data-ttu-id="9488b-109">详细</span><span class="sxs-lookup"><span data-stu-id="9488b-109">Verbose</span></span>|  
|<span data-ttu-id="9488b-110">通道</span><span class="sxs-lookup"><span data-stu-id="9488b-110">Channel</span></span>|<span data-ttu-id="9488b-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="9488b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9488b-112">描述</span><span class="sxs-lookup"><span data-stu-id="9488b-112">Description</span></span>  
 <span data-ttu-id="9488b-113">指示 FaultWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="9488b-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9488b-114">消息</span><span class="sxs-lookup"><span data-stu-id="9488b-114">Message</span></span>  
 <span data-ttu-id="9488b-115">开始执行的活动 DisplayName"%1"的 FaultWorkItem:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="9488b-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="9488b-116">异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。</span><span class="sxs-lookup"><span data-stu-id="9488b-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9488b-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="9488b-117">Details</span></span>  
  
|<span data-ttu-id="9488b-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="9488b-118">Data Item Name</span></span>|<span data-ttu-id="9488b-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="9488b-119">Data Item Type</span></span>|<span data-ttu-id="9488b-120">描述</span><span class="sxs-lookup"><span data-stu-id="9488b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9488b-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="9488b-121">FaultActivity</span></span>|<span data-ttu-id="9488b-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="9488b-122">xs:string</span></span>|<span data-ttu-id="9488b-123">错误活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="9488b-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="9488b-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="9488b-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="9488b-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="9488b-125">xs:string</span></span>|<span data-ttu-id="9488b-126">错误活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9488b-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="9488b-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="9488b-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="9488b-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="9488b-128">xs:string</span></span>|<span data-ttu-id="9488b-129">错误活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="9488b-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="9488b-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="9488b-130">ExceptionActivity</span></span>|<span data-ttu-id="9488b-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="9488b-131">xs:string</span></span>|<span data-ttu-id="9488b-132">引发了异常的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="9488b-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="9488b-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="9488b-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="9488b-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="9488b-134">xs:string</span></span>|<span data-ttu-id="9488b-135">引发了异常的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9488b-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="9488b-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="9488b-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="9488b-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="9488b-137">xs:string</span></span>|<span data-ttu-id="9488b-138">引发了异常的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="9488b-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="9488b-139">例外</span><span class="sxs-lookup"><span data-stu-id="9488b-139">Exception</span></span>|<span data-ttu-id="9488b-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="9488b-140">xs:string</span></span>|<span data-ttu-id="9488b-141">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="9488b-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="9488b-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9488b-142">AppDomain</span></span>|<span data-ttu-id="9488b-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="9488b-143">xs:string</span></span>|<span data-ttu-id="9488b-144">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="9488b-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
