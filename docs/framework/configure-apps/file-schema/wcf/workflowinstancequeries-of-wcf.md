---
title: <workflowInstanceQueries>WCF 的
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 8a58767745efab67fb7550de8770fec2c6226117
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854772"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="acbfd-102">\<WCF 的 Workflowinstancequeries&gt; ></span><span class="sxs-lookup"><span data-stu-id="acbfd-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="acbfd-103">表示配置元素的集合，这些配置元素跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="acbfd-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="acbfd-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="acbfd-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="acbfd-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="acbfd-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="acbfd-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="acbfd-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="acbfd-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="acbfd-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="acbfd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="acbfd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="acbfd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="acbfd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="acbfd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="acbfd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="acbfd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Workflowinstancequeries&gt; >**</span><span class="sxs-lookup"><span data-stu-id="acbfd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acbfd-112">语法</span><span class="sxs-lookup"><span data-stu-id="acbfd-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acbfd-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="acbfd-113">Attributes and elements</span></span>

<span data-ttu-id="acbfd-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="acbfd-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acbfd-115">特性</span><span class="sxs-lookup"><span data-stu-id="acbfd-115">Attributes</span></span>  

<span data-ttu-id="acbfd-116">无。</span><span class="sxs-lookup"><span data-stu-id="acbfd-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="acbfd-117">子元素</span><span class="sxs-lookup"><span data-stu-id="acbfd-117">Child elements</span></span>  
  
|<span data-ttu-id="acbfd-118">元素</span><span class="sxs-lookup"><span data-stu-id="acbfd-118">Element</span></span>|<span data-ttu-id="acbfd-119">描述</span><span class="sxs-lookup"><span data-stu-id="acbfd-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acbfd-120">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="acbfd-120">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="acbfd-121">一个查询，用于跟踪工作流实例生命周期的更改。</span><span class="sxs-lookup"><span data-stu-id="acbfd-121">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="acbfd-122">父元素</span><span class="sxs-lookup"><span data-stu-id="acbfd-122">Parent elements</span></span>  
  
|<span data-ttu-id="acbfd-123">元素</span><span class="sxs-lookup"><span data-stu-id="acbfd-123">Element</span></span>|<span data-ttu-id="acbfd-124">描述</span><span class="sxs-lookup"><span data-stu-id="acbfd-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acbfd-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="acbfd-125">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="acbfd-126">一个配置元素，该元素包含由[activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId)属性标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="acbfd-126">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acbfd-127">备注</span><span class="sxs-lookup"><span data-stu-id="acbfd-127">Remarks</span></span>

<span data-ttu-id="acbfd-128"><xref:System.Activities.Tracking.WorkflowInstanceQuery> 用于订阅以下 <xref:System.Activities.Tracking.TrackingRecord> 对象：</span><span class="sxs-lookup"><span data-stu-id="acbfd-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="acbfd-129">示例</span><span class="sxs-lookup"><span data-stu-id="acbfd-129">Example</span></span>  

<span data-ttu-id="acbfd-130">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="acbfd-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="acbfd-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="acbfd-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="acbfd-132">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="acbfd-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="acbfd-133">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="acbfd-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
