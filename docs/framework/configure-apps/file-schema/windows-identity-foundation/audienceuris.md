---
title: '&lt;audienceUris&gt;'
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: af138a4da49a48ed43e1bc8f2c2c81c56892feed
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48034475"
---
# <a name="ltaudienceurisgt"></a><span data-ttu-id="79836-102">&lt;audienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="79836-102">&lt;audienceUris&gt;</span></span>
<span data-ttu-id="79836-103">指定 Uri 都是可接受的信赖方 (RP) 标识符的集。</span><span class="sxs-lookup"><span data-stu-id="79836-103">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="79836-104">除非某个允许的受众 Uri 作用域内，将不会接受令牌。</span><span class="sxs-lookup"><span data-stu-id="79836-104">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="79836-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="79836-105">\<system.identityModel></span></span>  
<span data-ttu-id="79836-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="79836-106">\<identityConfiguration></span></span>  
<span data-ttu-id="79836-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="79836-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="79836-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="79836-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="79836-109">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="79836-109">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79836-110">语法</span><span class="sxs-lookup"><span data-stu-id="79836-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79836-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="79836-111">Attributes and Elements</span></span>  
 <span data-ttu-id="79836-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="79836-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79836-113">特性</span><span class="sxs-lookup"><span data-stu-id="79836-113">Attributes</span></span>  
  
|<span data-ttu-id="79836-114">特性</span><span class="sxs-lookup"><span data-stu-id="79836-114">Attribute</span></span>|<span data-ttu-id="79836-115">描述</span><span class="sxs-lookup"><span data-stu-id="79836-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79836-116">mode</span><span class="sxs-lookup"><span data-stu-id="79836-116">mode</span></span>|<span data-ttu-id="79836-117"><xref:System.IdentityModel.Selectors.AudienceUriMode>值，该值指定是否应该对传入令牌应用的访问群体限制。</span><span class="sxs-lookup"><span data-stu-id="79836-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="79836-118">可能的值为"始终"，"从不"，并"BearerKeyOnly"。</span><span class="sxs-lookup"><span data-stu-id="79836-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="79836-119">默认值为"始终"。</span><span class="sxs-lookup"><span data-stu-id="79836-119">The default is "Always".</span></span> <span data-ttu-id="79836-120">可选。</span><span class="sxs-lookup"><span data-stu-id="79836-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79836-121">子元素</span><span class="sxs-lookup"><span data-stu-id="79836-121">Child Elements</span></span>  
  
|<span data-ttu-id="79836-122">元素</span><span class="sxs-lookup"><span data-stu-id="79836-122">Element</span></span>|<span data-ttu-id="79836-123">描述</span><span class="sxs-lookup"><span data-stu-id="79836-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="79836-124">添加指定的 URI `value` audienceUris 集合的属性。</span><span class="sxs-lookup"><span data-stu-id="79836-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="79836-125">需要 `value` 属性。</span><span class="sxs-lookup"><span data-stu-id="79836-125">The `value` attribute is required.</span></span> <span data-ttu-id="79836-126">该 URI 是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="79836-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="79836-127">清除 audienceUris 的集合。</span><span class="sxs-lookup"><span data-stu-id="79836-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="79836-128">从集合中删除所有标识符。</span><span class="sxs-lookup"><span data-stu-id="79836-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="79836-129">删除指定的 URI `value` audienceUris 集合中的属性。</span><span class="sxs-lookup"><span data-stu-id="79836-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="79836-130">需要 `value` 属性。</span><span class="sxs-lookup"><span data-stu-id="79836-130">The `value` attribute is required.</span></span> <span data-ttu-id="79836-131">该 URI 是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="79836-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="79836-132">父元素</span><span class="sxs-lookup"><span data-stu-id="79836-132">Parent Elements</span></span>  
  
|<span data-ttu-id="79836-133">元素</span><span class="sxs-lookup"><span data-stu-id="79836-133">Element</span></span>|<span data-ttu-id="79836-134">描述</span><span class="sxs-lookup"><span data-stu-id="79836-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79836-135">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="79836-135">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="79836-136">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="79836-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79836-137">备注</span><span class="sxs-lookup"><span data-stu-id="79836-137">Remarks</span></span>  
 <span data-ttu-id="79836-138">默认情况下，该集合为空;使用`<add>`， `<clear>`，和`<remove>`要修改集合的元素。</span><span class="sxs-lookup"><span data-stu-id="79836-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="79836-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 并<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>对象所需配置任何的受众 URI 集合中的值允许的受众 URI 限制中的使用<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>对象。</span><span class="sxs-lookup"><span data-stu-id="79836-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="79836-140">`<audienceUris>`元素表示由<xref:System.IdentityModel.Configuration.AudienceUriElementCollection>类。</span><span class="sxs-lookup"><span data-stu-id="79836-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="79836-141">表示添加到集合的单个 URI<xref:System.IdentityModel.Configuration.AudienceUriElement>类。</span><span class="sxs-lookup"><span data-stu-id="79836-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79836-142">利用`<audienceUris>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已被弃用，但仍然支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="79836-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="79836-143">上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="79836-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79836-144">示例</span><span class="sxs-lookup"><span data-stu-id="79836-144">Example</span></span>  
 <span data-ttu-id="79836-145">下面的 XML 演示如何配置应用程序可接受的受众 Uri。</span><span class="sxs-lookup"><span data-stu-id="79836-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="79836-146">此示例将配置单个 URI。</span><span class="sxs-lookup"><span data-stu-id="79836-146">This example configures a single URI.</span></span> <span data-ttu-id="79836-147">将接受令牌作用域为此 URI，所有其他用户将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="79836-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
