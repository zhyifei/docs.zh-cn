---
title: <endpoint> 的 <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f1ffbc1e8efac70523d7f631c8cf9ba9a1622bfc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855321"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="ebf93-102">\<\<客户端 > > 终结点</span><span class="sxs-lookup"><span data-stu-id="ebf93-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="ebf93-103">指定通道终结点的协定、绑定和地址属性，客户端使用通道终结点与服务器上的服务终结点连接。</span><span class="sxs-lookup"><span data-stu-id="ebf93-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
<span data-ttu-id="ebf93-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ebf93-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ebf93-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ebf93-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ebf93-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<客户端 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="ebf93-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="ebf93-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<终结点 >**</span><span class="sxs-lookup"><span data-stu-id="ebf93-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf93-108">语法</span><span class="sxs-lookup"><span data-stu-id="ebf93-108">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          contract="String"
          endpointConfiguration="String"
          kind="String"
          name="String">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebf93-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ebf93-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ebf93-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ebf93-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebf93-111">特性</span><span class="sxs-lookup"><span data-stu-id="ebf93-111">Attributes</span></span>  
  
|<span data-ttu-id="ebf93-112">特性</span><span class="sxs-lookup"><span data-stu-id="ebf93-112">Attribute</span></span>|<span data-ttu-id="ebf93-113">描述</span><span class="sxs-lookup"><span data-stu-id="ebf93-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ebf93-114">地址</span><span class="sxs-lookup"><span data-stu-id="ebf93-114">address</span></span>|<span data-ttu-id="ebf93-115">必需的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="ebf93-115">Required string attribute.</span></span><br /><br /> <span data-ttu-id="ebf93-116">指定终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="ebf93-116">Specifies the address of the endpoint.</span></span> <span data-ttu-id="ebf93-117">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="ebf93-117">The default is an empty string.</span></span> <span data-ttu-id="ebf93-118">该地址必须为绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="ebf93-118">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="ebf93-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="ebf93-119">behaviorConfiguration</span></span>|<span data-ttu-id="ebf93-120">一个字符串，其中包含要用于实例化终结点的行为的行为名。</span><span class="sxs-lookup"><span data-stu-id="ebf93-120">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="ebf93-121">定义服务时，该行为名必须在作用域内。</span><span class="sxs-lookup"><span data-stu-id="ebf93-121">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="ebf93-122">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="ebf93-122">The default is an empty string.</span></span>|  
|<span data-ttu-id="ebf93-123">绑定</span><span class="sxs-lookup"><span data-stu-id="ebf93-123">binding</span></span>|<span data-ttu-id="ebf93-124">必需的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="ebf93-124">Required string attribute.</span></span><br /><br /> <span data-ttu-id="ebf93-125">一个字符串，指示要使用的绑定的类型。</span><span class="sxs-lookup"><span data-stu-id="ebf93-125">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="ebf93-126">该类型必须具有一个已注册的配置节，才能加以引用。</span><span class="sxs-lookup"><span data-stu-id="ebf93-126">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="ebf93-127">该类型是按节名而不是绑定的类型名注册的。</span><span class="sxs-lookup"><span data-stu-id="ebf93-127">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="ebf93-128">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ebf93-128">bindingConfiguration</span></span>|<span data-ttu-id="ebf93-129">可选。</span><span class="sxs-lookup"><span data-stu-id="ebf93-129">Optional.</span></span> <span data-ttu-id="ebf93-130">一个字符串，其中包含实例化终结点时要使用的绑定配置的名称。</span><span class="sxs-lookup"><span data-stu-id="ebf93-130">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="ebf93-131">定义终结点时，绑定配置必须在作用域内。</span><span class="sxs-lookup"><span data-stu-id="ebf93-131">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="ebf93-132">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="ebf93-132">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="ebf93-133">此属性与 `binding` 结合使用，以引用配置文件中的特定绑定配置。</span><span class="sxs-lookup"><span data-stu-id="ebf93-133">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="ebf93-134">如果尝试使用自定义绑定，请设置此属性。</span><span class="sxs-lookup"><span data-stu-id="ebf93-134">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="ebf93-135">否则，可能引发异常。</span><span class="sxs-lookup"><span data-stu-id="ebf93-135">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="ebf93-136">协定 (contract)</span><span class="sxs-lookup"><span data-stu-id="ebf93-136">contract</span></span>|<span data-ttu-id="ebf93-137">必需的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="ebf93-137">Required string attribute.</span></span><br /><br /> <span data-ttu-id="ebf93-138">一个字符串，指示此终结点公开了哪个协定。</span><span class="sxs-lookup"><span data-stu-id="ebf93-138">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="ebf93-139">程序集必须实现该协定类型。</span><span class="sxs-lookup"><span data-stu-id="ebf93-139">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="ebf93-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="ebf93-140">endpointConfiguration</span></span>|<span data-ttu-id="ebf93-141">一个字符串，指定由 `kind` 特性设置的标准终结点的名称，此名称引用此标准终结点的其他配置信息。</span><span class="sxs-lookup"><span data-stu-id="ebf93-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="ebf93-142">必须在 `<standardEndpoints>` 节中定义相同的名称。</span><span class="sxs-lookup"><span data-stu-id="ebf93-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="ebf93-143">kind</span><span class="sxs-lookup"><span data-stu-id="ebf93-143">kind</span></span>|<span data-ttu-id="ebf93-144">一个字符串，指定应用的标准终结点的类型。</span><span class="sxs-lookup"><span data-stu-id="ebf93-144">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="ebf93-145">此类型必须在 `<extensions>` 节或 machine.config 中进行注册。如果未指定任何值，则创建通用通道终结点。</span><span class="sxs-lookup"><span data-stu-id="ebf93-145">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="ebf93-146">NAME</span><span class="sxs-lookup"><span data-stu-id="ebf93-146">name</span></span>|<span data-ttu-id="ebf93-147">可选的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="ebf93-147">Optional string attribute.</span></span> <span data-ttu-id="ebf93-148">此属性唯一标识给定协定的终结点。</span><span class="sxs-lookup"><span data-stu-id="ebf93-148">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="ebf93-149">可以为一个给定协定类型定义多个客户端。</span><span class="sxs-lookup"><span data-stu-id="ebf93-149">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="ebf93-150">每个定义都必须用唯一的配置名称加以区分。</span><span class="sxs-lookup"><span data-stu-id="ebf93-150">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="ebf93-151">如果省略此属性，则将对应的终结点用作与指定协定类型相关联的默认终结点。</span><span class="sxs-lookup"><span data-stu-id="ebf93-151">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="ebf93-152">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="ebf93-152">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="ebf93-153">绑定的 `name` 属性用于通过 WSDL 进行的定义导出。</span><span class="sxs-lookup"><span data-stu-id="ebf93-153">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ebf93-154">子元素</span><span class="sxs-lookup"><span data-stu-id="ebf93-154">Child Elements</span></span>  
  
|<span data-ttu-id="ebf93-155">元素</span><span class="sxs-lookup"><span data-stu-id="ebf93-155">Element</span></span>|<span data-ttu-id="ebf93-156">描述</span><span class="sxs-lookup"><span data-stu-id="ebf93-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ebf93-157">\<headers></span><span class="sxs-lookup"><span data-stu-id="ebf93-157">\<headers></span></span>](headers.md)|<span data-ttu-id="ebf93-158">一个地址标头集合。</span><span class="sxs-lookup"><span data-stu-id="ebf93-158">A collection of address headers.</span></span>|  
|[<span data-ttu-id="ebf93-159">\<identity></span><span class="sxs-lookup"><span data-stu-id="ebf93-159">\<identity></span></span>](identity.md)|<span data-ttu-id="ebf93-160">一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ebf93-160">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ebf93-161">父元素</span><span class="sxs-lookup"><span data-stu-id="ebf93-161">Parent Elements</span></span>  
  
|<span data-ttu-id="ebf93-162">元素</span><span class="sxs-lookup"><span data-stu-id="ebf93-162">Element</span></span>|<span data-ttu-id="ebf93-163">描述</span><span class="sxs-lookup"><span data-stu-id="ebf93-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ebf93-164">\<client></span><span class="sxs-lookup"><span data-stu-id="ebf93-164">\<client></span></span>](client.md)|<span data-ttu-id="ebf93-165">一个配置节，定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="ebf93-165">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ebf93-166">示例</span><span class="sxs-lookup"><span data-stu-id="ebf93-166">Example</span></span>  
 <span data-ttu-id="ebf93-167">这是通道终结点配置的一个示例。</span><span class="sxs-lookup"><span data-stu-id="ebf93-167">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="ebf93-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebf93-168">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="ebf93-169">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="ebf93-169">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="ebf93-170">客户端</span><span class="sxs-lookup"><span data-stu-id="ebf93-170">Clients</span></span>](../../../wcf/feature-details/clients.md)
