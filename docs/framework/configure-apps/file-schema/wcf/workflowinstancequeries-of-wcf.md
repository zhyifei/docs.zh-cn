---
title: WCF 的 &lt;workflowInstanceQueries&gt;
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: dfa75a7e4729244ba5887e6666c0fdfe840e9faf
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45741958"
---
# <a name="ltworkflowinstancequeriesgt-of-wcf"></a><span data-ttu-id="278c9-102">WCF 的 &lt;workflowInstanceQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="278c9-102">&lt;workflowInstanceQueries&gt; of WCF</span></span>
<span data-ttu-id="278c9-103">表示配置元素的集合，这些配置元素跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="278c9-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="278c9-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="278c9-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="278c9-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="278c9-105">\<system.serviceModel></span></span>  
<span data-ttu-id="278c9-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="278c9-106">\<tracking></span></span>  
<span data-ttu-id="278c9-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="278c9-107">\<trackingProfile></span></span>  
<span data-ttu-id="278c9-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="278c9-108">\<workflow></span></span>  
<span data-ttu-id="278c9-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="278c9-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="278c9-110">语法</span><span class="sxs-lookup"><span data-stu-id="278c9-110">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="278c9-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="278c9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="278c9-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="278c9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="278c9-113">特性</span><span class="sxs-lookup"><span data-stu-id="278c9-113">Attributes</span></span>  
 <span data-ttu-id="278c9-114">无。</span><span class="sxs-lookup"><span data-stu-id="278c9-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="278c9-115">子元素</span><span class="sxs-lookup"><span data-stu-id="278c9-115">Child Elements</span></span>  
  
|<span data-ttu-id="278c9-116">元素</span><span class="sxs-lookup"><span data-stu-id="278c9-116">Element</span></span>|<span data-ttu-id="278c9-117">描述</span><span class="sxs-lookup"><span data-stu-id="278c9-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="278c9-118">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="278c9-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="278c9-119">一个查询，用于跟踪工作流实例生命周期的更改。</span><span class="sxs-lookup"><span data-stu-id="278c9-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="278c9-120">父元素</span><span class="sxs-lookup"><span data-stu-id="278c9-120">Parent Elements</span></span>  
  
|<span data-ttu-id="278c9-121">元素</span><span class="sxs-lookup"><span data-stu-id="278c9-121">Element</span></span>|<span data-ttu-id="278c9-122">描述</span><span class="sxs-lookup"><span data-stu-id="278c9-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="278c9-123">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="278c9-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="278c9-124">一个配置元素，包含由标识为特定工作流的所有查询[activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx)属性。</span><span class="sxs-lookup"><span data-stu-id="278c9-124">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="278c9-125">备注</span><span class="sxs-lookup"><span data-stu-id="278c9-125">Remarks</span></span>  
 <span data-ttu-id="278c9-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> 用于订阅以下 <xref:System.Activities.Tracking.TrackingRecord> 对象：</span><span class="sxs-lookup"><span data-stu-id="278c9-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="278c9-127">示例</span><span class="sxs-lookup"><span data-stu-id="278c9-127">Example</span></span>  
 <span data-ttu-id="278c9-128">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="278c9-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="278c9-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="278c9-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="278c9-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="278c9-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="278c9-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="278c9-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
