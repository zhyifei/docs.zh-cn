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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4266eb6480c98c7ea1b96f2325a018b0fdcba041
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowunhandledexceptiongt"></a><span data-ttu-id="1aece-102">&lt;workflowUnhandledException&gt;</span><span class="sxs-lookup"><span data-stu-id="1aece-102">&lt;workflowUnhandledException&gt;</span></span>
<span data-ttu-id="1aece-103">一种服务行为，可用于指定工作流服务中发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="1aece-103">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="1aece-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1aece-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1aece-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="1aece-105">\<behaviors></span></span>  
<span data-ttu-id="1aece-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1aece-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1aece-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="1aece-107">\<behavior></span></span>  
<span data-ttu-id="1aece-108">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="1aece-108">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aece-109">语法</span><span class="sxs-lookup"><span data-stu-id="1aece-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1aece-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1aece-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1aece-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1aece-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1aece-112">特性</span><span class="sxs-lookup"><span data-stu-id="1aece-112">Attributes</span></span>  
  
|<span data-ttu-id="1aece-113">特性</span><span class="sxs-lookup"><span data-stu-id="1aece-113">Attribute</span></span>|<span data-ttu-id="1aece-114">描述</span><span class="sxs-lookup"><span data-stu-id="1aece-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1aece-115">action</span><span class="sxs-lookup"><span data-stu-id="1aece-115">action</span></span>|<span data-ttu-id="1aece-116">一个字符串，指定发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="1aece-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="1aece-117">此特性的类型为 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span><span class="sxs-lookup"><span data-stu-id="1aece-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1aece-118">子元素</span><span class="sxs-lookup"><span data-stu-id="1aece-118">Child Elements</span></span>  
 <span data-ttu-id="1aece-119">无。</span><span class="sxs-lookup"><span data-stu-id="1aece-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1aece-120">父元素</span><span class="sxs-lookup"><span data-stu-id="1aece-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1aece-121">元素</span><span class="sxs-lookup"><span data-stu-id="1aece-121">Element</span></span>|<span data-ttu-id="1aece-122">描述</span><span class="sxs-lookup"><span data-stu-id="1aece-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1aece-123">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1aece-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="1aece-124">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="1aece-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1aece-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="1aece-125">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
