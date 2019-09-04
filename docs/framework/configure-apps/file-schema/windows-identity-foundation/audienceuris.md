---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252172"
---
# <a name="audienceuris"></a><span data-ttu-id="cc90e-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="cc90e-101">\<audienceUris></span></span>
<span data-ttu-id="cc90e-102">指定可接受的信赖方（RP）标识符的 Uri 集。</span><span class="sxs-lookup"><span data-stu-id="cc90e-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="cc90e-103">除非令牌的作用域是允许的受众 Uri 之一，否则不会接受令牌。</span><span class="sxs-lookup"><span data-stu-id="cc90e-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
<span data-ttu-id="cc90e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cc90e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cc90e-105">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="cc90e-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="cc90e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="cc90e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="cc90e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="cc90e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="cc90e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="cc90e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="cc90e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<audienceUris >**</span><span class="sxs-lookup"><span data-stu-id="cc90e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc90e-110">语法</span><span class="sxs-lookup"><span data-stu-id="cc90e-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc90e-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cc90e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cc90e-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cc90e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc90e-113">特性</span><span class="sxs-lookup"><span data-stu-id="cc90e-113">Attributes</span></span>  
  
|<span data-ttu-id="cc90e-114">特性</span><span class="sxs-lookup"><span data-stu-id="cc90e-114">Attribute</span></span>|<span data-ttu-id="cc90e-115">描述</span><span class="sxs-lookup"><span data-stu-id="cc90e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc90e-116">mode</span><span class="sxs-lookup"><span data-stu-id="cc90e-116">mode</span></span>|<span data-ttu-id="cc90e-117">一个<xref:System.IdentityModel.Selectors.AudienceUriMode>值，该值指定是否应将受众限制应用于传入令牌。</span><span class="sxs-lookup"><span data-stu-id="cc90e-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="cc90e-118">可能的值为 "始终"、"从不" 和 "BearerKeyOnly"。</span><span class="sxs-lookup"><span data-stu-id="cc90e-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="cc90e-119">默认值为 "Always"。</span><span class="sxs-lookup"><span data-stu-id="cc90e-119">The default is "Always".</span></span> <span data-ttu-id="cc90e-120">可选。</span><span class="sxs-lookup"><span data-stu-id="cc90e-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc90e-121">子元素</span><span class="sxs-lookup"><span data-stu-id="cc90e-121">Child Elements</span></span>  
  
|<span data-ttu-id="cc90e-122">元素</span><span class="sxs-lookup"><span data-stu-id="cc90e-122">Element</span></span>|<span data-ttu-id="cc90e-123">描述</span><span class="sxs-lookup"><span data-stu-id="cc90e-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="cc90e-124">将`value`属性指定的 URI 添加到 audienceUris 集合。</span><span class="sxs-lookup"><span data-stu-id="cc90e-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="cc90e-125">需要 `value` 属性。</span><span class="sxs-lookup"><span data-stu-id="cc90e-125">The `value` attribute is required.</span></span> <span data-ttu-id="cc90e-126">URI 区分大小写。</span><span class="sxs-lookup"><span data-stu-id="cc90e-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="cc90e-127">清除 audienceUris 集合。</span><span class="sxs-lookup"><span data-stu-id="cc90e-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="cc90e-128">所有标识符都将从集合中删除。</span><span class="sxs-lookup"><span data-stu-id="cc90e-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="cc90e-129">从 audienceUris 集合中移除`value`特性指定的 URI。</span><span class="sxs-lookup"><span data-stu-id="cc90e-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="cc90e-130">需要 `value` 属性。</span><span class="sxs-lookup"><span data-stu-id="cc90e-130">The `value` attribute is required.</span></span> <span data-ttu-id="cc90e-131">URI 区分大小写。</span><span class="sxs-lookup"><span data-stu-id="cc90e-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cc90e-132">父元素</span><span class="sxs-lookup"><span data-stu-id="cc90e-132">Parent Elements</span></span>  
  
|<span data-ttu-id="cc90e-133">元素</span><span class="sxs-lookup"><span data-stu-id="cc90e-133">Element</span></span>|<span data-ttu-id="cc90e-134">描述</span><span class="sxs-lookup"><span data-stu-id="cc90e-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc90e-135">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="cc90e-135">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="cc90e-136">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="cc90e-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc90e-137">备注</span><span class="sxs-lookup"><span data-stu-id="cc90e-137">Remarks</span></span>  
 <span data-ttu-id="cc90e-138">默认情况下，集合为空;使用`<add>`、 `<clear>`和`<remove>`元素可修改集合。</span><span class="sxs-lookup"><span data-stu-id="cc90e-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="cc90e-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>和<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>对象使用受众 uri 集合中的值来配置对象中允许的<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>受众 uri 限制。</span><span class="sxs-lookup"><span data-stu-id="cc90e-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="cc90e-140">元素由<xref:System.IdentityModel.Configuration.AudienceUriElementCollection>类表示。 `<audienceUris>`</span><span class="sxs-lookup"><span data-stu-id="cc90e-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="cc90e-141">添加到集合中的单个 URI 由<xref:System.IdentityModel.Configuration.AudienceUriElement>类表示。</span><span class="sxs-lookup"><span data-stu-id="cc90e-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc90e-142">使用`<audienceUris>`元素作为[ \<identityConfiguration >](identityconfiguration.md)元素的子元素已被弃用，但仍支持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="cc90e-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="cc90e-143">元素上的`<securityTokenHandlerConfiguration>`设置将替代`<identityConfiguration>`元素上的设置。</span><span class="sxs-lookup"><span data-stu-id="cc90e-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc90e-144">示例</span><span class="sxs-lookup"><span data-stu-id="cc90e-144">Example</span></span>  
 <span data-ttu-id="cc90e-145">下面的 XML 演示如何配置应用程序的可接受受众 Uri。</span><span class="sxs-lookup"><span data-stu-id="cc90e-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="cc90e-146">此示例配置单个 URI。</span><span class="sxs-lookup"><span data-stu-id="cc90e-146">This example configures a single URI.</span></span> <span data-ttu-id="cc90e-147">将接受范围为此 URI 的标记，所有其他标记将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="cc90e-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
