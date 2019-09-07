---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: aa2edafd9adc0317ed0023ad46688025dcecad67
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397521"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="35700-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="35700-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="35700-102">一种服务行为，可用于指定控制工作流实例如何运行的设置，包括持久性、未经处理的异常行为和空闲行为。</span><span class="sxs-lookup"><span data-stu-id="35700-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="35700-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="35700-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="35700-104">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="35700-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="35700-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="35700-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="35700-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="35700-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="35700-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="35700-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="35700-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowInstanceManagement >**</span><span class="sxs-lookup"><span data-stu-id="35700-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35700-109">语法</span><span class="sxs-lookup"><span data-stu-id="35700-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35700-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="35700-110">Attributes and Elements</span></span>  
 <span data-ttu-id="35700-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="35700-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35700-112">特性</span><span class="sxs-lookup"><span data-stu-id="35700-112">Attributes</span></span>  
  
|<span data-ttu-id="35700-113">特性</span><span class="sxs-lookup"><span data-stu-id="35700-113">Attribute</span></span>|<span data-ttu-id="35700-114">描述</span><span class="sxs-lookup"><span data-stu-id="35700-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35700-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="35700-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="35700-116">子元素</span><span class="sxs-lookup"><span data-stu-id="35700-116">Child Elements</span></span>  
 <span data-ttu-id="35700-117">无。</span><span class="sxs-lookup"><span data-stu-id="35700-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35700-118">父元素</span><span class="sxs-lookup"><span data-stu-id="35700-118">Parent Elements</span></span>  
  
|<span data-ttu-id="35700-119">元素</span><span class="sxs-lookup"><span data-stu-id="35700-119">Element</span></span>|<span data-ttu-id="35700-120">描述</span><span class="sxs-lookup"><span data-stu-id="35700-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35700-121">\<serviceBehaviors > 的\<行为 ></span><span class="sxs-lookup"><span data-stu-id="35700-121">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="35700-122">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="35700-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35700-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="35700-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
