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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3be696133bff5c1fc8858ab31093866ed05c98a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="45529-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="45529-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="45529-103">一种服务行为，可用于指定控制工作流实例如何运行的设置，包括持久性、未经处理的异常行为和空闲行为。</span><span class="sxs-lookup"><span data-stu-id="45529-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="45529-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="45529-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="45529-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="45529-105">\<behaviors></span></span>  
<span data-ttu-id="45529-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="45529-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="45529-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="45529-107">\<behavior></span></span>  
<span data-ttu-id="45529-108">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="45529-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45529-109">语法</span><span class="sxs-lookup"><span data-stu-id="45529-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45529-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="45529-110">Attributes and Elements</span></span>  
 <span data-ttu-id="45529-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="45529-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45529-112">特性</span><span class="sxs-lookup"><span data-stu-id="45529-112">Attributes</span></span>  
  
|<span data-ttu-id="45529-113">特性</span><span class="sxs-lookup"><span data-stu-id="45529-113">Attribute</span></span>|<span data-ttu-id="45529-114">描述</span><span class="sxs-lookup"><span data-stu-id="45529-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45529-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="45529-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="45529-116">子元素</span><span class="sxs-lookup"><span data-stu-id="45529-116">Child Elements</span></span>  
 <span data-ttu-id="45529-117">无。</span><span class="sxs-lookup"><span data-stu-id="45529-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45529-118">父元素</span><span class="sxs-lookup"><span data-stu-id="45529-118">Parent Elements</span></span>  
  
|<span data-ttu-id="45529-119">元素</span><span class="sxs-lookup"><span data-stu-id="45529-119">Element</span></span>|<span data-ttu-id="45529-120">描述</span><span class="sxs-lookup"><span data-stu-id="45529-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45529-121">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="45529-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="45529-122">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="45529-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45529-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="45529-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
