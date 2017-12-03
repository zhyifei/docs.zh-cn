---
title: 119 - WorkflowInstanceUpdatedRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 32485d0a-dcdb-45bc-b1e3-79fa9ad9439b
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f58a7c0e3b3122962e79f7f39f0c0f89f374bd10
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="119---workflowinstanceupdatedrecord"></a><span data-ttu-id="78286-102">119 - WorkflowInstanceUpdatedRecord</span><span class="sxs-lookup"><span data-stu-id="78286-102">119 - WorkflowInstanceUpdatedRecord</span></span>
## <a name="properties"></a><span data-ttu-id="78286-103">属性</span><span class="sxs-lookup"><span data-stu-id="78286-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78286-104">ID</span><span class="sxs-lookup"><span data-stu-id="78286-104">ID</span></span>|<span data-ttu-id="78286-105">119</span><span class="sxs-lookup"><span data-stu-id="78286-105">119</span></span>|  
|<span data-ttu-id="78286-106">关键字</span><span class="sxs-lookup"><span data-stu-id="78286-106">Keywords</span></span>|<span data-ttu-id="78286-107">HealthMonitoring、WFTracking</span><span class="sxs-lookup"><span data-stu-id="78286-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="78286-108">级别</span><span class="sxs-lookup"><span data-stu-id="78286-108">Level</span></span>|<span data-ttu-id="78286-109">信息</span><span class="sxs-lookup"><span data-stu-id="78286-109">Information</span></span>|  
|<span data-ttu-id="78286-110">通道</span><span class="sxs-lookup"><span data-stu-id="78286-110">Channel</span></span>|<span data-ttu-id="78286-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="78286-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="78286-112">描述</span><span class="sxs-lookup"><span data-stu-id="78286-112">Description</span></span>  
 <span data-ttu-id="78286-113">当更新工作流实例时，ETW 跟踪参与者将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="78286-113">This event is emitted by the ETW tracking participant when a workflow instance is updated.</span></span>  
  
## <a name="message"></a><span data-ttu-id="78286-114">消息</span><span class="sxs-lookup"><span data-stu-id="78286-114">Message</span></span>  
 <span data-ttu-id="78286-115">TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9</span><span class="sxs-lookup"><span data-stu-id="78286-115">TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9</span></span>  
  
## <a name="details"></a><span data-ttu-id="78286-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="78286-116">Details</span></span>  
  
|<span data-ttu-id="78286-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="78286-117">Data Item Name</span></span>|<span data-ttu-id="78286-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="78286-118">Data Item Type</span></span>|<span data-ttu-id="78286-119">描述</span><span class="sxs-lookup"><span data-stu-id="78286-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="78286-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="78286-120">InstanceId</span></span>|<span data-ttu-id="78286-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="78286-121">xs:GUID</span></span>|<span data-ttu-id="78286-122">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="78286-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="78286-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="78286-123">RecordNumber</span></span>|<span data-ttu-id="78286-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="78286-124">xs:long</span></span>|<span data-ttu-id="78286-125">发出的记录的序列号</span><span class="sxs-lookup"><span data-stu-id="78286-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="78286-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="78286-126">EventTime</span></span>|<span data-ttu-id="78286-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="78286-127">xs:dateTime</span></span>|<span data-ttu-id="78286-128">发出该事件时的 UTC 时间</span><span class="sxs-lookup"><span data-stu-id="78286-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="78286-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="78286-129">ActivityDefinitionId</span></span>|<span data-ttu-id="78286-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="78286-130">xs:string</span></span>|<span data-ttu-id="78286-131">工作流中根活动的名称</span><span class="sxs-lookup"><span data-stu-id="78286-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="78286-132">状态</span><span class="sxs-lookup"><span data-stu-id="78286-132">State</span></span>|<span data-ttu-id="78286-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="78286-133">xs:string</span></span>|<span data-ttu-id="78286-134">工作流的当前状态。</span><span class="sxs-lookup"><span data-stu-id="78286-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="78286-135">OriginalDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="78286-135">OriginalDefinitionIdentity</span></span>|<span data-ttu-id="78286-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="78286-136">xs:string</span></span>|<span data-ttu-id="78286-137">原始工作流定义 ID</span><span class="sxs-lookup"><span data-stu-id="78286-137">The original workflow definition id</span></span>|  
|<span data-ttu-id="78286-138">UpdatedDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="78286-138">UpdatedDefinitionIdentity</span></span>|<span data-ttu-id="78286-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="78286-139">xs:string</span></span>|<span data-ttu-id="78286-140">已更新的工作流定义 ID</span><span class="sxs-lookup"><span data-stu-id="78286-140">The updated workflow definition id</span></span>|  
|<span data-ttu-id="78286-141">批注</span><span class="sxs-lookup"><span data-stu-id="78286-141">Annotations</span></span>|<span data-ttu-id="78286-142">xs:string</span><span class="sxs-lookup"><span data-stu-id="78286-142">xs:string</span></span>|<span data-ttu-id="78286-143">已添加到此事件中的批注。</span><span class="sxs-lookup"><span data-stu-id="78286-143">The annotations that were added to this event.</span></span> <span data-ttu-id="78286-144">这些值存储在一个 xml 元素中格式\<项 >\<项名称 ="annotationName"type ="> annotationValue\</项 > \< /i >。</span><span class="sxs-lookup"><span data-stu-id="78286-144">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="78286-145">如果不指定任何批注，则该字符串包含\<项 / >。</span><span class="sxs-lookup"><span data-stu-id="78286-145">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="78286-146">ETW 事件大小受到 ETW 缓冲区大小或 ETW 事件最大负载的限制。</span><span class="sxs-lookup"><span data-stu-id="78286-146">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="78286-147">如果事件大小超出 ETW 限制，则通过丢弃批注并将批注值与截断事件\<项 >... \< /i >。</span><span class="sxs-lookup"><span data-stu-id="78286-147">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="78286-148">ProfileName</span><span class="sxs-lookup"><span data-stu-id="78286-148">ProfileName</span></span>|<span data-ttu-id="78286-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="78286-149">xs:string</span></span>|<span data-ttu-id="78286-150">导致发出此事件的跟踪配置文件的名称</span><span class="sxs-lookup"><span data-stu-id="78286-150">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="78286-151">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="78286-151">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="78286-152">xs:string</span><span class="sxs-lookup"><span data-stu-id="78286-152">xs:string</span></span>|<span data-ttu-id="78286-153">工作流定义 ID</span><span class="sxs-lookup"><span data-stu-id="78286-153">The workflow definition id</span></span>|  
|<span data-ttu-id="78286-154">AppDomain</span><span class="sxs-lookup"><span data-stu-id="78286-154">AppDomain</span></span>|<span data-ttu-id="78286-155">xs:string</span><span class="sxs-lookup"><span data-stu-id="78286-155">xs:string</span></span>|<span data-ttu-id="78286-156">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="78286-156">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
