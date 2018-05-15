---
title: '&lt;行为&gt;'
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: ca9cf5daa6590c14d4b5fd15c502d67af1f93b52
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltbehaviorsgt"></a><span data-ttu-id="2a526-102">&lt;行为&gt;</span><span class="sxs-lookup"><span data-stu-id="2a526-102">&lt;behaviors&gt;</span></span>
<span data-ttu-id="2a526-103">此元素定义名为 `endpointBehaviors` 和 `serviceBehaviors` 的两个子集合。</span><span class="sxs-lookup"><span data-stu-id="2a526-103">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="2a526-104">每个集合分别定义终结点和服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="2a526-104">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="2a526-105">每个行为元素由其唯一的 `name` 属性标识。</span><span class="sxs-lookup"><span data-stu-id="2a526-105">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="2a526-106">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="2a526-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="2a526-107">有关默认配置和无名称的绑定和行为的详细信息，请参阅[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="2a526-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="2a526-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2a526-108">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a526-109">语法</span><span class="sxs-lookup"><span data-stu-id="2a526-109">Syntax</span></span>  
  
```xml  
<behaviors>  
   <serviceBehaviors>  
   </serviceBehaviors>  
   <endpointBehaviors>  
   </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a526-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2a526-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2a526-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2a526-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a526-112">特性</span><span class="sxs-lookup"><span data-stu-id="2a526-112">Attributes</span></span>  
 <span data-ttu-id="2a526-113">无</span><span class="sxs-lookup"><span data-stu-id="2a526-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2a526-114">子元素</span><span class="sxs-lookup"><span data-stu-id="2a526-114">Child Elements</span></span>  
  
|<span data-ttu-id="2a526-115">元素</span><span class="sxs-lookup"><span data-stu-id="2a526-115">Element</span></span>|<span data-ttu-id="2a526-116">描述</span><span class="sxs-lookup"><span data-stu-id="2a526-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a526-117">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2a526-117">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="2a526-118">此配置节描述为特定终结点定义的所有行为。</span><span class="sxs-lookup"><span data-stu-id="2a526-118">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="2a526-119">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2a526-119">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="2a526-120">此配置节描述为特定服务定义的所有行为。</span><span class="sxs-lookup"><span data-stu-id="2a526-120">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a526-121">父元素</span><span class="sxs-lookup"><span data-stu-id="2a526-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2a526-122">元素</span><span class="sxs-lookup"><span data-stu-id="2a526-122">Element</span></span>|<span data-ttu-id="2a526-123">描述</span><span class="sxs-lookup"><span data-stu-id="2a526-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a526-124">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2a526-124">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="2a526-125">所有 Windows Communication Foundation (WCF) 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="2a526-125">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a526-126">备注</span><span class="sxs-lookup"><span data-stu-id="2a526-126">Remarks</span></span>  
 <span data-ttu-id="2a526-127">使用 `<remove>` 元素可以从集合中移除特定行为。</span><span class="sxs-lookup"><span data-stu-id="2a526-127">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="2a526-128">为此，您只需在 `name` 元素的 `<remove>` 特性中提供要移除的行为的名称。</span><span class="sxs-lookup"><span data-stu-id="2a526-128">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="2a526-129">还可以使用 `<clear>` 元素清除集合中的所有内容，来确保行为集合最初为空。</span><span class="sxs-lookup"><span data-stu-id="2a526-129">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a526-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a526-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="2a526-131">使用行为配置和扩展运行时</span><span class="sxs-lookup"><span data-stu-id="2a526-131">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 [<span data-ttu-id="2a526-132">配置客户端行为</span><span class="sxs-lookup"><span data-stu-id="2a526-132">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [<span data-ttu-id="2a526-133">指定客户端运行时行为</span><span class="sxs-lookup"><span data-stu-id="2a526-133">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [<span data-ttu-id="2a526-134">指定服务运行时行为</span><span class="sxs-lookup"><span data-stu-id="2a526-134">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)  
 [<span data-ttu-id="2a526-135">安全行为</span><span class="sxs-lookup"><span data-stu-id="2a526-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
