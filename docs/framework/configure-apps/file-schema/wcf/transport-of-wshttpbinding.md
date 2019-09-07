---
title: <transport> 的 <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 95cfa076f62f767af431ff5a0bcc2ca31b824e30
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399241"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="35cd1-102">\<wsHttpBinding > 的\<传输 ></span><span class="sxs-lookup"><span data-stu-id="35cd1-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="35cd1-103">定义 HTTP 传输的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="35cd1-103">Defines authentication settings for the HTTP transport.</span></span>

<span data-ttu-id="35cd1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="35cd1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="35cd1-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="35cd1-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="35cd1-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="35cd1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="35cd1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsHttpBinding >** ](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="35cd1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="35cd1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="35cd1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="35cd1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="35cd1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)</span></span>\
<span data-ttu-id="35cd1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<传输 >**</span><span class="sxs-lookup"><span data-stu-id="35cd1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="35cd1-111">语法</span><span class="sxs-lookup"><span data-stu-id="35cd1-111">Syntax</span></span>

```xml
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```

## <a name="type"></a><span data-ttu-id="35cd1-112">类型</span><span class="sxs-lookup"><span data-stu-id="35cd1-112">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="35cd1-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="35cd1-113">Attributes and Elements</span></span>

<span data-ttu-id="35cd1-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="35cd1-114">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="35cd1-115">特性</span><span class="sxs-lookup"><span data-stu-id="35cd1-115">Attributes</span></span>

|<span data-ttu-id="35cd1-116">特性</span><span class="sxs-lookup"><span data-stu-id="35cd1-116">Attribute</span></span>|<span data-ttu-id="35cd1-117">描述</span><span class="sxs-lookup"><span data-stu-id="35cd1-117">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="35cd1-118">指定用于向服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="35cd1-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="35cd1-119">此属性的类型为 <xref:System.ServiceModel.HttpClientCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="35cd1-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="35cd1-120">指定用于向域代理证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="35cd1-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="35cd1-121">此属性的类型为 <xref:System.ServiceModel.HttpProxyCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="35cd1-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="35cd1-122">一个字符串，指定摘要式或基本身份验证的身份验证领域。</span><span class="sxs-lookup"><span data-stu-id="35cd1-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="35cd1-123">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="35cd1-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="35cd1-124">身份验证领域至少指定执行身份验证的主机的名称。</span><span class="sxs-lookup"><span data-stu-id="35cd1-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="35cd1-125">它还可以指定具有访问权限的用户的集合。</span><span class="sxs-lookup"><span data-stu-id="35cd1-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="35cd1-126">用户可以查询身份验证领域，以确定多个可能的用户名和密码中哪一个可以使用。</span><span class="sxs-lookup"><span data-stu-id="35cd1-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="35cd1-127">此枚举指定应何时强制实施 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>。</span><span class="sxs-lookup"><span data-stu-id="35cd1-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="35cd1-128">1.Never – 绝不强制实施此策略（禁用扩展保护）。</span><span class="sxs-lookup"><span data-stu-id="35cd1-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="35cd1-129">2.WhenSupported – 仅在客户端支持扩展保护时才强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="35cd1-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="35cd1-130">3.Always – 总是强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="35cd1-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="35cd1-131">不支持扩展保护的客户端将无法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="35cd1-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="35cd1-132">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="35cd1-132">clientCredentialType Attribute</span></span>

|<span data-ttu-id="35cd1-133">值</span><span class="sxs-lookup"><span data-stu-id="35cd1-133">Value</span></span>|<span data-ttu-id="35cd1-134">描述</span><span class="sxs-lookup"><span data-stu-id="35cd1-134">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="35cd1-135">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="35cd1-135">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="35cd1-136">使用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="35cd1-136">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="35cd1-137">使用摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="35cd1-137">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="35cd1-138">对 Windows 域使用 NTLM 身份验证作为回退。</span><span class="sxs-lookup"><span data-stu-id="35cd1-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="35cd1-139">使用集成 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="35cd1-139">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="35cd1-140">使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="35cd1-140">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="35cd1-141">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="35cd1-141">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="35cd1-142">值</span><span class="sxs-lookup"><span data-stu-id="35cd1-142">Value</span></span>|<span data-ttu-id="35cd1-143">描述</span><span class="sxs-lookup"><span data-stu-id="35cd1-143">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="35cd1-144">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="35cd1-144">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="35cd1-145">使用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="35cd1-145">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="35cd1-146">使用摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="35cd1-146">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="35cd1-147">对 Windows 域使用 NTLM 作为回退。</span><span class="sxs-lookup"><span data-stu-id="35cd1-147">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="35cd1-148">使用集成 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="35cd1-148">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="35cd1-149">使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="35cd1-149">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="35cd1-150">子元素</span><span class="sxs-lookup"><span data-stu-id="35cd1-150">Child Elements</span></span>

<span data-ttu-id="35cd1-151">无。</span><span class="sxs-lookup"><span data-stu-id="35cd1-151">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="35cd1-152">父元素</span><span class="sxs-lookup"><span data-stu-id="35cd1-152">Parent Elements</span></span>

|<span data-ttu-id="35cd1-153">元素</span><span class="sxs-lookup"><span data-stu-id="35cd1-153">Element</span></span>|<span data-ttu-id="35cd1-154">描述</span><span class="sxs-lookup"><span data-stu-id="35cd1-154">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="35cd1-155">\<security></span><span class="sxs-lookup"><span data-stu-id="35cd1-155">\<security></span></span>](security-of-wshttpbinding.md)|<span data-ttu-id="35cd1-156">表示[ \<wsHttpBinding >](wshttpbinding.md)的安全功能。</span><span class="sxs-lookup"><span data-stu-id="35cd1-156">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="35cd1-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="35cd1-157">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="35cd1-158">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="35cd1-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="35cd1-159">绑定</span><span class="sxs-lookup"><span data-stu-id="35cd1-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="35cd1-160">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="35cd1-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="35cd1-161">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="35cd1-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="35cd1-162">\<binding></span><span class="sxs-lookup"><span data-stu-id="35cd1-162">\<binding></span></span>](../../../misc/binding.md)
