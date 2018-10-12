---
title: WCF 的 &lt;workflowInstanceQuery&gt;
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: 447564e46e5e74432802341d9f63adbb72667ab4
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123301"
---
# <a name="ltworkflowinstancequerygt-of-wcf"></a><span data-ttu-id="9e062-102">WCF 的 &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="9e062-102">&lt;workflowInstanceQuery&gt; of WCF</span></span>

<span data-ttu-id="9e062-103">表示一个查询，该查询跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="9e062-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="9e062-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9e062-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9e062-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9e062-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9e062-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="9e062-106">\<tracking></span></span>  
<span data-ttu-id="9e062-107">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="9e062-107">\<profiles></span></span>  
<span data-ttu-id="9e062-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9e062-108">\<trackingProfile></span></span>  
<span data-ttu-id="9e062-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="9e062-109">\<workflow></span></span>  
<span data-ttu-id="9e062-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="9e062-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="9e062-111">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="9e062-111">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e062-112">语法</span><span class="sxs-lookup"><span data-stu-id="9e062-112">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9e062-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9e062-113">Attributes and elements</span></span>  

<span data-ttu-id="9e062-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9e062-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e062-115">特性</span><span class="sxs-lookup"><span data-stu-id="9e062-115">Attributes</span></span>  

<span data-ttu-id="9e062-116">无。</span><span class="sxs-lookup"><span data-stu-id="9e062-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9e062-117">子元素</span><span class="sxs-lookup"><span data-stu-id="9e062-117">Child elements</span></span>  
  
|<span data-ttu-id="9e062-118">元素</span><span class="sxs-lookup"><span data-stu-id="9e062-118">Element</span></span>|<span data-ttu-id="9e062-119">描述</span><span class="sxs-lookup"><span data-stu-id="9e062-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e062-120">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="9e062-120">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="9e062-121">创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="9e062-121">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9e062-122">父元素</span><span class="sxs-lookup"><span data-stu-id="9e062-122">Parent elements</span></span>  
  
|<span data-ttu-id="9e062-123">元素</span><span class="sxs-lookup"><span data-stu-id="9e062-123">Element</span></span>|<span data-ttu-id="9e062-124">描述</span><span class="sxs-lookup"><span data-stu-id="9e062-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e062-125">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="9e062-125">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="9e062-126">表示配置元素的集合，这些配置元素跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="9e062-126">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e062-127">备注</span><span class="sxs-lookup"><span data-stu-id="9e062-127">Remarks</span></span>  

<span data-ttu-id="9e062-128"><xref:System.Activities.Tracking.WorkflowInstanceQuery> 用于订阅以下 <xref:System.Activities.Tracking.TrackingRecord> 对象：</span><span class="sxs-lookup"><span data-stu-id="9e062-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="9e062-129">示例</span><span class="sxs-lookup"><span data-stu-id="9e062-129">Example</span></span>  

<span data-ttu-id="9e062-130">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="9e062-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e062-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e062-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9e062-132">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="9e062-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9e062-133">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="9e062-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
