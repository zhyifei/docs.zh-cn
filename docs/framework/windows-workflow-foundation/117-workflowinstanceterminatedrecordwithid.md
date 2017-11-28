---
title: 117 - WorkflowInstanceTerminatedRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e68539d0-5338-468a-9f75-7e5b09d39a3c
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c8b2bc6325ec6f5cf1c3af8b7748a45ad21809cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="117---workflowinstanceterminatedrecordwithid"></a><span data-ttu-id="f66f5-102">117 - WorkflowInstanceTerminatedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="f66f5-102">117 - WorkflowInstanceTerminatedRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="f66f5-103">属性</span><span class="sxs-lookup"><span data-stu-id="f66f5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f66f5-104">ID</span><span class="sxs-lookup"><span data-stu-id="f66f5-104">ID</span></span>|<span data-ttu-id="f66f5-105">117</span><span class="sxs-lookup"><span data-stu-id="f66f5-105">117</span></span>|  
|<span data-ttu-id="f66f5-106">关键字</span><span class="sxs-lookup"><span data-stu-id="f66f5-106">Keywords</span></span>|<span data-ttu-id="f66f5-107">HealthMonitoring、WFTracking</span><span class="sxs-lookup"><span data-stu-id="f66f5-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="f66f5-108">级别</span><span class="sxs-lookup"><span data-stu-id="f66f5-108">Level</span></span>|<span data-ttu-id="f66f5-109">错误</span><span class="sxs-lookup"><span data-stu-id="f66f5-109">Error</span></span>|  
|<span data-ttu-id="f66f5-110">通道</span><span class="sxs-lookup"><span data-stu-id="f66f5-110">Channel</span></span>|<span data-ttu-id="f66f5-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="f66f5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f66f5-112">描述</span><span class="sxs-lookup"><span data-stu-id="f66f5-112">Description</span></span>  
 <span data-ttu-id="f66f5-113">当工作流实例发出 WorkflowInstanceTerminatedRecord 时，ETW 跟踪参与者将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="f66f5-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceTerminatedRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f66f5-114">消息</span><span class="sxs-lookup"><span data-stu-id="f66f5-114">Message</span></span>  
 <span data-ttu-id="f66f5-115">TrackRecord = WorkflowInstanceTerminatedRecord，InstanceID = %1，RecordNumber = %2，EventTime = %3，ActivityDefinitionId = %4，Reason = %5，Annotations = %6，ProfileName = %7，WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="f66f5-115">TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="f66f5-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="f66f5-116">Details</span></span>  
  
|<span data-ttu-id="f66f5-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="f66f5-117">Data Item Name</span></span>|<span data-ttu-id="f66f5-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="f66f5-118">Data Item Type</span></span>|<span data-ttu-id="f66f5-119">描述</span><span class="sxs-lookup"><span data-stu-id="f66f5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f66f5-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f66f5-120">InstanceId</span></span>|<span data-ttu-id="f66f5-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="f66f5-121">xs:GUID</span></span>|<span data-ttu-id="f66f5-122">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="f66f5-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="f66f5-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="f66f5-123">RecordNumber</span></span>|<span data-ttu-id="f66f5-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="f66f5-124">xs:long</span></span>|<span data-ttu-id="f66f5-125">发出的记录的序列号</span><span class="sxs-lookup"><span data-stu-id="f66f5-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="f66f5-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="f66f5-126">EventTime</span></span>|<span data-ttu-id="f66f5-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="f66f5-127">xs:dateTime</span></span>|<span data-ttu-id="f66f5-128">发出该事件时的 UTC 时间</span><span class="sxs-lookup"><span data-stu-id="f66f5-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="f66f5-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="f66f5-129">ActivityDefinitionId</span></span>|<span data-ttu-id="f66f5-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f66f5-130">xs:string</span></span>|<span data-ttu-id="f66f5-131">工作流中根活动的名称</span><span class="sxs-lookup"><span data-stu-id="f66f5-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="f66f5-132">状态</span><span class="sxs-lookup"><span data-stu-id="f66f5-132">State</span></span>|<span data-ttu-id="f66f5-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="f66f5-133">xs:string</span></span>|<span data-ttu-id="f66f5-134">工作流的当前状态。</span><span class="sxs-lookup"><span data-stu-id="f66f5-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="f66f5-135">批注</span><span class="sxs-lookup"><span data-stu-id="f66f5-135">Annotations</span></span>|<span data-ttu-id="f66f5-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="f66f5-136">xs:string</span></span>|<span data-ttu-id="f66f5-137">已添加到此事件中的批注。</span><span class="sxs-lookup"><span data-stu-id="f66f5-137">The annotations that were added to this event.</span></span> <span data-ttu-id="f66f5-138">这些值存储在一个 xml 元素中格式\<项 >\<项名称 ="annotationName"type ="> annotationValue\</项 > \< /i >。</span><span class="sxs-lookup"><span data-stu-id="f66f5-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="f66f5-139">如果不指定任何批注，则该字符串包含\<项 / >。</span><span class="sxs-lookup"><span data-stu-id="f66f5-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="f66f5-140">ETW 事件大小受到 ETW 缓冲区大小或 ETW 事件最大负载的限制。</span><span class="sxs-lookup"><span data-stu-id="f66f5-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="f66f5-141">如果事件大小超出 ETW 限制，则通过丢弃批注并将批注值与截断事件\<项 >... \< /i >。</span><span class="sxs-lookup"><span data-stu-id="f66f5-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="f66f5-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="f66f5-142">ProfileName</span></span>|<span data-ttu-id="f66f5-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="f66f5-143">xs:string</span></span>|<span data-ttu-id="f66f5-144">导致发出此事件的跟踪配置文件的名称</span><span class="sxs-lookup"><span data-stu-id="f66f5-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="f66f5-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="f66f5-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="f66f5-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="f66f5-146">xs:string</span></span>|<span data-ttu-id="f66f5-147">工作流定义 ID</span><span class="sxs-lookup"><span data-stu-id="f66f5-147">The workflow definition id</span></span>|  
|<span data-ttu-id="f66f5-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f66f5-148">AppDomain</span></span>|<span data-ttu-id="f66f5-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="f66f5-149">xs:string</span></span>|<span data-ttu-id="f66f5-150">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="f66f5-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
