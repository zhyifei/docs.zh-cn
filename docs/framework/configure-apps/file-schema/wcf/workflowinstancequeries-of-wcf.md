---
title: <workflowInstanceQueries> WCF 的
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 89e122b87743a81a80ce63b382ae235c1c4863bc
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759244"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="7ae20-102">\<workflowInstanceQueries > 的 WCF</span><span class="sxs-lookup"><span data-stu-id="7ae20-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="7ae20-103">表示配置元素的集合，这些配置元素跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="7ae20-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="7ae20-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="7ae20-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="7ae20-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7ae20-105">\<system.serviceModel></span></span>  
<span data-ttu-id="7ae20-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="7ae20-106">\<tracking></span></span>  
<span data-ttu-id="7ae20-107">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="7ae20-107">\<profiles></span></span>  
<span data-ttu-id="7ae20-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7ae20-108">\<trackingProfile></span></span>  
<span data-ttu-id="7ae20-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="7ae20-109">\<workflow></span></span>  
<span data-ttu-id="7ae20-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="7ae20-110">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ae20-111">语法</span><span class="sxs-lookup"><span data-stu-id="7ae20-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ae20-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7ae20-112">Attributes and elements</span></span>

<span data-ttu-id="7ae20-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7ae20-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ae20-114">特性</span><span class="sxs-lookup"><span data-stu-id="7ae20-114">Attributes</span></span>  

<span data-ttu-id="7ae20-115">无。</span><span class="sxs-lookup"><span data-stu-id="7ae20-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7ae20-116">子元素</span><span class="sxs-lookup"><span data-stu-id="7ae20-116">Child elements</span></span>  
  
|<span data-ttu-id="7ae20-117">元素</span><span class="sxs-lookup"><span data-stu-id="7ae20-117">Element</span></span>|<span data-ttu-id="7ae20-118">描述</span><span class="sxs-lookup"><span data-stu-id="7ae20-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ae20-119">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="7ae20-119">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="7ae20-120">一个查询，用于跟踪工作流实例生命周期的更改。</span><span class="sxs-lookup"><span data-stu-id="7ae20-120">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7ae20-121">父元素</span><span class="sxs-lookup"><span data-stu-id="7ae20-121">Parent elements</span></span>  
  
|<span data-ttu-id="7ae20-122">元素</span><span class="sxs-lookup"><span data-stu-id="7ae20-122">Element</span></span>|<span data-ttu-id="7ae20-123">描述</span><span class="sxs-lookup"><span data-stu-id="7ae20-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ae20-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="7ae20-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="7ae20-125">一个配置元素，包含由标识为特定工作流的所有查询[activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId)属性。</span><span class="sxs-lookup"><span data-stu-id="7ae20-125">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ae20-126">备注</span><span class="sxs-lookup"><span data-stu-id="7ae20-126">Remarks</span></span>

<span data-ttu-id="7ae20-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> 用于订阅以下 <xref:System.Activities.Tracking.TrackingRecord> 对象：</span><span class="sxs-lookup"><span data-stu-id="7ae20-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="7ae20-128">示例</span><span class="sxs-lookup"><span data-stu-id="7ae20-128">Example</span></span>  

<span data-ttu-id="7ae20-129">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="7ae20-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="7ae20-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ae20-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7ae20-131">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="7ae20-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7ae20-132">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="7ae20-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
