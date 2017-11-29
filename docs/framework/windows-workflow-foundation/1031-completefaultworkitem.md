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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 260647b56d945600afea5609f06d36385fa66014
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="ba290-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="ba290-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ba290-103">属性</span><span class="sxs-lookup"><span data-stu-id="ba290-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ba290-104">ID</span><span class="sxs-lookup"><span data-stu-id="ba290-104">ID</span></span>|<span data-ttu-id="ba290-105">1031</span><span class="sxs-lookup"><span data-stu-id="ba290-105">1031</span></span>|  
|<span data-ttu-id="ba290-106">关键字</span><span class="sxs-lookup"><span data-stu-id="ba290-106">Keywords</span></span>|<span data-ttu-id="ba290-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ba290-107">WFRuntime</span></span>|  
|<span data-ttu-id="ba290-108">级别</span><span class="sxs-lookup"><span data-stu-id="ba290-108">Level</span></span>|<span data-ttu-id="ba290-109">详细</span><span class="sxs-lookup"><span data-stu-id="ba290-109">Verbose</span></span>|  
|<span data-ttu-id="ba290-110">通道</span><span class="sxs-lookup"><span data-stu-id="ba290-110">Channel</span></span>|<span data-ttu-id="ba290-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="ba290-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ba290-112">描述</span><span class="sxs-lookup"><span data-stu-id="ba290-112">Description</span></span>  
 <span data-ttu-id="ba290-113">指示 FaultWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="ba290-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ba290-114">消息</span><span class="sxs-lookup"><span data-stu-id="ba290-114">Message</span></span>  
 <span data-ttu-id="ba290-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的 FaultWorkItem 已经完成。</span><span class="sxs-lookup"><span data-stu-id="ba290-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="ba290-116">异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。</span><span class="sxs-lookup"><span data-stu-id="ba290-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ba290-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="ba290-117">Details</span></span>  
  
|<span data-ttu-id="ba290-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="ba290-118">Data Item Name</span></span>|<span data-ttu-id="ba290-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="ba290-119">Data Item Type</span></span>|<span data-ttu-id="ba290-120">描述</span><span class="sxs-lookup"><span data-stu-id="ba290-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ba290-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="ba290-121">FaultActivity</span></span>|<span data-ttu-id="ba290-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ba290-122">xs:string</span></span>|<span data-ttu-id="ba290-123">错误活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="ba290-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="ba290-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ba290-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="ba290-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ba290-125">xs:string</span></span>|<span data-ttu-id="ba290-126">错误活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ba290-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="ba290-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ba290-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="ba290-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ba290-128">xs:string</span></span>|<span data-ttu-id="ba290-129">错误活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="ba290-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="ba290-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="ba290-130">ExceptionActivity</span></span>|<span data-ttu-id="ba290-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="ba290-131">xs:string</span></span>|<span data-ttu-id="ba290-132">引发了异常的活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="ba290-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ba290-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ba290-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="ba290-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="ba290-134">xs:string</span></span>|<span data-ttu-id="ba290-135">引发了异常的活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ba290-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ba290-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ba290-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="ba290-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="ba290-137">xs:string</span></span>|<span data-ttu-id="ba290-138">引发了异常的活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="ba290-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ba290-139">例外</span><span class="sxs-lookup"><span data-stu-id="ba290-139">Exception</span></span>|<span data-ttu-id="ba290-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="ba290-140">xs:string</span></span>|<span data-ttu-id="ba290-141">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="ba290-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="ba290-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ba290-142">AppDomain</span></span>|<span data-ttu-id="ba290-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="ba290-143">xs:string</span></span>|<span data-ttu-id="ba290-144">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="ba290-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
