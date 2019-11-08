---
title: <security> 的 <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: c8e4f2d000a155eecd2a6c7faaaf4af525b24ca3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738717"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="99b5c-102">\<basicHttpBinding 的安全 > \<</span><span class="sxs-lookup"><span data-stu-id="99b5c-102">\<security> of \<basicHttpBinding></span></span>
<span data-ttu-id="99b5c-103">定义[\<basicHttpBinding >](basichttpbinding.md)的安全功能。</span><span class="sxs-lookup"><span data-stu-id="99b5c-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
<span data-ttu-id="99b5c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="99b5c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="99b5c-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="99b5c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="99b5c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="99b5c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="99b5c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<basicHttpBinding >** ](basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="99b5c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="99b5c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="99b5c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="99b5c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<** ></span><span class="sxs-lookup"><span data-stu-id="99b5c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99b5c-110">语法</span><span class="sxs-lookup"><span data-stu-id="99b5c-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99b5c-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="99b5c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="99b5c-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="99b5c-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99b5c-113">特性</span><span class="sxs-lookup"><span data-stu-id="99b5c-113">Attributes</span></span>  
  
|<span data-ttu-id="99b5c-114">特性</span><span class="sxs-lookup"><span data-stu-id="99b5c-114">Attribute</span></span>|<span data-ttu-id="99b5c-115">描述</span><span class="sxs-lookup"><span data-stu-id="99b5c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99b5c-116">mode</span><span class="sxs-lookup"><span data-stu-id="99b5c-116">mode</span></span>|<span data-ttu-id="99b5c-117">可选。</span><span class="sxs-lookup"><span data-stu-id="99b5c-117">Optional.</span></span> <span data-ttu-id="99b5c-118">指定所使用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="99b5c-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="99b5c-119">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="99b5c-119">The default is `None`.</span></span> <span data-ttu-id="99b5c-120">此属性的类型为 <xref:System.ServiceModel.BasicHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="99b5c-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="99b5c-121">mode 属性</span><span class="sxs-lookup"><span data-stu-id="99b5c-121">mode Attribute</span></span>  
  
|<span data-ttu-id="99b5c-122">“值”</span><span class="sxs-lookup"><span data-stu-id="99b5c-122">Value</span></span>|<span data-ttu-id="99b5c-123">描述</span><span class="sxs-lookup"><span data-stu-id="99b5c-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99b5c-124">None</span><span class="sxs-lookup"><span data-stu-id="99b5c-124">None</span></span>|<span data-ttu-id="99b5c-125">-传输过程中消息不受保护。</span><span class="sxs-lookup"><span data-stu-id="99b5c-125">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="99b5c-126">传输</span><span class="sxs-lookup"><span data-stu-id="99b5c-126">Transport</span></span>|<span data-ttu-id="99b5c-127">使用 HTTPS 传输提供安全性。</span><span class="sxs-lookup"><span data-stu-id="99b5c-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="99b5c-128">用 HTTPS 保证 SOAP 消息的安全。</span><span class="sxs-lookup"><span data-stu-id="99b5c-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="99b5c-129">使用服务的 X.509 证书向客户端对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="99b5c-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="99b5c-130">使用所提供的 ClientCredentialType 对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="99b5c-130">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="99b5c-131">请参阅[\<传输 >](transport-of-basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="99b5c-131">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="99b5c-132">消息</span><span class="sxs-lookup"><span data-stu-id="99b5c-132">Message</span></span>|<span data-ttu-id="99b5c-133">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="99b5c-133">Security is provided using SOAP message security.</span></span> <span data-ttu-id="99b5c-134">默认情况下，将对正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="99b5c-134">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="99b5c-135">对于此绑定，系统要求向带外客户端提供服务器证书。</span><span class="sxs-lookup"><span data-stu-id="99b5c-135">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="99b5c-136">此绑定仅有的有效 `ClientCredentialType` 为 `Certificate`。</span><span class="sxs-lookup"><span data-stu-id="99b5c-136">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="99b5c-137">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="99b5c-137">TransportWithMessageCredential</span></span>|<span data-ttu-id="99b5c-138">完整性、保密性和服务器身份验证由传输安全来提供。</span><span class="sxs-lookup"><span data-stu-id="99b5c-138">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="99b5c-139">客户端身份验证采用 SOAP 消息安全方式提供。</span><span class="sxs-lookup"><span data-stu-id="99b5c-139">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="99b5c-140">如果要使用用户名/密码对用户进行身份验证，并且存在用于保护消息传输的现有 HTTP 部署，则适用此模式。</span><span class="sxs-lookup"><span data-stu-id="99b5c-140">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="99b5c-141">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="99b5c-141">TransportCredentialOnly</span></span>|<span data-ttu-id="99b5c-142">此模式并不提供消息的完整性和保密性，</span><span class="sxs-lookup"><span data-stu-id="99b5c-142">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="99b5c-143">而是提供基于 http 的客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="99b5c-143">It provides http-based client authentication.</span></span> <span data-ttu-id="99b5c-144">使用此模式时应当小心。</span><span class="sxs-lookup"><span data-stu-id="99b5c-144">This mode should be used with caution.</span></span> <span data-ttu-id="99b5c-145">在通过其他方式（如 IPSec）提供传输安全，并且 WCF 基础结构仅提供客户端身份验证的环境中，应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="99b5c-145">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99b5c-146">子元素</span><span class="sxs-lookup"><span data-stu-id="99b5c-146">Child Elements</span></span>  
  
|<span data-ttu-id="99b5c-147">元素</span><span class="sxs-lookup"><span data-stu-id="99b5c-147">Element</span></span>|<span data-ttu-id="99b5c-148">描述</span><span class="sxs-lookup"><span data-stu-id="99b5c-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99b5c-149">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="99b5c-149">\<transport></span></span>](transport-of-basichttpbinding.md)|<span data-ttu-id="99b5c-150">定义基本 HTTP 服务的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="99b5c-150">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="99b5c-151">此元素与 <xref:System.ServiceModel.HttpTransportSecurity> 相对应。</span><span class="sxs-lookup"><span data-stu-id="99b5c-151">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="99b5c-152">\<message ></span><span class="sxs-lookup"><span data-stu-id="99b5c-152">\<message></span></span>](message-of-basichttpbinding.md)|<span data-ttu-id="99b5c-153">定义基本 HTTP 服务的消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="99b5c-153">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="99b5c-154">此元素与 <xref:System.ServiceModel.BasicHttpMessageSecurity> 相对应。</span><span class="sxs-lookup"><span data-stu-id="99b5c-154">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99b5c-155">父元素</span><span class="sxs-lookup"><span data-stu-id="99b5c-155">Parent Elements</span></span>  
  
|<span data-ttu-id="99b5c-156">元素</span><span class="sxs-lookup"><span data-stu-id="99b5c-156">Element</span></span>|<span data-ttu-id="99b5c-157">描述</span><span class="sxs-lookup"><span data-stu-id="99b5c-157">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99b5c-158">绑定</span><span class="sxs-lookup"><span data-stu-id="99b5c-158">binding</span></span>|<span data-ttu-id="99b5c-159">[\<basicHttpBinding >](basichttpbinding.md)的绑定元素。</span><span class="sxs-lookup"><span data-stu-id="99b5c-159">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99b5c-160">备注</span><span class="sxs-lookup"><span data-stu-id="99b5c-160">Remarks</span></span>  
 <span data-ttu-id="99b5c-161">默认情况下，不会对 SOAP 消息进行保护，也不会对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="99b5c-161">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="99b5c-162">使用此元素，您可以配置 `basicHttpBinding` 元素的其他安全设置。</span><span class="sxs-lookup"><span data-stu-id="99b5c-162">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b5c-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="99b5c-163">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="99b5c-164">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="99b5c-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="99b5c-165">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="99b5c-165">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="99b5c-166">绑定</span><span class="sxs-lookup"><span data-stu-id="99b5c-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="99b5c-167">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="99b5c-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="99b5c-168">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="99b5c-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="99b5c-169">\<binding ></span><span class="sxs-lookup"><span data-stu-id="99b5c-169">\<binding></span></span>](bindings.md)
