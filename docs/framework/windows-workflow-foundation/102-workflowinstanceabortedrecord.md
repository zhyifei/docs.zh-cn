---
title: 102 - WorkflowInstanceAbortedRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bde4378d-4eea-4907-aaf2-c1a2bc770a37
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f47d94f41880e3463df883f94c2ff43e927a1001
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="102---workflowinstanceabortedrecord"></a><span data-ttu-id="fc387-102">102 - WorkflowInstanceAbortedRecord</span><span class="sxs-lookup"><span data-stu-id="fc387-102">102 - WorkflowInstanceAbortedRecord</span></span>
## <a name="properties"></a><span data-ttu-id="fc387-103">属性</span><span class="sxs-lookup"><span data-stu-id="fc387-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fc387-104">Id</span><span class="sxs-lookup"><span data-stu-id="fc387-104">Id</span></span>|<span data-ttu-id="fc387-105">102</span><span class="sxs-lookup"><span data-stu-id="fc387-105">102</span></span>|  
|<span data-ttu-id="fc387-106">关键字</span><span class="sxs-lookup"><span data-stu-id="fc387-106">Keywords</span></span>|<span data-ttu-id="fc387-107">EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking</span><span class="sxs-lookup"><span data-stu-id="fc387-107">EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="fc387-108">级别</span><span class="sxs-lookup"><span data-stu-id="fc387-108">Level</span></span>|<span data-ttu-id="fc387-109">警告</span><span class="sxs-lookup"><span data-stu-id="fc387-109">Warning</span></span>|  
|<span data-ttu-id="fc387-110">通道</span><span class="sxs-lookup"><span data-stu-id="fc387-110">Channel</span></span>|<span data-ttu-id="fc387-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="fc387-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fc387-112">描述</span><span class="sxs-lookup"><span data-stu-id="fc387-112">Description</span></span>  
 <span data-ttu-id="fc387-113">当工作流实例发出 WorkflowInstanceAbortedRecord 时，ETW 跟踪参与者将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="fc387-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceAbortedRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fc387-114">消息</span><span class="sxs-lookup"><span data-stu-id="fc387-114">Message</span></span>  
 <span data-ttu-id="fc387-115">TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7</span><span class="sxs-lookup"><span data-stu-id="fc387-115">TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7</span></span>  
  
## <a name="details"></a><span data-ttu-id="fc387-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="fc387-116">Details</span></span>  
  
|<span data-ttu-id="fc387-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="fc387-117">Data Item Name</span></span>|<span data-ttu-id="fc387-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="fc387-118">Data Item Type</span></span>|<span data-ttu-id="fc387-119">描述</span><span class="sxs-lookup"><span data-stu-id="fc387-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fc387-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="fc387-120">InstanceId</span></span>|<span data-ttu-id="fc387-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="fc387-121">xs:GUID</span></span>|<span data-ttu-id="fc387-122">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="fc387-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="fc387-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="fc387-123">RecordNumber</span></span>|<span data-ttu-id="fc387-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="fc387-124">xs:long</span></span>|<span data-ttu-id="fc387-125">发出的记录的序列号</span><span class="sxs-lookup"><span data-stu-id="fc387-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="fc387-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="fc387-126">EventTime</span></span>|<span data-ttu-id="fc387-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="fc387-127">xs:dateTime</span></span>|<span data-ttu-id="fc387-128">发出该事件时的 UTC 时间</span><span class="sxs-lookup"><span data-stu-id="fc387-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="fc387-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="fc387-129">ActivityDefinitionId</span></span>|<span data-ttu-id="fc387-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="fc387-130">xs:string</span></span>|<span data-ttu-id="fc387-131">工作流中根活动的名称</span><span class="sxs-lookup"><span data-stu-id="fc387-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="fc387-132">原因</span><span class="sxs-lookup"><span data-stu-id="fc387-132">Reason</span></span>|<span data-ttu-id="fc387-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="fc387-133">xs:string</span></span>|<span data-ttu-id="fc387-134">中止工作流的原因</span><span class="sxs-lookup"><span data-stu-id="fc387-134">The reason the workflow was aborted</span></span>|  
|<span data-ttu-id="fc387-135">批注</span><span class="sxs-lookup"><span data-stu-id="fc387-135">Annotations</span></span>|<span data-ttu-id="fc387-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="fc387-136">xs:string</span></span>|<span data-ttu-id="fc387-137">已添加到此事件中的批注。</span><span class="sxs-lookup"><span data-stu-id="fc387-137">The annotations that were added to this event.</span></span>  <span data-ttu-id="fc387-138">这些值存储在一个 xml 元素中格式\<项 >\<项名称 ="annotationName"type ="> annotationValue\</项 > \< /i >。</span><span class="sxs-lookup"><span data-stu-id="fc387-138">The values are stored in an xml element in the format \<items>\< item  name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span>  <span data-ttu-id="fc387-139">如果不指定任何批注，则该字符串包含\<项 / >。</span><span class="sxs-lookup"><span data-stu-id="fc387-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="fc387-140">ETW 事件大小受到 ETW 缓冲区大小或 ETW 事件最大负载的限制。</span><span class="sxs-lookup"><span data-stu-id="fc387-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="fc387-141">如果事件大小超出 ETW 限制，则通过丢弃批注并将批注值与截断事件\<项 >... \< /i >。</span><span class="sxs-lookup"><span data-stu-id="fc387-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="fc387-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="fc387-142">ProfileName</span></span>|<span data-ttu-id="fc387-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="fc387-143">xs:string</span></span>|<span data-ttu-id="fc387-144">导致发出此事件的跟踪配置文件的名称</span><span class="sxs-lookup"><span data-stu-id="fc387-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="fc387-145">HostReference</span><span class="sxs-lookup"><span data-stu-id="fc387-145">HostReference</span></span>|<span data-ttu-id="fc387-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="fc387-146">xs:string</span></span>|<span data-ttu-id="fc387-147">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="fc387-147">For web hosted services, this field uniquely identifies the service in the web hierarchy.</span></span>  <span data-ttu-id="fc387-148">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName 示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService</span><span class="sxs-lookup"><span data-stu-id="fc387-148">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName' Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'</span></span>|  
|<span data-ttu-id="fc387-149">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fc387-149">AppDomain</span></span>|<span data-ttu-id="fc387-150">xs:string</span><span class="sxs-lookup"><span data-stu-id="fc387-150">xs:string</span></span>|<span data-ttu-id="fc387-151">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="fc387-151">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
