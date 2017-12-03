---
title: 116 - WorkflowInstanceSuspendedRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 38232c03-6139-4494-a020-79bc83eb9dce
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 59b77e2fac36dea3afce77a74e0ccacb432a2ada
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="116---workflowinstancesuspendedrecordwithid"></a><span data-ttu-id="e1dcf-102">116 - WorkflowInstanceSuspendedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="e1dcf-102">116 - WorkflowInstanceSuspendedRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="e1dcf-103">属性</span><span class="sxs-lookup"><span data-stu-id="e1dcf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1dcf-104">ID</span><span class="sxs-lookup"><span data-stu-id="e1dcf-104">ID</span></span>|<span data-ttu-id="e1dcf-105">116</span><span class="sxs-lookup"><span data-stu-id="e1dcf-105">116</span></span>|  
|<span data-ttu-id="e1dcf-106">关键字</span><span class="sxs-lookup"><span data-stu-id="e1dcf-106">Keywords</span></span>|<span data-ttu-id="e1dcf-107">HealthMonitoring、WFTracking</span><span class="sxs-lookup"><span data-stu-id="e1dcf-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="e1dcf-108">级别</span><span class="sxs-lookup"><span data-stu-id="e1dcf-108">Level</span></span>|<span data-ttu-id="e1dcf-109">信息</span><span class="sxs-lookup"><span data-stu-id="e1dcf-109">Information</span></span>|  
|<span data-ttu-id="e1dcf-110">通道</span><span class="sxs-lookup"><span data-stu-id="e1dcf-110">Channel</span></span>|<span data-ttu-id="e1dcf-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="e1dcf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e1dcf-112">描述</span><span class="sxs-lookup"><span data-stu-id="e1dcf-112">Description</span></span>  
 <span data-ttu-id="e1dcf-113">当工作流实例发出 WorkflowInstanceSuspended Record 时，ETW 跟踪参与者将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="e1dcf-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceSuspended Record.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e1dcf-114">消息</span><span class="sxs-lookup"><span data-stu-id="e1dcf-114">Message</span></span>  
 <span data-ttu-id="e1dcf-115">TrackRecord = WorkflowInstanceSuspendedRecord，InstanceID = %1，RecordNumber = %2，EventTime = %3，ActivityDefinitionId = %4，Reason = %5，Annotations = %6，ProfileName = %7，WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="e1dcf-115">TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="e1dcf-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="e1dcf-116">Details</span></span>  
  
|<span data-ttu-id="e1dcf-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="e1dcf-117">Data Item Name</span></span>|<span data-ttu-id="e1dcf-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="e1dcf-118">Data Item Type</span></span>|<span data-ttu-id="e1dcf-119">描述</span><span class="sxs-lookup"><span data-stu-id="e1dcf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e1dcf-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e1dcf-120">InstanceId</span></span>|<span data-ttu-id="e1dcf-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="e1dcf-121">xs:GUID</span></span>|<span data-ttu-id="e1dcf-122">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="e1dcf-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="e1dcf-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="e1dcf-123">RecordNumber</span></span>|<span data-ttu-id="e1dcf-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="e1dcf-124">xs:long</span></span>|<span data-ttu-id="e1dcf-125">发出的记录的序列号</span><span class="sxs-lookup"><span data-stu-id="e1dcf-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="e1dcf-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="e1dcf-126">EventTime</span></span>|<span data-ttu-id="e1dcf-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="e1dcf-127">xs:dateTime</span></span>|<span data-ttu-id="e1dcf-128">发出该事件时的 UTC 时间</span><span class="sxs-lookup"><span data-stu-id="e1dcf-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="e1dcf-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="e1dcf-129">ActivityDefinitionId</span></span>|<span data-ttu-id="e1dcf-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1dcf-130">xs:string</span></span>|<span data-ttu-id="e1dcf-131">工作流中根活动的名称</span><span class="sxs-lookup"><span data-stu-id="e1dcf-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="e1dcf-132">状态</span><span class="sxs-lookup"><span data-stu-id="e1dcf-132">State</span></span>|<span data-ttu-id="e1dcf-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1dcf-133">xs:string</span></span>|<span data-ttu-id="e1dcf-134">工作流的当前状态。</span><span class="sxs-lookup"><span data-stu-id="e1dcf-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="e1dcf-135">批注</span><span class="sxs-lookup"><span data-stu-id="e1dcf-135">Annotations</span></span>|<span data-ttu-id="e1dcf-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1dcf-136">xs:string</span></span>|<span data-ttu-id="e1dcf-137">已添加到此事件中的批注。</span><span class="sxs-lookup"><span data-stu-id="e1dcf-137">The annotations that were added to this event.</span></span> <span data-ttu-id="e1dcf-138">这些值存储在一个 xml 元素中格式\<项 >\<项名称 ="annotationName"type ="> annotationValue\</项 > \< /i >。</span><span class="sxs-lookup"><span data-stu-id="e1dcf-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="e1dcf-139">如果不指定任何批注，则该字符串包含\<项 / >。</span><span class="sxs-lookup"><span data-stu-id="e1dcf-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="e1dcf-140">ETW 事件大小受到 ETW 缓冲区大小或 ETW 事件最大负载的限制。</span><span class="sxs-lookup"><span data-stu-id="e1dcf-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="e1dcf-141">如果事件大小超出 ETW 限制，则通过丢弃批注并将批注值与截断事件\<项 >... \< /i >。</span><span class="sxs-lookup"><span data-stu-id="e1dcf-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="e1dcf-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="e1dcf-142">ProfileName</span></span>|<span data-ttu-id="e1dcf-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1dcf-143">xs:string</span></span>|<span data-ttu-id="e1dcf-144">导致发出此事件的跟踪配置文件的名称</span><span class="sxs-lookup"><span data-stu-id="e1dcf-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="e1dcf-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="e1dcf-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="e1dcf-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1dcf-146">xs:string</span></span>|<span data-ttu-id="e1dcf-147">工作流定义 ID</span><span class="sxs-lookup"><span data-stu-id="e1dcf-147">The workflow definition id</span></span>|  
|<span data-ttu-id="e1dcf-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e1dcf-148">AppDomain</span></span>|<span data-ttu-id="e1dcf-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1dcf-149">xs:string</span></span>|<span data-ttu-id="e1dcf-150">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="e1dcf-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
