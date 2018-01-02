---
title: "&lt;endpointBehaviors&gt; 的 &lt;behavior&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aed43e76b817c9a2eded6c1e5daee183625ecc0d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltbehaviorgt-of-ltendpointbehaviorsgt"></a><span data-ttu-id="1dc36-102">&lt;endpointBehaviors&gt; 的 &lt;behavior&gt;</span><span class="sxs-lookup"><span data-stu-id="1dc36-102">&lt;behavior&gt; of &lt;endpointBehaviors&gt;</span></span>
<span data-ttu-id="1dc36-103">`behavior` 元素包含终结点行为的设置集合。</span><span class="sxs-lookup"><span data-stu-id="1dc36-103">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="1dc36-104">每个行为都按其 `name` 进行索引。</span><span class="sxs-lookup"><span data-stu-id="1dc36-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="1dc36-105">终结点可以通过此名称链接到每个行为。</span><span class="sxs-lookup"><span data-stu-id="1dc36-105">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="1dc36-106">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="1dc36-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="1dc36-107">有关默认配置和无名称的绑定和行为的详细信息，请参阅[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="1dc36-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="1dc36-108">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1dc36-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="1dc36-109">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="1dc36-109">\<behaviors></span></span>  
<span data-ttu-id="1dc36-110">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1dc36-110">\<endpointBehaviors></span></span>  
<span data-ttu-id="1dc36-111">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="1dc36-111">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dc36-112">语法</span><span class="sxs-lookup"><span data-stu-id="1dc36-112">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <endpointBehaviors>  
       <behavior name="String" />  
    </endpointBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dc36-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1dc36-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1dc36-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1dc36-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dc36-115">特性</span><span class="sxs-lookup"><span data-stu-id="1dc36-115">Attributes</span></span>  
  
|<span data-ttu-id="1dc36-116">特性</span><span class="sxs-lookup"><span data-stu-id="1dc36-116">Attribute</span></span>|<span data-ttu-id="1dc36-117">描述</span><span class="sxs-lookup"><span data-stu-id="1dc36-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1dc36-118">name</span><span class="sxs-lookup"><span data-stu-id="1dc36-118">name</span></span>|<span data-ttu-id="1dc36-119">一个包含行为的配置名称的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="1dc36-119">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="1dc36-120">此值是用户定义的一个字符串，该字符串必须是唯一的，因为它将充当元素的标识字符串。</span><span class="sxs-lookup"><span data-stu-id="1dc36-120">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="1dc36-121">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="1dc36-121">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="1dc36-122">有关默认配置和无名称的绑定和行为的详细信息，请参阅[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="1dc36-122">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1dc36-123">子元素</span><span class="sxs-lookup"><span data-stu-id="1dc36-123">Child Elements</span></span>  
  
|<span data-ttu-id="1dc36-124">元素</span><span class="sxs-lookup"><span data-stu-id="1dc36-124">Element</span></span>|<span data-ttu-id="1dc36-125">描述</span><span class="sxs-lookup"><span data-stu-id="1dc36-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dc36-126">\<c a t e ></span><span class="sxs-lookup"><span data-stu-id="1dc36-126">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="1dc36-127">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="1dc36-127">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[<span data-ttu-id="1dc36-128">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="1dc36-128">\<callbackDebug></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbackdebug.md)|<span data-ttu-id="1dc36-129">指定 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 回调对象的服务调试。</span><span class="sxs-lookup"><span data-stu-id="1dc36-129">Specifies service debugging for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] callback object.</span></span>|  
|[<span data-ttu-id="1dc36-130">\<callbackTimeouts ></span><span class="sxs-lookup"><span data-stu-id="1dc36-130">\<callbackTimeouts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbacktimeouts.md)|<span data-ttu-id="1dc36-131">指定客户端回调的超时。</span><span class="sxs-lookup"><span data-stu-id="1dc36-131">Specifies the timeout for the client callback.</span></span>|  
|[<span data-ttu-id="1dc36-132">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="1dc36-132">\<clientVia></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientvia.md)|<span data-ttu-id="1dc36-133">指定消息应采用的路由。</span><span class="sxs-lookup"><span data-stu-id="1dc36-133">Specifies the route a message should take.</span></span>|  
|[<span data-ttu-id="1dc36-134">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="1dc36-134">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer.md)|<span data-ttu-id="1dc36-135">包含 DataContractSerializer 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="1dc36-135">Contains configuration data for the DataContractSerializer.</span></span>|  
|[<span data-ttu-id="1dc36-136">\<dispatcherSynchronization ></span><span class="sxs-lookup"><span data-stu-id="1dc36-136">\<dispatcherSynchronization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/dispatchersynchronization.md)|<span data-ttu-id="1dc36-137">指定允许服务进行异步答复的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="1dc36-137">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[<span data-ttu-id="1dc36-138">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="1dc36-138">\<enableWebScript></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)|<span data-ttu-id="1dc36-139">启用终结点行为，此行为使得可以使用 ASP.NET AJAX 网页中的服务。</span><span class="sxs-lookup"><span data-stu-id="1dc36-139">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="1dc36-140">此行为只应该使用结合使用\<webHttpBinding > 标准绑定，或\<webMessageEncoding > 绑定元素。</span><span class="sxs-lookup"><span data-stu-id="1dc36-140">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[<span data-ttu-id="1dc36-141">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="1dc36-141">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="1dc36-142">指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="1dc36-142">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[<span data-ttu-id="1dc36-143">\<soapProcessing ></span><span class="sxs-lookup"><span data-stu-id="1dc36-143">\<soapProcessing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md)|<span data-ttu-id="1dc36-144">定义用于封送不同绑定类型和消息版本之间消息的客户端终结点行为。</span><span class="sxs-lookup"><span data-stu-id="1dc36-144">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[<span data-ttu-id="1dc36-145">\<v e ></span><span class="sxs-lookup"><span data-stu-id="1dc36-145">\<synchronousReceive></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/synchronousreceive-element.md)|<span data-ttu-id="1dc36-146">指定服务或客户端应用程序中用于接收消息的运行时行为。</span><span class="sxs-lookup"><span data-stu-id="1dc36-146">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="1dc36-147">它不具有任何属性或子元素。</span><span class="sxs-lookup"><span data-stu-id="1dc36-147">It does not have any attributes or child elements.</span></span>|  
|[<span data-ttu-id="1dc36-148">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="1dc36-148">\<transactedBatching></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactedbatching.md)|<span data-ttu-id="1dc36-149">指定接收操作是否支持事务批处理。</span><span class="sxs-lookup"><span data-stu-id="1dc36-149">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[<span data-ttu-id="1dc36-150">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="1dc36-150">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)|<span data-ttu-id="1dc36-151">通过配置指定终结点上的 WebHttpBehavior。</span><span class="sxs-lookup"><span data-stu-id="1dc36-151">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="1dc36-152">此行为与结合使用时， \<webHttpBinding > 标准绑定，启用 Web 编程模型的[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]服务。</span><span class="sxs-lookup"><span data-stu-id="1dc36-152">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1dc36-153">父元素</span><span class="sxs-lookup"><span data-stu-id="1dc36-153">Parent Elements</span></span>  
  
|<span data-ttu-id="1dc36-154">元素</span><span class="sxs-lookup"><span data-stu-id="1dc36-154">Element</span></span>|<span data-ttu-id="1dc36-155">描述</span><span class="sxs-lookup"><span data-stu-id="1dc36-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dc36-156">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1dc36-156">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="1dc36-157">终结点行为元素的集合。</span><span class="sxs-lookup"><span data-stu-id="1dc36-157">A collection of endpoint behavior elements.</span></span>|
