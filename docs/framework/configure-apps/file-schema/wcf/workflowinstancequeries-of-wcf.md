---
title: WCF 的 &lt;workflowInstanceQueries&gt;
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: e3ad1139781c54cc1ca4e2d2b264f3f375b49108
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145557"
---
# <a name="ltworkflowinstancequeriesgt-of-wcf"></a><span data-ttu-id="15de1-102">WCF 的 &lt;workflowInstanceQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="15de1-102">&lt;workflowInstanceQueries&gt; of WCF</span></span>

<span data-ttu-id="15de1-103">表示配置元素的集合，这些配置元素跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="15de1-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="15de1-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="15de1-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="15de1-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="15de1-105">\<system.serviceModel></span></span>  
<span data-ttu-id="15de1-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="15de1-106">\<tracking></span></span>  
<span data-ttu-id="15de1-107">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="15de1-107">\<profiles></span></span>  
<span data-ttu-id="15de1-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="15de1-108">\<trackingProfile></span></span>  
<span data-ttu-id="15de1-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="15de1-109">\<workflow></span></span>  
<span data-ttu-id="15de1-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="15de1-110">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15de1-111">语法</span><span class="sxs-lookup"><span data-stu-id="15de1-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15de1-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="15de1-112">Attributes and elements</span></span>

<span data-ttu-id="15de1-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="15de1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15de1-114">特性</span><span class="sxs-lookup"><span data-stu-id="15de1-114">Attributes</span></span>  

<span data-ttu-id="15de1-115">无。</span><span class="sxs-lookup"><span data-stu-id="15de1-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="15de1-116">子元素</span><span class="sxs-lookup"><span data-stu-id="15de1-116">Child elements</span></span>  
  
|<span data-ttu-id="15de1-117">元素</span><span class="sxs-lookup"><span data-stu-id="15de1-117">Element</span></span>|<span data-ttu-id="15de1-118">描述</span><span class="sxs-lookup"><span data-stu-id="15de1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15de1-119">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="15de1-119">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="15de1-120">一个查询，用于跟踪工作流实例生命周期的更改。</span><span class="sxs-lookup"><span data-stu-id="15de1-120">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15de1-121">父元素</span><span class="sxs-lookup"><span data-stu-id="15de1-121">Parent elements</span></span>  
  
|<span data-ttu-id="15de1-122">元素</span><span class="sxs-lookup"><span data-stu-id="15de1-122">Element</span></span>|<span data-ttu-id="15de1-123">描述</span><span class="sxs-lookup"><span data-stu-id="15de1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15de1-124">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="15de1-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="15de1-125">一个配置元素，包含由标识为特定工作流的所有查询[activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx)属性。</span><span class="sxs-lookup"><span data-stu-id="15de1-125">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15de1-126">备注</span><span class="sxs-lookup"><span data-stu-id="15de1-126">Remarks</span></span>

<span data-ttu-id="15de1-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> 用于订阅以下 <xref:System.Activities.Tracking.TrackingRecord> 对象：</span><span class="sxs-lookup"><span data-stu-id="15de1-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="15de1-128">示例</span><span class="sxs-lookup"><span data-stu-id="15de1-128">Example</span></span>  

<span data-ttu-id="15de1-129">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="15de1-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="15de1-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="15de1-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="15de1-131">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="15de1-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="15de1-132">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="15de1-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
