---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 556c444d5e48e27036c4b49338f6e70de7ef5c5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750743"
---
# <a name="audienceuris"></a><span data-ttu-id="b2b32-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="b2b32-101">\<audienceUris></span></span>
<span data-ttu-id="b2b32-102">指定 Uri 都是可接受的信赖方 (RP) 标识符的集。</span><span class="sxs-lookup"><span data-stu-id="b2b32-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="b2b32-103">除非某个允许的受众 Uri 作用域内，将不会接受令牌。</span><span class="sxs-lookup"><span data-stu-id="b2b32-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="b2b32-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b2b32-104">\<system.identityModel></span></span>  
<span data-ttu-id="b2b32-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b2b32-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b2b32-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b2b32-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b2b32-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b2b32-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="b2b32-108">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="b2b32-108">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2b32-109">语法</span><span class="sxs-lookup"><span data-stu-id="b2b32-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2b32-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b2b32-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b2b32-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b2b32-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2b32-112">特性</span><span class="sxs-lookup"><span data-stu-id="b2b32-112">Attributes</span></span>  
  
|<span data-ttu-id="b2b32-113">特性</span><span class="sxs-lookup"><span data-stu-id="b2b32-113">Attribute</span></span>|<span data-ttu-id="b2b32-114">描述</span><span class="sxs-lookup"><span data-stu-id="b2b32-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2b32-115">mode</span><span class="sxs-lookup"><span data-stu-id="b2b32-115">mode</span></span>|<span data-ttu-id="b2b32-116"><xref:System.IdentityModel.Selectors.AudienceUriMode>值，该值指定是否应该对传入令牌应用的访问群体限制。</span><span class="sxs-lookup"><span data-stu-id="b2b32-116">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="b2b32-117">可能的值为"始终"，"从不"，并"BearerKeyOnly"。</span><span class="sxs-lookup"><span data-stu-id="b2b32-117">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="b2b32-118">默认值为"始终"。</span><span class="sxs-lookup"><span data-stu-id="b2b32-118">The default is "Always".</span></span> <span data-ttu-id="b2b32-119">可选。</span><span class="sxs-lookup"><span data-stu-id="b2b32-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2b32-120">子元素</span><span class="sxs-lookup"><span data-stu-id="b2b32-120">Child Elements</span></span>  
  
|<span data-ttu-id="b2b32-121">元素</span><span class="sxs-lookup"><span data-stu-id="b2b32-121">Element</span></span>|<span data-ttu-id="b2b32-122">描述</span><span class="sxs-lookup"><span data-stu-id="b2b32-122">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="b2b32-123">添加指定的 URI `value` audienceUris 集合的属性。</span><span class="sxs-lookup"><span data-stu-id="b2b32-123">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="b2b32-124">需要 `value` 属性。</span><span class="sxs-lookup"><span data-stu-id="b2b32-124">The `value` attribute is required.</span></span> <span data-ttu-id="b2b32-125">该 URI 是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b2b32-125">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="b2b32-126">清除 audienceUris 的集合。</span><span class="sxs-lookup"><span data-stu-id="b2b32-126">Clears the audienceUris collection.</span></span> <span data-ttu-id="b2b32-127">从集合中删除所有标识符。</span><span class="sxs-lookup"><span data-stu-id="b2b32-127">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="b2b32-128">删除指定的 URI `value` audienceUris 集合中的属性。</span><span class="sxs-lookup"><span data-stu-id="b2b32-128">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="b2b32-129">需要 `value` 属性。</span><span class="sxs-lookup"><span data-stu-id="b2b32-129">The `value` attribute is required.</span></span> <span data-ttu-id="b2b32-130">该 URI 是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b2b32-130">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2b32-131">父元素</span><span class="sxs-lookup"><span data-stu-id="b2b32-131">Parent Elements</span></span>  
  
|<span data-ttu-id="b2b32-132">元素</span><span class="sxs-lookup"><span data-stu-id="b2b32-132">Element</span></span>|<span data-ttu-id="b2b32-133">描述</span><span class="sxs-lookup"><span data-stu-id="b2b32-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2b32-134">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b2b32-134">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="b2b32-135">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="b2b32-135">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2b32-136">备注</span><span class="sxs-lookup"><span data-stu-id="b2b32-136">Remarks</span></span>  
 <span data-ttu-id="b2b32-137">默认情况下，该集合为空;使用`<add>`， `<clear>`，和`<remove>`要修改集合的元素。</span><span class="sxs-lookup"><span data-stu-id="b2b32-137">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="b2b32-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 并<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>对象所需配置任何的受众 URI 集合中的值允许的受众 URI 限制中的使用<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>对象。</span><span class="sxs-lookup"><span data-stu-id="b2b32-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="b2b32-139">`<audienceUris>`元素表示由<xref:System.IdentityModel.Configuration.AudienceUriElementCollection>类。</span><span class="sxs-lookup"><span data-stu-id="b2b32-139">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="b2b32-140">表示添加到集合的单个 URI<xref:System.IdentityModel.Configuration.AudienceUriElement>类。</span><span class="sxs-lookup"><span data-stu-id="b2b32-140">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2b32-141">利用`<audienceUris>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已被弃用，但仍然支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="b2b32-141">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="b2b32-142">上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="b2b32-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2b32-143">示例</span><span class="sxs-lookup"><span data-stu-id="b2b32-143">Example</span></span>  
 <span data-ttu-id="b2b32-144">下面的 XML 演示如何配置应用程序可接受的受众 Uri。</span><span class="sxs-lookup"><span data-stu-id="b2b32-144">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="b2b32-145">此示例将配置单个 URI。</span><span class="sxs-lookup"><span data-stu-id="b2b32-145">This example configures a single URI.</span></span> <span data-ttu-id="b2b32-146">将接受令牌作用域为此 URI，所有其他用户将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="b2b32-146">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
