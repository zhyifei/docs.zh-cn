---
title: <security> 的 <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: e627a63221d0013c89495d7ff81e02047a03df89
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936512"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="7de22-102">\<wsHttpBinding 的\<安全 > ></span><span class="sxs-lookup"><span data-stu-id="7de22-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="7de22-103">表示[ \<wsHttpBinding >](wshttpbinding.md)的安全功能。</span><span class="sxs-lookup"><span data-stu-id="7de22-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="7de22-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7de22-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7de22-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7de22-105">\<bindings></span></span>  
<span data-ttu-id="7de22-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="7de22-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="7de22-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="7de22-107">\<binding></span></span>  
<span data-ttu-id="7de22-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="7de22-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7de22-109">语法</span><span class="sxs-lookup"><span data-stu-id="7de22-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7de22-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7de22-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7de22-111">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7de22-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7de22-112">特性</span><span class="sxs-lookup"><span data-stu-id="7de22-112">Attributes</span></span>  
  
|<span data-ttu-id="7de22-113">特性</span><span class="sxs-lookup"><span data-stu-id="7de22-113">Attribute</span></span>|<span data-ttu-id="7de22-114">描述</span><span class="sxs-lookup"><span data-stu-id="7de22-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7de22-115">mode</span><span class="sxs-lookup"><span data-stu-id="7de22-115">mode</span></span>|<span data-ttu-id="7de22-116">可有可无.</span><span class="sxs-lookup"><span data-stu-id="7de22-116">-   Optional.</span></span> <span data-ttu-id="7de22-117">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="7de22-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="7de22-118">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="7de22-118">The default is `Message`.</span></span><br /><span data-ttu-id="7de22-119">-此属性的类型<xref:System.ServiceModel.SecurityMode>为。</span><span class="sxs-lookup"><span data-stu-id="7de22-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="7de22-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="7de22-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="7de22-121">值</span><span class="sxs-lookup"><span data-stu-id="7de22-121">Value</span></span>|<span data-ttu-id="7de22-122">描述</span><span class="sxs-lookup"><span data-stu-id="7de22-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7de22-123">无</span><span class="sxs-lookup"><span data-stu-id="7de22-123">None</span></span>|<span data-ttu-id="7de22-124">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="7de22-124">Security is disabled.</span></span>|  
|<span data-ttu-id="7de22-125">传输</span><span class="sxs-lookup"><span data-stu-id="7de22-125">Transport</span></span>|<span data-ttu-id="7de22-126">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="7de22-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="7de22-127">此服务需要使用 SSL 证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="7de22-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="7de22-128">消息使用 HTTPS 得到了全面保护，客户端使用服务的 SSL 证书对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="7de22-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="7de22-129">客户端身份验证通过`ClientCredentials`</span><span class="sxs-lookup"><span data-stu-id="7de22-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="7de22-130">传输 > [ \<](transport-of-wshttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="7de22-130">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="7de22-131">消息</span><span class="sxs-lookup"><span data-stu-id="7de22-131">Message</span></span>|<span data-ttu-id="7de22-132">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="7de22-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="7de22-133">默认情况下，将对 SOAP 正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="7de22-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="7de22-134">此模式提供了各种各样的功能，例如服务凭据在带外客户端是否可用、要使用的算法套件以及通过 Security.Message 属性要应用于消息正文的保护级别。</span><span class="sxs-lookup"><span data-stu-id="7de22-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="7de22-135">每个会话将执行一次客户端身份验证，身份验证的结果在会话过程中将被缓存。</span><span class="sxs-lookup"><span data-stu-id="7de22-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="7de22-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="7de22-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="7de22-137">在此模式下，HTTPS 将提供完整性、保密性和服务器身份验证，SOAP 消息安全将提供客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="7de22-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="7de22-138">默认情况下，每个会话将执行一次客户端身份验证，身份验证的结果在会话过程中将被缓存。</span><span class="sxs-lookup"><span data-stu-id="7de22-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7de22-139">子元素</span><span class="sxs-lookup"><span data-stu-id="7de22-139">Child Elements</span></span>  
  
|<span data-ttu-id="7de22-140">元素</span><span class="sxs-lookup"><span data-stu-id="7de22-140">Element</span></span>|<span data-ttu-id="7de22-141">描述</span><span class="sxs-lookup"><span data-stu-id="7de22-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7de22-142">\<transport></span><span class="sxs-lookup"><span data-stu-id="7de22-142">\<transport></span></span>](transport-of-wshttpbinding.md)|<span data-ttu-id="7de22-143">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="7de22-143">Defines the transport security settings.</span></span> <span data-ttu-id="7de22-144">此元素与 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 类型相对应。</span><span class="sxs-lookup"><span data-stu-id="7de22-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="7de22-145">\<message></span><span class="sxs-lookup"><span data-stu-id="7de22-145">\<message></span></span>](message-of-wshttpbinding.md)|<span data-ttu-id="7de22-146">定义消息的安全设置。</span><span class="sxs-lookup"><span data-stu-id="7de22-146">Defines the security settings for the message.</span></span> <span data-ttu-id="7de22-147">此元素与 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 类型相对应。</span><span class="sxs-lookup"><span data-stu-id="7de22-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7de22-148">父元素</span><span class="sxs-lookup"><span data-stu-id="7de22-148">Parent Elements</span></span>  
  
|<span data-ttu-id="7de22-149">元素</span><span class="sxs-lookup"><span data-stu-id="7de22-149">Element</span></span>|<span data-ttu-id="7de22-150">描述</span><span class="sxs-lookup"><span data-stu-id="7de22-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7de22-151">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="7de22-151">\<wsHttpBinding></span></span>](wshttpbinding.md)|<span data-ttu-id="7de22-152">HTTP 传输应用程序的安全绑定。</span><span class="sxs-lookup"><span data-stu-id="7de22-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7de22-153">备注</span><span class="sxs-lookup"><span data-stu-id="7de22-153">Remarks</span></span>  
 <span data-ttu-id="7de22-154">WSHttpBinding 类专用于与实现 WS-\* 规范的服务进行互操作。</span><span class="sxs-lookup"><span data-stu-id="7de22-154">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="7de22-155">此绑定的传输安全为 HTTP 上的安全套接字层 (SSL)，即 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="7de22-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7de22-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="7de22-156">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="7de22-157">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="7de22-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7de22-158">绑定</span><span class="sxs-lookup"><span data-stu-id="7de22-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7de22-159">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="7de22-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7de22-160">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="7de22-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7de22-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="7de22-161">\<binding></span></span>](../../../misc/binding.md)
