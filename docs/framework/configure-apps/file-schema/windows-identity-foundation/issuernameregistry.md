---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: d0a1f8dd0c29aaee56c2ca1162cc70cc1e5ed106
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942671"
---
# <a name="issuernameregistry"></a><span data-ttu-id="697cd-101">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="697cd-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="697cd-102">配置标记处理程序集合中的处理程序使用的颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="697cd-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="697cd-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="697cd-103">\<system.identityModel></span></span>  
<span data-ttu-id="697cd-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="697cd-104">\<identityConfiguration></span></span>  
<span data-ttu-id="697cd-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="697cd-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="697cd-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="697cd-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="697cd-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="697cd-107">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="697cd-108">语法</span><span class="sxs-lookup"><span data-stu-id="697cd-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="697cd-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="697cd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="697cd-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="697cd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="697cd-111">特性</span><span class="sxs-lookup"><span data-stu-id="697cd-111">Attributes</span></span>  
  
|<span data-ttu-id="697cd-112">特性</span><span class="sxs-lookup"><span data-stu-id="697cd-112">Attribute</span></span>|<span data-ttu-id="697cd-113">描述</span><span class="sxs-lookup"><span data-stu-id="697cd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="697cd-114">type</span><span class="sxs-lookup"><span data-stu-id="697cd-114">type</span></span>|<span data-ttu-id="697cd-115">派生自<xref:System.IdentityModel.Tokens.IssuerNameRegistry>类的类型。</span><span class="sxs-lookup"><span data-stu-id="697cd-115">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="697cd-116">有关如何指定自定义`type`的详细信息, 请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="697cd-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="697cd-117">子元素</span><span class="sxs-lookup"><span data-stu-id="697cd-117">Child Elements</span></span>  
  
|<span data-ttu-id="697cd-118">元素</span><span class="sxs-lookup"><span data-stu-id="697cd-118">Element</span></span>|<span data-ttu-id="697cd-119">描述</span><span class="sxs-lookup"><span data-stu-id="697cd-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="697cd-120">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="697cd-120">\<trustedIssuers></span></span>](trustedissuers.md)|<span data-ttu-id="697cd-121">当属性指定基于配置的颁发者名称注册表<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> (类) 时, [ \<必须指定 s >](trustedissuers.md)元素。 `type`</span><span class="sxs-lookup"><span data-stu-id="697cd-121">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="697cd-122">S > 元素可以采用`<add>`、 `<clear>`或`<remove>`元素作为子元素。 [ \<](trustedissuers.md)</span><span class="sxs-lookup"><span data-stu-id="697cd-122">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="697cd-123">父元素</span><span class="sxs-lookup"><span data-stu-id="697cd-123">Parent Elements</span></span>  
  
|<span data-ttu-id="697cd-124">元素</span><span class="sxs-lookup"><span data-stu-id="697cd-124">Element</span></span>|<span data-ttu-id="697cd-125">描述</span><span class="sxs-lookup"><span data-stu-id="697cd-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="697cd-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="697cd-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="697cd-127">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="697cd-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="697cd-128">备注</span><span class="sxs-lookup"><span data-stu-id="697cd-128">Remarks</span></span>  
 <span data-ttu-id="697cd-129">使用颁发者名称注册表验证所有颁发者令牌。</span><span class="sxs-lookup"><span data-stu-id="697cd-129">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="697cd-130">这是从<xref:System.IdentityModel.Tokens.IssuerNameRegistry>类派生的对象。</span><span class="sxs-lookup"><span data-stu-id="697cd-130">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="697cd-131">颁发者名称注册表用于将助记键名称关联到验证相应颁发者生成的令牌签名所需的加密材料。</span><span class="sxs-lookup"><span data-stu-id="697cd-131">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="697cd-132">颁发者名称注册表将维护依赖方 (RP) 应用程序信任的颁发者的列表。</span><span class="sxs-lookup"><span data-stu-id="697cd-132">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="697cd-133">颁发者名称注册表的类型是使用`type`属性指定的。</span><span class="sxs-lookup"><span data-stu-id="697cd-133">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="697cd-134">`<issuerNameRegistry>`元素可以有一个或多个子元素, 这些子元素提供指定类型的配置。</span><span class="sxs-lookup"><span data-stu-id="697cd-134">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="697cd-135">通过重写<xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A>方法来提供处理这些子元素的逻辑。</span><span class="sxs-lookup"><span data-stu-id="697cd-135">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="697cd-136">WIF 提供单一颁发者名称注册表类型, 即<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类。</span><span class="sxs-lookup"><span data-stu-id="697cd-136">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="697cd-137">此类使用在配置中指定的一组受信任的颁发者证书。</span><span class="sxs-lookup"><span data-stu-id="697cd-137">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="697cd-138">它需要一个子配置元素, `<trustedIssuers>`在该元素下配置受信任的颁发者证书的集合。</span><span class="sxs-lookup"><span data-stu-id="697cd-138">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="697cd-139">受信任的证书是使用 "证书指纹" 的 "ASN" 编码形式指定的, 并且通过使用`<add>`、 `<clear>`或`<remove>`元素在集合中添加或删除。</span><span class="sxs-lookup"><span data-stu-id="697cd-139">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="697cd-140">元素由<xref:System.IdentityModel.Configuration.IssuerNameRegistryElement>类表示。 `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="697cd-140">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="697cd-141">将元素指定为[ \<identityConfiguration >](identityconfiguration.md)元素的子元素已被弃用, 但仍支持向后兼容。 `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="697cd-141">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="697cd-142">元素上的`<securityTokenHandlerConfiguration>`设置将替代`<identityConfiguration>`元素上的设置。</span><span class="sxs-lookup"><span data-stu-id="697cd-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="697cd-143">示例</span><span class="sxs-lookup"><span data-stu-id="697cd-143">Example</span></span>  
 <span data-ttu-id="697cd-144">下面的 XML 演示如何指定基于配置的颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="697cd-144">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="697cd-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="697cd-145">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
