---
title: <behavior> 的 <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: 489678a5adeae3965acae90a847c4b087478354d
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140810"
---
# <a name="behavior-of-endpointbehaviors"></a><span data-ttu-id="75da5-102">\<endpointBehaviors 的 \<行为 > ></span><span class="sxs-lookup"><span data-stu-id="75da5-102">\<behavior> of \<endpointBehaviors></span></span>
<span data-ttu-id="75da5-103">`behavior` 元素包含终结点行为的设置集合。</span><span class="sxs-lookup"><span data-stu-id="75da5-103">The `behavior` element contains a collection of settings for the behavior of an endpoint.</span></span> <span data-ttu-id="75da5-104">每个行为都按其 `name` 进行索引。</span><span class="sxs-lookup"><span data-stu-id="75da5-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="75da5-105">终结点可以通过此名称链接到每个行为。</span><span class="sxs-lookup"><span data-stu-id="75da5-105">Endpoints can link to each behavior through this name.</span></span> <span data-ttu-id="75da5-106">从 .NET Framework 4 开始，绑定和行为不需要具有名称。</span><span class="sxs-lookup"><span data-stu-id="75da5-106">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="75da5-107">有关默认配置和无值绑定和行为的详细信息，请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。</span><span class="sxs-lookup"><span data-stu-id="75da5-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
<span data-ttu-id="75da5-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="75da5-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="75da5-109">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="75da5-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="75da5-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="75da5-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="75da5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="75da5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="75da5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<行为 >**</span><span class="sxs-lookup"><span data-stu-id="75da5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75da5-113">语法</span><span class="sxs-lookup"><span data-stu-id="75da5-113">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75da5-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="75da5-114">Attributes and Elements</span></span>  
 <span data-ttu-id="75da5-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="75da5-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75da5-116">特性</span><span class="sxs-lookup"><span data-stu-id="75da5-116">Attributes</span></span>  
  
|<span data-ttu-id="75da5-117">特性</span><span class="sxs-lookup"><span data-stu-id="75da5-117">Attribute</span></span>|<span data-ttu-id="75da5-118">描述</span><span class="sxs-lookup"><span data-stu-id="75da5-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75da5-119">NAME</span><span class="sxs-lookup"><span data-stu-id="75da5-119">name</span></span>|<span data-ttu-id="75da5-120">一个包含行为的配置名称的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="75da5-120">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="75da5-121">此值是用户定义的一个字符串，该字符串必须是唯一的，因为它将充当元素的标识字符串。</span><span class="sxs-lookup"><span data-stu-id="75da5-121">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="75da5-122">从 .NET Framework 4 开始，绑定和行为不需要具有名称。</span><span class="sxs-lookup"><span data-stu-id="75da5-122">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="75da5-123">有关默认配置和无值绑定和行为的详细信息，请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。</span><span class="sxs-lookup"><span data-stu-id="75da5-123">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75da5-124">子元素</span><span class="sxs-lookup"><span data-stu-id="75da5-124">Child Elements</span></span>  
  
|<span data-ttu-id="75da5-125">元素</span><span class="sxs-lookup"><span data-stu-id="75da5-125">Element</span></span>|<span data-ttu-id="75da5-126">描述</span><span class="sxs-lookup"><span data-stu-id="75da5-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75da5-127">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="75da5-127">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="75da5-128">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="75da5-128">Specifies the credentials used to authenticate the client to a service.</span></span>|  
|[<span data-ttu-id="75da5-129">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="75da5-129">\<callbackDebug></span></span>](callbackdebug.md)|<span data-ttu-id="75da5-130">指定 Windows Communication Foundation （WCF）回调对象的服务调试。</span><span class="sxs-lookup"><span data-stu-id="75da5-130">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>|  
|[<span data-ttu-id="75da5-131">\<callbackTimeouts ></span><span class="sxs-lookup"><span data-stu-id="75da5-131">\<callbackTimeouts></span></span>](callbacktimeouts.md)|<span data-ttu-id="75da5-132">指定客户端回调的超时。</span><span class="sxs-lookup"><span data-stu-id="75da5-132">Specifies the timeout for the client callback.</span></span>|  
|[<span data-ttu-id="75da5-133">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="75da5-133">\<clientVia></span></span>](clientvia.md)|<span data-ttu-id="75da5-134">指定消息应采用的路由。</span><span class="sxs-lookup"><span data-stu-id="75da5-134">Specifies the route a message should take.</span></span>|  
|[<span data-ttu-id="75da5-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="75da5-135">\<dataContractSerializer></span></span>](datacontractserializer.md)|<span data-ttu-id="75da5-136">包含 DataContractSerializer 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="75da5-136">Contains configuration data for the DataContractSerializer.</span></span>|  
|[<span data-ttu-id="75da5-137">\<dispatcherSynchronization ></span><span class="sxs-lookup"><span data-stu-id="75da5-137">\<dispatcherSynchronization></span></span>](dispatchersynchronization.md)|<span data-ttu-id="75da5-138">指定允许服务进行异步答复的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="75da5-138">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>|  
|[<span data-ttu-id="75da5-139">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="75da5-139">\<enableWebScript></span></span>](enablewebscript.md)|<span data-ttu-id="75da5-140">启用终结点行为，此行为使得可以使用 ASP.NET AJAX 网页中的服务。</span><span class="sxs-lookup"><span data-stu-id="75da5-140">Enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span> <span data-ttu-id="75da5-141">该行为仅应与 \<webHttpBinding > 标准绑定或 \<w > 绑定元素一起使用。</span><span class="sxs-lookup"><span data-stu-id="75da5-141">The behavior should only be used in conjunction with either the \<webHttpBinding> standard binding, or the \<webMessageEncoding> binding element.</span></span>|  
|[<span data-ttu-id="75da5-142">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="75da5-142">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="75da5-143">指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。</span><span class="sxs-lookup"><span data-stu-id="75da5-143">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
|[<span data-ttu-id="75da5-144">\<soapProcessing ></span><span class="sxs-lookup"><span data-stu-id="75da5-144">\<soapProcessing></span></span>](soapprocessing.md)|<span data-ttu-id="75da5-145">定义用于封送不同绑定类型和消息版本之间消息的客户端终结点行为。</span><span class="sxs-lookup"><span data-stu-id="75da5-145">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>|  
|[<span data-ttu-id="75da5-146">\<synchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="75da5-146">\<synchronousReceive></span></span>](synchronousreceive-element.md)|<span data-ttu-id="75da5-147">指定服务或客户端应用程序中用于接收消息的运行时行为。</span><span class="sxs-lookup"><span data-stu-id="75da5-147">Specifies run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="75da5-148">它不具有任何属性或子元素。</span><span class="sxs-lookup"><span data-stu-id="75da5-148">It does not have any attributes or child elements.</span></span>|  
|[<span data-ttu-id="75da5-149">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="75da5-149">\<transactedBatching></span></span>](transactedbatching.md)|<span data-ttu-id="75da5-150">指定接收操作是否支持事务批处理。</span><span class="sxs-lookup"><span data-stu-id="75da5-150">Specifies whether transaction batching is supported for receive operations.</span></span>|  
|[<span data-ttu-id="75da5-151">\<Wcf-webhttp ></span><span class="sxs-lookup"><span data-stu-id="75da5-151">\<webHttp></span></span>](webhttp.md)|<span data-ttu-id="75da5-152">通过配置指定终结点上的 WebHttpBehavior。</span><span class="sxs-lookup"><span data-stu-id="75da5-152">Specifies the WebHttpBehavior on an endpoint through configuration.</span></span> <span data-ttu-id="75da5-153">此行为与 \<webHttpBinding > 标准绑定结合使用时，将为 WCF 服务启用 Web 编程模型。</span><span class="sxs-lookup"><span data-stu-id="75da5-153">This behavior, when used in conjunction with the \<webHttpBinding> standard binding, enables the Web programming model for a WCF service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="75da5-154">父元素</span><span class="sxs-lookup"><span data-stu-id="75da5-154">Parent Elements</span></span>  
  
|<span data-ttu-id="75da5-155">元素</span><span class="sxs-lookup"><span data-stu-id="75da5-155">Element</span></span>|<span data-ttu-id="75da5-156">描述</span><span class="sxs-lookup"><span data-stu-id="75da5-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75da5-157">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="75da5-157">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="75da5-158">终结点行为元素的集合。</span><span class="sxs-lookup"><span data-stu-id="75da5-158">A collection of endpoint behavior elements.</span></span>|
