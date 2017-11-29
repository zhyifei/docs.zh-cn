---
title: '&lt;workflowUnhandledException&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9b3e9450721de526aa489500f152a277acc52178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowunhandledexceptiongt"></a><span data-ttu-id="e9ccc-102">&lt;workflowUnhandledException&gt;</span><span class="sxs-lookup"><span data-stu-id="e9ccc-102">&lt;workflowUnhandledException&gt;</span></span>
<span data-ttu-id="e9ccc-103">一种服务行为，可用于指定工作流服务中发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-103">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="e9ccc-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e9ccc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e9ccc-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e9ccc-105">\<behaviors></span></span>  
<span data-ttu-id="e9ccc-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e9ccc-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e9ccc-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e9ccc-107">\<behavior></span></span>  
<span data-ttu-id="e9ccc-108">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="e9ccc-108">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9ccc-109">语法</span><span class="sxs-lookup"><span data-stu-id="e9ccc-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9ccc-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e9ccc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e9ccc-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9ccc-112">特性</span><span class="sxs-lookup"><span data-stu-id="e9ccc-112">Attributes</span></span>  
  
|<span data-ttu-id="e9ccc-113">特性</span><span class="sxs-lookup"><span data-stu-id="e9ccc-113">Attribute</span></span>|<span data-ttu-id="e9ccc-114">描述</span><span class="sxs-lookup"><span data-stu-id="e9ccc-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9ccc-115">action</span><span class="sxs-lookup"><span data-stu-id="e9ccc-115">action</span></span>|<span data-ttu-id="e9ccc-116">一个字符串，指定发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="e9ccc-117">此特性的类型为 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span><span class="sxs-lookup"><span data-stu-id="e9ccc-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9ccc-118">子元素</span><span class="sxs-lookup"><span data-stu-id="e9ccc-118">Child Elements</span></span>  
 <span data-ttu-id="e9ccc-119">无。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9ccc-120">父元素</span><span class="sxs-lookup"><span data-stu-id="e9ccc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e9ccc-121">元素</span><span class="sxs-lookup"><span data-stu-id="e9ccc-121">Element</span></span>|<span data-ttu-id="e9ccc-122">描述</span><span class="sxs-lookup"><span data-stu-id="e9ccc-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9ccc-123">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e9ccc-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="e9ccc-124">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9ccc-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9ccc-125">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
