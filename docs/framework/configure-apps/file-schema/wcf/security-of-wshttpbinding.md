---
title: "&lt;wsHttpBinding&gt; 的 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 30f44ad6ce7219ddd874108e62111ff947d7aa0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltwshttpbindinggt"></a><span data-ttu-id="a2cd3-102">&lt;wsHttpBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="a2cd3-102">&lt;security&gt; of &lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="a2cd3-103">表示的安全功能[ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-103">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="a2cd3-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a2cd3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a2cd3-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a2cd3-105">\<bindings></span></span>  
<span data-ttu-id="a2cd3-106">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a2cd3-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="a2cd3-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a2cd3-107">\<binding></span></span>  
<span data-ttu-id="a2cd3-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="a2cd3-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2cd3-109">语法</span><span class="sxs-lookup"><span data-stu-id="a2cd3-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">  
   <transport  
         clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string"   
      defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      defaultRealm="string" />  
   <message  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
       establishSecurityContext="Boolean"   
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2cd3-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a2cd3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a2cd3-111">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2cd3-112">特性</span><span class="sxs-lookup"><span data-stu-id="a2cd3-112">Attributes</span></span>  
  
|<span data-ttu-id="a2cd3-113">特性</span><span class="sxs-lookup"><span data-stu-id="a2cd3-113">Attribute</span></span>|<span data-ttu-id="a2cd3-114">描述</span><span class="sxs-lookup"><span data-stu-id="a2cd3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a2cd3-115">mode</span><span class="sxs-lookup"><span data-stu-id="a2cd3-115">mode</span></span>|<span data-ttu-id="a2cd3-116">-可选。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-116">-   Optional.</span></span> <span data-ttu-id="a2cd3-117">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="a2cd3-118">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-118">The default is `Message`.</span></span><br /><span data-ttu-id="a2cd3-119">-此特性的类型是<xref:System.ServiceModel.SecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a2cd3-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="a2cd3-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="a2cd3-121">值</span><span class="sxs-lookup"><span data-stu-id="a2cd3-121">Value</span></span>|<span data-ttu-id="a2cd3-122">描述</span><span class="sxs-lookup"><span data-stu-id="a2cd3-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a2cd3-123">无</span><span class="sxs-lookup"><span data-stu-id="a2cd3-123">None</span></span>|<span data-ttu-id="a2cd3-124">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-124">Security is disabled.</span></span>|  
|<span data-ttu-id="a2cd3-125">传输</span><span class="sxs-lookup"><span data-stu-id="a2cd3-125">Transport</span></span>|<span data-ttu-id="a2cd3-126">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="a2cd3-127">此服务需要使用 SSL 证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="a2cd3-128">消息使用 HTTPS 得到了全面保护，客户端使用服务的 SSL 证书对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="a2cd3-129">客户端身份验证通过`ClientCredentials`</span><span class="sxs-lookup"><span data-stu-id="a2cd3-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="a2cd3-130">[\<传输 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-130">of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="a2cd3-131">消息</span><span class="sxs-lookup"><span data-stu-id="a2cd3-131">Message</span></span>|<span data-ttu-id="a2cd3-132">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="a2cd3-133">默认情况下，将对 SOAP 正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="a2cd3-134">此模式提供了各种各样的功能，例如服务凭据在带外客户端是否可用、要使用的算法组以及通过 Security.Message 属性要应用于消息正文的保护级别。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="a2cd3-135">每个会话将执行一次客户端身份验证，身份验证的结果在会话过程中将被缓存。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="a2cd3-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="a2cd3-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="a2cd3-137">在此模式下，HTTPS 将提供完整性、保密性和服务器身份验证，SOAP 消息安全将提供客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="a2cd3-138">默认情况下，每个会话将执行一次客户端身份验证，身份验证的结果在会话过程中将被缓存。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2cd3-139">子元素</span><span class="sxs-lookup"><span data-stu-id="a2cd3-139">Child Elements</span></span>  
  
|<span data-ttu-id="a2cd3-140">元素</span><span class="sxs-lookup"><span data-stu-id="a2cd3-140">Element</span></span>|<span data-ttu-id="a2cd3-141">描述</span><span class="sxs-lookup"><span data-stu-id="a2cd3-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2cd3-142">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="a2cd3-142">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)|<span data-ttu-id="a2cd3-143">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-143">Defines the transport security settings.</span></span> <span data-ttu-id="a2cd3-144">此元素与 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 类型相对应。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="a2cd3-145">\<消息 ></span><span class="sxs-lookup"><span data-stu-id="a2cd3-145">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)|<span data-ttu-id="a2cd3-146">定义消息的安全设置。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-146">Defines the security settings for the message.</span></span> <span data-ttu-id="a2cd3-147">此元素与 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 类型相对应。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2cd3-148">父元素</span><span class="sxs-lookup"><span data-stu-id="a2cd3-148">Parent Elements</span></span>  
  
|<span data-ttu-id="a2cd3-149">元素</span><span class="sxs-lookup"><span data-stu-id="a2cd3-149">Element</span></span>|<span data-ttu-id="a2cd3-150">描述</span><span class="sxs-lookup"><span data-stu-id="a2cd3-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2cd3-151">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a2cd3-151">\<wsHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="a2cd3-152">HTTP 传输应用程序的安全绑定。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2cd3-153">备注</span><span class="sxs-lookup"><span data-stu-id="a2cd3-153">Remarks</span></span>  
 <span data-ttu-id="a2cd3-154">WSHttpBinding 类专用于与实现 WS-* 规范的服务进行互操作。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-154">The WSHttpBinding class is designed for interoperation with services that implement WS-* specifications.</span></span> <span data-ttu-id="a2cd3-155">此绑定的传输安全为 HTTP 上的安全套接字层 (SSL)，即 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="a2cd3-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2cd3-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2cd3-156">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 [<span data-ttu-id="a2cd3-157">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="a2cd3-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="a2cd3-158">绑定</span><span class="sxs-lookup"><span data-stu-id="a2cd3-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a2cd3-159">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="a2cd3-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a2cd3-160">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="a2cd3-160">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a2cd3-161">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a2cd3-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
