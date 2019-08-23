---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: c46d1fb9eb853e57c7ad1b97eb9a22556cdfb7d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913102"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="67a74-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="67a74-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="67a74-102">一种服务行为，可用于指定工作流服务中发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="67a74-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="67a74-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="67a74-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="67a74-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="67a74-104">\<behaviors></span></span>  
<span data-ttu-id="67a74-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="67a74-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="67a74-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="67a74-106">\<behavior></span></span>  
<span data-ttu-id="67a74-107">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="67a74-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67a74-108">语法</span><span class="sxs-lookup"><span data-stu-id="67a74-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67a74-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="67a74-109">Attributes and Elements</span></span>  
 <span data-ttu-id="67a74-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="67a74-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67a74-111">特性</span><span class="sxs-lookup"><span data-stu-id="67a74-111">Attributes</span></span>  
  
|<span data-ttu-id="67a74-112">特性</span><span class="sxs-lookup"><span data-stu-id="67a74-112">Attribute</span></span>|<span data-ttu-id="67a74-113">描述</span><span class="sxs-lookup"><span data-stu-id="67a74-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="67a74-114">action</span><span class="sxs-lookup"><span data-stu-id="67a74-114">action</span></span>|<span data-ttu-id="67a74-115">一个字符串，指定发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="67a74-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="67a74-116">此特性的类型为 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span><span class="sxs-lookup"><span data-stu-id="67a74-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67a74-117">子元素</span><span class="sxs-lookup"><span data-stu-id="67a74-117">Child Elements</span></span>  
 <span data-ttu-id="67a74-118">无。</span><span class="sxs-lookup"><span data-stu-id="67a74-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67a74-119">父元素</span><span class="sxs-lookup"><span data-stu-id="67a74-119">Parent Elements</span></span>  
  
|<span data-ttu-id="67a74-120">元素</span><span class="sxs-lookup"><span data-stu-id="67a74-120">Element</span></span>|<span data-ttu-id="67a74-121">描述</span><span class="sxs-lookup"><span data-stu-id="67a74-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67a74-122">\<serviceBehaviors > 的\<行为 ></span><span class="sxs-lookup"><span data-stu-id="67a74-122">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="67a74-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="67a74-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67a74-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="67a74-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
