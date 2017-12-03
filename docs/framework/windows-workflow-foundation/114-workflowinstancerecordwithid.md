---
title: 114 - WorkflowInstanceRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bd8b4a1-b210-4c07-8156-f19392318c08
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c7f6324d6d563ca19b16a76cff809649ad90e3dd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="114---workflowinstancerecordwithid"></a><span data-ttu-id="3018d-102">114 - WorkflowInstanceRecordWithId</span><span class="sxs-lookup"><span data-stu-id="3018d-102">114 - WorkflowInstanceRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="3018d-103">属性</span><span class="sxs-lookup"><span data-stu-id="3018d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3018d-104">ID</span><span class="sxs-lookup"><span data-stu-id="3018d-104">ID</span></span>|<span data-ttu-id="3018d-105">114</span><span class="sxs-lookup"><span data-stu-id="3018d-105">114</span></span>|  
|<span data-ttu-id="3018d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="3018d-106">Keywords</span></span>|<span data-ttu-id="3018d-107">HealthMonitoring、WFTracking</span><span class="sxs-lookup"><span data-stu-id="3018d-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="3018d-108">级别</span><span class="sxs-lookup"><span data-stu-id="3018d-108">Level</span></span>|<span data-ttu-id="3018d-109">信息</span><span class="sxs-lookup"><span data-stu-id="3018d-109">Information</span></span>|  
|<span data-ttu-id="3018d-110">通道</span><span class="sxs-lookup"><span data-stu-id="3018d-110">Channel</span></span>|<span data-ttu-id="3018d-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="3018d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3018d-112">描述</span><span class="sxs-lookup"><span data-stu-id="3018d-112">Description</span></span>  
 <span data-ttu-id="3018d-113">工作流实例发出以下工作流状态的 WorkflowInstanceRecord 时，ETW 跟踪参与者将发出此事件：已启动、已继续、已持久保存、空闲、已删除、已完成、已取消、已卸载和已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="3018d-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceRecord for workflow states : Started, Resumed, Persisted, Idle, Deleted, Completed, Canceled, Unloaded, Unsuspended.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3018d-114">消息</span><span class="sxs-lookup"><span data-stu-id="3018d-114">Message</span></span>  
 <span data-ttu-id="3018d-115">TrackRecord= WorkflowInstanceRecord，InstanceID = %1，RecordNumber = %2，EventTime = %3，ActivityDefinitionId = %4，State = %5，Annotations = %6， ProfileName = %7，WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="3018d-115">TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="3018d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="3018d-116">Details</span></span>  
  
|<span data-ttu-id="3018d-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="3018d-117">Data Item Name</span></span>|<span data-ttu-id="3018d-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="3018d-118">Data Item Type</span></span>|<span data-ttu-id="3018d-119">描述</span><span class="sxs-lookup"><span data-stu-id="3018d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3018d-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3018d-120">InstanceId</span></span>|<span data-ttu-id="3018d-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="3018d-121">xs:GUID</span></span>|<span data-ttu-id="3018d-122">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="3018d-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="3018d-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="3018d-123">RecordNumber</span></span>|<span data-ttu-id="3018d-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="3018d-124">xs:long</span></span>|<span data-ttu-id="3018d-125">发出的记录的序列号</span><span class="sxs-lookup"><span data-stu-id="3018d-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="3018d-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="3018d-126">EventTime</span></span>|<span data-ttu-id="3018d-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="3018d-127">xs:dateTime</span></span>|<span data-ttu-id="3018d-128">发出该事件时的 UTC 时间</span><span class="sxs-lookup"><span data-stu-id="3018d-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="3018d-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="3018d-129">ActivityDefinitionId</span></span>|<span data-ttu-id="3018d-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3018d-130">xs:string</span></span>|<span data-ttu-id="3018d-131">工作流中根活动的名称</span><span class="sxs-lookup"><span data-stu-id="3018d-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="3018d-132">状态</span><span class="sxs-lookup"><span data-stu-id="3018d-132">State</span></span>|<span data-ttu-id="3018d-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="3018d-133">xs:string</span></span>|<span data-ttu-id="3018d-134">工作流的当前状态。</span><span class="sxs-lookup"><span data-stu-id="3018d-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="3018d-135">批注</span><span class="sxs-lookup"><span data-stu-id="3018d-135">Annotations</span></span>|<span data-ttu-id="3018d-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="3018d-136">xs:string</span></span>|<span data-ttu-id="3018d-137">已添加到此事件中的批注。</span><span class="sxs-lookup"><span data-stu-id="3018d-137">The annotations that were added to this event.</span></span> <span data-ttu-id="3018d-138">这些值存储在一个 xml 元素中格式\<项 >\<项名称 ="annotationName"type ="> annotationValue\</项 > \< /i >。</span><span class="sxs-lookup"><span data-stu-id="3018d-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="3018d-139">如果不指定任何批注，则该字符串包含\<项 / >。</span><span class="sxs-lookup"><span data-stu-id="3018d-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="3018d-140">ETW 事件大小受到 ETW 缓冲区大小或 ETW 事件最大负载的限制。</span><span class="sxs-lookup"><span data-stu-id="3018d-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="3018d-141">如果事件大小超出 ETW 限制，则通过丢弃批注并将批注值与截断事件\<项 >... \< /i >。</span><span class="sxs-lookup"><span data-stu-id="3018d-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="3018d-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="3018d-142">ProfileName</span></span>|<span data-ttu-id="3018d-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="3018d-143">xs:string</span></span>|<span data-ttu-id="3018d-144">导致发出此事件的跟踪配置文件的名称</span><span class="sxs-lookup"><span data-stu-id="3018d-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="3018d-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="3018d-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="3018d-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="3018d-146">xs:string</span></span>|<span data-ttu-id="3018d-147">工作流定义 ID</span><span class="sxs-lookup"><span data-stu-id="3018d-147">The workflow definition id</span></span>|  
|<span data-ttu-id="3018d-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3018d-148">AppDomain</span></span>|<span data-ttu-id="3018d-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="3018d-149">xs:string</span></span>|<span data-ttu-id="3018d-150">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="3018d-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
