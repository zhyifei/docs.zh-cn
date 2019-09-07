---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 11e301de1ab3dbd4c97f236bfd07c5de4a632272
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398580"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="20a8f-101">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="20a8f-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="20a8f-102">表示配置元素的集合，这些配置元素跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="20a8f-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="20a8f-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="20a8f-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="20a8f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="20a8f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="20a8f-105">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="20a8f-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="20a8f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="20a8f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="20a8f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="20a8f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="20a8f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="20a8f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="20a8f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Workflowinstancequeries&gt; >**</span><span class="sxs-lookup"><span data-stu-id="20a8f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20a8f-110">语法</span><span class="sxs-lookup"><span data-stu-id="20a8f-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20a8f-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="20a8f-111">Attributes and Elements</span></span>  

<span data-ttu-id="20a8f-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="20a8f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20a8f-113">特性</span><span class="sxs-lookup"><span data-stu-id="20a8f-113">Attributes</span></span>  

<span data-ttu-id="20a8f-114">无。</span><span class="sxs-lookup"><span data-stu-id="20a8f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20a8f-115">子元素</span><span class="sxs-lookup"><span data-stu-id="20a8f-115">Child Elements</span></span>  
  
|<span data-ttu-id="20a8f-116">元素</span><span class="sxs-lookup"><span data-stu-id="20a8f-116">Element</span></span>|<span data-ttu-id="20a8f-117">描述</span><span class="sxs-lookup"><span data-stu-id="20a8f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20a8f-118">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="20a8f-118">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="20a8f-119">一个查询，用于跟踪工作流实例生命周期的更改。</span><span class="sxs-lookup"><span data-stu-id="20a8f-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20a8f-120">父元素</span><span class="sxs-lookup"><span data-stu-id="20a8f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="20a8f-121">元素</span><span class="sxs-lookup"><span data-stu-id="20a8f-121">Element</span></span>|<span data-ttu-id="20a8f-122">描述</span><span class="sxs-lookup"><span data-stu-id="20a8f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20a8f-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="20a8f-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="20a8f-124">一个配置元素，该元素包含由**activityDefinitionId**属性标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="20a8f-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20a8f-125">备注</span><span class="sxs-lookup"><span data-stu-id="20a8f-125">Remarks</span></span>  

<span data-ttu-id="20a8f-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> 用于订阅以下 <xref:System.Activities.Tracking.TrackingRecord> 对象：</span><span class="sxs-lookup"><span data-stu-id="20a8f-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="20a8f-127">示例</span><span class="sxs-lookup"><span data-stu-id="20a8f-127">Example</span></span>  

<span data-ttu-id="20a8f-128">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="20a8f-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="20a8f-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="20a8f-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="20a8f-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="20a8f-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="20a8f-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="20a8f-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
