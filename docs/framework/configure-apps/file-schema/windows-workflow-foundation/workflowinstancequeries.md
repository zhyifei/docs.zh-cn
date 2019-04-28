---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: e54f98c980f60d02377e38d53d9d0eb48581eec0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613285"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="9bd2a-101">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="9bd2a-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="9bd2a-102">表示配置元素的集合，这些配置元素跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="9bd2a-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="9bd2a-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9bd2a-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9bd2a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9bd2a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="9bd2a-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="9bd2a-105">\<tracking></span></span>  
<span data-ttu-id="9bd2a-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9bd2a-106">\<trackingProfile></span></span>  
<span data-ttu-id="9bd2a-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="9bd2a-107">\<workflow></span></span>  
<span data-ttu-id="9bd2a-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="9bd2a-108">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bd2a-109">语法</span><span class="sxs-lookup"><span data-stu-id="9bd2a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9bd2a-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9bd2a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9bd2a-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9bd2a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9bd2a-112">特性</span><span class="sxs-lookup"><span data-stu-id="9bd2a-112">Attributes</span></span>  
 <span data-ttu-id="9bd2a-113">无。</span><span class="sxs-lookup"><span data-stu-id="9bd2a-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9bd2a-114">子元素</span><span class="sxs-lookup"><span data-stu-id="9bd2a-114">Child Elements</span></span>  
  
|<span data-ttu-id="9bd2a-115">元素</span><span class="sxs-lookup"><span data-stu-id="9bd2a-115">Element</span></span>|<span data-ttu-id="9bd2a-116">描述</span><span class="sxs-lookup"><span data-stu-id="9bd2a-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9bd2a-117">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="9bd2a-117">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="9bd2a-118">一个查询，用于跟踪工作流实例生命周期的更改。</span><span class="sxs-lookup"><span data-stu-id="9bd2a-118">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9bd2a-119">父元素</span><span class="sxs-lookup"><span data-stu-id="9bd2a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9bd2a-120">元素</span><span class="sxs-lookup"><span data-stu-id="9bd2a-120">Element</span></span>|<span data-ttu-id="9bd2a-121">描述</span><span class="sxs-lookup"><span data-stu-id="9bd2a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9bd2a-122">\<workflow></span><span class="sxs-lookup"><span data-stu-id="9bd2a-122">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="9bd2a-123">一个配置元素，包含由标识为特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="9bd2a-123">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bd2a-124">备注</span><span class="sxs-lookup"><span data-stu-id="9bd2a-124">Remarks</span></span>  
 <span data-ttu-id="9bd2a-125"><xref:System.Activities.Tracking.WorkflowInstanceQuery> 用于订阅以下 <xref:System.Activities.Tracking.TrackingRecord> 对象：</span><span class="sxs-lookup"><span data-stu-id="9bd2a-125">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="9bd2a-126">示例</span><span class="sxs-lookup"><span data-stu-id="9bd2a-126">Example</span></span>  
 <span data-ttu-id="9bd2a-127">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="9bd2a-127">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9bd2a-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="9bd2a-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9bd2a-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="9bd2a-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9bd2a-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="9bd2a-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
