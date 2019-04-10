---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 108c349a44ed3ac902652f86241c1e96a622549b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204232"
---
# <a name="behaviors"></a><span data-ttu-id="34aad-101">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="34aad-101">\<behaviors></span></span>
<span data-ttu-id="34aad-102">此元素定义名为 `endpointBehaviors` 和 `serviceBehaviors` 的两个子集合。</span><span class="sxs-lookup"><span data-stu-id="34aad-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="34aad-103">每个集合分别定义终结点和服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="34aad-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="34aad-104">每个行为元素由其唯一的 `name` 属性标识。</span><span class="sxs-lookup"><span data-stu-id="34aad-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="34aad-105">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="34aad-105">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="34aad-106">有关默认配置以及无名称绑定和行为的详细信息，请参阅[Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="34aad-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="34aad-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="34aad-107">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34aad-108">语法</span><span class="sxs-lookup"><span data-stu-id="34aad-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34aad-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="34aad-109">Attributes and Elements</span></span>  
 <span data-ttu-id="34aad-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="34aad-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34aad-111">特性</span><span class="sxs-lookup"><span data-stu-id="34aad-111">Attributes</span></span>  
 <span data-ttu-id="34aad-112">None</span><span class="sxs-lookup"><span data-stu-id="34aad-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="34aad-113">子元素</span><span class="sxs-lookup"><span data-stu-id="34aad-113">Child Elements</span></span>  
  
|<span data-ttu-id="34aad-114">元素</span><span class="sxs-lookup"><span data-stu-id="34aad-114">Element</span></span>|<span data-ttu-id="34aad-115">描述</span><span class="sxs-lookup"><span data-stu-id="34aad-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34aad-116">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="34aad-116">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="34aad-117">此配置节描述为特定终结点定义的所有行为。</span><span class="sxs-lookup"><span data-stu-id="34aad-117">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="34aad-118">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="34aad-118">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="34aad-119">此配置节描述为特定服务定义的所有行为。</span><span class="sxs-lookup"><span data-stu-id="34aad-119">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34aad-120">父元素</span><span class="sxs-lookup"><span data-stu-id="34aad-120">Parent Elements</span></span>  
  
|<span data-ttu-id="34aad-121">元素</span><span class="sxs-lookup"><span data-stu-id="34aad-121">Element</span></span>|<span data-ttu-id="34aad-122">描述</span><span class="sxs-lookup"><span data-stu-id="34aad-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34aad-123">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="34aad-123">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="34aad-124">所有 Windows Communication Foundation (WCF) 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="34aad-124">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34aad-125">备注</span><span class="sxs-lookup"><span data-stu-id="34aad-125">Remarks</span></span>  
 <span data-ttu-id="34aad-126">使用 `<remove>` 元素可以从集合中移除特定行为。</span><span class="sxs-lookup"><span data-stu-id="34aad-126">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="34aad-127">为此，您只需在 `name` 元素的 `<remove>` 特性中提供要移除的行为的名称。</span><span class="sxs-lookup"><span data-stu-id="34aad-127">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="34aad-128">还可以使用 `<clear>` 元素清除集合中的所有内容，来确保行为集合最初为空。</span><span class="sxs-lookup"><span data-stu-id="34aad-128">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34aad-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="34aad-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="34aad-130">使用行为配置和扩展运行时</span><span class="sxs-lookup"><span data-stu-id="34aad-130">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="34aad-131">配置客户端行为</span><span class="sxs-lookup"><span data-stu-id="34aad-131">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="34aad-132">指定客户端运行时行为</span><span class="sxs-lookup"><span data-stu-id="34aad-132">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="34aad-133">指定服务运行时行为</span><span class="sxs-lookup"><span data-stu-id="34aad-133">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="34aad-134">安全行为</span><span class="sxs-lookup"><span data-stu-id="34aad-134">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
