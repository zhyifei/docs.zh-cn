---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 29b6d8982e712a0fa595b3103803f1795adea892
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398568"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="764d4-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="764d4-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="764d4-102">一种服务行为，可用于指定工作流服务中发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="764d4-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="764d4-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="764d4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="764d4-104">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="764d4-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="764d4-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="764d4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="764d4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="764d4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="764d4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="764d4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="764d4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowUnhandledException >**</span><span class="sxs-lookup"><span data-stu-id="764d4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="764d4-109">语法</span><span class="sxs-lookup"><span data-stu-id="764d4-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="764d4-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="764d4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="764d4-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="764d4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="764d4-112">特性</span><span class="sxs-lookup"><span data-stu-id="764d4-112">Attributes</span></span>  
  
|<span data-ttu-id="764d4-113">特性</span><span class="sxs-lookup"><span data-stu-id="764d4-113">Attribute</span></span>|<span data-ttu-id="764d4-114">描述</span><span class="sxs-lookup"><span data-stu-id="764d4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="764d4-115">action</span><span class="sxs-lookup"><span data-stu-id="764d4-115">action</span></span>|<span data-ttu-id="764d4-116">一个字符串，指定发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="764d4-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="764d4-117">此特性的类型为 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span><span class="sxs-lookup"><span data-stu-id="764d4-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="764d4-118">子元素</span><span class="sxs-lookup"><span data-stu-id="764d4-118">Child Elements</span></span>  
 <span data-ttu-id="764d4-119">无。</span><span class="sxs-lookup"><span data-stu-id="764d4-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="764d4-120">父元素</span><span class="sxs-lookup"><span data-stu-id="764d4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="764d4-121">元素</span><span class="sxs-lookup"><span data-stu-id="764d4-121">Element</span></span>|<span data-ttu-id="764d4-122">描述</span><span class="sxs-lookup"><span data-stu-id="764d4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="764d4-123">\<serviceBehaviors > 的\<行为 ></span><span class="sxs-lookup"><span data-stu-id="764d4-123">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="764d4-124">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="764d4-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="764d4-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="764d4-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
