---
title: "&lt;netTcpBinding&gt; 的 &lt;transport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5cf7a0aedc1fcd387b4b41233cd7c31b7ec64de4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltnettcpbindinggt"></a><span data-ttu-id="445a9-102">&lt;netTcpBinding&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="445a9-102">&lt;transport&gt; of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="445a9-103">定义与配置的终结点的消息级安全性要求的类型[ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="445a9-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>  
  
 <span data-ttu-id="445a9-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="445a9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="445a9-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="445a9-105">\<bindings></span></span>  
<span data-ttu-id="445a9-106">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="445a9-106">\<netTcpBinding></span></span>  
<span data-ttu-id="445a9-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="445a9-107">\<binding></span></span>  
<span data-ttu-id="445a9-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="445a9-108">\<security></span></span>  
<span data-ttu-id="445a9-109">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="445a9-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="445a9-110">语法</span><span class="sxs-lookup"><span data-stu-id="445a9-110">Syntax</span></span>  
  
```xml  
<netTcpBinding>  
    <binding>  
        <security  
         mode="None|Transport|Message|TransportWithMessageCredential">  
            <transport clientCredentialType="None|Windows|Certificate"  
             protectionLevel="None|Sign|EncryptAndSign"             sslProtocols="Tls|Tls11|Tls12">  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</netTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="445a9-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="445a9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="445a9-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="445a9-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="445a9-113">特性</span><span class="sxs-lookup"><span data-stu-id="445a9-113">Attributes</span></span>  
  
|<span data-ttu-id="445a9-114">特性</span><span class="sxs-lookup"><span data-stu-id="445a9-114">Attribute</span></span>|<span data-ttu-id="445a9-115">描述</span><span class="sxs-lookup"><span data-stu-id="445a9-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="445a9-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="445a9-116">clientCredentialType</span></span>|<span data-ttu-id="445a9-117">可选。</span><span class="sxs-lookup"><span data-stu-id="445a9-117">Optional.</span></span> <span data-ttu-id="445a9-118">指定要在使用传输安全性执行客户端身份验证时使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="445a9-118">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="445a9-119">默认值是`Windows`。</span><span class="sxs-lookup"><span data-stu-id="445a9-119">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="445a9-120">-此特性的类型是<xref:System.ServiceModel.TcpClientCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="445a9-120">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="445a9-121">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="445a9-121">protectionLevel</span></span>|<span data-ttu-id="445a9-122">可选。</span><span class="sxs-lookup"><span data-stu-id="445a9-122">Optional.</span></span> <span data-ttu-id="445a9-123">定义 TCP 传输级别的安全性。</span><span class="sxs-lookup"><span data-stu-id="445a9-123">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="445a9-124">对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="445a9-124">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="445a9-125">加密可以在传输过程中提供数据级保密。</span><span class="sxs-lookup"><span data-stu-id="445a9-125">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="445a9-126">默认值为 `EncryptAndSign`。</span><span class="sxs-lookup"><span data-stu-id="445a9-126">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="445a9-127">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="445a9-127">sslProtocols</span></span>|<span data-ttu-id="445a9-128">指定支持哪些 SslProtocols 的 SslProtocols 枚举标志值。</span><span class="sxs-lookup"><span data-stu-id="445a9-128">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="445a9-129">默认值是 Tls &#124;Tls11 &#124; Tls12。</span><span class="sxs-lookup"><span data-stu-id="445a9-129">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="445a9-130">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="445a9-130">policyEnforcement</span></span>|<span data-ttu-id="445a9-131">此枚举指定应何时强制实施 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>。</span><span class="sxs-lookup"><span data-stu-id="445a9-131">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="445a9-132">1.Never – 绝不强制实施此策略（禁用扩展保护）。</span><span class="sxs-lookup"><span data-stu-id="445a9-132">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="445a9-133">2.WhenSupported – 仅在客户端支持扩展保护时才强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="445a9-133">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="445a9-134">3.Always – 总是强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="445a9-134">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="445a9-135">不支持扩展保护的客户端将无法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="445a9-135">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="445a9-136">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="445a9-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="445a9-137">值</span><span class="sxs-lookup"><span data-stu-id="445a9-137">Value</span></span>|<span data-ttu-id="445a9-138">描述</span><span class="sxs-lookup"><span data-stu-id="445a9-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="445a9-139">无</span><span class="sxs-lookup"><span data-stu-id="445a9-139">None</span></span>|<span data-ttu-id="445a9-140">客户端为匿名客户端。</span><span class="sxs-lookup"><span data-stu-id="445a9-140">The client is anonymous.</span></span> <span data-ttu-id="445a9-141">这需要服务证书。</span><span class="sxs-lookup"><span data-stu-id="445a9-141">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="445a9-142">Windows</span><span class="sxs-lookup"><span data-stu-id="445a9-142">Windows</span></span>|<span data-ttu-id="445a9-143">指定使用 SP 协商（Kerberos 协商）进行客户端 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="445a9-143">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="445a9-144">证书</span><span class="sxs-lookup"><span data-stu-id="445a9-144">Certificate</span></span>|<span data-ttu-id="445a9-145">使用证书进行对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="445a9-145">The client is authenticated using a certificate.</span></span> <span data-ttu-id="445a9-146">这使用 SSL 协商并需要服务证书。</span><span class="sxs-lookup"><span data-stu-id="445a9-146">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="445a9-147">protectionLevel 属性</span><span class="sxs-lookup"><span data-stu-id="445a9-147">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="445a9-148">值</span><span class="sxs-lookup"><span data-stu-id="445a9-148">Value</span></span>|<span data-ttu-id="445a9-149">描述</span><span class="sxs-lookup"><span data-stu-id="445a9-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="445a9-150">无</span><span class="sxs-lookup"><span data-stu-id="445a9-150">None</span></span>|<span data-ttu-id="445a9-151">无保护。</span><span class="sxs-lookup"><span data-stu-id="445a9-151">No protection.</span></span>|  
|<span data-ttu-id="445a9-152">Sign</span><span class="sxs-lookup"><span data-stu-id="445a9-152">Sign</span></span>|<span data-ttu-id="445a9-153">对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="445a9-153">Messages are signed.</span></span>|  
|<span data-ttu-id="445a9-154">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="445a9-154">EncryptAndSign</span></span>|<span data-ttu-id="445a9-155">-消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="445a9-155">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="445a9-156">子元素</span><span class="sxs-lookup"><span data-stu-id="445a9-156">Child Elements</span></span>  
 <span data-ttu-id="445a9-157">无</span><span class="sxs-lookup"><span data-stu-id="445a9-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="445a9-158">父元素</span><span class="sxs-lookup"><span data-stu-id="445a9-158">Parent Elements</span></span>  
  
|<span data-ttu-id="445a9-159">元素</span><span class="sxs-lookup"><span data-stu-id="445a9-159">Element</span></span>|<span data-ttu-id="445a9-160">描述</span><span class="sxs-lookup"><span data-stu-id="445a9-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="445a9-161">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="445a9-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|<span data-ttu-id="445a9-162">指定的安全功能[ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="445a9-162">Specifies the security capabilities of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="445a9-163">备注</span><span class="sxs-lookup"><span data-stu-id="445a9-163">Remarks</span></span>  
 <span data-ttu-id="445a9-164">使用传输安全性以获得 SOAP 消息的完整性和保密性以及相互身份验证。</span><span class="sxs-lookup"><span data-stu-id="445a9-164">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="445a9-165">如果在绑定上选择此安全模式，则使用安全传输配置信道栈，并且使用传输安全性（如 Windows (Negotiate) 或 SSLL）保护 SOAP 消息安全通过 TCP 传递。</span><span class="sxs-lookup"><span data-stu-id="445a9-165">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="445a9-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="445a9-166">See Also</span></span>  
 <xref:System.ServiceModel.TcpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [<span data-ttu-id="445a9-167">保护服务和客户端</span><span class="sxs-lookup"><span data-stu-id="445a9-167">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="445a9-168">绑定</span><span class="sxs-lookup"><span data-stu-id="445a9-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="445a9-169">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="445a9-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="445a9-170">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="445a9-170">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="445a9-171">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="445a9-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
