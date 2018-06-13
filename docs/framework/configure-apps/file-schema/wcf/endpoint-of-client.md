---
title: '&lt;client&gt; 的 &lt;endpoint&gt;'
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f9a69483ab058823fd419edc84868e801b91d2c9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748056"
---
# <a name="ltendpointgt-of-ltclientgt"></a><span data-ttu-id="b747b-102">&lt;client&gt; 的 &lt;endpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="b747b-102">&lt;endpoint&gt; of &lt;client&gt;</span></span>
<span data-ttu-id="b747b-103">指定通道终结点的协定、绑定和地址属性，客户端使用通道终结点与服务器上的服务终结点连接。</span><span class="sxs-lookup"><span data-stu-id="b747b-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
 <span data-ttu-id="b747b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b747b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b747b-105">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="b747b-105">\<client></span></span>  
<span data-ttu-id="b747b-106">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="b747b-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b747b-107">语法</span><span class="sxs-lookup"><span data-stu-id="b747b-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"  
   behaviorConfiguration="String"  
   binding="String"  
   bindingConfiguration="String"  
   contract="String"   endpointConfiguration="String"   kind="String"  
   name="String"  
</endpoint>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b747b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b747b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b747b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b747b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b747b-110">特性</span><span class="sxs-lookup"><span data-stu-id="b747b-110">Attributes</span></span>  
  
|<span data-ttu-id="b747b-111">特性</span><span class="sxs-lookup"><span data-stu-id="b747b-111">Attribute</span></span>|<span data-ttu-id="b747b-112">描述</span><span class="sxs-lookup"><span data-stu-id="b747b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b747b-113">address</span><span class="sxs-lookup"><span data-stu-id="b747b-113">address</span></span>|<span data-ttu-id="b747b-114">必需的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="b747b-114">Required string attribute.</span></span><br /><br /> <span data-ttu-id="b747b-115">指定终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="b747b-115">Specifies the address of the endpoint.</span></span> <span data-ttu-id="b747b-116">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="b747b-116">The default is an empty string.</span></span> <span data-ttu-id="b747b-117">该地址必须为绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="b747b-117">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="b747b-118">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="b747b-118">behaviorConfiguration</span></span>|<span data-ttu-id="b747b-119">一个字符串，其中包含要用于实例化终结点的行为的行为名。</span><span class="sxs-lookup"><span data-stu-id="b747b-119">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="b747b-120">定义服务时，该行为名必须在作用域内。</span><span class="sxs-lookup"><span data-stu-id="b747b-120">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="b747b-121">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="b747b-121">The default is an empty string.</span></span>|  
|<span data-ttu-id="b747b-122">绑定</span><span class="sxs-lookup"><span data-stu-id="b747b-122">binding</span></span>|<span data-ttu-id="b747b-123">必需的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="b747b-123">Required string attribute.</span></span><br /><br /> <span data-ttu-id="b747b-124">一个字符串，指示要使用的绑定的类型。</span><span class="sxs-lookup"><span data-stu-id="b747b-124">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="b747b-125">该类型必须具有一个已注册的配置节，才能加以引用。</span><span class="sxs-lookup"><span data-stu-id="b747b-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="b747b-126">该类型是按节名而不是绑定的类型名注册的。</span><span class="sxs-lookup"><span data-stu-id="b747b-126">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="b747b-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b747b-127">bindingConfiguration</span></span>|<span data-ttu-id="b747b-128">可选。</span><span class="sxs-lookup"><span data-stu-id="b747b-128">Optional.</span></span> <span data-ttu-id="b747b-129">一个字符串，其中包含实例化终结点时要使用的绑定配置的名称。</span><span class="sxs-lookup"><span data-stu-id="b747b-129">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="b747b-130">定义终结点时，绑定配置必须在作用域内。</span><span class="sxs-lookup"><span data-stu-id="b747b-130">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="b747b-131">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="b747b-131">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="b747b-132">此属性与 `binding` 结合使用，以引用配置文件中的特定绑定配置。</span><span class="sxs-lookup"><span data-stu-id="b747b-132">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="b747b-133">如果尝试使用自定义绑定，请设置此属性。</span><span class="sxs-lookup"><span data-stu-id="b747b-133">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="b747b-134">否则，可能引发异常。</span><span class="sxs-lookup"><span data-stu-id="b747b-134">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="b747b-135">Contract — 协定</span><span class="sxs-lookup"><span data-stu-id="b747b-135">contract</span></span>|<span data-ttu-id="b747b-136">必需的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="b747b-136">Required string attribute.</span></span><br /><br /> <span data-ttu-id="b747b-137">一个字符串，指示此终结点公开了哪个协定。</span><span class="sxs-lookup"><span data-stu-id="b747b-137">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="b747b-138">程序集必须实现该协定类型。</span><span class="sxs-lookup"><span data-stu-id="b747b-138">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="b747b-139">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="b747b-139">endpointConfiguration</span></span>|<span data-ttu-id="b747b-140">一个字符串，指定由 `kind` 特性设置的标准终结点的名称，此名称引用此标准终结点的其他配置信息。</span><span class="sxs-lookup"><span data-stu-id="b747b-140">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="b747b-141">必须在 `<standardEndpoints>` 节中定义相同的名称。</span><span class="sxs-lookup"><span data-stu-id="b747b-141">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="b747b-142">kind</span><span class="sxs-lookup"><span data-stu-id="b747b-142">kind</span></span>|<span data-ttu-id="b747b-143">一个字符串，指定应用的标准终结点的类型。</span><span class="sxs-lookup"><span data-stu-id="b747b-143">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="b747b-144">此类型必须在 `<extensions>` 节或 machine.config 中进行注册。如果未指定任何值，则创建通用通道终结点。</span><span class="sxs-lookup"><span data-stu-id="b747b-144">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="b747b-145">name</span><span class="sxs-lookup"><span data-stu-id="b747b-145">name</span></span>|<span data-ttu-id="b747b-146">可选的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="b747b-146">Optional string attribute.</span></span> <span data-ttu-id="b747b-147">此属性唯一标识给定协定的终结点。</span><span class="sxs-lookup"><span data-stu-id="b747b-147">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="b747b-148">可以为一个给定协定类型定义多个客户端。</span><span class="sxs-lookup"><span data-stu-id="b747b-148">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="b747b-149">每个定义都必须用唯一的配置名称加以区分。</span><span class="sxs-lookup"><span data-stu-id="b747b-149">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="b747b-150">如果省略此属性，则将对应的终结点用作与指定协定类型相关联的默认终结点。</span><span class="sxs-lookup"><span data-stu-id="b747b-150">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="b747b-151">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="b747b-151">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="b747b-152">绑定的 `name` 属性用于通过 WSDL 进行的定义导出。</span><span class="sxs-lookup"><span data-stu-id="b747b-152">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b747b-153">子元素</span><span class="sxs-lookup"><span data-stu-id="b747b-153">Child Elements</span></span>  
  
|<span data-ttu-id="b747b-154">元素</span><span class="sxs-lookup"><span data-stu-id="b747b-154">Element</span></span>|<span data-ttu-id="b747b-155">描述</span><span class="sxs-lookup"><span data-stu-id="b747b-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b747b-156">\<headers></span><span class="sxs-lookup"><span data-stu-id="b747b-156">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="b747b-157">一个地址标头集合。</span><span class="sxs-lookup"><span data-stu-id="b747b-157">A collection of address headers.</span></span>|  
|[<span data-ttu-id="b747b-158">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="b747b-158">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="b747b-159">一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b747b-159">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b747b-160">父元素</span><span class="sxs-lookup"><span data-stu-id="b747b-160">Parent Elements</span></span>  
  
|<span data-ttu-id="b747b-161">元素</span><span class="sxs-lookup"><span data-stu-id="b747b-161">Element</span></span>|<span data-ttu-id="b747b-162">描述</span><span class="sxs-lookup"><span data-stu-id="b747b-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b747b-163">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="b747b-163">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="b747b-164">一个配置节，定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="b747b-164">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b747b-165">示例</span><span class="sxs-lookup"><span data-stu-id="b747b-165">Example</span></span>  
 <span data-ttu-id="b747b-166">这是通道终结点配置的一个示例。</span><span class="sxs-lookup"><span data-stu-id="b747b-166">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"  
    bindingConfiguration="usingDefaults"  
    name="MyBinding"  
    binding="customBinding"  
    contract="HelloWorld">  
</endpoint>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b747b-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="b747b-167">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>  
 <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>  
 [<span data-ttu-id="b747b-168">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="b747b-168">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="b747b-169">客户端</span><span class="sxs-lookup"><span data-stu-id="b747b-169">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
