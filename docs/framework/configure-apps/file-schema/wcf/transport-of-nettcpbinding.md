---
title: <transport> 的 <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 4ef08ad73a03dea21d27217364a7bacb46a3848e
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735931"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="53799-102">\<netTcpBinding> 的 \<transport></span><span class="sxs-lookup"><span data-stu-id="53799-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="53799-103">定义使用[\<netTcpBinding >](nettcpbinding.md)配置的终结点的消息级安全性要求的类型。</span><span class="sxs-lookup"><span data-stu-id="53799-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
<span data-ttu-id="53799-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="53799-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="53799-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="53799-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="53799-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="53799-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="53799-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netTcpBinding >** ](nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="53799-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)</span></span>\
<span data-ttu-id="53799-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="53799-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="53799-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](security-of-nettcpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="53799-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)</span></span>\
<span data-ttu-id="53799-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<传输 >**</span><span class="sxs-lookup"><span data-stu-id="53799-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53799-111">语法</span><span class="sxs-lookup"><span data-stu-id="53799-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53799-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="53799-112">Attributes and Elements</span></span>  
 <span data-ttu-id="53799-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="53799-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53799-114">特性</span><span class="sxs-lookup"><span data-stu-id="53799-114">Attributes</span></span>  
  
|<span data-ttu-id="53799-115">特性</span><span class="sxs-lookup"><span data-stu-id="53799-115">Attribute</span></span>|<span data-ttu-id="53799-116">描述</span><span class="sxs-lookup"><span data-stu-id="53799-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53799-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="53799-117">clientCredentialType</span></span>|<span data-ttu-id="53799-118">可选。</span><span class="sxs-lookup"><span data-stu-id="53799-118">Optional.</span></span> <span data-ttu-id="53799-119">指定要在使用传输安全性执行客户端身份验证时使用的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="53799-119">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="53799-120">-默认值为 `Windows`。</span><span class="sxs-lookup"><span data-stu-id="53799-120">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="53799-121">-此属性的类型为 <xref:System.ServiceModel.TcpClientCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="53799-121">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="53799-122">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="53799-122">protectionLevel</span></span>|<span data-ttu-id="53799-123">可选。</span><span class="sxs-lookup"><span data-stu-id="53799-123">Optional.</span></span> <span data-ttu-id="53799-124">定义 TCP 传输级别的安全性。</span><span class="sxs-lookup"><span data-stu-id="53799-124">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="53799-125">对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。</span><span class="sxs-lookup"><span data-stu-id="53799-125">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="53799-126">加密可以在传输过程中提供数据级保密。</span><span class="sxs-lookup"><span data-stu-id="53799-126">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="53799-127">默认值为 `EncryptAndSign`。</span><span class="sxs-lookup"><span data-stu-id="53799-127">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="53799-128">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="53799-128">sslProtocols</span></span>|<span data-ttu-id="53799-129">指定支持哪些 SslProtocols 的 SslProtocols 枚举标志值。</span><span class="sxs-lookup"><span data-stu-id="53799-129">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="53799-130">默认值为 Tls&#124;Tls11&#124;Tls12。</span><span class="sxs-lookup"><span data-stu-id="53799-130">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="53799-131">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="53799-131">policyEnforcement</span></span>|<span data-ttu-id="53799-132">此枚举指定应何时强制实施 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>。</span><span class="sxs-lookup"><span data-stu-id="53799-132">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="53799-133">1. 从不–不强制实施策略（禁用扩展保护）。</span><span class="sxs-lookup"><span data-stu-id="53799-133">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="53799-134">WhenSupported-仅当客户端支持扩展保护时才强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="53799-134">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="53799-135">3. always –始终强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="53799-135">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="53799-136">不支持扩展保护的客户端将无法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="53799-136">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="53799-137">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="53799-137">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="53799-138">“值”</span><span class="sxs-lookup"><span data-stu-id="53799-138">Value</span></span>|<span data-ttu-id="53799-139">描述</span><span class="sxs-lookup"><span data-stu-id="53799-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53799-140">None</span><span class="sxs-lookup"><span data-stu-id="53799-140">None</span></span>|<span data-ttu-id="53799-141">客户端为匿名客户端。</span><span class="sxs-lookup"><span data-stu-id="53799-141">The client is anonymous.</span></span> <span data-ttu-id="53799-142">这需要服务证书。</span><span class="sxs-lookup"><span data-stu-id="53799-142">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="53799-143">Windows</span><span class="sxs-lookup"><span data-stu-id="53799-143">Windows</span></span>|<span data-ttu-id="53799-144">指定使用 SP 协商（Kerberos 协商）进行客户端 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="53799-144">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="53799-145">证书</span><span class="sxs-lookup"><span data-stu-id="53799-145">Certificate</span></span>|<span data-ttu-id="53799-146">使用证书进行对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="53799-146">The client is authenticated using a certificate.</span></span> <span data-ttu-id="53799-147">这使用 SSL 协商并需要服务证书。</span><span class="sxs-lookup"><span data-stu-id="53799-147">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="53799-148">protectionLevel 属性</span><span class="sxs-lookup"><span data-stu-id="53799-148">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="53799-149">“值”</span><span class="sxs-lookup"><span data-stu-id="53799-149">Value</span></span>|<span data-ttu-id="53799-150">描述</span><span class="sxs-lookup"><span data-stu-id="53799-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53799-151">None</span><span class="sxs-lookup"><span data-stu-id="53799-151">None</span></span>|<span data-ttu-id="53799-152">无保护。</span><span class="sxs-lookup"><span data-stu-id="53799-152">No protection.</span></span>|  
|<span data-ttu-id="53799-153">Sign</span><span class="sxs-lookup"><span data-stu-id="53799-153">Sign</span></span>|<span data-ttu-id="53799-154">对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="53799-154">Messages are signed.</span></span>|  
|<span data-ttu-id="53799-155">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="53799-155">EncryptAndSign</span></span>|<span data-ttu-id="53799-156">-对消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="53799-156">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53799-157">子元素</span><span class="sxs-lookup"><span data-stu-id="53799-157">Child Elements</span></span>  
 <span data-ttu-id="53799-158">None</span><span class="sxs-lookup"><span data-stu-id="53799-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53799-159">父元素</span><span class="sxs-lookup"><span data-stu-id="53799-159">Parent Elements</span></span>  
  
|<span data-ttu-id="53799-160">元素</span><span class="sxs-lookup"><span data-stu-id="53799-160">Element</span></span>|<span data-ttu-id="53799-161">描述</span><span class="sxs-lookup"><span data-stu-id="53799-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53799-162">\<security ></span><span class="sxs-lookup"><span data-stu-id="53799-162">\<security></span></span>](security-of-nettcpbinding.md)|<span data-ttu-id="53799-163">指定[\<netTcpBinding >](nettcpbinding.md)的安全功能。</span><span class="sxs-lookup"><span data-stu-id="53799-163">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53799-164">备注</span><span class="sxs-lookup"><span data-stu-id="53799-164">Remarks</span></span>  
 <span data-ttu-id="53799-165">使用传输安全性以获得 SOAP 消息的完整性和保密性以及相互身份验证。</span><span class="sxs-lookup"><span data-stu-id="53799-165">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="53799-166">如果在绑定上选择此安全模式，则使用安全传输配置信道栈，并且使用传输安全性（如 Windows (Negotiate) 或 SSLL）保护 SOAP 消息安全通过 TCP 传递。</span><span class="sxs-lookup"><span data-stu-id="53799-166">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53799-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="53799-167">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="53799-168">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="53799-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="53799-169">绑定</span><span class="sxs-lookup"><span data-stu-id="53799-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="53799-170">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="53799-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="53799-171">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="53799-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="53799-172">\<binding ></span><span class="sxs-lookup"><span data-stu-id="53799-172">\<binding></span></span>](bindings.md)
