---
title: <transport> 的 <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: ea025751020d6d98292f6bc3ecfe9421af0cb793
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372316"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="9061c-102">\<transport> of \<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9061c-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="9061c-103">定义 HTTP 传输的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="9061c-103">Defines authentication settings for the HTTP transport.</span></span>

<span data-ttu-id="9061c-104">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="9061c-104">\<system.serviceModel>\\</span></span>
<span data-ttu-id="9061c-105">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="9061c-105">\<bindings>\\</span></span>
<span data-ttu-id="9061c-106">\<wsHttpBinding>\\</span><span class="sxs-lookup"><span data-stu-id="9061c-106">\<wsHttpBinding>\\</span></span>
<span data-ttu-id="9061c-107">\<binding>\\</span><span class="sxs-lookup"><span data-stu-id="9061c-107">\<binding>\\</span></span>
<span data-ttu-id="9061c-108">\<安全 > \\</span><span class="sxs-lookup"><span data-stu-id="9061c-108">\<security>\\</span></span>
<span data-ttu-id="9061c-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="9061c-109">\<transport></span></span>

## <a name="syntax"></a><span data-ttu-id="9061c-110">语法</span><span class="sxs-lookup"><span data-stu-id="9061c-110">Syntax</span></span>

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

## <a name="type"></a><span data-ttu-id="9061c-111">类型</span><span class="sxs-lookup"><span data-stu-id="9061c-111">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="9061c-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9061c-112">Attributes and Elements</span></span>

<span data-ttu-id="9061c-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9061c-113">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9061c-114">特性</span><span class="sxs-lookup"><span data-stu-id="9061c-114">Attributes</span></span>

|<span data-ttu-id="9061c-115">特性</span><span class="sxs-lookup"><span data-stu-id="9061c-115">Attribute</span></span>|<span data-ttu-id="9061c-116">描述</span><span class="sxs-lookup"><span data-stu-id="9061c-116">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="9061c-117">指定用于向服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="9061c-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="9061c-118">此属性的类型为 <xref:System.ServiceModel.HttpClientCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="9061c-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="9061c-119">指定用于向域代理证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="9061c-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="9061c-120">此属性的类型为 <xref:System.ServiceModel.HttpProxyCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="9061c-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="9061c-121">一个字符串，指定摘要式或基本身份验证的身份验证领域。</span><span class="sxs-lookup"><span data-stu-id="9061c-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="9061c-122">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="9061c-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="9061c-123">身份验证领域至少指定执行身份验证的主机的名称。</span><span class="sxs-lookup"><span data-stu-id="9061c-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="9061c-124">它还可以指定具有访问权限的用户的集合。</span><span class="sxs-lookup"><span data-stu-id="9061c-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="9061c-125">用户可以查询身份验证领域，以确定多个可能的用户名和密码中哪一个可以使用。</span><span class="sxs-lookup"><span data-stu-id="9061c-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="9061c-126">此枚举指定应何时强制实施 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>。</span><span class="sxs-lookup"><span data-stu-id="9061c-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="9061c-127">1.Never – 绝不强制实施此策略（禁用扩展保护）。</span><span class="sxs-lookup"><span data-stu-id="9061c-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="9061c-128">2.WhenSupported – 仅在客户端支持扩展保护时才强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="9061c-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="9061c-129">3.Always – 总是强制实施此策略。</span><span class="sxs-lookup"><span data-stu-id="9061c-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="9061c-130">不支持扩展保护的客户端将无法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9061c-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="9061c-131">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="9061c-131">clientCredentialType Attribute</span></span>

|<span data-ttu-id="9061c-132">值</span><span class="sxs-lookup"><span data-stu-id="9061c-132">Value</span></span>|<span data-ttu-id="9061c-133">描述</span><span class="sxs-lookup"><span data-stu-id="9061c-133">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="9061c-134">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="9061c-134">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="9061c-135">使用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="9061c-135">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="9061c-136">使用摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="9061c-136">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="9061c-137">对 Windows 域使用 NTLM 身份验证作为回退。</span><span class="sxs-lookup"><span data-stu-id="9061c-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="9061c-138">使用集成 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="9061c-138">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="9061c-139">使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9061c-139">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="9061c-140">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="9061c-140">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="9061c-141">值</span><span class="sxs-lookup"><span data-stu-id="9061c-141">Value</span></span>|<span data-ttu-id="9061c-142">描述</span><span class="sxs-lookup"><span data-stu-id="9061c-142">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="9061c-143">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="9061c-143">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="9061c-144">使用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="9061c-144">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="9061c-145">使用摘要式身份验证。</span><span class="sxs-lookup"><span data-stu-id="9061c-145">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="9061c-146">对 Windows 域使用 NTLM 作为回退。</span><span class="sxs-lookup"><span data-stu-id="9061c-146">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="9061c-147">使用集成 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="9061c-147">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="9061c-148">使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9061c-148">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9061c-149">子元素</span><span class="sxs-lookup"><span data-stu-id="9061c-149">Child Elements</span></span>

<span data-ttu-id="9061c-150">无。</span><span class="sxs-lookup"><span data-stu-id="9061c-150">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9061c-151">父元素</span><span class="sxs-lookup"><span data-stu-id="9061c-151">Parent Elements</span></span>

|<span data-ttu-id="9061c-152">元素</span><span class="sxs-lookup"><span data-stu-id="9061c-152">Element</span></span>|<span data-ttu-id="9061c-153">描述</span><span class="sxs-lookup"><span data-stu-id="9061c-153">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9061c-154">\<security></span><span class="sxs-lookup"><span data-stu-id="9061c-154">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="9061c-155">表示的安全功能[ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="9061c-155">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="9061c-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="9061c-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="9061c-157">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="9061c-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9061c-158">绑定</span><span class="sxs-lookup"><span data-stu-id="9061c-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="9061c-159">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="9061c-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9061c-160">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="9061c-160">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9061c-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="9061c-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
