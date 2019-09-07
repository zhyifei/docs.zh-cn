---
title: <transport> 的 <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 41f11be9b4ae8f7a7535c9766965de8575cff784
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399320"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="9b6f6-102">\<netTcpBinding> 的 \<transport></span><span class="sxs-lookup"><span data-stu-id="9b6f6-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="9b6f6-103">定义使用[ \<netTcpBinding >](nettcpbinding.md)配置的终结点的消息级安全性要求的类型。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
<span data-ttu-id="9b6f6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b6f6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b6f6-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9b6f6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9b6f6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9b6f6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9b6f6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netTcpBinding >** ](nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9b6f6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)</span></span>\
<span data-ttu-id="9b6f6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="9b6f6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9b6f6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9b6f6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)</span></span>\
<span data-ttu-id="9b6f6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<传输 >**</span><span class="sxs-lookup"><span data-stu-id="9b6f6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b6f6-111">语法</span><span class="sxs-lookup"><span data-stu-id="9b6f6-111">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential">
      <transport clientCredentialType="None|Windows|Certificate"
                 protectionLevel="None|Sign|EncryptAndSign"
                 sslProtocols="Tls|Tls11|Tls12">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b6f6-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9b6f6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9b6f6-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b6f6-114">特性</span><span class="sxs-lookup"><span data-stu-id="9b6f6-114">Attributes</span></span>  
  
|<span data-ttu-id="9b6f6-115">特性</span><span class="sxs-lookup"><span data-stu-id="9b6f6-115">Attribute</span></span>|<span data-ttu-id="9b6f6-116">描述</span><span class="sxs-lookup"><span data-stu-id="9b6f6-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b6f6-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="9b6f6-117">clientCredentialType</span></span>|<span data-ttu-id="9b6f6-118">可选。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-118">Optional.</span></span> <span data-ttu-id="9b6f6-119">指定要在使用传输安全性执行客户端身份验证时使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-119">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="9b6f6-120">-默认值为`Windows`。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-120">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="9b6f6-121">-此属性的类型<xref:System.ServiceModel.TcpClientCredentialType>为。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-121">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="9b6f6-122">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="9b6f6-122">protectionLevel</span></span>|<span data-ttu-id="9b6f6-123">可选。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-123">Optional.</span></span> <span data-ttu-id="9b6f6-124">定义 TCP 传输级别的安全性。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-124">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="9b6f6-125">对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-125">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="9b6f6-126">加密可以在传输过程中提供数据级保密。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-126">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="9b6f6-127">默认值为 `EncryptAndSign`。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-127">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="9b6f6-128">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="9b6f6-128">sslProtocols</span></span>|<span data-ttu-id="9b6f6-129">指定支持哪些 SslProtocols 的 SslProtocols 枚举标志值。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-129">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="9b6f6-130">默认值为 Tls&#124;Tls11&#124;Tls12。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-130">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="9b6f6-131">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="9b6f6-131">policyEnforcement</span></span>|<span data-ttu-id="9b6f6-132">此枚举指定应何时强制实施 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-132">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="9b6f6-133">1.Never – 绝不强制实施此策略（禁用扩展保护）。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-133">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="9b6f6-134">2.WhenSupported – 仅在客户端支持扩展保护时才强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-134">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="9b6f6-135">3.Always – 总是强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-135">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="9b6f6-136">不支持扩展保护的客户端将无法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-136">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="9b6f6-137">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="9b6f6-137">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9b6f6-138">值</span><span class="sxs-lookup"><span data-stu-id="9b6f6-138">Value</span></span>|<span data-ttu-id="9b6f6-139">描述</span><span class="sxs-lookup"><span data-stu-id="9b6f6-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9b6f6-140">无</span><span class="sxs-lookup"><span data-stu-id="9b6f6-140">None</span></span>|<span data-ttu-id="9b6f6-141">客户端为匿名客户端。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-141">The client is anonymous.</span></span> <span data-ttu-id="9b6f6-142">这需要服务证书。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-142">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="9b6f6-143">Windows</span><span class="sxs-lookup"><span data-stu-id="9b6f6-143">Windows</span></span>|<span data-ttu-id="9b6f6-144">指定使用 SP 协商（Kerberos 协商）进行客户端 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-144">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="9b6f6-145">证书</span><span class="sxs-lookup"><span data-stu-id="9b6f6-145">Certificate</span></span>|<span data-ttu-id="9b6f6-146">使用证书进行对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-146">The client is authenticated using a certificate.</span></span> <span data-ttu-id="9b6f6-147">这使用 SSL 协商并需要服务证书。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-147">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="9b6f6-148">protectionLevel 属性</span><span class="sxs-lookup"><span data-stu-id="9b6f6-148">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="9b6f6-149">值</span><span class="sxs-lookup"><span data-stu-id="9b6f6-149">Value</span></span>|<span data-ttu-id="9b6f6-150">描述</span><span class="sxs-lookup"><span data-stu-id="9b6f6-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9b6f6-151">无</span><span class="sxs-lookup"><span data-stu-id="9b6f6-151">None</span></span>|<span data-ttu-id="9b6f6-152">无保护。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-152">No protection.</span></span>|  
|<span data-ttu-id="9b6f6-153">Sign</span><span class="sxs-lookup"><span data-stu-id="9b6f6-153">Sign</span></span>|<span data-ttu-id="9b6f6-154">对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-154">Messages are signed.</span></span>|  
|<span data-ttu-id="9b6f6-155">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="9b6f6-155">EncryptAndSign</span></span>|<span data-ttu-id="9b6f6-156">-对消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-156">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b6f6-157">子元素</span><span class="sxs-lookup"><span data-stu-id="9b6f6-157">Child Elements</span></span>  
 <span data-ttu-id="9b6f6-158">无</span><span class="sxs-lookup"><span data-stu-id="9b6f6-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b6f6-159">父元素</span><span class="sxs-lookup"><span data-stu-id="9b6f6-159">Parent Elements</span></span>  
  
|<span data-ttu-id="9b6f6-160">元素</span><span class="sxs-lookup"><span data-stu-id="9b6f6-160">Element</span></span>|<span data-ttu-id="9b6f6-161">描述</span><span class="sxs-lookup"><span data-stu-id="9b6f6-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b6f6-162">\<security></span><span class="sxs-lookup"><span data-stu-id="9b6f6-162">\<security></span></span>](security-of-nettcpbinding.md)|<span data-ttu-id="9b6f6-163">指定[ \<netTcpBinding >](nettcpbinding.md)的安全功能。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-163">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b6f6-164">备注</span><span class="sxs-lookup"><span data-stu-id="9b6f6-164">Remarks</span></span>  
 <span data-ttu-id="9b6f6-165">使用传输安全性以获得 SOAP 消息的完整性和保密性以及相互身份验证。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-165">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="9b6f6-166">如果在绑定上选择此安全模式，则使用安全传输配置信道栈，并且使用传输安全性（如 Windows (Negotiate) 或 SSLL）保护 SOAP 消息安全通过 TCP 传递。</span><span class="sxs-lookup"><span data-stu-id="9b6f6-166">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b6f6-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b6f6-167">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="9b6f6-168">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="9b6f6-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9b6f6-169">绑定</span><span class="sxs-lookup"><span data-stu-id="9b6f6-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9b6f6-170">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="9b6f6-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9b6f6-171">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="9b6f6-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9b6f6-172">\<binding></span><span class="sxs-lookup"><span data-stu-id="9b6f6-172">\<binding></span></span>](../../../misc/binding.md)
