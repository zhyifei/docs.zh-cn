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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b25dbd5ced96b8e9ca3ef51e4de841a6238d2cbc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="75d61-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="75d61-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="75d61-103">属性</span><span class="sxs-lookup"><span data-stu-id="75d61-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75d61-104">ID</span><span class="sxs-lookup"><span data-stu-id="75d61-104">ID</span></span>|<span data-ttu-id="75d61-105">1030</span><span class="sxs-lookup"><span data-stu-id="75d61-105">1030</span></span>|  
|<span data-ttu-id="75d61-106">关键字</span><span class="sxs-lookup"><span data-stu-id="75d61-106">Keywords</span></span>|<span data-ttu-id="75d61-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="75d61-107">WFRuntime</span></span>|  
|<span data-ttu-id="75d61-108">级别</span><span class="sxs-lookup"><span data-stu-id="75d61-108">Level</span></span>|<span data-ttu-id="75d61-109">详细</span><span class="sxs-lookup"><span data-stu-id="75d61-109">Verbose</span></span>|  
|<span data-ttu-id="75d61-110">通道</span><span class="sxs-lookup"><span data-stu-id="75d61-110">Channel</span></span>|<span data-ttu-id="75d61-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="75d61-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="75d61-112">描述</span><span class="sxs-lookup"><span data-stu-id="75d61-112">Description</span></span>  
 <span data-ttu-id="75d61-113">指示 FaultWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="75d61-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="75d61-114">消息</span><span class="sxs-lookup"><span data-stu-id="75d61-114">Message</span></span>  
 <span data-ttu-id="75d61-115">开始执行的活动 DisplayName"%1"的 FaultWorkItem:"%2"、 InstanceId:"%3"。</span><span class="sxs-lookup"><span data-stu-id="75d61-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="75d61-116">异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。</span><span class="sxs-lookup"><span data-stu-id="75d61-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="75d61-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="75d61-117">Details</span></span>  
  
|<span data-ttu-id="75d61-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="75d61-118">Data Item Name</span></span>|<span data-ttu-id="75d61-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="75d61-119">Data Item Type</span></span>|<span data-ttu-id="75d61-120">描述</span><span class="sxs-lookup"><span data-stu-id="75d61-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="75d61-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="75d61-121">FaultActivity</span></span>|<span data-ttu-id="75d61-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="75d61-122">xs:string</span></span>|<span data-ttu-id="75d61-123">错误活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="75d61-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="75d61-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="75d61-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="75d61-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="75d61-125">xs:string</span></span>|<span data-ttu-id="75d61-126">错误活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="75d61-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="75d61-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="75d61-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="75d61-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="75d61-128">xs:string</span></span>|<span data-ttu-id="75d61-129">错误活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="75d61-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="75d61-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="75d61-130">ExceptionActivity</span></span>|<span data-ttu-id="75d61-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="75d61-131">xs:string</span></span>|<span data-ttu-id="75d61-132">引发了异常的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="75d61-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="75d61-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="75d61-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="75d61-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="75d61-134">xs:string</span></span>|<span data-ttu-id="75d61-135">引发了异常的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="75d61-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="75d61-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="75d61-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="75d61-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="75d61-137">xs:string</span></span>|<span data-ttu-id="75d61-138">引发了异常的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="75d61-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="75d61-139">例外</span><span class="sxs-lookup"><span data-stu-id="75d61-139">Exception</span></span>|<span data-ttu-id="75d61-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="75d61-140">xs:string</span></span>|<span data-ttu-id="75d61-141">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="75d61-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="75d61-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="75d61-142">AppDomain</span></span>|<span data-ttu-id="75d61-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="75d61-143">xs:string</span></span>|<span data-ttu-id="75d61-144">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="75d61-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
