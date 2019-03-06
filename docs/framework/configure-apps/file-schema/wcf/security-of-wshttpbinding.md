---
title: <security> 的 <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: 0de9ade585a2170aa1def9898581aedddc651bd7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366083"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="19272-102">\<安全 > 的\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="19272-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="19272-103">表示的安全功能[ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="19272-103">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="19272-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="19272-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="19272-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="19272-105">\<bindings></span></span>  
<span data-ttu-id="19272-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="19272-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="19272-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="19272-107">\<binding></span></span>  
<span data-ttu-id="19272-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="19272-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19272-109">语法</span><span class="sxs-lookup"><span data-stu-id="19272-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="String"
             defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             defaultRealm="String" />
  <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           establishSecurityContext="Boolean"
           negotiateServiceCredential="Boolean" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19272-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="19272-110">Attributes and Elements</span></span>  
 <span data-ttu-id="19272-111">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="19272-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19272-112">特性</span><span class="sxs-lookup"><span data-stu-id="19272-112">Attributes</span></span>  
  
|<span data-ttu-id="19272-113">特性</span><span class="sxs-lookup"><span data-stu-id="19272-113">Attribute</span></span>|<span data-ttu-id="19272-114">描述</span><span class="sxs-lookup"><span data-stu-id="19272-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19272-115">mode</span><span class="sxs-lookup"><span data-stu-id="19272-115">mode</span></span>|<span data-ttu-id="19272-116">-可选。</span><span class="sxs-lookup"><span data-stu-id="19272-116">-   Optional.</span></span> <span data-ttu-id="19272-117">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="19272-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="19272-118">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="19272-118">The default is `Message`.</span></span><br /><span data-ttu-id="19272-119">-此特性的类型是<xref:System.ServiceModel.SecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="19272-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="19272-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="19272-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="19272-121">值</span><span class="sxs-lookup"><span data-stu-id="19272-121">Value</span></span>|<span data-ttu-id="19272-122">描述</span><span class="sxs-lookup"><span data-stu-id="19272-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="19272-123">无</span><span class="sxs-lookup"><span data-stu-id="19272-123">None</span></span>|<span data-ttu-id="19272-124">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="19272-124">Security is disabled.</span></span>|  
|<span data-ttu-id="19272-125">传输</span><span class="sxs-lookup"><span data-stu-id="19272-125">Transport</span></span>|<span data-ttu-id="19272-126">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="19272-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="19272-127">此服务需要使用 SSL 证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="19272-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="19272-128">消息使用 HTTPS 得到了全面保护，客户端使用服务的 SSL 证书对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="19272-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="19272-129">客户端身份验证通过`ClientCredentials`</span><span class="sxs-lookup"><span data-stu-id="19272-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="19272-130">[\<传输 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="19272-130">of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="19272-131">消息</span><span class="sxs-lookup"><span data-stu-id="19272-131">Message</span></span>|<span data-ttu-id="19272-132">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="19272-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="19272-133">默认情况下，将对 SOAP 正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="19272-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="19272-134">此模式提供了各种各样的功能，例如服务凭据在带外客户端是否可用、要使用的算法组以及通过 Security.Message 属性要应用于消息正文的保护级别。</span><span class="sxs-lookup"><span data-stu-id="19272-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="19272-135">每个会话将执行一次客户端身份验证，身份验证的结果在会话过程中将被缓存。</span><span class="sxs-lookup"><span data-stu-id="19272-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="19272-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="19272-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="19272-137">在此模式下，HTTPS 将提供完整性、保密性和服务器身份验证，SOAP 消息安全将提供客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="19272-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="19272-138">默认情况下，每个会话将执行一次客户端身份验证，身份验证的结果在会话过程中将被缓存。</span><span class="sxs-lookup"><span data-stu-id="19272-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19272-139">子元素</span><span class="sxs-lookup"><span data-stu-id="19272-139">Child Elements</span></span>  
  
|<span data-ttu-id="19272-140">元素</span><span class="sxs-lookup"><span data-stu-id="19272-140">Element</span></span>|<span data-ttu-id="19272-141">描述</span><span class="sxs-lookup"><span data-stu-id="19272-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19272-142">\<transport></span><span class="sxs-lookup"><span data-stu-id="19272-142">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)|<span data-ttu-id="19272-143">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="19272-143">Defines the transport security settings.</span></span> <span data-ttu-id="19272-144">此元素与 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 类型相对应。</span><span class="sxs-lookup"><span data-stu-id="19272-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="19272-145">\<message></span><span class="sxs-lookup"><span data-stu-id="19272-145">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)|<span data-ttu-id="19272-146">定义消息的安全设置。</span><span class="sxs-lookup"><span data-stu-id="19272-146">Defines the security settings for the message.</span></span> <span data-ttu-id="19272-147">此元素与 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 类型相对应。</span><span class="sxs-lookup"><span data-stu-id="19272-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19272-148">父元素</span><span class="sxs-lookup"><span data-stu-id="19272-148">Parent Elements</span></span>  
  
|<span data-ttu-id="19272-149">元素</span><span class="sxs-lookup"><span data-stu-id="19272-149">Element</span></span>|<span data-ttu-id="19272-150">描述</span><span class="sxs-lookup"><span data-stu-id="19272-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19272-151">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="19272-151">\<wsHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="19272-152">HTTP 传输应用程序的安全绑定。</span><span class="sxs-lookup"><span data-stu-id="19272-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19272-153">备注</span><span class="sxs-lookup"><span data-stu-id="19272-153">Remarks</span></span>  
 <span data-ttu-id="19272-154">WSHttpBinding 类专用于与实现 WS-\* 规范的服务进行互操作。</span><span class="sxs-lookup"><span data-stu-id="19272-154">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="19272-155">此绑定的传输安全为 HTTP 上的安全套接字层 (SSL)，即 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="19272-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19272-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="19272-156">See also</span></span>
- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="19272-157">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="19272-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="19272-158">绑定</span><span class="sxs-lookup"><span data-stu-id="19272-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="19272-159">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="19272-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="19272-160">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="19272-160">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="19272-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="19272-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
