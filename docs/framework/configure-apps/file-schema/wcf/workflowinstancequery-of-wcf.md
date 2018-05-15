---
title: WCF 的 &lt;workflowInstanceQuery&gt;
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: c3b68dda42fd7a9356366a0887feb359d0232b32
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowinstancequerygt-of-wcf"></a><span data-ttu-id="10c0a-102">WCF 的 &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="10c0a-102">&lt;workflowInstanceQuery&gt; of WCF</span></span>
<span data-ttu-id="10c0a-103">表示一个查询，该查询跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="10c0a-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="10c0a-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="10c0a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="10c0a-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="10c0a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="10c0a-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="10c0a-106">\<tracking></span></span>  
<span data-ttu-id="10c0a-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="10c0a-107">\<trackingProfile></span></span>  
<span data-ttu-id="10c0a-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="10c0a-108">\<workflow></span></span>  
<span data-ttu-id="10c0a-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="10c0a-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="10c0a-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="10c0a-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10c0a-111">语法</span><span class="sxs-lookup"><span data-stu-id="10c0a-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10c0a-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="10c0a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="10c0a-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="10c0a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10c0a-114">特性</span><span class="sxs-lookup"><span data-stu-id="10c0a-114">Attributes</span></span>  
 <span data-ttu-id="10c0a-115">无。</span><span class="sxs-lookup"><span data-stu-id="10c0a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="10c0a-116">子元素</span><span class="sxs-lookup"><span data-stu-id="10c0a-116">Child Elements</span></span>  
  
|<span data-ttu-id="10c0a-117">元素</span><span class="sxs-lookup"><span data-stu-id="10c0a-117">Element</span></span>|<span data-ttu-id="10c0a-118">描述</span><span class="sxs-lookup"><span data-stu-id="10c0a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10c0a-119">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="10c0a-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="10c0a-120">创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="10c0a-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10c0a-121">父元素</span><span class="sxs-lookup"><span data-stu-id="10c0a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="10c0a-122">元素</span><span class="sxs-lookup"><span data-stu-id="10c0a-122">Element</span></span>|<span data-ttu-id="10c0a-123">描述</span><span class="sxs-lookup"><span data-stu-id="10c0a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10c0a-124">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="10c0a-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="10c0a-125">表示配置元素的集合，这些配置元素跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="10c0a-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10c0a-126">备注</span><span class="sxs-lookup"><span data-stu-id="10c0a-126">Remarks</span></span>  
 <span data-ttu-id="10c0a-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> 用于订阅以下 <xref:System.Activities.Tracking.TrackingRecord> 对象：</span><span class="sxs-lookup"><span data-stu-id="10c0a-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="10c0a-128">示例</span><span class="sxs-lookup"><span data-stu-id="10c0a-128">Example</span></span>  
 <span data-ttu-id="10c0a-129">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="10c0a-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="10c0a-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="10c0a-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="10c0a-131">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="10c0a-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="10c0a-132">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="10c0a-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
