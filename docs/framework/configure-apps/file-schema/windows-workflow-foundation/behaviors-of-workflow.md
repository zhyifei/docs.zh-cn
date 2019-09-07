---
title: <behaviors>的工作流
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 05a15cdf5c043eb5d94b36028324310d2b7a8413
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398881"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="f4c1f-102">\<工作流 > 行为</span><span class="sxs-lookup"><span data-stu-id="f4c1f-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="f4c1f-103">此元素包含**serviceBehaviors**集合。</span><span class="sxs-lookup"><span data-stu-id="f4c1f-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="f4c1f-104">集合中的每个元素定义工作流服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="f4c1f-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="f4c1f-105">每个行为元素都由其唯一**名称**属性标识。</span><span class="sxs-lookup"><span data-stu-id="f4c1f-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
<span data-ttu-id="f4c1f-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f4c1f-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f4c1f-107">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f4c1f-107">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="f4c1f-108">&nbsp;&nbsp;&nbsp;&nbsp; **\<行为 >**</span><span class="sxs-lookup"><span data-stu-id="f4c1f-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4c1f-109">语法</span><span class="sxs-lookup"><span data-stu-id="f4c1f-109">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4c1f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f4c1f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f4c1f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f4c1f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4c1f-112">特性</span><span class="sxs-lookup"><span data-stu-id="f4c1f-112">Attributes</span></span>  
 <span data-ttu-id="f4c1f-113">无</span><span class="sxs-lookup"><span data-stu-id="f4c1f-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f4c1f-114">子元素</span><span class="sxs-lookup"><span data-stu-id="f4c1f-114">Child Elements</span></span>  
  
|<span data-ttu-id="f4c1f-115">元素</span><span class="sxs-lookup"><span data-stu-id="f4c1f-115">Element</span></span>|<span data-ttu-id="f4c1f-116">描述</span><span class="sxs-lookup"><span data-stu-id="f4c1f-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4c1f-117">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f4c1f-117">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="f4c1f-118">此配置节表示为特定工作流服务定义的所有行为。</span><span class="sxs-lookup"><span data-stu-id="f4c1f-118">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f4c1f-119">父元素</span><span class="sxs-lookup"><span data-stu-id="f4c1f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f4c1f-120">元素</span><span class="sxs-lookup"><span data-stu-id="f4c1f-120">Element</span></span>|<span data-ttu-id="f4c1f-121">描述</span><span class="sxs-lookup"><span data-stu-id="f4c1f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4c1f-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f4c1f-122">\<system.serviceModel></span></span>](../wcf/system-servicemodel.md)|<span data-ttu-id="f4c1f-123">所有工作流配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="f4c1f-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4c1f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4c1f-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="f4c1f-125">使用行为配置和扩展运行时</span><span class="sxs-lookup"><span data-stu-id="f4c1f-125">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
