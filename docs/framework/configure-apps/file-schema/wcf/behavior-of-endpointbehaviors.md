---
title: <behavior> 的 <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: f14e80798a9b088508f23d718c8b386286ad65a3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919840"
---
# <a name="behavior-of-endpointbehaviors"></a><span data-ttu-id="9d42a-102">\<endpointBehaviors > 的\<行为 ></span><span class="sxs-lookup"><span data-stu-id="9d42a-102">\<behavior> of \<endpointBehaviors></span></span>
<span data-ttu-id="9d42a-103">`behavior` 元素包含终结点行为的设置集合。</span><span class="sxs-lookup"><span data-stu-id="9d42a-103">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="9d42a-104">每个行为都按其 `name` 进行索引。</span><span class="sxs-lookup"><span data-stu-id="9d42a-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="9d42a-105">终结点可以通过此名称链接到每个行为。</span><span class="sxs-lookup"><span data-stu-id="9d42a-105">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="9d42a-106">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="9d42a-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9d42a-107">有关默认配置和无值绑定和行为的详细信息, 请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。</span><span class="sxs-lookup"><span data-stu-id="9d42a-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="9d42a-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9d42a-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="9d42a-109">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="9d42a-109">\<behaviors></span></span>  
<span data-ttu-id="9d42a-110">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="9d42a-110">\<endpointBehaviors></span></span>  
<span data-ttu-id="9d42a-111">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="9d42a-111">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d42a-112">语法</span><span class="sxs-lookup"><span data-stu-id="9d42a-112">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d42a-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9d42a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9d42a-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9d42a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d42a-115">特性</span><span class="sxs-lookup"><span data-stu-id="9d42a-115">Attributes</span></span>  
  
|<span data-ttu-id="9d42a-116">特性</span><span class="sxs-lookup"><span data-stu-id="9d42a-116">Attribute</span></span>|<span data-ttu-id="9d42a-117">描述</span><span class="sxs-lookup"><span data-stu-id="9d42a-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d42a-118">NAME</span><span class="sxs-lookup"><span data-stu-id="9d42a-118">name</span></span>|<span data-ttu-id="9d42a-119">一个包含行为的配置名称的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="9d42a-119">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="9d42a-120">此值是用户定义的一个字符串，该字符串必须是唯一的，因为它将充当元素的标识字符串。</span><span class="sxs-lookup"><span data-stu-id="9d42a-120">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="9d42a-121">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="9d42a-121">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9d42a-122">有关默认配置和无值绑定和行为的详细信息, 请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。</span><span class="sxs-lookup"><span data-stu-id="9d42a-122">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d42a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="9d42a-123">Child Elements</span></span>  
  
|<span data-ttu-id="9d42a-124">元素</span><span class="sxs-lookup"><span data-stu-id="9d42a-124">Element</span></span>|<span data-ttu-id="9d42a-125">描述</span><span class="sxs-lookup"><span data-stu-id="9d42a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d42a-126">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="9d42a-126">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="9d42a-127">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="9d42a-127">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[<span data-ttu-id="9d42a-128">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="9d42a-128">\<callbackDebug></span></span>](callbackdebug.md)|<span data-ttu-id="9d42a-129">指定 Windows Communication Foundation (WCF) 回调对象的服务调试。</span><span class="sxs-lookup"><span data-stu-id="9d42a-129">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>|  
|[<span data-ttu-id="9d42a-130">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="9d42a-130">\<callbackTimeouts></span></span>](callbacktimeouts.md)|<span data-ttu-id="9d42a-131">指定客户端回调的超时。</span><span class="sxs-lookup"><span data-stu-id="9d42a-131">Specifies the timeout for the client callback.</span></span>|  
|[<span data-ttu-id="9d42a-132">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="9d42a-132">\<clientVia></span></span>](clientvia.md)|<span data-ttu-id="9d42a-133">指定消息应采用的路由。</span><span class="sxs-lookup"><span data-stu-id="9d42a-133">Specifies the route a message should take.</span></span>|  
|[<span data-ttu-id="9d42a-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="9d42a-134">\<dataContractSerializer></span></span>](datacontractserializer.md)|<span data-ttu-id="9d42a-135">包含 DataContractSerializer 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="9d42a-135">Contains configuration data for the DataContractSerializer.</span></span>|  
|[<span data-ttu-id="9d42a-136">\<dispatcherSynchronization></span><span class="sxs-lookup"><span data-stu-id="9d42a-136">\<dispatcherSynchronization></span></span>](dispatchersynchronization.md)|<span data-ttu-id="9d42a-137">指定允许服务进行异步答复的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="9d42a-137">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[<span data-ttu-id="9d42a-138">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="9d42a-138">\<enableWebScript></span></span>](enablewebscript.md)|<span data-ttu-id="9d42a-139">启用终结点行为，此行为使得可以使用 ASP.NET AJAX 网页中的服务。</span><span class="sxs-lookup"><span data-stu-id="9d42a-139">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="9d42a-140">该行为只应与\<webHttpBinding > 标准绑定\<或 w > 绑定元素一起使用。</span><span class="sxs-lookup"><span data-stu-id="9d42a-140">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[<span data-ttu-id="9d42a-141">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="9d42a-141">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="9d42a-142">指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="9d42a-142">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[<span data-ttu-id="9d42a-143">\<soapProcessing></span><span class="sxs-lookup"><span data-stu-id="9d42a-143">\<soapProcessing></span></span>](soapprocessing.md)|<span data-ttu-id="9d42a-144">定义用于封送不同绑定类型和消息版本之间消息的客户端终结点行为。</span><span class="sxs-lookup"><span data-stu-id="9d42a-144">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[<span data-ttu-id="9d42a-145">\<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="9d42a-145">\<synchronousReceive></span></span>](synchronousreceive-element.md)|<span data-ttu-id="9d42a-146">指定服务或客户端应用程序中用于接收消息的运行时行为。</span><span class="sxs-lookup"><span data-stu-id="9d42a-146">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="9d42a-147">它不具有任何属性或子元素。</span><span class="sxs-lookup"><span data-stu-id="9d42a-147">It does not have any attributes or child elements.</span></span>|  
|[<span data-ttu-id="9d42a-148">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="9d42a-148">\<transactedBatching></span></span>](transactedbatching.md)|<span data-ttu-id="9d42a-149">指定接收操作是否支持事务批处理。</span><span class="sxs-lookup"><span data-stu-id="9d42a-149">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[<span data-ttu-id="9d42a-150">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="9d42a-150">\<webHttp></span></span>](webhttp.md)|<span data-ttu-id="9d42a-151">通过配置指定终结点上的 WebHttpBehavior。</span><span class="sxs-lookup"><span data-stu-id="9d42a-151">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="9d42a-152">此行为与\<webHttpBinding > 标准绑定结合使用时, 将为 WCF 服务启用 Web 编程模型。</span><span class="sxs-lookup"><span data-stu-id="9d42a-152">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a WCF service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9d42a-153">父元素</span><span class="sxs-lookup"><span data-stu-id="9d42a-153">Parent Elements</span></span>  
  
|<span data-ttu-id="9d42a-154">元素</span><span class="sxs-lookup"><span data-stu-id="9d42a-154">Element</span></span>|<span data-ttu-id="9d42a-155">描述</span><span class="sxs-lookup"><span data-stu-id="9d42a-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d42a-156">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="9d42a-156">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="9d42a-157">终结点行为元素的集合。</span><span class="sxs-lookup"><span data-stu-id="9d42a-157">A collection of endpoint behavior elements.</span></span>|
