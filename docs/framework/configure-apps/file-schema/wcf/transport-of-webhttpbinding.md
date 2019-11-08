---
title: <transport> 的 <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: e8016eb9058f132722587368f1f8c7c03220af4a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732787"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="6f19e-102">\<webHttpBinding 的 \<传输 > ></span><span class="sxs-lookup"><span data-stu-id="6f19e-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="6f19e-103">定义配置为接收 HTTP 请求的服务终结点的传输级安全设置。</span><span class="sxs-lookup"><span data-stu-id="6f19e-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
<span data-ttu-id="6f19e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6f19e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6f19e-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="6f19e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6f19e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="6f19e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6f19e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webHttpBinding >** ](webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6f19e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="6f19e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="6f19e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6f19e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](security-of-webhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="6f19e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)</span></span>\
<span data-ttu-id="6f19e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<传输 >**</span><span class="sxs-lookup"><span data-stu-id="6f19e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f19e-111">语法</span><span class="sxs-lookup"><span data-stu-id="6f19e-111">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="6f19e-112">键入</span><span class="sxs-lookup"><span data-stu-id="6f19e-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f19e-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6f19e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6f19e-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6f19e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f19e-115">特性</span><span class="sxs-lookup"><span data-stu-id="6f19e-115">Attributes</span></span>  
  
|<span data-ttu-id="6f19e-116">特性</span><span class="sxs-lookup"><span data-stu-id="6f19e-116">Attribute</span></span>|<span data-ttu-id="6f19e-117">描述</span><span class="sxs-lookup"><span data-stu-id="6f19e-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="6f19e-118">指定用于向服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="6f19e-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="6f19e-119">此属性的类型为 <xref:System.ServiceModel.HttpClientCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="6f19e-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="6f19e-120">指定用于向域代理证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="6f19e-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="6f19e-121">此属性的类型为 <xref:System.ServiceModel.HttpProxyCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="6f19e-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="6f19e-122">一个字符串，指定摘要式或基本身份验证的身份验证领域。</span><span class="sxs-lookup"><span data-stu-id="6f19e-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="6f19e-123">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="6f19e-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="6f19e-124">身份验证领域至少指定执行身份验证的主机的名称。</span><span class="sxs-lookup"><span data-stu-id="6f19e-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="6f19e-125">它还可以指定具有访问权限的用户的集合。</span><span class="sxs-lookup"><span data-stu-id="6f19e-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="6f19e-126">用户可以查询身份验证领域，以确定多个可能的用户名和密码中哪一个可以使用。</span><span class="sxs-lookup"><span data-stu-id="6f19e-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="6f19e-127">此枚举指定应何时强制实施 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>。</span><span class="sxs-lookup"><span data-stu-id="6f19e-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="6f19e-128">1. 从不–不强制实施策略（禁用扩展保护）。</span><span class="sxs-lookup"><span data-stu-id="6f19e-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="6f19e-129">WhenSupported-仅当客户端支持扩展保护时才强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="6f19e-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="6f19e-130">3. always –始终强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="6f19e-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="6f19e-131">不支持扩展保护的客户端将无法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="6f19e-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="6f19e-132">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="6f19e-132">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="6f19e-133">“值”</span><span class="sxs-lookup"><span data-stu-id="6f19e-133">Value</span></span>|<span data-ttu-id="6f19e-134">描述</span><span class="sxs-lookup"><span data-stu-id="6f19e-134">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="6f19e-135">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="6f19e-135">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="6f19e-136">使用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="6f19e-136">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="6f19e-137">使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="6f19e-137">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="6f19e-138">使用摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="6f19e-138">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="6f19e-139">对 Windows 域使用 NTLM 身份验证作为回退。</span><span class="sxs-lookup"><span data-stu-id="6f19e-139">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="6f19e-140">使用集成 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6f19e-140">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="6f19e-141">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="6f19e-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="6f19e-142">“值”</span><span class="sxs-lookup"><span data-stu-id="6f19e-142">Value</span></span>|<span data-ttu-id="6f19e-143">描述</span><span class="sxs-lookup"><span data-stu-id="6f19e-143">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="6f19e-144">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="6f19e-144">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="6f19e-145">使用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="6f19e-145">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="6f19e-146">使用摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="6f19e-146">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="6f19e-147">对 Windows 域使用 NTLM 作为回退。</span><span class="sxs-lookup"><span data-stu-id="6f19e-147">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="6f19e-148">使用集成 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6f19e-148">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f19e-149">子元素</span><span class="sxs-lookup"><span data-stu-id="6f19e-149">Child Elements</span></span>  
 <span data-ttu-id="6f19e-150">无。</span><span class="sxs-lookup"><span data-stu-id="6f19e-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f19e-151">父元素</span><span class="sxs-lookup"><span data-stu-id="6f19e-151">Parent Elements</span></span>  
  
|<span data-ttu-id="6f19e-152">元素</span><span class="sxs-lookup"><span data-stu-id="6f19e-152">Element</span></span>|<span data-ttu-id="6f19e-153">描述</span><span class="sxs-lookup"><span data-stu-id="6f19e-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f19e-154">\<security ></span><span class="sxs-lookup"><span data-stu-id="6f19e-154">\<security></span></span>](security-of-webhttpbinding.md)|<span data-ttu-id="6f19e-155">表示[\<wsHttpBinding >](wshttpbinding.md)元素的安全功能。</span><span class="sxs-lookup"><span data-stu-id="6f19e-155">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f19e-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f19e-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="6f19e-157">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="6f19e-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6f19e-158">绑定</span><span class="sxs-lookup"><span data-stu-id="6f19e-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6f19e-159">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="6f19e-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6f19e-160">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="6f19e-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6f19e-161">\<binding ></span><span class="sxs-lookup"><span data-stu-id="6f19e-161">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="6f19e-162">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="6f19e-162">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
