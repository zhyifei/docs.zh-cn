---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: cfe3350ac42d1e0e837b79f25753f62dc2051dd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613386"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="4dc04-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="4dc04-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="4dc04-102">一种服务行为，可用于指定工作流服务中发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="4dc04-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="4dc04-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4dc04-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="4dc04-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="4dc04-104">\<behaviors></span></span>  
<span data-ttu-id="4dc04-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4dc04-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="4dc04-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4dc04-106">\<behavior></span></span>  
<span data-ttu-id="4dc04-107">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="4dc04-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dc04-108">语法</span><span class="sxs-lookup"><span data-stu-id="4dc04-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4dc04-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4dc04-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4dc04-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4dc04-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4dc04-111">特性</span><span class="sxs-lookup"><span data-stu-id="4dc04-111">Attributes</span></span>  
  
|<span data-ttu-id="4dc04-112">特性</span><span class="sxs-lookup"><span data-stu-id="4dc04-112">Attribute</span></span>|<span data-ttu-id="4dc04-113">描述</span><span class="sxs-lookup"><span data-stu-id="4dc04-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4dc04-114">action</span><span class="sxs-lookup"><span data-stu-id="4dc04-114">action</span></span>|<span data-ttu-id="4dc04-115">一个字符串，指定发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="4dc04-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="4dc04-116">此特性的类型为 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span><span class="sxs-lookup"><span data-stu-id="4dc04-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4dc04-117">子元素</span><span class="sxs-lookup"><span data-stu-id="4dc04-117">Child Elements</span></span>  
 <span data-ttu-id="4dc04-118">无。</span><span class="sxs-lookup"><span data-stu-id="4dc04-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4dc04-119">父元素</span><span class="sxs-lookup"><span data-stu-id="4dc04-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4dc04-120">元素</span><span class="sxs-lookup"><span data-stu-id="4dc04-120">Element</span></span>|<span data-ttu-id="4dc04-121">描述</span><span class="sxs-lookup"><span data-stu-id="4dc04-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4dc04-122">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4dc04-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="4dc04-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="4dc04-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4dc04-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="4dc04-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
