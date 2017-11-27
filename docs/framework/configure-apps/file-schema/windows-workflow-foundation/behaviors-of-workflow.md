---
title: "工作流的 &lt;behaviors&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40278c0a3d99dd5c37df1d642b8a2e13e9f62633
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltbehaviorsgt-of-workflow"></a><span data-ttu-id="e2c7b-102">工作流的 &lt;behaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="e2c7b-102">&lt;behaviors&gt; of workflow</span></span>
<span data-ttu-id="e2c7b-103">此元素包含**serviceBehaviors**集合。</span><span class="sxs-lookup"><span data-stu-id="e2c7b-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="e2c7b-104">集合中的每个元素定义工作流服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="e2c7b-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="e2c7b-105">每个行为元素由其唯一标识**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="e2c7b-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="e2c7b-106">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e2c7b-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2c7b-107">语法</span><span class="sxs-lookup"><span data-stu-id="e2c7b-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2c7b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e2c7b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e2c7b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e2c7b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2c7b-110">特性</span><span class="sxs-lookup"><span data-stu-id="e2c7b-110">Attributes</span></span>  
 <span data-ttu-id="e2c7b-111">无</span><span class="sxs-lookup"><span data-stu-id="e2c7b-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e2c7b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e2c7b-112">Child Elements</span></span>  
  
|<span data-ttu-id="e2c7b-113">元素</span><span class="sxs-lookup"><span data-stu-id="e2c7b-113">Element</span></span>|<span data-ttu-id="e2c7b-114">描述</span><span class="sxs-lookup"><span data-stu-id="e2c7b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2c7b-115">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e2c7b-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="e2c7b-116">此配置节表示为特定工作流服务定义的所有行为。</span><span class="sxs-lookup"><span data-stu-id="e2c7b-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e2c7b-117">父元素</span><span class="sxs-lookup"><span data-stu-id="e2c7b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e2c7b-118">元素</span><span class="sxs-lookup"><span data-stu-id="e2c7b-118">Element</span></span>|<span data-ttu-id="e2c7b-119">描述</span><span class="sxs-lookup"><span data-stu-id="e2c7b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2c7b-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e2c7b-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="e2c7b-121">所有工作流配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="e2c7b-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2c7b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2c7b-122">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="e2c7b-123">配置和扩展的运行时带有行为</span><span class="sxs-lookup"><span data-stu-id="e2c7b-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
