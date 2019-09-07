---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: 68e44584858e55c136bc3c3dc5f1fb333485fa17
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397513"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="49d2e-101">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="49d2e-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="49d2e-102">表示一个查询，该查询跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="49d2e-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="49d2e-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="49d2e-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="49d2e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="49d2e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="49d2e-105">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="49d2e-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="49d2e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="49d2e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="49d2e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="49d2e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="49d2e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="49d2e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="49d2e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflowinstancequeries&gt; >** ](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="49d2e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="49d2e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowInstanceQuery >**</span><span class="sxs-lookup"><span data-stu-id="49d2e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49d2e-111">语法</span><span class="sxs-lookup"><span data-stu-id="49d2e-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49d2e-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="49d2e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="49d2e-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="49d2e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49d2e-114">特性</span><span class="sxs-lookup"><span data-stu-id="49d2e-114">Attributes</span></span>  
 <span data-ttu-id="49d2e-115">无。</span><span class="sxs-lookup"><span data-stu-id="49d2e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="49d2e-116">子元素</span><span class="sxs-lookup"><span data-stu-id="49d2e-116">Child Elements</span></span>  
  
|<span data-ttu-id="49d2e-117">元素</span><span class="sxs-lookup"><span data-stu-id="49d2e-117">Element</span></span>|<span data-ttu-id="49d2e-118">描述</span><span class="sxs-lookup"><span data-stu-id="49d2e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49d2e-119">\<states></span><span class="sxs-lookup"><span data-stu-id="49d2e-119">\<states></span></span>](states.md)|<span data-ttu-id="49d2e-120">创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="49d2e-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49d2e-121">父元素</span><span class="sxs-lookup"><span data-stu-id="49d2e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="49d2e-122">元素</span><span class="sxs-lookup"><span data-stu-id="49d2e-122">Element</span></span>|<span data-ttu-id="49d2e-123">描述</span><span class="sxs-lookup"><span data-stu-id="49d2e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49d2e-124">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="49d2e-124">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="49d2e-125">表示配置元素的集合，这些配置元素跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="49d2e-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49d2e-126">备注</span><span class="sxs-lookup"><span data-stu-id="49d2e-126">Remarks</span></span>  
 <span data-ttu-id="49d2e-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> 用于订阅以下 <xref:System.Activities.Tracking.TrackingRecord> 对象：</span><span class="sxs-lookup"><span data-stu-id="49d2e-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="49d2e-128">示例</span><span class="sxs-lookup"><span data-stu-id="49d2e-128">Example</span></span>  
 <span data-ttu-id="49d2e-129">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="49d2e-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="49d2e-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="49d2e-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="49d2e-131">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="49d2e-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="49d2e-132">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="49d2e-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
