---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 98bc1b24da6e65a11a39d133057c1bb55b003a58
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191609"
---
# <a name="workflowinstancemanagement"></a><span data-ttu-id="160fb-101">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="160fb-101">\<workflowInstanceManagement></span></span>
<span data-ttu-id="160fb-102">一种服务行为，可用于指定控制工作流实例如何运行的设置，包括持久性、未经处理的异常行为和空闲行为。</span><span class="sxs-lookup"><span data-stu-id="160fb-102">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="160fb-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="160fb-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="160fb-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="160fb-104">\<behaviors></span></span>  
<span data-ttu-id="160fb-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="160fb-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="160fb-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="160fb-106">\<behavior></span></span>  
<span data-ttu-id="160fb-107">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="160fb-107">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="160fb-108">语法</span><span class="sxs-lookup"><span data-stu-id="160fb-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="160fb-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="160fb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="160fb-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="160fb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="160fb-111">特性</span><span class="sxs-lookup"><span data-stu-id="160fb-111">Attributes</span></span>  
  
|<span data-ttu-id="160fb-112">特性</span><span class="sxs-lookup"><span data-stu-id="160fb-112">Attribute</span></span>|<span data-ttu-id="160fb-113">描述</span><span class="sxs-lookup"><span data-stu-id="160fb-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="160fb-114">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="160fb-114">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="160fb-115">子元素</span><span class="sxs-lookup"><span data-stu-id="160fb-115">Child Elements</span></span>  
 <span data-ttu-id="160fb-116">无。</span><span class="sxs-lookup"><span data-stu-id="160fb-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="160fb-117">父元素</span><span class="sxs-lookup"><span data-stu-id="160fb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="160fb-118">元素</span><span class="sxs-lookup"><span data-stu-id="160fb-118">Element</span></span>|<span data-ttu-id="160fb-119">描述</span><span class="sxs-lookup"><span data-stu-id="160fb-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="160fb-120">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="160fb-120">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="160fb-121">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="160fb-121">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="160fb-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="160fb-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
