---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: cfe3350ac42d1e0e837b79f25753f62dc2051dd2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096246"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="60f8f-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="60f8f-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="60f8f-102">一种服务行为，可用于指定工作流服务中发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="60f8f-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="60f8f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="60f8f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="60f8f-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="60f8f-104">\<behaviors></span></span>  
<span data-ttu-id="60f8f-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="60f8f-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="60f8f-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="60f8f-106">\<behavior></span></span>  
<span data-ttu-id="60f8f-107">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="60f8f-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60f8f-108">语法</span><span class="sxs-lookup"><span data-stu-id="60f8f-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60f8f-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="60f8f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="60f8f-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="60f8f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60f8f-111">特性</span><span class="sxs-lookup"><span data-stu-id="60f8f-111">Attributes</span></span>  
  
|<span data-ttu-id="60f8f-112">特性</span><span class="sxs-lookup"><span data-stu-id="60f8f-112">Attribute</span></span>|<span data-ttu-id="60f8f-113">描述</span><span class="sxs-lookup"><span data-stu-id="60f8f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60f8f-114">action</span><span class="sxs-lookup"><span data-stu-id="60f8f-114">action</span></span>|<span data-ttu-id="60f8f-115">一个字符串，指定发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="60f8f-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="60f8f-116">此属性是类型的</span><span class="sxs-lookup"><span data-stu-id="60f8f-116">This attribute is of type</span></span> <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction>|  
  
### <a name="child-elements"></a><span data-ttu-id="60f8f-117">子元素</span><span class="sxs-lookup"><span data-stu-id="60f8f-117">Child Elements</span></span>  
 <span data-ttu-id="60f8f-118">无。</span><span class="sxs-lookup"><span data-stu-id="60f8f-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60f8f-119">父元素</span><span class="sxs-lookup"><span data-stu-id="60f8f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="60f8f-120">元素</span><span class="sxs-lookup"><span data-stu-id="60f8f-120">Element</span></span>|<span data-ttu-id="60f8f-121">描述</span><span class="sxs-lookup"><span data-stu-id="60f8f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60f8f-122">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="60f8f-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="60f8f-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="60f8f-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60f8f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="60f8f-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
