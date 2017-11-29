---
title: '&lt;workflowInstanceManagement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9883cedbbe3657eb82c25abbad66487e39ce2579
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="313a9-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="313a9-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="313a9-103">一种服务行为，可用于指定控制工作流实例如何运行的设置，包括持久性、未经处理的异常行为和空闲行为。</span><span class="sxs-lookup"><span data-stu-id="313a9-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="313a9-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="313a9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="313a9-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="313a9-105">\<behaviors></span></span>  
<span data-ttu-id="313a9-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="313a9-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="313a9-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="313a9-107">\<behavior></span></span>  
<span data-ttu-id="313a9-108">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="313a9-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="313a9-109">语法</span><span class="sxs-lookup"><span data-stu-id="313a9-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="313a9-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="313a9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="313a9-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="313a9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="313a9-112">特性</span><span class="sxs-lookup"><span data-stu-id="313a9-112">Attributes</span></span>  
  
|<span data-ttu-id="313a9-113">特性</span><span class="sxs-lookup"><span data-stu-id="313a9-113">Attribute</span></span>|<span data-ttu-id="313a9-114">描述</span><span class="sxs-lookup"><span data-stu-id="313a9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="313a9-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="313a9-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="313a9-116">子元素</span><span class="sxs-lookup"><span data-stu-id="313a9-116">Child Elements</span></span>  
 <span data-ttu-id="313a9-117">无。</span><span class="sxs-lookup"><span data-stu-id="313a9-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="313a9-118">父元素</span><span class="sxs-lookup"><span data-stu-id="313a9-118">Parent Elements</span></span>  
  
|<span data-ttu-id="313a9-119">元素</span><span class="sxs-lookup"><span data-stu-id="313a9-119">Element</span></span>|<span data-ttu-id="313a9-120">描述</span><span class="sxs-lookup"><span data-stu-id="313a9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="313a9-121">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="313a9-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="313a9-122">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="313a9-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="313a9-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="313a9-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
