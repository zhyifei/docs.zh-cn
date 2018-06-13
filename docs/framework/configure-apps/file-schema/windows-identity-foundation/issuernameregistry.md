---
title: '&lt;issuerNameRegistry&gt;'
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b695cc6d66e5b9e45bb6a5fd22d594bc22ea3cba
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757523"
---
# <a name="ltissuernameregistrygt"></a><span data-ttu-id="68466-102">&lt;issuerNameRegistry&gt;</span><span class="sxs-lookup"><span data-stu-id="68466-102">&lt;issuerNameRegistry&gt;</span></span>
<span data-ttu-id="68466-103">配置的颁发者名称注册表，由标记处理程序集合中的处理程序。</span><span class="sxs-lookup"><span data-stu-id="68466-103">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="68466-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="68466-104">\<system.identityModel></span></span>  
<span data-ttu-id="68466-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="68466-105">\<identityConfiguration></span></span>  
<span data-ttu-id="68466-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="68466-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="68466-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="68466-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="68466-108">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="68466-108">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68466-109">语法</span><span class="sxs-lookup"><span data-stu-id="68466-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68466-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="68466-110">Attributes and Elements</span></span>  
 <span data-ttu-id="68466-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="68466-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68466-112">特性</span><span class="sxs-lookup"><span data-stu-id="68466-112">Attributes</span></span>  
  
|<span data-ttu-id="68466-113">特性</span><span class="sxs-lookup"><span data-stu-id="68466-113">Attribute</span></span>|<span data-ttu-id="68466-114">描述</span><span class="sxs-lookup"><span data-stu-id="68466-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="68466-115">类型</span><span class="sxs-lookup"><span data-stu-id="68466-115">type</span></span>|<span data-ttu-id="68466-116">派生自类型<xref:System.IdentityModel.Tokens.IssuerNameRegistry>类。</span><span class="sxs-lookup"><span data-stu-id="68466-116">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="68466-117">有关如何指定自定义的详细信息`type`，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="68466-117">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68466-118">子元素</span><span class="sxs-lookup"><span data-stu-id="68466-118">Child Elements</span></span>  
  
|<span data-ttu-id="68466-119">元素</span><span class="sxs-lookup"><span data-stu-id="68466-119">Element</span></span>|<span data-ttu-id="68466-120">描述</span><span class="sxs-lookup"><span data-stu-id="68466-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68466-121">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="68466-121">\<trustedIssuers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|<span data-ttu-id="68466-122">当`type`属性指定基于配置的颁发者名称注册表 (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类)，则[ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)必须指定元素。</span><span class="sxs-lookup"><span data-stu-id="68466-122">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="68466-123">[ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)元素可以`<add>`， `<clear>`，或`<remove>`元素作为子元素。</span><span class="sxs-lookup"><span data-stu-id="68466-123">The [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="68466-124">父元素</span><span class="sxs-lookup"><span data-stu-id="68466-124">Parent Elements</span></span>  
  
|<span data-ttu-id="68466-125">元素</span><span class="sxs-lookup"><span data-stu-id="68466-125">Element</span></span>|<span data-ttu-id="68466-126">描述</span><span class="sxs-lookup"><span data-stu-id="68466-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68466-127">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="68466-127">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="68466-128">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="68466-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68466-129">备注</span><span class="sxs-lookup"><span data-stu-id="68466-129">Remarks</span></span>  
 <span data-ttu-id="68466-130">颁发者的所有令牌使用颁发者名称注册表进行都验证。</span><span class="sxs-lookup"><span data-stu-id="68466-130">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="68466-131">这是一个对象，派生自<xref:System.IdentityModel.Tokens.IssuerNameRegistry>类。</span><span class="sxs-lookup"><span data-stu-id="68466-131">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="68466-132">颁发者名称注册表用于将验证由相应的颁发者的令牌的签名所需的加密材料的助记键名称相关联。</span><span class="sxs-lookup"><span data-stu-id="68466-132">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="68466-133">颁发者名称注册表维护受信任的信赖方 (RP) 应用程序的颁发者的列表。</span><span class="sxs-lookup"><span data-stu-id="68466-133">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="68466-134">使用指定的颁发者名称注册表类型`type`属性。</span><span class="sxs-lookup"><span data-stu-id="68466-134">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="68466-135">`<issuerNameRegistry>`元素可以拥有一个或多个提供指定类型的配置的子元素。</span><span class="sxs-lookup"><span data-stu-id="68466-135">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="68466-136">提供通过重写处理这些子元素的逻辑<xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="68466-136">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="68466-137">WIF 提供单个颁发者名称注册表类型超出了框中，<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类。</span><span class="sxs-lookup"><span data-stu-id="68466-137">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="68466-138">此类使用一的组配置中指定的受信任颁发者证书。</span><span class="sxs-lookup"><span data-stu-id="68466-138">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="68466-139">它需要子配置元素，`<trustedIssuers>`下配置的受信任颁发者证书的集合。</span><span class="sxs-lookup"><span data-stu-id="68466-139">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="68466-140">受信任的证书指定使用 ASN.1 编码形式的证书指纹和添加或从集合中移除使用`<add>`， `<clear>`，或`<remove>`元素。</span><span class="sxs-lookup"><span data-stu-id="68466-140">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="68466-141">`<issuerNameRegistry>`元素表示由<xref:System.IdentityModel.Configuration.IssuerNameRegistryElement>类。</span><span class="sxs-lookup"><span data-stu-id="68466-141">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68466-142">指定`<issuerNameRegistry>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已弃用，但仍支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="68466-142">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="68466-143">上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="68466-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68466-144">示例</span><span class="sxs-lookup"><span data-stu-id="68466-144">Example</span></span>  
 <span data-ttu-id="68466-145">下面的 XML 演示如何指定配置基于颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="68466-145">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="68466-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="68466-146">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
