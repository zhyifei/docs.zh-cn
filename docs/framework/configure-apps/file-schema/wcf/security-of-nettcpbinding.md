---
title: "&lt;netTcpBinding&gt; 的 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 08e9f1f3b2145d94f491933639211a6eabd3c9fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltnettcpbindinggt"></a><span data-ttu-id="811ca-102">&lt;netTcpBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="811ca-102">&lt;security&gt; of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="811ca-103">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="811ca-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="811ca-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="811ca-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="811ca-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="811ca-105">\<bindings></span></span>  
<span data-ttu-id="811ca-106">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="811ca-106">\<netTcpBinding></span></span>  
<span data-ttu-id="811ca-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="811ca-107">\<binding></span></span>  
<span data-ttu-id="811ca-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="811ca-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="811ca-109">语法</span><span class="sxs-lookup"><span data-stu-id="811ca-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
           protectionLevel="None/Sign/EncryptAndSign" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="811ca-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="811ca-110">Attributes and Elements</span></span>  
 <span data-ttu-id="811ca-111">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="811ca-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="811ca-112">特性</span><span class="sxs-lookup"><span data-stu-id="811ca-112">Attributes</span></span>  
  
|<span data-ttu-id="811ca-113">特性</span><span class="sxs-lookup"><span data-stu-id="811ca-113">Attribute</span></span>|<span data-ttu-id="811ca-114">描述</span><span class="sxs-lookup"><span data-stu-id="811ca-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="811ca-115">mode</span><span class="sxs-lookup"><span data-stu-id="811ca-115">mode</span></span>|<span data-ttu-id="811ca-116">可选。</span><span class="sxs-lookup"><span data-stu-id="811ca-116">Optional.</span></span> <span data-ttu-id="811ca-117">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="811ca-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="811ca-118">以下列出了有效值。</span><span class="sxs-lookup"><span data-stu-id="811ca-118">Valid values are shown below.</span></span> <span data-ttu-id="811ca-119">默认值为 `Transport`。</span><span class="sxs-lookup"><span data-stu-id="811ca-119">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="811ca-120">此属性的类型为 <xref:System.ServiceModel.SecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="811ca-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="811ca-121">mode 属性</span><span class="sxs-lookup"><span data-stu-id="811ca-121">mode Attribute</span></span>  
  
|<span data-ttu-id="811ca-122">值</span><span class="sxs-lookup"><span data-stu-id="811ca-122">Value</span></span>|<span data-ttu-id="811ca-123">描述</span><span class="sxs-lookup"><span data-stu-id="811ca-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="811ca-124">无</span><span class="sxs-lookup"><span data-stu-id="811ca-124">None</span></span>|<span data-ttu-id="811ca-125">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="811ca-125">Security is disabled.</span></span>|  
|<span data-ttu-id="811ca-126">传输</span><span class="sxs-lookup"><span data-stu-id="811ca-126">Transport</span></span>|<span data-ttu-id="811ca-127">使用 TLS over TCP 或 SPNego 提供传输安全性。</span><span class="sxs-lookup"><span data-stu-id="811ca-127">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="811ca-128">此服务可能需要使用 SSL 证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="811ca-128">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="811ca-129">可以通过此模式来控制保护级别。</span><span class="sxs-lookup"><span data-stu-id="811ca-129">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="811ca-130">消息</span><span class="sxs-lookup"><span data-stu-id="811ca-130">Message</span></span>|<span data-ttu-id="811ca-131">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="811ca-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="811ca-132">默认情况下，将对 SOAP 正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="811ca-132">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="811ca-133">此模式提供了各种各样的功能，例如服务凭据在带外客户端是否可用、要使用的算法组以及要应用于消息正文的保护级别。</span><span class="sxs-lookup"><span data-stu-id="811ca-133">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="811ca-134">每个会话将执行一次客户端身份验证，身份验证的结果在会话过程中将被缓存。</span><span class="sxs-lookup"><span data-stu-id="811ca-134">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="811ca-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="811ca-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="811ca-136">传输安全性与消息安全性结合使用。</span><span class="sxs-lookup"><span data-stu-id="811ca-136">Transport security is coupled with message security.</span></span> <span data-ttu-id="811ca-137">使用 TLS over TCP 或 SPNego 提供传输安全性，传输安全性可确保完整性、保密性和服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="811ca-137">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="811ca-138">SOAP 消息安全性提供客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="811ca-138">SOAP message security provides client authentication.</span></span> <span data-ttu-id="811ca-139">默认情况下，每个会话将执行一次客户端身份验证，身份验证的结果在会话过程中将被缓存。</span><span class="sxs-lookup"><span data-stu-id="811ca-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="811ca-140">子元素</span><span class="sxs-lookup"><span data-stu-id="811ca-140">Child Elements</span></span>  
  
|<span data-ttu-id="811ca-141">元素</span><span class="sxs-lookup"><span data-stu-id="811ca-141">Element</span></span>|<span data-ttu-id="811ca-142">描述</span><span class="sxs-lookup"><span data-stu-id="811ca-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="811ca-143">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="811ca-143">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)|<span data-ttu-id="811ca-144">定义传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="811ca-144">Defines the security settings for the transport.</span></span> <span data-ttu-id="811ca-145">此元素的类型为 <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="811ca-145">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[<span data-ttu-id="811ca-146">\<消息 ></span><span class="sxs-lookup"><span data-stu-id="811ca-146">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)|<span data-ttu-id="811ca-147">定义消息的安全设置。</span><span class="sxs-lookup"><span data-stu-id="811ca-147">Defines the security settings for the message.</span></span> <span data-ttu-id="811ca-148">此元素的类型为 <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>。</span><span class="sxs-lookup"><span data-stu-id="811ca-148">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="811ca-149">父元素</span><span class="sxs-lookup"><span data-stu-id="811ca-149">Parent Elements</span></span>  
  
|<span data-ttu-id="811ca-150">元素</span><span class="sxs-lookup"><span data-stu-id="811ca-150">Element</span></span>|<span data-ttu-id="811ca-151">描述</span><span class="sxs-lookup"><span data-stu-id="811ca-151">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="811ca-152">绑定</span><span class="sxs-lookup"><span data-stu-id="811ca-152">binding</span></span>|<span data-ttu-id="811ca-153">绑定元素[ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="811ca-153">The binding element of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="811ca-154">备注</span><span class="sxs-lookup"><span data-stu-id="811ca-154">Remarks</span></span>  
 <span data-ttu-id="811ca-155">每个标准绑定都提供用于控制传输安全性要求的参数。</span><span class="sxs-lookup"><span data-stu-id="811ca-155">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="811ca-156">这些参数通常包括指定是使用消息级安全性还是使用传输级安全性的安全模式，还包括客户端凭据类型的选项。</span><span class="sxs-lookup"><span data-stu-id="811ca-156">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="811ca-157">基于这些参数提供的可供选择的选项，构建一个具有适当安全性的信道堆栈。</span><span class="sxs-lookup"><span data-stu-id="811ca-157">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="811ca-158">由 Windows Communication Foundation (WCF) 提供的系统提供的绑定是一组旨在满足一些最常见的方案要求的绑定。</span><span class="sxs-lookup"><span data-stu-id="811ca-158">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="811ca-159">所有这些绑定都允许为某些特定的目标方案指定安全要求。</span><span class="sxs-lookup"><span data-stu-id="811ca-159">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="811ca-160">此配置元素提供用于 `netTcpBinding` 的安全规范。</span><span class="sxs-lookup"><span data-stu-id="811ca-160">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="811ca-161">这是一种适合于跨计算机通信的安全、可靠且进行了优化的绑定。</span><span class="sxs-lookup"><span data-stu-id="811ca-161">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="811ca-162">默认情况下，它生成运行时通信堆栈，该堆栈支持用于消息传递的 TCP、消息安全性和身份验证的 Windows 安全、可靠的 WS-ReliableMessaging，以及二进制消息编码。</span><span class="sxs-lookup"><span data-stu-id="811ca-162">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="811ca-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="811ca-163">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpSecurity>  
 <xref:System.ServiceModel.NetTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [<span data-ttu-id="811ca-164">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="811ca-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="811ca-165">绑定</span><span class="sxs-lookup"><span data-stu-id="811ca-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="811ca-166">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="811ca-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="811ca-167">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="811ca-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="811ca-168">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="811ca-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
