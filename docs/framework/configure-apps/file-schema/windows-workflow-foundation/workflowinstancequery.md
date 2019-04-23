---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: 6fe02cfea91633da41c8ebc7d8a78dd005ad3f4a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080899"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="41943-101">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="41943-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="41943-102">表示一个查询，该查询跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="41943-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="41943-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="41943-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="41943-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="41943-104">\<system.serviceModel></span></span>  
<span data-ttu-id="41943-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="41943-105">\<tracking></span></span>  
<span data-ttu-id="41943-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="41943-106">\<trackingProfile></span></span>  
<span data-ttu-id="41943-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="41943-107">\<workflow></span></span>  
<span data-ttu-id="41943-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="41943-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="41943-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="41943-109">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41943-110">语法</span><span class="sxs-lookup"><span data-stu-id="41943-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41943-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="41943-111">Attributes and Elements</span></span>  
 <span data-ttu-id="41943-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="41943-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41943-113">特性</span><span class="sxs-lookup"><span data-stu-id="41943-113">Attributes</span></span>  
 <span data-ttu-id="41943-114">无。</span><span class="sxs-lookup"><span data-stu-id="41943-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="41943-115">子元素</span><span class="sxs-lookup"><span data-stu-id="41943-115">Child Elements</span></span>  
  
|<span data-ttu-id="41943-116">元素</span><span class="sxs-lookup"><span data-stu-id="41943-116">Element</span></span>|<span data-ttu-id="41943-117">描述</span><span class="sxs-lookup"><span data-stu-id="41943-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41943-118">\<states></span><span class="sxs-lookup"><span data-stu-id="41943-118">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="41943-119">创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="41943-119">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="41943-120">父元素</span><span class="sxs-lookup"><span data-stu-id="41943-120">Parent Elements</span></span>  
  
|<span data-ttu-id="41943-121">元素</span><span class="sxs-lookup"><span data-stu-id="41943-121">Element</span></span>|<span data-ttu-id="41943-122">描述</span><span class="sxs-lookup"><span data-stu-id="41943-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41943-123">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="41943-123">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="41943-124">表示配置元素的集合，这些配置元素跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="41943-124">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41943-125">备注</span><span class="sxs-lookup"><span data-stu-id="41943-125">Remarks</span></span>  
 <span data-ttu-id="41943-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> 用于订阅以下 <xref:System.Activities.Tracking.TrackingRecord> 对象：</span><span class="sxs-lookup"><span data-stu-id="41943-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="41943-127">示例</span><span class="sxs-lookup"><span data-stu-id="41943-127">Example</span></span>  
 <span data-ttu-id="41943-128">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="41943-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="41943-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="41943-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="41943-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="41943-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="41943-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="41943-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
