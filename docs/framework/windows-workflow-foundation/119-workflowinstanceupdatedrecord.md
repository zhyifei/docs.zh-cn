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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2b838f764b1f86b0477dc797620dca5f99bb13d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="119---workflowinstanceupdatedrecord"></a><span data-ttu-id="544f2-102">119 - WorkflowInstanceUpdatedRecord</span><span class="sxs-lookup"><span data-stu-id="544f2-102">119 - WorkflowInstanceUpdatedRecord</span></span>
## <a name="properties"></a><span data-ttu-id="544f2-103">属性</span><span class="sxs-lookup"><span data-stu-id="544f2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="544f2-104">ID</span><span class="sxs-lookup"><span data-stu-id="544f2-104">ID</span></span>|<span data-ttu-id="544f2-105">119</span><span class="sxs-lookup"><span data-stu-id="544f2-105">119</span></span>|  
|<span data-ttu-id="544f2-106">关键字</span><span class="sxs-lookup"><span data-stu-id="544f2-106">Keywords</span></span>|<span data-ttu-id="544f2-107">HealthMonitoring、WFTracking</span><span class="sxs-lookup"><span data-stu-id="544f2-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="544f2-108">级别</span><span class="sxs-lookup"><span data-stu-id="544f2-108">Level</span></span>|<span data-ttu-id="544f2-109">信息</span><span class="sxs-lookup"><span data-stu-id="544f2-109">Information</span></span>|  
|<span data-ttu-id="544f2-110">通道</span><span class="sxs-lookup"><span data-stu-id="544f2-110">Channel</span></span>|<span data-ttu-id="544f2-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="544f2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="544f2-112">描述</span><span class="sxs-lookup"><span data-stu-id="544f2-112">Description</span></span>  
 <span data-ttu-id="544f2-113">当更新工作流实例时，ETW 跟踪参与者将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="544f2-113">This event is emitted by the ETW tracking participant when a workflow instance is updated.</span></span>  
  
## <a name="message"></a><span data-ttu-id="544f2-114">消息</span><span class="sxs-lookup"><span data-stu-id="544f2-114">Message</span></span>  
 <span data-ttu-id="544f2-115">TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9</span><span class="sxs-lookup"><span data-stu-id="544f2-115">TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9</span></span>  
  
## <a name="details"></a><span data-ttu-id="544f2-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="544f2-116">Details</span></span>  
  
|<span data-ttu-id="544f2-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="544f2-117">Data Item Name</span></span>|<span data-ttu-id="544f2-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="544f2-118">Data Item Type</span></span>|<span data-ttu-id="544f2-119">描述</span><span class="sxs-lookup"><span data-stu-id="544f2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="544f2-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="544f2-120">InstanceId</span></span>|<span data-ttu-id="544f2-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="544f2-121">xs:GUID</span></span>|<span data-ttu-id="544f2-122">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="544f2-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="544f2-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="544f2-123">RecordNumber</span></span>|<span data-ttu-id="544f2-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="544f2-124">xs:long</span></span>|<span data-ttu-id="544f2-125">发出的记录的序列号</span><span class="sxs-lookup"><span data-stu-id="544f2-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="544f2-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="544f2-126">EventTime</span></span>|<span data-ttu-id="544f2-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="544f2-127">xs:dateTime</span></span>|<span data-ttu-id="544f2-128">发出该事件时的 UTC 时间</span><span class="sxs-lookup"><span data-stu-id="544f2-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="544f2-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="544f2-129">ActivityDefinitionId</span></span>|<span data-ttu-id="544f2-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="544f2-130">xs:string</span></span>|<span data-ttu-id="544f2-131">工作流中根活动的名称</span><span class="sxs-lookup"><span data-stu-id="544f2-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="544f2-132">状态</span><span class="sxs-lookup"><span data-stu-id="544f2-132">State</span></span>|<span data-ttu-id="544f2-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="544f2-133">xs:string</span></span>|<span data-ttu-id="544f2-134">工作流的当前状态。</span><span class="sxs-lookup"><span data-stu-id="544f2-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="544f2-135">OriginalDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="544f2-135">OriginalDefinitionIdentity</span></span>|<span data-ttu-id="544f2-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="544f2-136">xs:string</span></span>|<span data-ttu-id="544f2-137">原始工作流定义 ID</span><span class="sxs-lookup"><span data-stu-id="544f2-137">The original workflow definition id</span></span>|  
|<span data-ttu-id="544f2-138">UpdatedDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="544f2-138">UpdatedDefinitionIdentity</span></span>|<span data-ttu-id="544f2-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="544f2-139">xs:string</span></span>|<span data-ttu-id="544f2-140">已更新的工作流定义 ID</span><span class="sxs-lookup"><span data-stu-id="544f2-140">The updated workflow definition id</span></span>|  
|<span data-ttu-id="544f2-141">批注</span><span class="sxs-lookup"><span data-stu-id="544f2-141">Annotations</span></span>|<span data-ttu-id="544f2-142">xs:string</span><span class="sxs-lookup"><span data-stu-id="544f2-142">xs:string</span></span>|<span data-ttu-id="544f2-143">已添加到此事件中的批注。</span><span class="sxs-lookup"><span data-stu-id="544f2-143">The annotations that were added to this event.</span></span> <span data-ttu-id="544f2-144">这些值存储在一个 xml 元素中格式\<项 >\<项名称 ="annotationName"type ="> annotationValue\</项 > \< /i >。</span><span class="sxs-lookup"><span data-stu-id="544f2-144">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="544f2-145">如果不指定任何批注，则该字符串包含\<项 / >。</span><span class="sxs-lookup"><span data-stu-id="544f2-145">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="544f2-146">ETW 事件大小受到 ETW 缓冲区大小或 ETW 事件最大负载的限制。</span><span class="sxs-lookup"><span data-stu-id="544f2-146">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="544f2-147">如果事件大小超出 ETW 限制，则通过丢弃批注并将批注值与截断事件\<项 >... \< /i >。</span><span class="sxs-lookup"><span data-stu-id="544f2-147">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="544f2-148">ProfileName</span><span class="sxs-lookup"><span data-stu-id="544f2-148">ProfileName</span></span>|<span data-ttu-id="544f2-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="544f2-149">xs:string</span></span>|<span data-ttu-id="544f2-150">导致发出此事件的跟踪配置文件的名称</span><span class="sxs-lookup"><span data-stu-id="544f2-150">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="544f2-151">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="544f2-151">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="544f2-152">xs:string</span><span class="sxs-lookup"><span data-stu-id="544f2-152">xs:string</span></span>|<span data-ttu-id="544f2-153">工作流定义 ID</span><span class="sxs-lookup"><span data-stu-id="544f2-153">The workflow definition id</span></span>|  
|<span data-ttu-id="544f2-154">AppDomain</span><span class="sxs-lookup"><span data-stu-id="544f2-154">AppDomain</span></span>|<span data-ttu-id="544f2-155">xs:string</span><span class="sxs-lookup"><span data-stu-id="544f2-155">xs:string</span></span>|<span data-ttu-id="544f2-156">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="544f2-156">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
