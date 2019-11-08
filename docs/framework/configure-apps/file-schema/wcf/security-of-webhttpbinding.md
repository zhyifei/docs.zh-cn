---
title: <security> 的 <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 77009dc950a608da9e0db3a7d09be67e1ed46137
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738638"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="e0fa6-102">\<webHttpBinding 的安全 > \<</span><span class="sxs-lookup"><span data-stu-id="e0fa6-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="e0fa6-103">指定使用[\<webHttpBinding >](webhttpbinding.md)配置的终结点的安全要求。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
<span data-ttu-id="e0fa6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e0fa6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e0fa6-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="e0fa6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e0fa6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e0fa6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e0fa6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webHttpBinding >** ](webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="e0fa6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="e0fa6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="e0fa6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e0fa6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<** ></span><span class="sxs-lookup"><span data-stu-id="e0fa6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0fa6-110">语法</span><span class="sxs-lookup"><span data-stu-id="e0fa6-110">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0fa6-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e0fa6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e0fa6-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0fa6-113">特性</span><span class="sxs-lookup"><span data-stu-id="e0fa6-113">Attributes</span></span>  
  
|<span data-ttu-id="e0fa6-114">特性</span><span class="sxs-lookup"><span data-stu-id="e0fa6-114">Attribute</span></span>|<span data-ttu-id="e0fa6-115">描述</span><span class="sxs-lookup"><span data-stu-id="e0fa6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0fa6-116">mode</span><span class="sxs-lookup"><span data-stu-id="e0fa6-116">mode</span></span>|<span data-ttu-id="e0fa6-117">指定终结点是使用传输级安全模式还是不使用安全模式。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-117">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="e0fa6-118">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-118">The default is `None`.</span></span> <span data-ttu-id="e0fa6-119">此属性的类型为 <xref:System.ServiceModel.WebHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-119">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e0fa6-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="e0fa6-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="e0fa6-121">“值”</span><span class="sxs-lookup"><span data-stu-id="e0fa6-121">Value</span></span>|<span data-ttu-id="e0fa6-122">描述</span><span class="sxs-lookup"><span data-stu-id="e0fa6-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e0fa6-123">None</span><span class="sxs-lookup"><span data-stu-id="e0fa6-123">None</span></span>|<span data-ttu-id="e0fa6-124">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-124">Security is disabled.</span></span>|  
|<span data-ttu-id="e0fa6-125">传输</span><span class="sxs-lookup"><span data-stu-id="e0fa6-125">Transport</span></span>|<span data-ttu-id="e0fa6-126">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="e0fa6-127">此服务需要使用 SSL 证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="e0fa6-128">消息使用 HTTPS 获得全面保护，而且客户端使用服务的 SSL 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-128">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="e0fa6-129">客户端身份验证通过[\<传输 >](transport-of-webhttpbinding.md)的 `ClientCredentialType` 属性进行控制。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-129">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="e0fa6-130">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="e0fa6-130">TransportCredentialOnly</span></span>|<span data-ttu-id="e0fa6-131">此模式并不提供消息的完整性和保密性，</span><span class="sxs-lookup"><span data-stu-id="e0fa6-131">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="e0fa6-132">而是提供基于 HTTP 的客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-132">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="e0fa6-133">使用此模式时应当小心。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-133">This mode should be used with caution.</span></span> <span data-ttu-id="e0fa6-134">在通过其他方式（如 IPSec）提供传输安全，并且 WCF 基础结构仅提供客户端身份验证的环境中，应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-134">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0fa6-135">子元素</span><span class="sxs-lookup"><span data-stu-id="e0fa6-135">Child Elements</span></span>  
  
|<span data-ttu-id="e0fa6-136">元素</span><span class="sxs-lookup"><span data-stu-id="e0fa6-136">Element</span></span>|<span data-ttu-id="e0fa6-137">描述</span><span class="sxs-lookup"><span data-stu-id="e0fa6-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0fa6-138">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="e0fa6-138">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="e0fa6-139">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-139">Defines the transport security settings.</span></span> <span data-ttu-id="e0fa6-140">此元素与 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 类型相对应。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-140">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e0fa6-141">父元素</span><span class="sxs-lookup"><span data-stu-id="e0fa6-141">Parent Elements</span></span>  
  
|<span data-ttu-id="e0fa6-142">元素</span><span class="sxs-lookup"><span data-stu-id="e0fa6-142">Element</span></span>|<span data-ttu-id="e0fa6-143">描述</span><span class="sxs-lookup"><span data-stu-id="e0fa6-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0fa6-144">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e0fa6-144">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="e0fa6-145">一个绑定元素，用于为响应 HTTP 请求（而不是 SOAP 消息）的 Windows Communication Foundation （WCF） Web 服务配置终结点。</span><span class="sxs-lookup"><span data-stu-id="e0fa6-145">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0fa6-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0fa6-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="e0fa6-147">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="e0fa6-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e0fa6-148">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="e0fa6-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="e0fa6-149">绑定</span><span class="sxs-lookup"><span data-stu-id="e0fa6-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e0fa6-150">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="e0fa6-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e0fa6-151">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="e0fa6-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e0fa6-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="e0fa6-152">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="e0fa6-153">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="e0fa6-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
