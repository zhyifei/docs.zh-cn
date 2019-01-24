---
title: '&lt;workflowInstanceManagement&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: ba3d9415efc21012b470fd2e9a7f426ca8f3aad1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662057"
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="a36c5-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="a36c5-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="a36c5-103">一种服务行为，可用于指定控制工作流实例如何运行的设置，包括持久性、未经处理的异常行为和空闲行为。</span><span class="sxs-lookup"><span data-stu-id="a36c5-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="a36c5-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a36c5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a36c5-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a36c5-105">\<behaviors></span></span>  
<span data-ttu-id="a36c5-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a36c5-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a36c5-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a36c5-107">\<behavior></span></span>  
<span data-ttu-id="a36c5-108">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="a36c5-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a36c5-109">语法</span><span class="sxs-lookup"><span data-stu-id="a36c5-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a36c5-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a36c5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a36c5-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a36c5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a36c5-112">特性</span><span class="sxs-lookup"><span data-stu-id="a36c5-112">Attributes</span></span>  
  
|<span data-ttu-id="a36c5-113">特性</span><span class="sxs-lookup"><span data-stu-id="a36c5-113">Attribute</span></span>|<span data-ttu-id="a36c5-114">描述</span><span class="sxs-lookup"><span data-stu-id="a36c5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a36c5-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="a36c5-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="a36c5-116">子元素</span><span class="sxs-lookup"><span data-stu-id="a36c5-116">Child Elements</span></span>  
 <span data-ttu-id="a36c5-117">无。</span><span class="sxs-lookup"><span data-stu-id="a36c5-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a36c5-118">父元素</span><span class="sxs-lookup"><span data-stu-id="a36c5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a36c5-119">元素</span><span class="sxs-lookup"><span data-stu-id="a36c5-119">Element</span></span>|<span data-ttu-id="a36c5-120">描述</span><span class="sxs-lookup"><span data-stu-id="a36c5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a36c5-121">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a36c5-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="a36c5-122">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="a36c5-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a36c5-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="a36c5-123">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
