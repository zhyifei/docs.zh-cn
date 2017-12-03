---
title: 100 - WorkflowInstanceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed4d1851-b378-489b-a22d-c1db09571fb4
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e60b972c015bd7f3ec304c83e03812e2460b8ca3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="100---workflowinstancerecord"></a><span data-ttu-id="0ecc8-102">100 - WorkflowInstanceRecord</span><span class="sxs-lookup"><span data-stu-id="0ecc8-102">100 - WorkflowInstanceRecord</span></span>
## <a name="properties"></a><span data-ttu-id="0ecc8-103">属性</span><span class="sxs-lookup"><span data-stu-id="0ecc8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ecc8-104">Id</span><span class="sxs-lookup"><span data-stu-id="0ecc8-104">Id</span></span>|<span data-ttu-id="0ecc8-105">100</span><span class="sxs-lookup"><span data-stu-id="0ecc8-105">100</span></span>|  
|<span data-ttu-id="0ecc8-106">关键字</span><span class="sxs-lookup"><span data-stu-id="0ecc8-106">Keywords</span></span>|<span data-ttu-id="0ecc8-107">EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking</span><span class="sxs-lookup"><span data-stu-id="0ecc8-107">EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="0ecc8-108">级别</span><span class="sxs-lookup"><span data-stu-id="0ecc8-108">Level</span></span>|<span data-ttu-id="0ecc8-109">信息</span><span class="sxs-lookup"><span data-stu-id="0ecc8-109">Information</span></span>|  
|<span data-ttu-id="0ecc8-110">通道</span><span class="sxs-lookup"><span data-stu-id="0ecc8-110">Channel</span></span>|<span data-ttu-id="0ecc8-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="0ecc8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0ecc8-112">描述</span><span class="sxs-lookup"><span data-stu-id="0ecc8-112">Description</span></span>  
 <span data-ttu-id="0ecc8-113">工作流实例发出以下工作流状态的 WorkflowInstanceRecord 时，ETW 跟踪参与者将发出此事件：已启动、已继续、已持久保存、空闲、已删除、已完成、已取消、已卸载和已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceRecord for workflow states : Started, Resumed, Persisted, Idle, Deleted, Completed, Canceled, Unloaded, Unsuspended.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0ecc8-114">消息</span><span class="sxs-lookup"><span data-stu-id="0ecc8-114">Message</span></span>  
 <span data-ttu-id="0ecc8-115">TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7</span><span class="sxs-lookup"><span data-stu-id="0ecc8-115">TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7</span></span>  
  
## <a name="details"></a><span data-ttu-id="0ecc8-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="0ecc8-116">Details</span></span>  
  
|<span data-ttu-id="0ecc8-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="0ecc8-117">Data Item Name</span></span>|<span data-ttu-id="0ecc8-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="0ecc8-118">Data Item Type</span></span>|<span data-ttu-id="0ecc8-119">描述</span><span class="sxs-lookup"><span data-stu-id="0ecc8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0ecc8-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0ecc8-120">InstanceId</span></span>|<span data-ttu-id="0ecc8-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="0ecc8-121">xs:GUID</span></span>|<span data-ttu-id="0ecc8-122">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="0ecc8-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="0ecc8-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="0ecc8-123">RecordNumber</span></span>|<span data-ttu-id="0ecc8-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="0ecc8-124">xs:long</span></span>|<span data-ttu-id="0ecc8-125">发出的记录的序列号</span><span class="sxs-lookup"><span data-stu-id="0ecc8-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="0ecc8-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="0ecc8-126">EventTime</span></span>|<span data-ttu-id="0ecc8-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="0ecc8-127">xs:dateTime</span></span>|<span data-ttu-id="0ecc8-128">发出该事件时的 UTC 时间</span><span class="sxs-lookup"><span data-stu-id="0ecc8-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="0ecc8-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="0ecc8-129">ActivityDefinitionId</span></span>|<span data-ttu-id="0ecc8-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ecc8-130">xs:string</span></span>|<span data-ttu-id="0ecc8-131">工作流中根活动的名称</span><span class="sxs-lookup"><span data-stu-id="0ecc8-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="0ecc8-132">状态</span><span class="sxs-lookup"><span data-stu-id="0ecc8-132">State</span></span>|<span data-ttu-id="0ecc8-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ecc8-133">xs:string</span></span>|<span data-ttu-id="0ecc8-134">工作流的当前状态。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="0ecc8-135">批注</span><span class="sxs-lookup"><span data-stu-id="0ecc8-135">Annotations</span></span>|<span data-ttu-id="0ecc8-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ecc8-136">xs:string</span></span>|<span data-ttu-id="0ecc8-137">已添加到此事件中的批注。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-137">The annotations that were added to this event.</span></span>  <span data-ttu-id="0ecc8-138">这些值存储在一个 xml 元素中格式\<项 >\<项名称 ="annotationName"type ="> annotationValue\</项 > \< /i >。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-138">The values are stored in an xml element in the format \<items>\< item  name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span>  <span data-ttu-id="0ecc8-139">如果不指定任何批注，则该字符串包含\<项 / >。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="0ecc8-140">ETW 事件大小受到 ETW 缓冲区大小或 ETW 事件最大负载的限制。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="0ecc8-141">如果事件大小超出 ETW 限制，则通过丢弃批注并将批注值与截断事件\<项 >... \< /i >。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="0ecc8-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="0ecc8-142">ProfileName</span></span>|<span data-ttu-id="0ecc8-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ecc8-143">xs:string</span></span>|<span data-ttu-id="0ecc8-144">导致发出此事件的跟踪配置文件的名称</span><span class="sxs-lookup"><span data-stu-id="0ecc8-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="0ecc8-145">HostReference</span><span class="sxs-lookup"><span data-stu-id="0ecc8-145">HostReference</span></span>|<span data-ttu-id="0ecc8-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ecc8-146">xs:string</span></span>|<span data-ttu-id="0ecc8-147">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-147">For web hosted services, this field uniquely identifies the service in the web hierarchy.</span></span>  <span data-ttu-id="0ecc8-148">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName 示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService</span><span class="sxs-lookup"><span data-stu-id="0ecc8-148">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName' Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'</span></span>|  
|<span data-ttu-id="0ecc8-149">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0ecc8-149">AppDomain</span></span>|<span data-ttu-id="0ecc8-150">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ecc8-150">xs:string</span></span>|<span data-ttu-id="0ecc8-151">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="0ecc8-151">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
