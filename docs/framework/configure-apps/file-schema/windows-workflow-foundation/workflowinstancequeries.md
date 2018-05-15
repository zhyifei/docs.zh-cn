---
title: '&lt;workflowInstanceQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: a165d6f55afbbf1489a7355d4207a74ac1f003ef
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowinstancequeriesgt"></a><span data-ttu-id="17a88-102">&lt;workflowInstanceQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="17a88-102">&lt;workflowInstanceQueries&gt;</span></span>
<span data-ttu-id="17a88-103">表示配置元素的集合，这些配置元素跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="17a88-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="17a88-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="17a88-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="17a88-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="17a88-105">\<system.serviceModel></span></span>  
<span data-ttu-id="17a88-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="17a88-106">\<tracking></span></span>  
<span data-ttu-id="17a88-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="17a88-107">\<trackingProfile></span></span>  
<span data-ttu-id="17a88-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="17a88-108">\<workflow></span></span>  
<span data-ttu-id="17a88-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="17a88-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17a88-110">语法</span><span class="sxs-lookup"><span data-stu-id="17a88-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17a88-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="17a88-111">Attributes and Elements</span></span>  
 <span data-ttu-id="17a88-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="17a88-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17a88-113">特性</span><span class="sxs-lookup"><span data-stu-id="17a88-113">Attributes</span></span>  
 <span data-ttu-id="17a88-114">无。</span><span class="sxs-lookup"><span data-stu-id="17a88-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="17a88-115">子元素</span><span class="sxs-lookup"><span data-stu-id="17a88-115">Child Elements</span></span>  
  
|<span data-ttu-id="17a88-116">元素</span><span class="sxs-lookup"><span data-stu-id="17a88-116">Element</span></span>|<span data-ttu-id="17a88-117">描述</span><span class="sxs-lookup"><span data-stu-id="17a88-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17a88-118">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="17a88-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="17a88-119">一个查询，用于跟踪工作流实例生命周期的更改。</span><span class="sxs-lookup"><span data-stu-id="17a88-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="17a88-120">父元素</span><span class="sxs-lookup"><span data-stu-id="17a88-120">Parent Elements</span></span>  
  
|<span data-ttu-id="17a88-121">元素</span><span class="sxs-lookup"><span data-stu-id="17a88-121">Element</span></span>|<span data-ttu-id="17a88-122">描述</span><span class="sxs-lookup"><span data-stu-id="17a88-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17a88-123">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="17a88-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="17a88-124">一个配置元素，包含由标识的特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="17a88-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17a88-125">备注</span><span class="sxs-lookup"><span data-stu-id="17a88-125">Remarks</span></span>  
 <span data-ttu-id="17a88-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> 用于订阅以下 <xref:System.Activities.Tracking.TrackingRecord> 对象：</span><span class="sxs-lookup"><span data-stu-id="17a88-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="17a88-127">示例</span><span class="sxs-lookup"><span data-stu-id="17a88-127">Example</span></span>  
 <span data-ttu-id="17a88-128">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="17a88-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="17a88-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="17a88-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="17a88-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="17a88-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="17a88-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="17a88-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
