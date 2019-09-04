---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 209e702da80f2569f2b6c068f50f1af4489157f6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251969"
---
# <a name="issuernameregistry"></a><span data-ttu-id="d2798-101">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="d2798-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="d2798-102">配置标记处理程序集合中的处理程序使用的颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="d2798-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
<span data-ttu-id="d2798-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d2798-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d2798-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="d2798-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="d2798-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d2798-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="d2798-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="d2798-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="d2798-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d2798-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="d2798-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerNameRegistry >**</span><span class="sxs-lookup"><span data-stu-id="d2798-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2798-109">语法</span><span class="sxs-lookup"><span data-stu-id="d2798-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2798-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d2798-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d2798-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d2798-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2798-112">特性</span><span class="sxs-lookup"><span data-stu-id="d2798-112">Attributes</span></span>  
  
|<span data-ttu-id="d2798-113">特性</span><span class="sxs-lookup"><span data-stu-id="d2798-113">Attribute</span></span>|<span data-ttu-id="d2798-114">描述</span><span class="sxs-lookup"><span data-stu-id="d2798-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2798-115">type</span><span class="sxs-lookup"><span data-stu-id="d2798-115">type</span></span>|<span data-ttu-id="d2798-116">派生自<xref:System.IdentityModel.Tokens.IssuerNameRegistry>类的类型。</span><span class="sxs-lookup"><span data-stu-id="d2798-116">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="d2798-117">有关如何指定自定义`type`的详细信息，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="d2798-117">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2798-118">子元素</span><span class="sxs-lookup"><span data-stu-id="d2798-118">Child Elements</span></span>  
  
|<span data-ttu-id="d2798-119">元素</span><span class="sxs-lookup"><span data-stu-id="d2798-119">Element</span></span>|<span data-ttu-id="d2798-120">描述</span><span class="sxs-lookup"><span data-stu-id="d2798-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2798-121">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="d2798-121">\<trustedIssuers></span></span>](trustedissuers.md)|<span data-ttu-id="d2798-122">当属性指定基于配置的颁发者名称注册表<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> （类）时， [ \<必须指定 s >](trustedissuers.md)元素。 `type`</span><span class="sxs-lookup"><span data-stu-id="d2798-122">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="d2798-123">S > 元素可以采用`<add>`、 `<clear>`或`<remove>`元素作为子元素。 [ \<](trustedissuers.md)</span><span class="sxs-lookup"><span data-stu-id="d2798-123">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d2798-124">父元素</span><span class="sxs-lookup"><span data-stu-id="d2798-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d2798-125">元素</span><span class="sxs-lookup"><span data-stu-id="d2798-125">Element</span></span>|<span data-ttu-id="d2798-126">描述</span><span class="sxs-lookup"><span data-stu-id="d2798-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2798-127">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d2798-127">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="d2798-128">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="d2798-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2798-129">备注</span><span class="sxs-lookup"><span data-stu-id="d2798-129">Remarks</span></span>  
 <span data-ttu-id="d2798-130">使用颁发者名称注册表验证所有颁发者令牌。</span><span class="sxs-lookup"><span data-stu-id="d2798-130">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="d2798-131">这是从<xref:System.IdentityModel.Tokens.IssuerNameRegistry>类派生的对象。</span><span class="sxs-lookup"><span data-stu-id="d2798-131">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="d2798-132">颁发者名称注册表用于将助记键名称关联到验证相应颁发者生成的令牌签名所需的加密材料。</span><span class="sxs-lookup"><span data-stu-id="d2798-132">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="d2798-133">颁发者名称注册表将维护依赖方（RP）应用程序信任的颁发者的列表。</span><span class="sxs-lookup"><span data-stu-id="d2798-133">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="d2798-134">颁发者名称注册表的类型是使用`type`属性指定的。</span><span class="sxs-lookup"><span data-stu-id="d2798-134">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="d2798-135">`<issuerNameRegistry>`元素可以有一个或多个子元素，这些子元素提供指定类型的配置。</span><span class="sxs-lookup"><span data-stu-id="d2798-135">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="d2798-136">通过重写<xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A>方法来提供处理这些子元素的逻辑。</span><span class="sxs-lookup"><span data-stu-id="d2798-136">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="d2798-137">WIF 提供单一颁发者名称注册表类型，即<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类。</span><span class="sxs-lookup"><span data-stu-id="d2798-137">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="d2798-138">此类使用在配置中指定的一组受信任的颁发者证书。</span><span class="sxs-lookup"><span data-stu-id="d2798-138">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="d2798-139">它需要一个子配置元素， `<trustedIssuers>`在该元素下配置受信任的颁发者证书的集合。</span><span class="sxs-lookup"><span data-stu-id="d2798-139">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="d2798-140">受信任的证书是使用 "证书指纹" 的 "ASN" 编码形式指定的，并且通过使用`<add>`、 `<clear>`或`<remove>`元素在集合中添加或删除。</span><span class="sxs-lookup"><span data-stu-id="d2798-140">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="d2798-141">元素由<xref:System.IdentityModel.Configuration.IssuerNameRegistryElement>类表示。 `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="d2798-141">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2798-142">将元素指定为[ \<identityConfiguration >](identityconfiguration.md)元素的子元素已被弃用，但仍支持向后兼容。 `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="d2798-142">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="d2798-143">元素上的`<securityTokenHandlerConfiguration>`设置将替代`<identityConfiguration>`元素上的设置。</span><span class="sxs-lookup"><span data-stu-id="d2798-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2798-144">示例</span><span class="sxs-lookup"><span data-stu-id="d2798-144">Example</span></span>  
 <span data-ttu-id="d2798-145">下面的 XML 演示如何指定基于配置的颁发者名称注册表。</span><span class="sxs-lookup"><span data-stu-id="d2798-145">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2798-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2798-146">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
