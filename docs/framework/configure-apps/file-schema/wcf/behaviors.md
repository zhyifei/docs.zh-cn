---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 8fcb5ac0c552d1ac2e849c95a5c0757d0c142f3d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926398"
---
# <a name="behaviors"></a><span data-ttu-id="eb5ba-101">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="eb5ba-101">\<behaviors></span></span>
<span data-ttu-id="eb5ba-102">此元素定义名为 `endpointBehaviors` 和 `serviceBehaviors` 的两个子集合。</span><span class="sxs-lookup"><span data-stu-id="eb5ba-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="eb5ba-103">每个集合分别定义终结点和服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="eb5ba-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="eb5ba-104">每个行为元素由其唯一的 `name` 属性标识。</span><span class="sxs-lookup"><span data-stu-id="eb5ba-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="eb5ba-105">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="eb5ba-105">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="eb5ba-106">有关默认配置和无值绑定和行为的详细信息, 请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。</span><span class="sxs-lookup"><span data-stu-id="eb5ba-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="eb5ba-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="eb5ba-107">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb5ba-108">语法</span><span class="sxs-lookup"><span data-stu-id="eb5ba-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb5ba-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="eb5ba-109">Attributes and Elements</span></span>  
 <span data-ttu-id="eb5ba-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="eb5ba-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb5ba-111">特性</span><span class="sxs-lookup"><span data-stu-id="eb5ba-111">Attributes</span></span>  
 <span data-ttu-id="eb5ba-112">无</span><span class="sxs-lookup"><span data-stu-id="eb5ba-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb5ba-113">子元素</span><span class="sxs-lookup"><span data-stu-id="eb5ba-113">Child Elements</span></span>  
  
|<span data-ttu-id="eb5ba-114">元素</span><span class="sxs-lookup"><span data-stu-id="eb5ba-114">Element</span></span>|<span data-ttu-id="eb5ba-115">描述</span><span class="sxs-lookup"><span data-stu-id="eb5ba-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb5ba-116">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="eb5ba-116">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="eb5ba-117">此配置节描述为特定终结点定义的所有行为。</span><span class="sxs-lookup"><span data-stu-id="eb5ba-117">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="eb5ba-118">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="eb5ba-118">\<serviceBehaviors></span></span>](servicebehaviors.md)|<span data-ttu-id="eb5ba-119">此配置节描述为特定服务定义的所有行为。</span><span class="sxs-lookup"><span data-stu-id="eb5ba-119">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb5ba-120">父元素</span><span class="sxs-lookup"><span data-stu-id="eb5ba-120">Parent Elements</span></span>  
  
|<span data-ttu-id="eb5ba-121">元素</span><span class="sxs-lookup"><span data-stu-id="eb5ba-121">Element</span></span>|<span data-ttu-id="eb5ba-122">描述</span><span class="sxs-lookup"><span data-stu-id="eb5ba-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb5ba-123">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="eb5ba-123">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="eb5ba-124">所有 Windows Communication Foundation (WCF) 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="eb5ba-124">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb5ba-125">备注</span><span class="sxs-lookup"><span data-stu-id="eb5ba-125">Remarks</span></span>  
 <span data-ttu-id="eb5ba-126">使用 `<remove>` 元素可以从集合中移除特定行为。</span><span class="sxs-lookup"><span data-stu-id="eb5ba-126">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="eb5ba-127">为此，您只需在 `name` 元素的 `<remove>` 特性中提供要移除的行为的名称。</span><span class="sxs-lookup"><span data-stu-id="eb5ba-127">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="eb5ba-128">还可以使用 `<clear>` 元素清除集合中的所有内容，来确保行为集合最初为空。</span><span class="sxs-lookup"><span data-stu-id="eb5ba-128">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb5ba-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb5ba-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="eb5ba-130">使用行为配置和扩展运行时</span><span class="sxs-lookup"><span data-stu-id="eb5ba-130">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="eb5ba-131">配置客户端行为</span><span class="sxs-lookup"><span data-stu-id="eb5ba-131">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="eb5ba-132">指定客户端运行时行为</span><span class="sxs-lookup"><span data-stu-id="eb5ba-132">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="eb5ba-133">指定服务运行时行为</span><span class="sxs-lookup"><span data-stu-id="eb5ba-133">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="eb5ba-134">安全行为</span><span class="sxs-lookup"><span data-stu-id="eb5ba-134">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
