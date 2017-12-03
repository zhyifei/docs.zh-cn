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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bffe7cbf3cadf072a8bab88555b069983d262e38
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltbehaviorsgt-of-workflow"></a><span data-ttu-id="de271-102">工作流的 &lt;behaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="de271-102">&lt;behaviors&gt; of workflow</span></span>
<span data-ttu-id="de271-103">此元素包含**serviceBehaviors**集合。</span><span class="sxs-lookup"><span data-stu-id="de271-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="de271-104">集合中的每个元素定义工作流服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="de271-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="de271-105">每个行为元素由其唯一标识**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="de271-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="de271-106">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="de271-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de271-107">语法</span><span class="sxs-lookup"><span data-stu-id="de271-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de271-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="de271-108">Attributes and Elements</span></span>  
 <span data-ttu-id="de271-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="de271-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de271-110">特性</span><span class="sxs-lookup"><span data-stu-id="de271-110">Attributes</span></span>  
 <span data-ttu-id="de271-111">无</span><span class="sxs-lookup"><span data-stu-id="de271-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="de271-112">子元素</span><span class="sxs-lookup"><span data-stu-id="de271-112">Child Elements</span></span>  
  
|<span data-ttu-id="de271-113">元素</span><span class="sxs-lookup"><span data-stu-id="de271-113">Element</span></span>|<span data-ttu-id="de271-114">描述</span><span class="sxs-lookup"><span data-stu-id="de271-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de271-115">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="de271-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="de271-116">此配置节表示为特定工作流服务定义的所有行为。</span><span class="sxs-lookup"><span data-stu-id="de271-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="de271-117">父元素</span><span class="sxs-lookup"><span data-stu-id="de271-117">Parent Elements</span></span>  
  
|<span data-ttu-id="de271-118">元素</span><span class="sxs-lookup"><span data-stu-id="de271-118">Element</span></span>|<span data-ttu-id="de271-119">描述</span><span class="sxs-lookup"><span data-stu-id="de271-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de271-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="de271-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="de271-121">所有工作流配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="de271-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de271-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de271-122">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="de271-123">配置和扩展的运行时带有行为</span><span class="sxs-lookup"><span data-stu-id="de271-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
