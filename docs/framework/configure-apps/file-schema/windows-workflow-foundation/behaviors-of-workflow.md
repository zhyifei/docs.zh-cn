---
title: <behaviors> 工作流
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: b7c5cf93a82ac88c25f9c478ad52cf41eb6f6d65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790294"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="07528-102">\<行为 > 的工作流</span><span class="sxs-lookup"><span data-stu-id="07528-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="07528-103">此元素包含**serviceBehaviors**集合。</span><span class="sxs-lookup"><span data-stu-id="07528-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="07528-104">集合中的每个元素定义工作流服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="07528-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="07528-105">每个行为元素由其唯一**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="07528-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="07528-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="07528-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07528-107">语法</span><span class="sxs-lookup"><span data-stu-id="07528-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07528-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="07528-108">Attributes and Elements</span></span>  
 <span data-ttu-id="07528-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="07528-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07528-110">特性</span><span class="sxs-lookup"><span data-stu-id="07528-110">Attributes</span></span>  
 <span data-ttu-id="07528-111">None</span><span class="sxs-lookup"><span data-stu-id="07528-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="07528-112">子元素</span><span class="sxs-lookup"><span data-stu-id="07528-112">Child Elements</span></span>  
  
|<span data-ttu-id="07528-113">元素</span><span class="sxs-lookup"><span data-stu-id="07528-113">Element</span></span>|<span data-ttu-id="07528-114">描述</span><span class="sxs-lookup"><span data-stu-id="07528-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07528-115">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="07528-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="07528-116">此配置节表示为特定工作流服务定义的所有行为。</span><span class="sxs-lookup"><span data-stu-id="07528-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07528-117">父元素</span><span class="sxs-lookup"><span data-stu-id="07528-117">Parent Elements</span></span>  
  
|<span data-ttu-id="07528-118">元素</span><span class="sxs-lookup"><span data-stu-id="07528-118">Element</span></span>|<span data-ttu-id="07528-119">描述</span><span class="sxs-lookup"><span data-stu-id="07528-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07528-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="07528-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="07528-121">所有工作流配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="07528-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07528-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="07528-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="07528-123">使用行为配置和扩展运行时</span><span class="sxs-lookup"><span data-stu-id="07528-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
