---
title: <endpoint> 元素
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: 667086cda010daf51cb92116d636b9b526b4b34b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163405"
---
# <a name="endpoint-element"></a><span data-ttu-id="d9e50-102">\<终结点 > 元素</span><span class="sxs-lookup"><span data-stu-id="d9e50-102">\<endpoint> element</span></span>
<span data-ttu-id="d9e50-103">指定用于公开服务的服务终结点的绑定、协定和地址属性。</span><span class="sxs-lookup"><span data-stu-id="d9e50-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
 <span data-ttu-id="d9e50-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d9e50-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d9e50-105">\<service></span><span class="sxs-lookup"><span data-stu-id="d9e50-105">\<service></span></span>  
<span data-ttu-id="d9e50-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="d9e50-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9e50-107">语法</span><span class="sxs-lookup"><span data-stu-id="d9e50-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9e50-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d9e50-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d9e50-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d9e50-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9e50-110">特性</span><span class="sxs-lookup"><span data-stu-id="d9e50-110">Attributes</span></span>  
  
|<span data-ttu-id="d9e50-111">特性</span><span class="sxs-lookup"><span data-stu-id="d9e50-111">Attribute</span></span>|<span data-ttu-id="d9e50-112">描述</span><span class="sxs-lookup"><span data-stu-id="d9e50-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9e50-113">地址</span><span class="sxs-lookup"><span data-stu-id="d9e50-113">address</span></span>|<span data-ttu-id="d9e50-114">一个包含终结点地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="d9e50-114">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="d9e50-115">可以将地址指定为绝对地址或相对地址。</span><span class="sxs-lookup"><span data-stu-id="d9e50-115">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="d9e50-116">如果提供的是相对地址，则需要主机提供适合于绑定中所使用的传输方案的基址。</span><span class="sxs-lookup"><span data-stu-id="d9e50-116">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="d9e50-117">如果未配置地址，则假定基址为该终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="d9e50-117">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="d9e50-118">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="d9e50-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="d9e50-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="d9e50-119">behaviorConfiguration</span></span>|<span data-ttu-id="d9e50-120">一个字符串，其中包含要在终结点中使用的行为的名称。</span><span class="sxs-lookup"><span data-stu-id="d9e50-120">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="d9e50-121">绑定</span><span class="sxs-lookup"><span data-stu-id="d9e50-121">binding</span></span>|<span data-ttu-id="d9e50-122">必需的字符串属性，此属性指定要使用的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="d9e50-122">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="d9e50-123">该类型必须具有一个已注册的配置节，才能加以引用。</span><span class="sxs-lookup"><span data-stu-id="d9e50-123">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="d9e50-124">该类型是按节名而不是绑定的类型名注册的。</span><span class="sxs-lookup"><span data-stu-id="d9e50-124">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="d9e50-125">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d9e50-125">bindingConfiguration</span></span>|<span data-ttu-id="d9e50-126">一个字符串，指定实例化终结点时所使用的绑定的绑定名称。</span><span class="sxs-lookup"><span data-stu-id="d9e50-126">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="d9e50-127">定义终结点时，绑定名称必须在作用域内。</span><span class="sxs-lookup"><span data-stu-id="d9e50-127">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="d9e50-128">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="d9e50-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="d9e50-129">此属性与 `binding` 结合使用，以引用配置文件中的特定绑定配置。</span><span class="sxs-lookup"><span data-stu-id="d9e50-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="d9e50-130">如果尝试使用自定义绑定，请设置此属性。</span><span class="sxs-lookup"><span data-stu-id="d9e50-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="d9e50-131">否则，可能引发异常。</span><span class="sxs-lookup"><span data-stu-id="d9e50-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="d9e50-132">bindingName</span><span class="sxs-lookup"><span data-stu-id="d9e50-132">bindingName</span></span>|<span data-ttu-id="d9e50-133">一个字符串，指定绑定的唯一限定名称，用于通过 WSDL 进行的定义导出。</span><span class="sxs-lookup"><span data-stu-id="d9e50-133">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="d9e50-134">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="d9e50-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="d9e50-135">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="d9e50-135">bindingNamespace</span></span>|<span data-ttu-id="d9e50-136">一个字符串，指定绑定的命名空间的限定名称，用于通过 WSDL 进行的定义导出。</span><span class="sxs-lookup"><span data-stu-id="d9e50-136">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="d9e50-137">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="d9e50-137">The default is an empty string.</span></span>|  
|<span data-ttu-id="d9e50-138">Contract — 协定</span><span class="sxs-lookup"><span data-stu-id="d9e50-138">contract</span></span>|<span data-ttu-id="d9e50-139">一个字符串，指示此终结点公开了哪个协定。</span><span class="sxs-lookup"><span data-stu-id="d9e50-139">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="d9e50-140">程序集必须实现该协定类型。</span><span class="sxs-lookup"><span data-stu-id="d9e50-140">The assembly must implement the contract type.</span></span> <span data-ttu-id="d9e50-141">如果服务实现所实现的是单个协定类型，则可以省略此属性。</span><span class="sxs-lookup"><span data-stu-id="d9e50-141">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="d9e50-142">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="d9e50-142">The default is an empty string.</span></span>|  
|<span data-ttu-id="d9e50-143">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="d9e50-143">endpointConfiguration</span></span>|<span data-ttu-id="d9e50-144">一个字符串，指定由 `kind` 特性设置的标准终结点的名称，此名称引用此标准终结点的其他配置信息。</span><span class="sxs-lookup"><span data-stu-id="d9e50-144">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="d9e50-145">必须在 `<standardEndpoints>` 节中定义相同的名称。</span><span class="sxs-lookup"><span data-stu-id="d9e50-145">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="d9e50-146">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="d9e50-146">isSystemEndpoint</span></span>|<span data-ttu-id="d9e50-147">一个布尔值，指定终结点是否是基础结构终结点。</span><span class="sxs-lookup"><span data-stu-id="d9e50-147">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="d9e50-148">kind</span><span class="sxs-lookup"><span data-stu-id="d9e50-148">kind</span></span>|<span data-ttu-id="d9e50-149">一个字符串，指定应用的标准终结点的类型。</span><span class="sxs-lookup"><span data-stu-id="d9e50-149">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="d9e50-150">此类型必须在 `<extensions>` 节或 machine.config 中进行注册。如果未指定任何值，则创建常规服务终结点。</span><span class="sxs-lookup"><span data-stu-id="d9e50-150">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="d9e50-151">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="d9e50-151">listenUriMode</span></span>|<span data-ttu-id="d9e50-152">指定传输如何处理供服务侦听的 `ListenUri`。</span><span class="sxs-lookup"><span data-stu-id="d9e50-152">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="d9e50-153">有效值为</span><span class="sxs-lookup"><span data-stu-id="d9e50-153">Valid values are</span></span><br /><br /> <span data-ttu-id="d9e50-154">-   Explicit</span><span class="sxs-lookup"><span data-stu-id="d9e50-154">-   Explicit</span></span><br /><span data-ttu-id="d9e50-155">唯一</span><span class="sxs-lookup"><span data-stu-id="d9e50-155">-   Unique</span></span><br /><br /> <span data-ttu-id="d9e50-156">默认值为 Explicit。</span><span class="sxs-lookup"><span data-stu-id="d9e50-156">The default value is Explicit.</span></span>|  
|<span data-ttu-id="d9e50-157">listenUri</span><span class="sxs-lookup"><span data-stu-id="d9e50-157">listenUri</span></span>|<span data-ttu-id="d9e50-158">一个字符串，指定服务终结点侦听的 URI。</span><span class="sxs-lookup"><span data-stu-id="d9e50-158">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="d9e50-159">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="d9e50-159">The default is an empty string.</span></span>|  
|<span data-ttu-id="d9e50-160">name</span><span class="sxs-lookup"><span data-stu-id="d9e50-160">name</span></span>|<span data-ttu-id="d9e50-161">可选特性。</span><span class="sxs-lookup"><span data-stu-id="d9e50-161">Optional attribute.</span></span> <span data-ttu-id="d9e50-162">一个指定服务终结点名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="d9e50-162">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="d9e50-163">默认值为绑定名称和协定说明名称的串联。</span><span class="sxs-lookup"><span data-stu-id="d9e50-163">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="d9e50-164">服务可能有多个终结点，因此终结点的 `name` 特性是通过服务名称区分的。</span><span class="sxs-lookup"><span data-stu-id="d9e50-164">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9e50-165">子元素</span><span class="sxs-lookup"><span data-stu-id="d9e50-165">Child Elements</span></span>  
  
|<span data-ttu-id="d9e50-166">元素</span><span class="sxs-lookup"><span data-stu-id="d9e50-166">Element</span></span>|<span data-ttu-id="d9e50-167">描述</span><span class="sxs-lookup"><span data-stu-id="d9e50-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9e50-168">\<headers></span><span class="sxs-lookup"><span data-stu-id="d9e50-168">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="d9e50-169">一个地址标头集合。</span><span class="sxs-lookup"><span data-stu-id="d9e50-169">A collection of address headers.</span></span>|  
|[<span data-ttu-id="d9e50-170">\<identity></span><span class="sxs-lookup"><span data-stu-id="d9e50-170">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="d9e50-171">一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d9e50-171">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9e50-172">父元素</span><span class="sxs-lookup"><span data-stu-id="d9e50-172">Parent Elements</span></span>  
  
|<span data-ttu-id="d9e50-173">元素</span><span class="sxs-lookup"><span data-stu-id="d9e50-173">Element</span></span>|<span data-ttu-id="d9e50-174">描述</span><span class="sxs-lookup"><span data-stu-id="d9e50-174">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9e50-175">\<service></span><span class="sxs-lookup"><span data-stu-id="d9e50-175">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="d9e50-176">一个配置节，定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="d9e50-176">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d9e50-177">示例</span><span class="sxs-lookup"><span data-stu-id="d9e50-177">Example</span></span>  
 <span data-ttu-id="d9e50-178">这是服务终结点配置的一个示例。</span><span class="sxs-lookup"><span data-stu-id="d9e50-178">This is an example of a service endpoint configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d9e50-179">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9e50-179">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="d9e50-180">终结点：地址、绑定和协定</span><span class="sxs-lookup"><span data-stu-id="d9e50-180">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="d9e50-181">如何：在配置中创建服务终结点</span><span class="sxs-lookup"><span data-stu-id="d9e50-181">How to: Create a Service Endpoint in Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
