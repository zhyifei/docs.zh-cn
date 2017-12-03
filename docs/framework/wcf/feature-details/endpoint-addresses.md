---
title: "终结点地址"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- addresses [WCF]
- Windows Communication Foundation [WCF], addresses
- WCF [WCF], addresses
ms.assetid: 13f269e3-ebb1-433c-86cf-54fbd866a627
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3231e5b043dd0e65c09f25eed56341e660bf1f87
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-addresses"></a><span data-ttu-id="329b1-102">终结点地址</span><span class="sxs-lookup"><span data-stu-id="329b1-102">Endpoint Addresses</span></span>
<span data-ttu-id="329b1-103">每个终结点都具有与其关联的地址，该地址用于查找和标识终结点。</span><span class="sxs-lookup"><span data-stu-id="329b1-103">Every endpoint has an address associated with it, which is used to locate and identify the endpoint.</span></span> <span data-ttu-id="329b1-104">此地址主要包括指定终结点位置的统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="329b1-104">This address consists primarily of a Uniform Resource Identifier (URI), which specifies the location of the endpoint.</span></span> <span data-ttu-id="329b1-105">终结点地址在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 编程模型中由 <xref:System.ServiceModel.EndpointAddress> 类表示，该类包含一个可选的 <xref:System.ServiceModel.EndpointAddress.Identity%2A> 属性（允许由与一个终结点交换消息的其他终结点对该终结点进行身份验证）和一组可选的 <xref:System.ServiceModel.EndpointAddress.Headers%2A> 属性（定义到达服务所需的任何其他 SOAP 头）。</span><span class="sxs-lookup"><span data-stu-id="329b1-105">The endpoint address is represented in the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] programming model by the <xref:System.ServiceModel.EndpointAddress> class, which contains an optional <xref:System.ServiceModel.EndpointAddress.Identity%2A> property that enables the authentication of the endpoint by other endpoints that exchange messages with it, and a set of optional <xref:System.ServiceModel.EndpointAddress.Headers%2A> properties, which define any other SOAP headers required to reach the service.</span></span> <span data-ttu-id="329b1-106">可选头提供其他的更详细寻址信息以标识服务终结点或与之交互。</span><span class="sxs-lookup"><span data-stu-id="329b1-106">The optional headers provide additional and more detailed addressing information to identify or interact with the service endpoint.</span></span> <span data-ttu-id="329b1-107">终结点的地址在网络上表示为 WS-Addressing 终结点引用 (EPR)。</span><span class="sxs-lookup"><span data-stu-id="329b1-107">The address of an endpoint is represented on the wire as a WS-Addressing endpoint reference (EPR).</span></span>  
  
## <a name="uri-structure-of-an-address"></a><span data-ttu-id="329b1-108">地址的 URI 结构</span><span class="sxs-lookup"><span data-stu-id="329b1-108">URI Structure of an Address</span></span>  
 <span data-ttu-id="329b1-109">大多数传输的地址 URI 包含四个部分。</span><span class="sxs-lookup"><span data-stu-id="329b1-109">The address URI for most transports has four parts.</span></span> <span data-ttu-id="329b1-110">例如，下面详细列举了 URI http://www.fabrikam.com:322/mathservice.svc/secureEndpoint 的四个部分：</span><span class="sxs-lookup"><span data-stu-id="329b1-110">For example, the four parts of the URI http://www.fabrikam.com:322/mathservice.svc/secureEndpoint can be itemized as follows:</span></span>  
  
-   <span data-ttu-id="329b1-111">方案：http:</span><span class="sxs-lookup"><span data-stu-id="329b1-111">Scheme: http:</span></span>  
  
-   <span data-ttu-id="329b1-112">计算机：www.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="329b1-112">Machine: www.fabrikam.com</span></span>  
  
-   <span data-ttu-id="329b1-113">（可选）端口：322</span><span class="sxs-lookup"><span data-stu-id="329b1-113">(optional) Port: 322</span></span>  
  
-   <span data-ttu-id="329b1-114">路径：/mathservice.svc/secureEndpoint</span><span class="sxs-lookup"><span data-stu-id="329b1-114">Path: /mathservice.svc/secureEndpoint</span></span>  
  
## <a name="defining-an-address-for-a-service"></a><span data-ttu-id="329b1-115">定义服务地址</span><span class="sxs-lookup"><span data-stu-id="329b1-115">Defining an Address for a Service</span></span>  
 <span data-ttu-id="329b1-116">您可以通过使用代码以强制方式或通过配置以声明方式指定服务的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="329b1-116">The endpoint address for a service can be specified either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="329b1-117">在代码中定义终结点通常是不可行的，因为已部署服务的绑定和地址通常与在部署服务时所用的绑定和地址不同。</span><span class="sxs-lookup"><span data-stu-id="329b1-117">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="329b1-118">一般而言，使用配置定义服务终结点比使用代码更为可行。</span><span class="sxs-lookup"><span data-stu-id="329b1-118">Generally, it is more practical to define service endpoints using configuration rather than code.</span></span> <span data-ttu-id="329b1-119">通过在代码之外保存绑定和寻址信息，无须重新编译或重新部署应用程序即可更改它们。</span><span class="sxs-lookup"><span data-stu-id="329b1-119">Keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
### <a name="defining-an-address-in-configuration"></a><span data-ttu-id="329b1-120">在配置中定义地址</span><span class="sxs-lookup"><span data-stu-id="329b1-120">Defining an Address in Configuration</span></span>  
 <span data-ttu-id="329b1-121">若要在配置文件中定义终结点，使用[\<终结点 >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="329b1-121">To define an endpoint in a configuration file, use the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="329b1-122">有关详细信息和示例，请参阅[指定终结点地址](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)。</span><span class="sxs-lookup"><span data-stu-id="329b1-122">For details and an example, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
### <a name="defining-an-address-in-code"></a><span data-ttu-id="329b1-123">在代码中定义地址</span><span class="sxs-lookup"><span data-stu-id="329b1-123">Defining an Address in Code</span></span>  
 <span data-ttu-id="329b1-124">在代码中可以使用 <xref:System.ServiceModel.EndpointAddress> 类创建终结点地址。</span><span class="sxs-lookup"><span data-stu-id="329b1-124">An endpoint address can be created in code with the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="329b1-125">有关详细信息和示例，请参阅[指定终结点地址](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)。</span><span class="sxs-lookup"><span data-stu-id="329b1-125">For details and an example, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
### <a name="endpoints-in-wsdl"></a><span data-ttu-id="329b1-126">WSDL 中的终结点</span><span class="sxs-lookup"><span data-stu-id="329b1-126">Endpoints in WSDL</span></span>  
 <span data-ttu-id="329b1-127">在 WSDL 中终结点地址也可以表示为对应终结点的 `wsdl:port` 元素内的 WS-Addressing EPR 元素。</span><span class="sxs-lookup"><span data-stu-id="329b1-127">An endpoint address can also be represented in WSDL as a WS-Addressing EPR element inside the corresponding endpoint's `wsdl:port` element.</span></span> <span data-ttu-id="329b1-128">EPR 包含终结点的地址以及所有的地址属性。</span><span class="sxs-lookup"><span data-stu-id="329b1-128">The EPR contains the endpoint's address as well as any address properties.</span></span> <span data-ttu-id="329b1-129">有关详细信息和示例，请参阅[指定终结点地址](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)。</span><span class="sxs-lookup"><span data-stu-id="329b1-129">For details and an example, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
## <a name="multiple-iis-binding-support-in-net-framework-35"></a><span data-ttu-id="329b1-130">多个 IIS 绑定支持在.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="329b1-130">Multiple IIS Binding Support in .NET Framework 3.5</span></span>  
 <span data-ttu-id="329b1-131">Internet 服务提供商通常在同一服务器和站点上承载许多应用程序，以增加站点密度和降低总拥有成本。</span><span class="sxs-lookup"><span data-stu-id="329b1-131">Internet service providers often host many applications on the same server and site to increase the site density and lower total cost of ownership.</span></span> <span data-ttu-id="329b1-132">这些应用程序通常绑定到不同的基址。</span><span class="sxs-lookup"><span data-stu-id="329b1-132">These applications are typically bound to different base addresses.</span></span> <span data-ttu-id="329b1-133">Internet 信息服务 (IIS) 网站可以包含多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="329b1-133">An Internet Information Services (IIS) Web site can contain multiple applications.</span></span> <span data-ttu-id="329b1-134">可以通过一个或多个 IIS 绑定访问站点中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="329b1-134">The applications in a site can be accessed through one or more IIS bindings.</span></span>  
  
 <span data-ttu-id="329b1-135">IIS 绑定提供了两则信息：绑定协议和绑定信息。</span><span class="sxs-lookup"><span data-stu-id="329b1-135">IIS bindings provide two pieces of information: a binding protocol, and binding information.</span></span> <span data-ttu-id="329b1-136">绑定协议定义发生通信所依据的方案，而绑定信息是用于访问站点的信息。</span><span class="sxs-lookup"><span data-stu-id="329b1-136">The binding protocol defines the scheme over which communication occurs, and binding information is the information used to access the site.</span></span>  
  
 <span data-ttu-id="329b1-137">下面的示例演示可以存在于 IIS 绑定中的组件：</span><span class="sxs-lookup"><span data-stu-id="329b1-137">The following example shows the components that can be present in an IIS binding:</span></span>  
  
-   <span data-ttu-id="329b1-138">绑定协议：HTTP</span><span class="sxs-lookup"><span data-stu-id="329b1-138">Binding protocol: HTTP</span></span>  
  
-   <span data-ttu-id="329b1-139">绑定信息：IP 地址、端口、主机头</span><span class="sxs-lookup"><span data-stu-id="329b1-139">Binding Information: IP Address, Port, Host header</span></span>  
  
 <span data-ttu-id="329b1-140">IIS 可以为每个站点指定多个绑定，这会导致每个方案有多个基址。</span><span class="sxs-lookup"><span data-stu-id="329b1-140">IIS can specify multiple bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="329b1-141">在 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 之前，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不支持一个方案有多个地址；如果指定了多个地址，则在激活期间引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="329b1-141">Prior to [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] did not support multiple addresses for a schema and, if they were specified, threw a <xref:System.ArgumentException> during activation.</span></span>  
  
 <span data-ttu-id="329b1-142">通过 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]，Internet 服务提供商可以在同一站点上使用同一方案的不同基址承载多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="329b1-142">The [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] enables Internet service providers to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="329b1-143">例如，一个站点可能包含以下基址：</span><span class="sxs-lookup"><span data-stu-id="329b1-143">For example, a site could contain the following base addresses:</span></span>  
  
-   <span data-ttu-id="329b1-144">http://payroll.myorg.com/Service.svc</span><span class="sxs-lookup"><span data-stu-id="329b1-144">http://payroll.myorg.com/Service.svc</span></span>  
  
-   <span data-ttu-id="329b1-145">http://shipping.myorg.com/Service.svc</span><span class="sxs-lookup"><span data-stu-id="329b1-145">http://shipping.myorg.com/Service.svc</span></span>  
  
 <span data-ttu-id="329b1-146">使用 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]，可以在配置文件中指定 AppDomain 级别的前缀筛选器。</span><span class="sxs-lookup"><span data-stu-id="329b1-146">With [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], you specify a prefix filter at the AppDomain level in the configuration file.</span></span> <span data-ttu-id="329b1-147">实现此操作[ \<Baseaddressprefixfilter >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)元素，它包含的前缀列表。</span><span class="sxs-lookup"><span data-stu-id="329b1-147">You do this with the [\<baseAddressPrefixFilters>](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md) element, which contains a list of prefixes.</span></span> <span data-ttu-id="329b1-148">基于可选前缀列表筛选由 IIS 提供的传入基址。</span><span class="sxs-lookup"><span data-stu-id="329b1-148">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list.</span></span> <span data-ttu-id="329b1-149">默认情况下，如果未指定前缀，则使所有地址通过。</span><span class="sxs-lookup"><span data-stu-id="329b1-149">By default, when a prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="329b1-150">指定前缀导致仅使该方案的匹配基址通过。</span><span class="sxs-lookup"><span data-stu-id="329b1-150">Specifying the prefix results in only the matching base address for that scheme to be passed through.</span></span>  
  
 <span data-ttu-id="329b1-151">下面的配置代码示例使用前缀筛选器。</span><span class="sxs-lookup"><span data-stu-id="329b1-151">The following is an example of configuration code that uses the prefix filters.</span></span>  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="net.tcp://payroll.myorg.com:8000"/>  
        <add prefix="http://shipping.myorg.com:8000"/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="329b1-152">在前面的示例中，net.tcp://payroll.myorg.com:8000 和 http://shipping.myorg.com:8000 是其各自方案的唯一基址（已使它们通过）。</span><span class="sxs-lookup"><span data-stu-id="329b1-152">In the preceding example, net.tcp://payroll.myorg.com:8000 and http://shipping.myorg.com:8000 are the only base addresses, for their respective schemes, which are passed through.</span></span>  
  
 <span data-ttu-id="329b1-153">`baseAddressPrefixFilter` 不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="329b1-153">The `baseAddressPrefixFilter` does not support wildcards.</span></span>  
  
 <span data-ttu-id="329b1-154">IIS 提供的基址可能具有绑定到 `baseAddressPrefixFilters` 列表中不存在的其他方案的地址。</span><span class="sxs-lookup"><span data-stu-id="329b1-154">The base addresses supplied by IIS may have addresses bound to other schemes not present in `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="329b1-155">不会筛选出这些地址。</span><span class="sxs-lookup"><span data-stu-id="329b1-155">These addresses are not filtered out.</span></span>  
  
## <a name="multiple-iis-binding-support-in-net-framework-4-and-later"></a><span data-ttu-id="329b1-156">.NET Framework 4 以及更高版本中的多个 IIS 绑定支持</span><span class="sxs-lookup"><span data-stu-id="329b1-156">Multiple IIS Binding Support in .NET Framework 4 and later</span></span>  
 <span data-ttu-id="329b1-157">从 .NET 4 开始，通过将 <xref:System.ServiceModel.ServiceHostingEnvironment> 的 <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A> 设置为 True，您无需选取单个基址便可实现对 IIS 中多个绑定的支持。</span><span class="sxs-lookup"><span data-stu-id="329b1-157">Starting in .NET 4, you can enable support for multiple bindings in IIS without having to pick a single base address, by setting <xref:System.ServiceModel.ServiceHostingEnvironment>’s <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A> setting to true.</span></span> <span data-ttu-id="329b1-158">此支持限于 HTTP 协议方案。</span><span class="sxs-lookup"><span data-stu-id="329b1-158">This support is limited to HTTP protocol schemes.</span></span>  
  
 <span data-ttu-id="329b1-159">下面是一个示例的配置代码在使用 multipleSiteBindingsEnabled [ \<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)。</span><span class="sxs-lookup"><span data-stu-id="329b1-159">The following is an example of configuration code that uses multipleSiteBindingsEnabled on [\<serviceHostingEnvironment>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md).</span></span>  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment multipleSiteBindingsEnabled="true" >  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="329b1-160">对于 HTTP 和非 HTTP 协议，当使用此设置启用多个网站绑定时，忽略任何 baseAddressPrefixFilter 设置。</span><span class="sxs-lookup"><span data-stu-id="329b1-160">Any baseAddressPrefixFilters settings are ignored, for both HTTP and non-HTTP protocols, when multiple site bindings are enabled using this setting.</span></span>  
  
 <span data-ttu-id="329b1-161">有关详细信息和示例，请参阅[支持多个 IIS 站点绑定](../../../../docs/framework/wcf/feature-details/supporting-multiple-iis-site-bindings.md)和<xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A>。</span><span class="sxs-lookup"><span data-stu-id="329b1-161">For details and examples, see [Supporting Multiple IIS Site Bindings](../../../../docs/framework/wcf/feature-details/supporting-multiple-iis-site-bindings.md) and <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A>.</span></span>  
  
## <a name="extending-addressing-in-wcf-services"></a><span data-ttu-id="329b1-162">在 WCF 服务中扩展寻址</span><span class="sxs-lookup"><span data-stu-id="329b1-162">Extending Addressing in WCF Services</span></span>  
 <span data-ttu-id="329b1-163">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务的默认寻址模型使用终结点地址 URI 以达到以下目的：</span><span class="sxs-lookup"><span data-stu-id="329b1-163">The default addressing model of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services uses the endpoint address URI for the following purposes:</span></span>  
  
-   <span data-ttu-id="329b1-164">指定服务侦听地址，即终结点侦听消息的位置，</span><span class="sxs-lookup"><span data-stu-id="329b1-164">To specify the service listening address, the location at which the endpoint listens for messages,</span></span>  
  
-   <span data-ttu-id="329b1-165">指定 SOAP 地址筛选器，即终结点期望作为 SOAP 头的地址。</span><span class="sxs-lookup"><span data-stu-id="329b1-165">To specify the SOAP address filter, the address an endpoint expects as a SOAP header.</span></span>  
  
 <span data-ttu-id="329b1-166">可以单独指定用于其中每个目的的值，从而允许涉及有用方案的若干寻址扩展：</span><span class="sxs-lookup"><span data-stu-id="329b1-166">The values for each of these purposes can be specified separately, allowing several extensions of addressing that cover useful scenarios:</span></span>  
  
-   <span data-ttu-id="329b1-167">SOAP 媒介：客户端发送的消息在到达其最终目的地之前遍历一个或多个处理消息的其他服务。</span><span class="sxs-lookup"><span data-stu-id="329b1-167">SOAP intermediaries: a message sent by a client traverses one or more additional services that process the message before it reaches its final destination.</span></span> <span data-ttu-id="329b1-168">SOAP 媒介可以执行各种任务，如对消息进行缓存、路由、负载平衡或架构验证。</span><span class="sxs-lookup"><span data-stu-id="329b1-168">SOAP intermediaries can perform various tasks, such as caching, routing, load-balancing, or schema validation on the messages.</span></span> <span data-ttu-id="329b1-169">此方案是通过将消息发送到单独的物理地址（`via`，以媒介为目标），而不是仅发送到逻辑地址（`wsa:To`，以最终目的地为目标）完成的。</span><span class="sxs-lookup"><span data-stu-id="329b1-169">This scenario is accomplished by sending messages to a separate physical address (`via`) that targets the intermediary rather than just to a logical address (`wsa:To`) that targets the ultimate destination.</span></span>  
  
-   <span data-ttu-id="329b1-170">终结点的侦听地址是专用 URI，它设置为与其 `listenURI` 属性不同的值。</span><span class="sxs-lookup"><span data-stu-id="329b1-170">The listening address of the endpoint is a private URI and is set to a different value than its `listenURI` property.</span></span>  
  
 <span data-ttu-id="329b1-171">`via` 指定的传输地址是将消息发往 `to` 参数指定的、服务所在的某个其他远程地址途中应该最初发送到的地址。</span><span class="sxs-lookup"><span data-stu-id="329b1-171">The transport address that the `via` specifies is the location to which a message should initially be sent on its way to some other remote address specified by the `to` parameter at which the service is located.</span></span> <span data-ttu-id="329b1-172">在大多数 Internet 方案中，`via` URI 与服务的最终 <xref:System.ServiceModel.EndpointAddress.Uri%2A> 地址的 `to` 属性相同。</span><span class="sxs-lookup"><span data-stu-id="329b1-172">In most Internet scenarios, the `via` URI is the same as the <xref:System.ServiceModel.EndpointAddress.Uri%2A> property of the final `to` address of the service.</span></span> <span data-ttu-id="329b1-173">仅当必须执行手动路由时，才区分这两个地址。</span><span class="sxs-lookup"><span data-stu-id="329b1-173">You only distinguish between these two addresses when you must do manual routing.</span></span>  
  
### <a name="addressing-headers"></a><span data-ttu-id="329b1-174">寻址头</span><span class="sxs-lookup"><span data-stu-id="329b1-174">Addressing Headers</span></span>  
 <span data-ttu-id="329b1-175">除了其基本 URI 外，终结点可以按一个或多个 SOAP 标头寻址。</span><span class="sxs-lookup"><span data-stu-id="329b1-175">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="329b1-176">这一点在其中很有用的一组方案是一组 SOAP 媒介方案，其中终结点要求该终结点的客户端包括以媒介为目标的 SOAP 头。</span><span class="sxs-lookup"><span data-stu-id="329b1-176">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span>  
  
 <span data-ttu-id="329b1-177">可以通过两种方法定义自定义地址头 - 使用代码或使用配置：</span><span class="sxs-lookup"><span data-stu-id="329b1-177">You can define custom address headers in two ways—by using either code or configuration:</span></span>  
  
-   <span data-ttu-id="329b1-178">在代码中，通过使用 <xref:System.ServiceModel.Channels.AddressHeader> 类创建自定义地址头，然后在构造 <xref:System.ServiceModel.EndpointAddress> 时使用它。</span><span class="sxs-lookup"><span data-stu-id="329b1-178">In code, create custom address headers by using the <xref:System.ServiceModel.Channels.AddressHeader> class, and then used in the construction of an <xref:System.ServiceModel.EndpointAddress>.</span></span>  
  
-   <span data-ttu-id="329b1-179">在配置中，自定义[\<标头 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)指定的子级为[\<终结点 >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017)元素。</span><span class="sxs-lookup"><span data-stu-id="329b1-179">In configuration, custom [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) are specified as children of the [\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>  
  
 <span data-ttu-id="329b1-180">配置通常比代码更可取，因为它允许你在部署后更改头。</span><span class="sxs-lookup"><span data-stu-id="329b1-180">Configuration is generally preferable to code, as it allows you to change the headers after deployment.</span></span>  
  
### <a name="custom-listening-addresses"></a><span data-ttu-id="329b1-181">自定义侦听地址</span><span class="sxs-lookup"><span data-stu-id="329b1-181">Custom Listening Addresses</span></span>  
 <span data-ttu-id="329b1-182">可以将侦听地址设置为与终结点的 URI 不同的值。</span><span class="sxs-lookup"><span data-stu-id="329b1-182">You can set the listening address to a different value than the endpoint’s URI.</span></span> <span data-ttu-id="329b1-183">在要公开的 SOAP 地址为公共 SOAP 媒介的地址，而终结点实际侦听的地址是专用网络地址的媒介方案中，这是很有用的。</span><span class="sxs-lookup"><span data-stu-id="329b1-183">This is useful in intermediary scenarios where the SOAP address to be exposed is that of a public SOAP intermediary, whereas the address where the endpoint actually listens is a private network address.</span></span>  
  
 <span data-ttu-id="329b1-184">可以通过使用代码或配置指定自定义侦听地址：</span><span class="sxs-lookup"><span data-stu-id="329b1-184">You can specify a custom listening address by using either code or configuration:</span></span>  
  
-   <span data-ttu-id="329b1-185">在代码中，通过将 <xref:System.ServiceModel.Description.ClientViaBehavior> 类添加到终结点的行为集合指定自定义侦听地址。</span><span class="sxs-lookup"><span data-stu-id="329b1-185">In code, specify a custom listening address by adding a <xref:System.ServiceModel.Description.ClientViaBehavior> class to the endpoint’s behavior collection.</span></span>  
  
-   <span data-ttu-id="329b1-186">在配置中，指定的自定义侦听地址`ListenUri`的服务属性[\<终结点 >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017)元素。</span><span class="sxs-lookup"><span data-stu-id="329b1-186">In configuration, specify a custom listening address with the `ListenUri` attribute of the service [\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>  
  
### <a name="custom-soap-address-filter"></a><span data-ttu-id="329b1-187">自定义 SOAP 地址筛选器</span><span class="sxs-lookup"><span data-stu-id="329b1-187">Custom SOAP Address Filter</span></span>  
 <span data-ttu-id="329b1-188"><xref:System.ServiceModel.EndpointAddress.Uri%2A> 与任何 <xref:System.ServiceModel.EndpointAddress.Headers%2A> 属性联合使用，以定义终结点的 SOAP 地址筛选器 (<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>)。</span><span class="sxs-lookup"><span data-stu-id="329b1-188">The <xref:System.ServiceModel.EndpointAddress.Uri%2A> is used in conjunction with any <xref:System.ServiceModel.EndpointAddress.Headers%2A> property to define an endpoint’s SOAP address filter (<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>).</span></span> <span data-ttu-id="329b1-189">默认情况下，此筛选器验证传入消息是否具有与终结点的 URI 匹配的 `To` 消息头，以及所有必需的终结点头是否存在于消息中。</span><span class="sxs-lookup"><span data-stu-id="329b1-189">By default, this filter verifies that an incoming message has a `To` message header that matches the endpoint’s URI and that all of the required endpoint headers are present in the message.</span></span>  
  
 <span data-ttu-id="329b1-190">在某些方案中，终结点接收抵达基础传输的所有消息，而不仅仅是具有相应 `To` 头的消息。</span><span class="sxs-lookup"><span data-stu-id="329b1-190">In some scenarios, an endpoint receives all messages that arrive on the underlying transport, and not just those with the appropriate `To` header.</span></span> <span data-ttu-id="329b1-191">若要启用这一点，用户可以使用 <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> 类。</span><span class="sxs-lookup"><span data-stu-id="329b1-191">To enable this, the user can use the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329b1-192">另请参阅</span><span class="sxs-lookup"><span data-stu-id="329b1-192">See Also</span></span>  
 [<span data-ttu-id="329b1-193">指定终结点地址</span><span class="sxs-lookup"><span data-stu-id="329b1-193">Specifying an Endpoint Address</span></span>](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 [<span data-ttu-id="329b1-194">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="329b1-194">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
