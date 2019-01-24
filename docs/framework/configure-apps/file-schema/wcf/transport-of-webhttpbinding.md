---
title: '&lt;webHttpBinding&gt; 的 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: 657de92129d27e70834cb401cde42d24b633f7ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677012"
---
# <a name="lttransportgt-of-ltwebhttpbindinggt"></a><span data-ttu-id="ca619-102">&lt;webHttpBinding&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="ca619-102">&lt;transport&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="ca619-103">定义配置为接收 HTTP 请求的服务终结点的传输级安全设置。</span><span class="sxs-lookup"><span data-stu-id="ca619-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
 <span data-ttu-id="ca619-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ca619-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ca619-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ca619-105">\<bindings></span></span>  
<span data-ttu-id="ca619-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ca619-106">\<webHttpBinding></span></span>  
<span data-ttu-id="ca619-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="ca619-107">\<binding></span></span>  
<span data-ttu-id="ca619-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="ca619-108">\<security></span></span>  
<span data-ttu-id="ca619-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="ca619-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca619-110">语法</span><span class="sxs-lookup"><span data-stu-id="ca619-110">Syntax</span></span>  
  
```xml  
<webHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</webHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="ca619-111">类型</span><span class="sxs-lookup"><span data-stu-id="ca619-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca619-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ca619-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ca619-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ca619-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca619-114">特性</span><span class="sxs-lookup"><span data-stu-id="ca619-114">Attributes</span></span>  
  
|<span data-ttu-id="ca619-115">特性</span><span class="sxs-lookup"><span data-stu-id="ca619-115">Attribute</span></span>|<span data-ttu-id="ca619-116">描述</span><span class="sxs-lookup"><span data-stu-id="ca619-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="ca619-117">指定用于向服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="ca619-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="ca619-118">此属性的类型为 <xref:System.ServiceModel.HttpClientCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="ca619-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="ca619-119">指定用于向域代理证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="ca619-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="ca619-120">此属性的类型为 <xref:System.ServiceModel.HttpProxyCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="ca619-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="ca619-121">一个字符串，指定摘要式或基本身份验证的身份验证领域。</span><span class="sxs-lookup"><span data-stu-id="ca619-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="ca619-122">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="ca619-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="ca619-123">身份验证领域至少指定执行身份验证的主机的名称。</span><span class="sxs-lookup"><span data-stu-id="ca619-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="ca619-124">它还可以指定具有访问权限的用户的集合。</span><span class="sxs-lookup"><span data-stu-id="ca619-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="ca619-125">用户可以查询身份验证领域，以确定多个可能的用户名和密码中哪一个可以使用。</span><span class="sxs-lookup"><span data-stu-id="ca619-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="ca619-126">此枚举指定应何时强制实施 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>。</span><span class="sxs-lookup"><span data-stu-id="ca619-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="ca619-127">1.Never – 绝不强制实施此策略（禁用扩展保护）。</span><span class="sxs-lookup"><span data-stu-id="ca619-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="ca619-128">2.WhenSupported – 仅在客户端支持扩展保护时才强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="ca619-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="ca619-129">3.Always – 总是强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="ca619-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="ca619-130">不支持扩展保护的客户端将无法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ca619-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="ca619-131">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="ca619-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="ca619-132">值</span><span class="sxs-lookup"><span data-stu-id="ca619-132">Value</span></span>|<span data-ttu-id="ca619-133">描述</span><span class="sxs-lookup"><span data-stu-id="ca619-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="ca619-134">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="ca619-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="ca619-135">使用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="ca619-135">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="ca619-136">使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ca619-136">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="ca619-137">使用摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="ca619-137">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="ca619-138">对 Windows 域使用 NTLM 身份验证作为回退。</span><span class="sxs-lookup"><span data-stu-id="ca619-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="ca619-139">使用集成 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ca619-139">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="ca619-140">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="ca619-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="ca619-141">值</span><span class="sxs-lookup"><span data-stu-id="ca619-141">Value</span></span>|<span data-ttu-id="ca619-142">描述</span><span class="sxs-lookup"><span data-stu-id="ca619-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="ca619-143">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="ca619-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="ca619-144">使用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="ca619-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="ca619-145">使用摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="ca619-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="ca619-146">对 Windows 域使用 NTLM 作为回退。</span><span class="sxs-lookup"><span data-stu-id="ca619-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="ca619-147">使用集成 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ca619-147">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca619-148">子元素</span><span class="sxs-lookup"><span data-stu-id="ca619-148">Child Elements</span></span>  
 <span data-ttu-id="ca619-149">无。</span><span class="sxs-lookup"><span data-stu-id="ca619-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca619-150">父元素</span><span class="sxs-lookup"><span data-stu-id="ca619-150">Parent Elements</span></span>  
  
|<span data-ttu-id="ca619-151">元素</span><span class="sxs-lookup"><span data-stu-id="ca619-151">Element</span></span>|<span data-ttu-id="ca619-152">描述</span><span class="sxs-lookup"><span data-stu-id="ca619-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca619-153">\<security></span><span class="sxs-lookup"><span data-stu-id="ca619-153">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|<span data-ttu-id="ca619-154">表示的安全功能[ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="ca619-154">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca619-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca619-155">See also</span></span>
- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="ca619-156">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="ca619-156">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ca619-157">绑定</span><span class="sxs-lookup"><span data-stu-id="ca619-157">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ca619-158">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="ca619-158">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ca619-159">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="ca619-159">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ca619-160">\<binding></span><span class="sxs-lookup"><span data-stu-id="ca619-160">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="ca619-161">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="ca619-161">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
