---
title: <endpoint> 元素
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: fb9d3bf9b5f1a742abcc70d78af026c179ec4c4d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855389"
---
# <a name="endpoint-element"></a><span data-ttu-id="d2438-102">\<endpoint > 元素</span><span class="sxs-lookup"><span data-stu-id="d2438-102">\<endpoint> element</span></span>
<span data-ttu-id="d2438-103">指定用于公开服务的服务终结点的绑定、协定和地址属性。</span><span class="sxs-lookup"><span data-stu-id="d2438-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
<span data-ttu-id="d2438-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d2438-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d2438-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d2438-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d2438-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<服务 >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="d2438-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="d2438-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<服务 >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="d2438-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="d2438-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<终结点 >**</span><span class="sxs-lookup"><span data-stu-id="d2438-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2438-109">语法</span><span class="sxs-lookup"><span data-stu-id="d2438-109">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          bindingName="String"
          bindingNamespace="String"
          contract="String"
          endpointConfiguration="String"
          isSystemEndpoint="Boolean"
          kind="String"
          listenUriMode="Explicit/Unique"
          listenUri="Uri">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2438-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d2438-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d2438-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d2438-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2438-112">特性</span><span class="sxs-lookup"><span data-stu-id="d2438-112">Attributes</span></span>  
  
|<span data-ttu-id="d2438-113">特性</span><span class="sxs-lookup"><span data-stu-id="d2438-113">Attribute</span></span>|<span data-ttu-id="d2438-114">描述</span><span class="sxs-lookup"><span data-stu-id="d2438-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2438-115">地址</span><span class="sxs-lookup"><span data-stu-id="d2438-115">address</span></span>|<span data-ttu-id="d2438-116">一个包含终结点地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="d2438-116">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="d2438-117">可以将地址指定为绝对地址或相对地址。</span><span class="sxs-lookup"><span data-stu-id="d2438-117">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="d2438-118">如果提供的是相对地址，则需要主机提供适合于绑定中所使用的传输方案的基址。</span><span class="sxs-lookup"><span data-stu-id="d2438-118">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="d2438-119">如果未配置地址，则假定基址为该终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="d2438-119">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="d2438-120">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="d2438-120">The default is an empty string.</span></span>|  
|<span data-ttu-id="d2438-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="d2438-121">behaviorConfiguration</span></span>|<span data-ttu-id="d2438-122">一个字符串，其中包含要在终结点中使用的行为的名称。</span><span class="sxs-lookup"><span data-stu-id="d2438-122">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="d2438-123">绑定</span><span class="sxs-lookup"><span data-stu-id="d2438-123">binding</span></span>|<span data-ttu-id="d2438-124">必需的字符串属性，此属性指定要使用的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="d2438-124">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="d2438-125">该类型必须具有一个已注册的配置节，才能加以引用。</span><span class="sxs-lookup"><span data-stu-id="d2438-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="d2438-126">该类型是按节名而不是绑定的类型名注册的。</span><span class="sxs-lookup"><span data-stu-id="d2438-126">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="d2438-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d2438-127">bindingConfiguration</span></span>|<span data-ttu-id="d2438-128">一个字符串，指定实例化终结点时所使用的绑定的绑定名称。</span><span class="sxs-lookup"><span data-stu-id="d2438-128">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="d2438-129">定义终结点时，绑定名称必须在作用域内。</span><span class="sxs-lookup"><span data-stu-id="d2438-129">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="d2438-130">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="d2438-130">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="d2438-131">此属性与 `binding` 结合使用，以引用配置文件中的特定绑定配置。</span><span class="sxs-lookup"><span data-stu-id="d2438-131">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="d2438-132">如果尝试使用自定义绑定，请设置此属性。</span><span class="sxs-lookup"><span data-stu-id="d2438-132">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="d2438-133">否则，可能引发异常。</span><span class="sxs-lookup"><span data-stu-id="d2438-133">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="d2438-134">bindingName</span><span class="sxs-lookup"><span data-stu-id="d2438-134">bindingName</span></span>|<span data-ttu-id="d2438-135">一个字符串，指定绑定的唯一限定名称，用于通过 WSDL 进行的定义导出。</span><span class="sxs-lookup"><span data-stu-id="d2438-135">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="d2438-136">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="d2438-136">The default is an empty string.</span></span>|  
|<span data-ttu-id="d2438-137">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="d2438-137">bindingNamespace</span></span>|<span data-ttu-id="d2438-138">一个字符串，指定绑定的命名空间的限定名称，用于通过 WSDL 进行的定义导出。</span><span class="sxs-lookup"><span data-stu-id="d2438-138">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="d2438-139">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="d2438-139">The default is an empty string.</span></span>|  
|<span data-ttu-id="d2438-140">协定 (contract)</span><span class="sxs-lookup"><span data-stu-id="d2438-140">contract</span></span>|<span data-ttu-id="d2438-141">一个字符串，指示此终结点公开了哪个协定。</span><span class="sxs-lookup"><span data-stu-id="d2438-141">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="d2438-142">程序集必须实现该协定类型。</span><span class="sxs-lookup"><span data-stu-id="d2438-142">The assembly must implement the contract type.</span></span> <span data-ttu-id="d2438-143">如果服务实现所实现的是单个协定类型，则可以省略此属性。</span><span class="sxs-lookup"><span data-stu-id="d2438-143">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="d2438-144">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="d2438-144">The default is an empty string.</span></span>|  
|<span data-ttu-id="d2438-145">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="d2438-145">endpointConfiguration</span></span>|<span data-ttu-id="d2438-146">一个字符串，指定由 `kind` 特性设置的标准终结点的名称，此名称引用此标准终结点的其他配置信息。</span><span class="sxs-lookup"><span data-stu-id="d2438-146">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="d2438-147">必须在 `<standardEndpoints>` 节中定义相同的名称。</span><span class="sxs-lookup"><span data-stu-id="d2438-147">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="d2438-148">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="d2438-148">isSystemEndpoint</span></span>|<span data-ttu-id="d2438-149">一个布尔值，指定终结点是否是基础结构终结点。</span><span class="sxs-lookup"><span data-stu-id="d2438-149">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="d2438-150">kind</span><span class="sxs-lookup"><span data-stu-id="d2438-150">kind</span></span>|<span data-ttu-id="d2438-151">一个字符串，指定应用的标准终结点的类型。</span><span class="sxs-lookup"><span data-stu-id="d2438-151">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="d2438-152">此类型必须在 `<extensions>` 节或 machine.config 中进行注册。如果未指定任何值，则创建常规服务终结点。</span><span class="sxs-lookup"><span data-stu-id="d2438-152">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="d2438-153">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="d2438-153">listenUriMode</span></span>|<span data-ttu-id="d2438-154">指定传输如何处理供服务侦听的 `ListenUri`。</span><span class="sxs-lookup"><span data-stu-id="d2438-154">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="d2438-155">有效值为</span><span class="sxs-lookup"><span data-stu-id="d2438-155">Valid values are</span></span><br /><br /> <span data-ttu-id="d2438-156">-Explicit</span><span class="sxs-lookup"><span data-stu-id="d2438-156">-   Explicit</span></span><br /><span data-ttu-id="d2438-157">-唯一</span><span class="sxs-lookup"><span data-stu-id="d2438-157">-   Unique</span></span><br /><br /> <span data-ttu-id="d2438-158">默认值为 Explicit。</span><span class="sxs-lookup"><span data-stu-id="d2438-158">The default value is Explicit.</span></span>|  
|<span data-ttu-id="d2438-159">listenUri</span><span class="sxs-lookup"><span data-stu-id="d2438-159">listenUri</span></span>|<span data-ttu-id="d2438-160">一个字符串，指定服务终结点侦听的 URI。</span><span class="sxs-lookup"><span data-stu-id="d2438-160">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="d2438-161">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="d2438-161">The default is an empty string.</span></span>|  
|<span data-ttu-id="d2438-162">NAME</span><span class="sxs-lookup"><span data-stu-id="d2438-162">name</span></span>|<span data-ttu-id="d2438-163">可选特性。</span><span class="sxs-lookup"><span data-stu-id="d2438-163">Optional attribute.</span></span> <span data-ttu-id="d2438-164">一个指定服务终结点名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="d2438-164">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="d2438-165">默认值为绑定名称和协定说明名称的串联。</span><span class="sxs-lookup"><span data-stu-id="d2438-165">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="d2438-166">服务可能有多个终结点，因此终结点的 `name` 特性是通过服务名称区分的。</span><span class="sxs-lookup"><span data-stu-id="d2438-166">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2438-167">子元素</span><span class="sxs-lookup"><span data-stu-id="d2438-167">Child Elements</span></span>  
  
|<span data-ttu-id="d2438-168">元素</span><span class="sxs-lookup"><span data-stu-id="d2438-168">Element</span></span>|<span data-ttu-id="d2438-169">描述</span><span class="sxs-lookup"><span data-stu-id="d2438-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2438-170">\<headers></span><span class="sxs-lookup"><span data-stu-id="d2438-170">\<headers></span></span>](headers.md)|<span data-ttu-id="d2438-171">一个地址标头集合。</span><span class="sxs-lookup"><span data-stu-id="d2438-171">A collection of address headers.</span></span>|  
|[<span data-ttu-id="d2438-172">\<identity></span><span class="sxs-lookup"><span data-stu-id="d2438-172">\<identity></span></span>](identity.md)|<span data-ttu-id="d2438-173">一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d2438-173">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d2438-174">父元素</span><span class="sxs-lookup"><span data-stu-id="d2438-174">Parent Elements</span></span>  
  
|<span data-ttu-id="d2438-175">元素</span><span class="sxs-lookup"><span data-stu-id="d2438-175">Element</span></span>|<span data-ttu-id="d2438-176">描述</span><span class="sxs-lookup"><span data-stu-id="d2438-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2438-177">\<service></span><span class="sxs-lookup"><span data-stu-id="d2438-177">\<service></span></span>](service.md)|<span data-ttu-id="d2438-178">一个配置节，定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="d2438-178">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d2438-179">示例</span><span class="sxs-lookup"><span data-stu-id="d2438-179">Example</span></span>  
 <span data-ttu-id="d2438-180">这是服务终结点配置的一个示例。</span><span class="sxs-lookup"><span data-stu-id="d2438-180">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          bindingName="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
  <headers>
    <region xmlns="http://tempuri.org/">EastCoast</region>
    <member xmlns="http://tempuri.org/">Gold</member>
  </headers>
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="d2438-181">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2438-181">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="d2438-182">终结点地址、绑定和协定</span><span class="sxs-lookup"><span data-stu-id="d2438-182">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="d2438-183">如何：在配置中创建服务终结点</span><span class="sxs-lookup"><span data-stu-id="d2438-183">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
