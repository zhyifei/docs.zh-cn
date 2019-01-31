---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: db4e0492772d6fd0e155843422b7350aa630f713
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269518"
---
# <a name="issuernameregistry"></a><span data-ttu-id="905be-101">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="905be-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="905be-102">配置颁发者名称注册的标记处理程序集合中的处理程序使用。</span><span class="sxs-lookup"><span data-stu-id="905be-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="905be-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="905be-103">\<system.identityModel></span></span>  
<span data-ttu-id="905be-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="905be-104">\<identityConfiguration></span></span>  
<span data-ttu-id="905be-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="905be-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="905be-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="905be-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="905be-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="905be-107">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="905be-108">语法</span><span class="sxs-lookup"><span data-stu-id="905be-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="905be-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="905be-109">Attributes and Elements</span></span>  
 <span data-ttu-id="905be-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="905be-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="905be-111">特性</span><span class="sxs-lookup"><span data-stu-id="905be-111">Attributes</span></span>  
  
|<span data-ttu-id="905be-112">特性</span><span class="sxs-lookup"><span data-stu-id="905be-112">Attribute</span></span>|<span data-ttu-id="905be-113">描述</span><span class="sxs-lookup"><span data-stu-id="905be-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="905be-114">类型</span><span class="sxs-lookup"><span data-stu-id="905be-114">type</span></span>|<span data-ttu-id="905be-115">从派生的类型的<xref:System.IdentityModel.Tokens.IssuerNameRegistry>类。</span><span class="sxs-lookup"><span data-stu-id="905be-115">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="905be-116">详细了解如何指定自定义`type`，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="905be-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="905be-117">子元素</span><span class="sxs-lookup"><span data-stu-id="905be-117">Child Elements</span></span>  
  
|<span data-ttu-id="905be-118">元素</span><span class="sxs-lookup"><span data-stu-id="905be-118">Element</span></span>|<span data-ttu-id="905be-119">描述</span><span class="sxs-lookup"><span data-stu-id="905be-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="905be-120">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="905be-120">\<trustedIssuers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|<span data-ttu-id="905be-121">当`type`属性指定基于配置的颁布者名称注册表 (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类)，则[ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)必须指定元素。</span><span class="sxs-lookup"><span data-stu-id="905be-121">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="905be-122">[ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)元素可能需要`<add>`， `<clear>`，或`<remove>`元素作为子元素。</span><span class="sxs-lookup"><span data-stu-id="905be-122">The [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="905be-123">父元素</span><span class="sxs-lookup"><span data-stu-id="905be-123">Parent Elements</span></span>  
  
|<span data-ttu-id="905be-124">元素</span><span class="sxs-lookup"><span data-stu-id="905be-124">Element</span></span>|<span data-ttu-id="905be-125">描述</span><span class="sxs-lookup"><span data-stu-id="905be-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="905be-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="905be-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="905be-127">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="905be-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="905be-128">备注</span><span class="sxs-lookup"><span data-stu-id="905be-128">Remarks</span></span>  
 <span data-ttu-id="905be-129">所有颁发者令牌进行验证使用颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="905be-129">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="905be-130">这是一个对象，派生自<xref:System.IdentityModel.Tokens.IssuerNameRegistry>类。</span><span class="sxs-lookup"><span data-stu-id="905be-130">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="905be-131">颁发者名称注册表用于将验证由相应发行人生成的标志签名所需的加密材料的助记键名称相关联。</span><span class="sxs-lookup"><span data-stu-id="905be-131">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="905be-132">颁发者名称注册表维护信赖方 (RP) 应用程序由受信任的颁发者列表。</span><span class="sxs-lookup"><span data-stu-id="905be-132">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="905be-133">使用指定的颁发者名称注册表类型`type`属性。</span><span class="sxs-lookup"><span data-stu-id="905be-133">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="905be-134">`<issuerNameRegistry>`元素可以具有一个或多个提供指定类型的配置的子元素。</span><span class="sxs-lookup"><span data-stu-id="905be-134">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="905be-135">提供处理通过重写这些子元素的逻辑<xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="905be-135">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="905be-136">WIF 提供单一的颁发者名称注册表类型默认情况下，<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类。</span><span class="sxs-lookup"><span data-stu-id="905be-136">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="905be-137">此类使用一的组配置中指定的受信任的颁发者证书。</span><span class="sxs-lookup"><span data-stu-id="905be-137">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="905be-138">它需要子配置元素，`<trustedIssuers>`下配置受信任的颁发者证书的集合。</span><span class="sxs-lookup"><span data-stu-id="905be-138">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="905be-139">受信任的证书使用 ASN.1 编码形式的证书指纹以及添加或从集合中删除通过使用指定`<add>`， `<clear>`，或`<remove>`元素。</span><span class="sxs-lookup"><span data-stu-id="905be-139">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="905be-140">`<issuerNameRegistry>`元素表示由<xref:System.IdentityModel.Configuration.IssuerNameRegistryElement>类。</span><span class="sxs-lookup"><span data-stu-id="905be-140">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="905be-141">指定`<issuerNameRegistry>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已被弃用，但仍然支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="905be-141">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="905be-142">上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="905be-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="905be-143">示例</span><span class="sxs-lookup"><span data-stu-id="905be-143">Example</span></span>  
 <span data-ttu-id="905be-144">下面的 XML 演示如何指定配置基于颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="905be-144">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="905be-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="905be-145">See also</span></span>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
