---
title: '&lt;serviceMetadata&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b0b98c637c98c75aab5009f9a2f35b8ce6b90012
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="ltservicemetadatagt"></a><span data-ttu-id="57002-102">&lt;serviceMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="57002-102">&lt;serviceMetadata&gt;</span></span>
<span data-ttu-id="57002-103">指定服务元数据的发布和相关信息。</span><span class="sxs-lookup"><span data-stu-id="57002-103">Specifies the publication of service metadata and associated information.</span></span>  
  
<span data-ttu-id="57002-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="57002-104">\<system.serviceModel></span></span>  
<span data-ttu-id="57002-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="57002-105">\<behaviors></span></span>  
<span data-ttu-id="57002-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="57002-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="57002-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="57002-107">\<behavior></span></span>  
<span data-ttu-id="57002-108">\<serviceMetadata ></span><span class="sxs-lookup"><span data-stu-id="57002-108">\<serviceMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57002-109">语法</span><span class="sxs-lookup"><span data-stu-id="57002-109">Syntax</span></span>  
  
```xml
<serviceMetadata externalMetadataLocation="String"  
                 httpGetBinding="String" 
                 httpGetBindingConfiguration="String"  
                 httpGetEnabled="Boolean" 
                 httpGetUrl="String" 
                 httpsGetBinding="String" 
                 httpsGetBindingConfiguration="String"  
                 httpsGetEnabled="Boolean"   
                 httpsGetUrl="String"  
                 policyVersion="Policy12/Policy15" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57002-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="57002-110">Attributes and Elements</span></span>  
 <span data-ttu-id="57002-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="57002-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57002-112">特性</span><span class="sxs-lookup"><span data-stu-id="57002-112">Attributes</span></span>  
  
|<span data-ttu-id="57002-113">特性</span><span class="sxs-lookup"><span data-stu-id="57002-113">Attribute</span></span>|<span data-ttu-id="57002-114">描述</span><span class="sxs-lookup"><span data-stu-id="57002-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="57002-115">externalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="57002-115">externalMetadataLocation</span></span>|<span data-ttu-id="57002-116">一个包含 WSDL 文件的位置的 URI，该文件将返回到用户以响应 WSDL 和 MEX 请求而非自动生成的 WSDL。</span><span class="sxs-lookup"><span data-stu-id="57002-116">A Uri that contains the location of a WSDL file, which is returned to the user in response to WSDL and MEX requests instead of the auto-generated WSDL.</span></span> <span data-ttu-id="57002-117">当未设置此属性时，将返回默认的 WSDL。</span><span class="sxs-lookup"><span data-stu-id="57002-117">When this attribute is not set, the default WSDL is returned.</span></span> <span data-ttu-id="57002-118">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="57002-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="57002-119">httpGetBinding</span><span class="sxs-lookup"><span data-stu-id="57002-119">httpGetBinding</span></span>|<span data-ttu-id="57002-120">一个字符串，指定将用于通过 HTTP GET 进行元数据检索的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="57002-120">A string that specifies the type of the binding that will be used for metadata retrieval via HTTP GET.</span></span> <span data-ttu-id="57002-121">此设置是可选的。</span><span class="sxs-lookup"><span data-stu-id="57002-121">This setting is optional.</span></span> <span data-ttu-id="57002-122">如果未指定此设置，则将使用默认绑定。</span><span class="sxs-lookup"><span data-stu-id="57002-122">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="57002-123">仅支持具有支持 <xref:System.ServiceModel.Channels.IReplyChannel> 的内部绑定元素的绑定。</span><span class="sxs-lookup"><span data-stu-id="57002-123">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="57002-124">此外，绑定的 <xref:System.ServiceModel.Channels.MessageVersion> 属性必须为 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>。</span><span class="sxs-lookup"><span data-stu-id="57002-124">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="57002-125">httpGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="57002-125">httpGetBindingConfiguration</span></span>|<span data-ttu-id="57002-126">一个字符串，用于设置在 `httpGetBinding` 特性中指定的绑定的名称，此名称引用此绑定的其他配置信息。</span><span class="sxs-lookup"><span data-stu-id="57002-126">A string that sets the name of the binding that is specified in the `httpGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="57002-127">必须在 `<bindings>` 节中定义相同的名称。</span><span class="sxs-lookup"><span data-stu-id="57002-127">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="57002-128">httpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="57002-128">httpGetEnabled</span></span>|<span data-ttu-id="57002-129">一个布尔值，指定是否发布服务元数据以便使用 HTTP/Get 请求进行检索。</span><span class="sxs-lookup"><span data-stu-id="57002-129">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="57002-130">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="57002-130">The default is `false`.</span></span><br /><br /> <span data-ttu-id="57002-131">如果未指定 httpGetUrl 属性，则发布元数据的地址为服务地址加上“?wsdl”。</span><span class="sxs-lookup"><span data-stu-id="57002-131">If the httpGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="57002-132">例如，如果服务地址为"http://localhost:8080/CalculatorService"，则 HTTP/Get 元数据地址为"http://localhost:8080/CalculatorService?wsdl"。</span><span class="sxs-lookup"><span data-stu-id="57002-132">For example, if the service address is "http://localhost:8080/CalculatorService", the HTTP/Get metadata address is "http://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="57002-133">如果此属性为`false`，或服务的地址不基于 HTTP 或 HTTPS，"？ wsdl"将被忽略。</span><span class="sxs-lookup"><span data-stu-id="57002-133">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="57002-134">httpGetUrl</span><span class="sxs-lookup"><span data-stu-id="57002-134">httpGetUrl</span></span>|<span data-ttu-id="57002-135">一个 URI，指定发布元数据的地址以便使用 HTTP/Get 请求进行检索。</span><span class="sxs-lookup"><span data-stu-id="57002-135">A Uri that specifies the address at which the metadata is published for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="57002-136">如果指定了相对 Uri，则它将被视为相对于服务的基址。</span><span class="sxs-lookup"><span data-stu-id="57002-136">If a relative Uri is specified it will be treated as relative to the service’s base address.</span></span>|  
|<span data-ttu-id="57002-137">httpsGetBinding</span><span class="sxs-lookup"><span data-stu-id="57002-137">httpsGetBinding</span></span>|<span data-ttu-id="57002-138">一个字符串，指定将用于通过 HTTPS GET 进行元数据检索的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="57002-138">A string that specifies the type of the binding that will be used for metadata retrieval via HTTPS GET.</span></span> <span data-ttu-id="57002-139">此设置是可选的。</span><span class="sxs-lookup"><span data-stu-id="57002-139">This setting is optional.</span></span> <span data-ttu-id="57002-140">如果未指定此设置，则将使用默认绑定。</span><span class="sxs-lookup"><span data-stu-id="57002-140">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="57002-141">仅支持具有支持 <xref:System.ServiceModel.Channels.IReplyChannel> 的内部绑定元素的绑定。</span><span class="sxs-lookup"><span data-stu-id="57002-141">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="57002-142">此外，绑定的 <xref:System.ServiceModel.Channels.MessageVersion> 属性必须为 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>。</span><span class="sxs-lookup"><span data-stu-id="57002-142">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="57002-143">httpsGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="57002-143">httpsGetBindingConfiguration</span></span>|<span data-ttu-id="57002-144">一个字符串，用于设置在 `httpsGetBinding` 特性中指定的绑定的名称，此名称引用此绑定的其他配置信息。</span><span class="sxs-lookup"><span data-stu-id="57002-144">A string that sets the name of the binding that is specified in the `httpsGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="57002-145">必须在 `<bindings>` 节中定义相同的名称。</span><span class="sxs-lookup"><span data-stu-id="57002-145">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="57002-146">httpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="57002-146">httpsGetEnabled</span></span>|<span data-ttu-id="57002-147">一个布尔值，指定是否发布服务元数据以便使用 HTTPS/Get 请求进行检索。</span><span class="sxs-lookup"><span data-stu-id="57002-147">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTPS/Get request.</span></span> <span data-ttu-id="57002-148">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="57002-148">The default is `false`.</span></span><br /><br /> <span data-ttu-id="57002-149">如果未指定 httpsGetUrl 属性，则发布元数据的地址为服务地址加上“?wsdl”。</span><span class="sxs-lookup"><span data-stu-id="57002-149">If the httpsGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="57002-150">例如，如果服务地址为"https://localhost:8080/CalculatorService"，则 HTTP/Get 元数据地址为"https://localhost:8080/CalculatorService?wsdl"。</span><span class="sxs-lookup"><span data-stu-id="57002-150">For example, if the service address is "https://localhost:8080/CalculatorService", the HTTP/Get metadata address is "https://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="57002-151">如果此属性为`false`，或服务的地址不基于 HTTP 或 HTTPS，"？ wsdl"将被忽略。</span><span class="sxs-lookup"><span data-stu-id="57002-151">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="57002-152">httpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="57002-152">httpsGetUrl</span></span>|<span data-ttu-id="57002-153">一个 URI，指定发布元数据的地址以便使用 HTTPS/Get 请求进行检索。</span><span class="sxs-lookup"><span data-stu-id="57002-153">A Uri that specifies the address at which the metadata is published for retrieval using an HTTPS/Get request.</span></span>|  
|<span data-ttu-id="57002-154">policyVersion</span><span class="sxs-lookup"><span data-stu-id="57002-154">policyVersion</span></span>|<span data-ttu-id="57002-155">一个字符串，指定所使用的 WS-Policy 规范的版本。</span><span class="sxs-lookup"><span data-stu-id="57002-155">A string that specifies the version of the WS-Policy specification being used.</span></span> <span data-ttu-id="57002-156">此属性的类型为 <xref:System.ServiceModel.Description.PolicyVersion>。</span><span class="sxs-lookup"><span data-stu-id="57002-156">This attribute is of type <xref:System.ServiceModel.Description.PolicyVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57002-157">子元素</span><span class="sxs-lookup"><span data-stu-id="57002-157">Child Elements</span></span>  
 <span data-ttu-id="57002-158">无</span><span class="sxs-lookup"><span data-stu-id="57002-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57002-159">父元素</span><span class="sxs-lookup"><span data-stu-id="57002-159">Parent Elements</span></span>  
  
|<span data-ttu-id="57002-160">元素</span><span class="sxs-lookup"><span data-stu-id="57002-160">Element</span></span>|<span data-ttu-id="57002-161">描述</span><span class="sxs-lookup"><span data-stu-id="57002-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57002-162">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="57002-162">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="57002-163">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="57002-163">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57002-164">备注</span><span class="sxs-lookup"><span data-stu-id="57002-164">Remarks</span></span>  
 <span data-ttu-id="57002-165">此配置元素允许您控制服务的元数据发布功能。</span><span class="sxs-lookup"><span data-stu-id="57002-165">This configuration element allows you to control the metadata publishing features of a service.</span></span> <span data-ttu-id="57002-166">为了防止无意中泄露潜在的敏感服务元数据，[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 服务的默认配置将禁用元数据发布。</span><span class="sxs-lookup"><span data-stu-id="57002-166">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services disables metadata publishing.</span></span> <span data-ttu-id="57002-167">默认情况下此行为是安全的，但也意味着您无法使用元数据导入工具（例如 Svcutil.exe）生成调用服务所需的客户端代码，除非在配置中显式启用服务的元数据发布行为。</span><span class="sxs-lookup"><span data-stu-id="57002-167">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="57002-168">使用此配置元素，可以为服务启用此发布行为。</span><span class="sxs-lookup"><span data-stu-id="57002-168">Using this configuration element, you can enable this publishing behavior for your service.</span></span>  
  
 <span data-ttu-id="57002-169">有关配置此行为的详细示例，请参阅[元数据发布行为](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="57002-169">For a detailed example of configuring this behavior, see [Metadata Publishing Behavior](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).</span></span>  
  
 <span data-ttu-id="57002-170">利用可选的 `httpGetBinding` 和 `httpsGetBinding`属性，您可以配置用于通过 HTTP GET（或 HTTPS GET）检索元数据的绑定。</span><span class="sxs-lookup"><span data-stu-id="57002-170">The optional `httpGetBinding` and `httpsGetBinding` attributes allow you to configure the bindings used for metadata retrieval via HTTP GET (or HTTPS GET).</span></span> <span data-ttu-id="57002-171">如果未指定这两个属性，则根据情况使用相应的默认绑定（采用 HTTP 时为 `HttpTransportBindingElement`，采用 HTTPS 时为 `HttpsTransportBindingElement`）进行元数据检索。</span><span class="sxs-lookup"><span data-stu-id="57002-171">If they are not specified, the default bindings (`HttpTransportBindingElement`, in the case of HTTP and `HttpsTransportBindingElement`, in the case of HTTPS) are used for metadata retrieval as appropriate.</span></span> <span data-ttu-id="57002-172">请注意：不能将这些属性用于内置 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="57002-172">Notice that you cannot use these attributes with the built-in WCF bindings.</span></span> <span data-ttu-id="57002-173">仅支持具有支持 <xref:System.ServiceModel.Channels.IReplyChannel> 的内部绑定元素的绑定。</span><span class="sxs-lookup"><span data-stu-id="57002-173">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="57002-174">此外，绑定的 <xref:System.ServiceModel.Channels.MessageVersion> 属性必须为 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>。</span><span class="sxs-lookup"><span data-stu-id="57002-174">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="57002-175">为了降低服务被恶意使用者滥用的可能性，可以使用 SSL over HTTP (HTTPS) 机制来确保传输的安全。</span><span class="sxs-lookup"><span data-stu-id="57002-175">To reduce the exposure of a service to malicious users, it is possible to secure the transfer using the SSL over HTTP (HTTPS) mechanism.</span></span> <span data-ttu-id="57002-176">为此，必须首先将一个适合的 X.509 证书绑定到承载该服务的计算机上的特定端口。</span><span class="sxs-lookup"><span data-stu-id="57002-176">To do so, you must first bind a suitable X.509 certificate to a specific port on the computer that is hosting the service.</span></span> <span data-ttu-id="57002-177">(有关详细信息，请参阅[使用证书](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。)然后，将此元素添加到服务配置，并将 `httpsGetEnabled` 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="57002-177">(For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Second, add this element to the service configuration and set the `httpsGetEnabled` attribute to `true`.</span></span> <span data-ttu-id="57002-178">最后，将 `httpsGetUrl` 属性设置为服务元数据终结点的 URL，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="57002-178">Finally, set the `httpsGetUrl` attribute to the URL of the service metadata endpoint, as shown in the following example.</span></span>  
  
```xml
<behaviors>  
  <serviceBehaviors>  
    <behavior name="NewBehavior">  
      <serviceMetadata httpsGetEnabled="true"   
                       httpsGetUrl="https://myComputerName/myEndpoint" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="example"></a><span data-ttu-id="57002-179">示例</span><span class="sxs-lookup"><span data-stu-id="57002-179">Example</span></span>  
 <span data-ttu-id="57002-180">下面的示例配置服务以公开元数据使用\<serviceMetadata > 元素。</span><span class="sxs-lookup"><span data-stu-id="57002-180">The following example configure a service to expose metadata by using the \<serviceMetadata> element.</span></span> <span data-ttu-id="57002-181">它还配置终结点以便将 `IMetadataExchange` 协定作为 WS-MetadataExchange (MEX) 协议的实现公开。</span><span class="sxs-lookup"><span data-stu-id="57002-181">It also configures an endpoint to expose the `IMetadataExchange` contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="57002-182">此示例使用的是 `mexHttpBinding`，这是一种便于使用的标准绑定，与安全模式设置为 `wsHttpBinding` 的 `None` 等效。</span><span class="sxs-lookup"><span data-stu-id="57002-182">The example uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="57002-183">使用相对地址"mex"终结点，当解决针对服务基地址导致终结点地址的http://localhost/servicemodelsamples/service.svc/mex。</span><span class="sxs-lookup"><span data-stu-id="57002-183">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of http://localhost/servicemodelsamples/service.svc/mex.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService" 
               behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc -->  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex   
             To expose the IMetadataExchange contract, you must enable the serviceMetadata behavior as demonstrated below. -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <!-- The serviceMetadata behavior publishes metadata through   
               the IMetadataExchange contract. When this behavior is   
               present, you can expose this contract through an endpoint   
               as shown above. Setting httpGetEnabled to true publishes   
               the service's WSDL at the <baseaddress>?wsdl  
               eg. http://localhost/servicemodelsamples/service.svc?wsdl -->  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="57002-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="57002-184">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
 [<span data-ttu-id="57002-185">安全行为</span><span class="sxs-lookup"><span data-stu-id="57002-185">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="57002-186">元数据发布行为</span><span class="sxs-lookup"><span data-stu-id="57002-186">Metadata Publishing Behavior</span></span>](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
