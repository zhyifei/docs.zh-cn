---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 003221ed4dc7f4ccf72d2e0d3a91265e13172813
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941959"
---
# <a name="audienceuris"></a><span data-ttu-id="03467-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="03467-101">\<audienceUris></span></span>
<span data-ttu-id="03467-102">指定可接受的信赖方 (RP) 标识符的 Uri 集。</span><span class="sxs-lookup"><span data-stu-id="03467-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="03467-103">除非令牌的作用域是允许的受众 Uri 之一, 否则不会接受令牌。</span><span class="sxs-lookup"><span data-stu-id="03467-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="03467-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="03467-104">\<system.identityModel></span></span>  
<span data-ttu-id="03467-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="03467-105">\<identityConfiguration></span></span>  
<span data-ttu-id="03467-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="03467-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="03467-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="03467-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="03467-108">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="03467-108">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03467-109">语法</span><span class="sxs-lookup"><span data-stu-id="03467-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03467-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="03467-110">Attributes and Elements</span></span>  
 <span data-ttu-id="03467-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="03467-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03467-112">特性</span><span class="sxs-lookup"><span data-stu-id="03467-112">Attributes</span></span>  
  
|<span data-ttu-id="03467-113">特性</span><span class="sxs-lookup"><span data-stu-id="03467-113">Attribute</span></span>|<span data-ttu-id="03467-114">描述</span><span class="sxs-lookup"><span data-stu-id="03467-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03467-115">mode</span><span class="sxs-lookup"><span data-stu-id="03467-115">mode</span></span>|<span data-ttu-id="03467-116">一个<xref:System.IdentityModel.Selectors.AudienceUriMode>值, 该值指定是否应将受众限制应用于传入令牌。</span><span class="sxs-lookup"><span data-stu-id="03467-116">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="03467-117">可能的值为 "始终"、"从不" 和 "BearerKeyOnly"。</span><span class="sxs-lookup"><span data-stu-id="03467-117">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="03467-118">默认值为 "Always"。</span><span class="sxs-lookup"><span data-stu-id="03467-118">The default is "Always".</span></span> <span data-ttu-id="03467-119">可选。</span><span class="sxs-lookup"><span data-stu-id="03467-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03467-120">子元素</span><span class="sxs-lookup"><span data-stu-id="03467-120">Child Elements</span></span>  
  
|<span data-ttu-id="03467-121">元素</span><span class="sxs-lookup"><span data-stu-id="03467-121">Element</span></span>|<span data-ttu-id="03467-122">描述</span><span class="sxs-lookup"><span data-stu-id="03467-122">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="03467-123">将`value`属性指定的 URI 添加到 audienceUris 集合。</span><span class="sxs-lookup"><span data-stu-id="03467-123">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="03467-124">需要 `value` 属性。</span><span class="sxs-lookup"><span data-stu-id="03467-124">The `value` attribute is required.</span></span> <span data-ttu-id="03467-125">URI 区分大小写。</span><span class="sxs-lookup"><span data-stu-id="03467-125">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="03467-126">清除 audienceUris 集合。</span><span class="sxs-lookup"><span data-stu-id="03467-126">Clears the audienceUris collection.</span></span> <span data-ttu-id="03467-127">所有标识符都将从集合中删除。</span><span class="sxs-lookup"><span data-stu-id="03467-127">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="03467-128">从 audienceUris 集合中移除`value`特性指定的 URI。</span><span class="sxs-lookup"><span data-stu-id="03467-128">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="03467-129">需要 `value` 属性。</span><span class="sxs-lookup"><span data-stu-id="03467-129">The `value` attribute is required.</span></span> <span data-ttu-id="03467-130">URI 区分大小写。</span><span class="sxs-lookup"><span data-stu-id="03467-130">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03467-131">父元素</span><span class="sxs-lookup"><span data-stu-id="03467-131">Parent Elements</span></span>  
  
|<span data-ttu-id="03467-132">元素</span><span class="sxs-lookup"><span data-stu-id="03467-132">Element</span></span>|<span data-ttu-id="03467-133">描述</span><span class="sxs-lookup"><span data-stu-id="03467-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03467-134">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="03467-134">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="03467-135">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="03467-135">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03467-136">备注</span><span class="sxs-lookup"><span data-stu-id="03467-136">Remarks</span></span>  
 <span data-ttu-id="03467-137">默认情况下, 集合为空;使用`<add>`、 `<clear>`和`<remove>`元素可修改集合。</span><span class="sxs-lookup"><span data-stu-id="03467-137">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="03467-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>和<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>对象使用受众 uri 集合中的值来配置对象中允许的<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>受众 uri 限制。</span><span class="sxs-lookup"><span data-stu-id="03467-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="03467-139">元素由<xref:System.IdentityModel.Configuration.AudienceUriElementCollection>类表示。 `<audienceUris>`</span><span class="sxs-lookup"><span data-stu-id="03467-139">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="03467-140">添加到集合中的单个 URI 由<xref:System.IdentityModel.Configuration.AudienceUriElement>类表示。</span><span class="sxs-lookup"><span data-stu-id="03467-140">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03467-141">使用`<audienceUris>`元素作为[ \<identityConfiguration >](identityconfiguration.md)元素的子元素已被弃用, 但仍支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="03467-141">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="03467-142">元素上的`<securityTokenHandlerConfiguration>`设置将替代`<identityConfiguration>`元素上的设置。</span><span class="sxs-lookup"><span data-stu-id="03467-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03467-143">示例</span><span class="sxs-lookup"><span data-stu-id="03467-143">Example</span></span>  
 <span data-ttu-id="03467-144">下面的 XML 演示如何配置应用程序的可接受受众 Uri。</span><span class="sxs-lookup"><span data-stu-id="03467-144">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="03467-145">此示例配置单个 URI。</span><span class="sxs-lookup"><span data-stu-id="03467-145">This example configures a single URI.</span></span> <span data-ttu-id="03467-146">将接受范围为此 URI 的标记, 所有其他标记将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="03467-146">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
