---
title: <serviceMetadata>
ms.date: 03/30/2017
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
ms.openlocfilehash: 04bc29e8e842f5bb0252685fc3088a86535f4668
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379492"
---
# <a name="servicemetadata"></a><span data-ttu-id="f6024-101">\<serviceMetadata></span><span class="sxs-lookup"><span data-stu-id="f6024-101">\<serviceMetadata></span></span>
<span data-ttu-id="f6024-102">指定服务元数据的发布和相关信息。</span><span class="sxs-lookup"><span data-stu-id="f6024-102">Specifies the publication of service metadata and associated information.</span></span>  
  
<span data-ttu-id="f6024-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f6024-103">\<system.serviceModel></span></span>  
<span data-ttu-id="f6024-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f6024-104">\<behaviors></span></span>  
<span data-ttu-id="f6024-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f6024-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="f6024-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f6024-106">\<behavior></span></span>  
<span data-ttu-id="f6024-107">\<serviceMetadata></span><span class="sxs-lookup"><span data-stu-id="f6024-107">\<serviceMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6024-108">语法</span><span class="sxs-lookup"><span data-stu-id="f6024-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6024-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f6024-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f6024-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f6024-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6024-111">特性</span><span class="sxs-lookup"><span data-stu-id="f6024-111">Attributes</span></span>  
  
|<span data-ttu-id="f6024-112">特性</span><span class="sxs-lookup"><span data-stu-id="f6024-112">Attribute</span></span>|<span data-ttu-id="f6024-113">描述</span><span class="sxs-lookup"><span data-stu-id="f6024-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f6024-114">externalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="f6024-114">externalMetadataLocation</span></span>|<span data-ttu-id="f6024-115">一个包含 WSDL 文件的位置的 URI，该文件将返回到用户以响应 WSDL 和 MEX 请求而非自动生成的 WSDL。</span><span class="sxs-lookup"><span data-stu-id="f6024-115">A Uri that contains the location of a WSDL file, which is returned to the user in response to WSDL and MEX requests instead of the auto-generated WSDL.</span></span> <span data-ttu-id="f6024-116">当未设置此属性时，将返回默认的 WSDL。</span><span class="sxs-lookup"><span data-stu-id="f6024-116">When this attribute is not set, the default WSDL is returned.</span></span> <span data-ttu-id="f6024-117">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="f6024-117">The default is an empty string.</span></span>|  
|<span data-ttu-id="f6024-118">httpGetBinding</span><span class="sxs-lookup"><span data-stu-id="f6024-118">httpGetBinding</span></span>|<span data-ttu-id="f6024-119">一个字符串，指定将用于通过 HTTP GET 进行元数据检索的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="f6024-119">A string that specifies the type of the binding that will be used for metadata retrieval via HTTP GET.</span></span> <span data-ttu-id="f6024-120">此设置是可选的。</span><span class="sxs-lookup"><span data-stu-id="f6024-120">This setting is optional.</span></span> <span data-ttu-id="f6024-121">如果未指定此设置，则将使用默认绑定。</span><span class="sxs-lookup"><span data-stu-id="f6024-121">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="f6024-122">仅支持具有支持 <xref:System.ServiceModel.Channels.IReplyChannel> 的内部绑定元素的绑定。</span><span class="sxs-lookup"><span data-stu-id="f6024-122">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="f6024-123">此外，绑定的 <xref:System.ServiceModel.Channels.MessageVersion> 属性必须为 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>。</span><span class="sxs-lookup"><span data-stu-id="f6024-123">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="f6024-124">httpGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="f6024-124">httpGetBindingConfiguration</span></span>|<span data-ttu-id="f6024-125">一个字符串，用于设置在 `httpGetBinding` 特性中指定的绑定的名称，此名称引用此绑定的其他配置信息。</span><span class="sxs-lookup"><span data-stu-id="f6024-125">A string that sets the name of the binding that is specified in the `httpGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="f6024-126">必须在 `<bindings>` 节中定义相同的名称。</span><span class="sxs-lookup"><span data-stu-id="f6024-126">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="f6024-127">httpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="f6024-127">httpGetEnabled</span></span>|<span data-ttu-id="f6024-128">一个布尔值，指定是否发布服务元数据以便使用 HTTP/Get 请求进行检索。</span><span class="sxs-lookup"><span data-stu-id="f6024-128">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="f6024-129">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="f6024-129">The default is `false`.</span></span><br /><br /> <span data-ttu-id="f6024-130">如果未指定 httpGetUrl 属性，则发布元数据的地址为服务地址加上“?wsdl”。</span><span class="sxs-lookup"><span data-stu-id="f6024-130">If the httpGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="f6024-131">例如，如果服务地址为"http://localhost:8080/CalculatorService"，HTTP/Get 元数据地址为"http://localhost:8080/CalculatorService?wsdl"。</span><span class="sxs-lookup"><span data-stu-id="f6024-131">For example, if the service address is "http://localhost:8080/CalculatorService", the HTTP/Get metadata address is "http://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="f6024-132">如果此属性为`false`，或该服务的地址不基于 HTTP 或 HTTPS，"？ wsdl"将被忽略。</span><span class="sxs-lookup"><span data-stu-id="f6024-132">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="f6024-133">httpGetUrl</span><span class="sxs-lookup"><span data-stu-id="f6024-133">httpGetUrl</span></span>|<span data-ttu-id="f6024-134">一个 URI，指定发布元数据的地址以便使用 HTTP/Get 请求进行检索。</span><span class="sxs-lookup"><span data-stu-id="f6024-134">A Uri that specifies the address at which the metadata is published for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="f6024-135">如果指定了相对 Uri，则它将被视为相对于服务的基址。</span><span class="sxs-lookup"><span data-stu-id="f6024-135">If a relative Uri is specified it will be treated as relative to the service’s base address.</span></span>|  
|<span data-ttu-id="f6024-136">httpsGetBinding</span><span class="sxs-lookup"><span data-stu-id="f6024-136">httpsGetBinding</span></span>|<span data-ttu-id="f6024-137">一个字符串，指定将用于通过 HTTPS GET 进行元数据检索的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="f6024-137">A string that specifies the type of the binding that will be used for metadata retrieval via HTTPS GET.</span></span> <span data-ttu-id="f6024-138">此设置是可选的。</span><span class="sxs-lookup"><span data-stu-id="f6024-138">This setting is optional.</span></span> <span data-ttu-id="f6024-139">如果未指定此设置，则将使用默认绑定。</span><span class="sxs-lookup"><span data-stu-id="f6024-139">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="f6024-140">仅支持具有支持 <xref:System.ServiceModel.Channels.IReplyChannel> 的内部绑定元素的绑定。</span><span class="sxs-lookup"><span data-stu-id="f6024-140">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="f6024-141">此外，绑定的 <xref:System.ServiceModel.Channels.MessageVersion> 属性必须为 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>。</span><span class="sxs-lookup"><span data-stu-id="f6024-141">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="f6024-142">httpsGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="f6024-142">httpsGetBindingConfiguration</span></span>|<span data-ttu-id="f6024-143">一个字符串，用于设置在 `httpsGetBinding` 特性中指定的绑定的名称，此名称引用此绑定的其他配置信息。</span><span class="sxs-lookup"><span data-stu-id="f6024-143">A string that sets the name of the binding that is specified in the `httpsGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="f6024-144">必须在 `<bindings>` 节中定义相同的名称。</span><span class="sxs-lookup"><span data-stu-id="f6024-144">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="f6024-145">httpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="f6024-145">httpsGetEnabled</span></span>|<span data-ttu-id="f6024-146">一个布尔值，指定是否发布服务元数据以便使用 HTTPS/Get 请求进行检索。</span><span class="sxs-lookup"><span data-stu-id="f6024-146">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTPS/Get request.</span></span> <span data-ttu-id="f6024-147">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="f6024-147">The default is `false`.</span></span><br /><br /> <span data-ttu-id="f6024-148">如果未指定 httpsGetUrl 属性，则发布元数据的地址为服务地址加上“?wsdl”。</span><span class="sxs-lookup"><span data-stu-id="f6024-148">If the httpsGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="f6024-149">例如，如果服务地址为"https://localhost:8080/CalculatorService"，HTTP/Get 元数据地址为"https://localhost:8080/CalculatorService?wsdl"。</span><span class="sxs-lookup"><span data-stu-id="f6024-149">For example, if the service address is "https://localhost:8080/CalculatorService", the HTTP/Get metadata address is "https://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="f6024-150">如果此属性为`false`，或该服务的地址不基于 HTTP 或 HTTPS，"？ wsdl"将被忽略。</span><span class="sxs-lookup"><span data-stu-id="f6024-150">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="f6024-151">httpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="f6024-151">httpsGetUrl</span></span>|<span data-ttu-id="f6024-152">一个 URI，指定发布元数据的地址以便使用 HTTPS/Get 请求进行检索。</span><span class="sxs-lookup"><span data-stu-id="f6024-152">A Uri that specifies the address at which the metadata is published for retrieval using an HTTPS/Get request.</span></span>|  
|<span data-ttu-id="f6024-153">policyVersion</span><span class="sxs-lookup"><span data-stu-id="f6024-153">policyVersion</span></span>|<span data-ttu-id="f6024-154">一个字符串，指定所使用的 WS-Policy 规范的版本。</span><span class="sxs-lookup"><span data-stu-id="f6024-154">A string that specifies the version of the WS-Policy specification being used.</span></span> <span data-ttu-id="f6024-155">此属性的类型为 <xref:System.ServiceModel.Description.PolicyVersion>。</span><span class="sxs-lookup"><span data-stu-id="f6024-155">This attribute is of type <xref:System.ServiceModel.Description.PolicyVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6024-156">子元素</span><span class="sxs-lookup"><span data-stu-id="f6024-156">Child Elements</span></span>  
 <span data-ttu-id="f6024-157">无</span><span class="sxs-lookup"><span data-stu-id="f6024-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f6024-158">父元素</span><span class="sxs-lookup"><span data-stu-id="f6024-158">Parent Elements</span></span>  
  
|<span data-ttu-id="f6024-159">元素</span><span class="sxs-lookup"><span data-stu-id="f6024-159">Element</span></span>|<span data-ttu-id="f6024-160">描述</span><span class="sxs-lookup"><span data-stu-id="f6024-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6024-161">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f6024-161">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f6024-162">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="f6024-162">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6024-163">备注</span><span class="sxs-lookup"><span data-stu-id="f6024-163">Remarks</span></span>  
 <span data-ttu-id="f6024-164">此配置元素允许您控制服务的元数据发布功能。</span><span class="sxs-lookup"><span data-stu-id="f6024-164">This configuration element allows you to control the metadata publishing features of a service.</span></span> <span data-ttu-id="f6024-165">若要防止无意中泄漏可能敏感的服务元数据，Windows Communication Foundation (WCF) 服务的默认配置，请禁用元数据发布。</span><span class="sxs-lookup"><span data-stu-id="f6024-165">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="f6024-166">默认情况下此行为是安全的，但也意味着你无法使用元数据导入工具（例如 Svcutil.exe）生成调用服务所需的客户端代码，除非在配置中显式启用服务的元数据发布行为。</span><span class="sxs-lookup"><span data-stu-id="f6024-166">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="f6024-167">使用此配置元素，可以为服务启用此发布行为。</span><span class="sxs-lookup"><span data-stu-id="f6024-167">Using this configuration element, you can enable this publishing behavior for your service.</span></span>  
  
 <span data-ttu-id="f6024-168">有关配置此行为的详细示例，请参阅[元数据发布行为](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="f6024-168">For a detailed example of configuring this behavior, see [Metadata Publishing Behavior](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).</span></span>  
  
 <span data-ttu-id="f6024-169">利用可选的 `httpGetBinding` 和 `httpsGetBinding`属性，你可以配置用于通过 HTTP GET（或 HTTPS GET）检索元数据的绑定。</span><span class="sxs-lookup"><span data-stu-id="f6024-169">The optional `httpGetBinding` and `httpsGetBinding` attributes allow you to configure the bindings used for metadata retrieval via HTTP GET (or HTTPS GET).</span></span> <span data-ttu-id="f6024-170">如果未指定这两个属性，则根据情况使用相应的默认绑定（采用 HTTP 时为 `HttpTransportBindingElement`，采用 HTTPS 时为 `HttpsTransportBindingElement`）进行元数据检索。</span><span class="sxs-lookup"><span data-stu-id="f6024-170">If they are not specified, the default bindings (`HttpTransportBindingElement`, in the case of HTTP and `HttpsTransportBindingElement`, in the case of HTTPS) are used for metadata retrieval as appropriate.</span></span> <span data-ttu-id="f6024-171">请注意：不能将这些属性用于内置 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="f6024-171">Notice that you cannot use these attributes with the built-in WCF bindings.</span></span> <span data-ttu-id="f6024-172">仅支持具有支持 <xref:System.ServiceModel.Channels.IReplyChannel> 的内部绑定元素的绑定。</span><span class="sxs-lookup"><span data-stu-id="f6024-172">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="f6024-173">此外，绑定的 <xref:System.ServiceModel.Channels.MessageVersion> 属性必须为 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>。</span><span class="sxs-lookup"><span data-stu-id="f6024-173">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="f6024-174">为了降低服务被恶意使用者滥用的可能性，可以使用 SSL over HTTP (HTTPS) 机制来确保传输的安全。</span><span class="sxs-lookup"><span data-stu-id="f6024-174">To reduce the exposure of a service to malicious users, it is possible to secure the transfer using the SSL over HTTP (HTTPS) mechanism.</span></span> <span data-ttu-id="f6024-175">为此，必须首先将一个适合的 X.509 证书绑定到承载该服务的计算机上的特定端口。</span><span class="sxs-lookup"><span data-stu-id="f6024-175">To do so, you must first bind a suitable X.509 certificate to a specific port on the computer that is hosting the service.</span></span> <span data-ttu-id="f6024-176">(有关详细信息，请参阅[Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。)然后，将此元素添加到服务配置，并将 `httpsGetEnabled` 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="f6024-176">(For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Second, add this element to the service configuration and set the `httpsGetEnabled` attribute to `true`.</span></span> <span data-ttu-id="f6024-177">最后，将 `httpsGetUrl` 属性设置为服务元数据终结点的 URL，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="f6024-177">Finally, set the `httpsGetUrl` attribute to the URL of the service metadata endpoint, as shown in the following example.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="f6024-178">示例</span><span class="sxs-lookup"><span data-stu-id="f6024-178">Example</span></span>  
 <span data-ttu-id="f6024-179">下面的示例将服务配置为使用公开元数据\<serviceMetadata > 元素。</span><span class="sxs-lookup"><span data-stu-id="f6024-179">The following example configure a service to expose metadata by using the \<serviceMetadata> element.</span></span> <span data-ttu-id="f6024-180">它还配置终结点以便将 `IMetadataExchange` 协定作为 WS-MetadataExchange (MEX) 协议的实现公开。</span><span class="sxs-lookup"><span data-stu-id="f6024-180">It also configures an endpoint to expose the `IMetadataExchange` contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="f6024-181">此示例使用的是 `mexHttpBinding`，这是一种便于使用的标准绑定，与安全模式设置为 `wsHttpBinding` 的 `None` 等效。</span><span class="sxs-lookup"><span data-stu-id="f6024-181">The example uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="f6024-182">使用相对地址"mex"在终结点，此操作时解决针对基本服务地址会导致终结点地址的`http://localhost/servicemodelsamples/service.svc/mex`。</span><span class="sxs-lookup"><span data-stu-id="f6024-182">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of `http://localhost/servicemodelsamples/service.svc/mex`.</span></span>  
  
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
          <!-- The serviceMetadata behavior publishes metadata through the IMetadataExchange contract. When this behavior is
               present, you can expose this contract through an endpoint as shown above. Setting httpGetEnabled to true publishes
               the service's WSDL at the <baseaddress>?wsdl eg. http://localhost/servicemodelsamples/service.svc?wsdl -->
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="f6024-183">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6024-183">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [<span data-ttu-id="f6024-184">安全行为</span><span class="sxs-lookup"><span data-stu-id="f6024-184">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f6024-185">元数据发布行为</span><span class="sxs-lookup"><span data-stu-id="f6024-185">Metadata Publishing Behavior</span></span>](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
