---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: a22c72b7a683e3ecab4344c92e7d835a184a58d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947151"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="adc78-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="adc78-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="adc78-102">一种服务行为，可用于指定控制工作流实例如何运行的设置，包括持久性、未经处理的异常行为和空闲行为。</span><span class="sxs-lookup"><span data-stu-id="adc78-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="adc78-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="adc78-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="adc78-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="adc78-104">\<behaviors></span></span>  
<span data-ttu-id="adc78-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="adc78-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="adc78-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="adc78-106">\<behavior></span></span>  
<span data-ttu-id="adc78-107">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="adc78-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adc78-108">语法</span><span class="sxs-lookup"><span data-stu-id="adc78-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="adc78-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="adc78-109">Attributes and Elements</span></span>  
 <span data-ttu-id="adc78-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="adc78-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="adc78-111">特性</span><span class="sxs-lookup"><span data-stu-id="adc78-111">Attributes</span></span>  
  
|<span data-ttu-id="adc78-112">特性</span><span class="sxs-lookup"><span data-stu-id="adc78-112">Attribute</span></span>|<span data-ttu-id="adc78-113">描述</span><span class="sxs-lookup"><span data-stu-id="adc78-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="adc78-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="adc78-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="adc78-115">子元素</span><span class="sxs-lookup"><span data-stu-id="adc78-115">Child Elements</span></span>  
 <span data-ttu-id="adc78-116">无。</span><span class="sxs-lookup"><span data-stu-id="adc78-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="adc78-117">父元素</span><span class="sxs-lookup"><span data-stu-id="adc78-117">Parent Elements</span></span>  
  
|<span data-ttu-id="adc78-118">元素</span><span class="sxs-lookup"><span data-stu-id="adc78-118">Element</span></span>|<span data-ttu-id="adc78-119">描述</span><span class="sxs-lookup"><span data-stu-id="adc78-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="adc78-120">\<serviceBehaviors > 的\<行为 ></span><span class="sxs-lookup"><span data-stu-id="adc78-120">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="adc78-121">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="adc78-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="adc78-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="adc78-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
