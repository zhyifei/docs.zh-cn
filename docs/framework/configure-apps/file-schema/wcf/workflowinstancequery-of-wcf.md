---
title: <workflowInstanceQuery>WCF 的
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: eaf0cd204265aac7c1421e3de0c33963e6bbb7a1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854740"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="aeca6-102">\<WCF 的 workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="aeca6-102">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="aeca6-103">表示一个查询，该查询跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="aeca6-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="aeca6-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="aeca6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="aeca6-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aeca6-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aeca6-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aeca6-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aeca6-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aeca6-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="aeca6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="aeca6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="aeca6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aeca6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="aeca6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aeca6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="aeca6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflowinstancequeries&gt; >** ](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="aeca6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="aeca6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowInstanceQuery >**</span><span class="sxs-lookup"><span data-stu-id="aeca6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aeca6-113">语法</span><span class="sxs-lookup"><span data-stu-id="aeca6-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aeca6-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="aeca6-114">Attributes and elements</span></span>  

<span data-ttu-id="aeca6-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="aeca6-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aeca6-116">特性</span><span class="sxs-lookup"><span data-stu-id="aeca6-116">Attributes</span></span>  

<span data-ttu-id="aeca6-117">无。</span><span class="sxs-lookup"><span data-stu-id="aeca6-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aeca6-118">子元素</span><span class="sxs-lookup"><span data-stu-id="aeca6-118">Child elements</span></span>  
  
|<span data-ttu-id="aeca6-119">元素</span><span class="sxs-lookup"><span data-stu-id="aeca6-119">Element</span></span>|<span data-ttu-id="aeca6-120">描述</span><span class="sxs-lookup"><span data-stu-id="aeca6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aeca6-121">\<states></span><span class="sxs-lookup"><span data-stu-id="aeca6-121">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="aeca6-122">创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="aeca6-122">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aeca6-123">父元素</span><span class="sxs-lookup"><span data-stu-id="aeca6-123">Parent elements</span></span>  
  
|<span data-ttu-id="aeca6-124">元素</span><span class="sxs-lookup"><span data-stu-id="aeca6-124">Element</span></span>|<span data-ttu-id="aeca6-125">描述</span><span class="sxs-lookup"><span data-stu-id="aeca6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aeca6-126">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="aeca6-126">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="aeca6-127">表示配置元素的集合，这些配置元素跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="aeca6-127">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aeca6-128">备注</span><span class="sxs-lookup"><span data-stu-id="aeca6-128">Remarks</span></span>  

<span data-ttu-id="aeca6-129"><xref:System.Activities.Tracking.WorkflowInstanceQuery> 用于订阅以下 <xref:System.Activities.Tracking.TrackingRecord> 对象：</span><span class="sxs-lookup"><span data-stu-id="aeca6-129">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="aeca6-130">示例</span><span class="sxs-lookup"><span data-stu-id="aeca6-130">Example</span></span>  

<span data-ttu-id="aeca6-131">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="aeca6-131">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="aeca6-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="aeca6-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="aeca6-133">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="aeca6-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="aeca6-134">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="aeca6-134">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
