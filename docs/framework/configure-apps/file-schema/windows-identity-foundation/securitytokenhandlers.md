---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 017309436660991c69da569e9cc4219e842ecaa3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251875"
---
# <a name="securitytokenhandlers"></a><span data-ttu-id="d4673-101">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d4673-101">\<securityTokenHandlers></span></span>
<span data-ttu-id="d4673-102">指定注册到终结点的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="d4673-102">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
<span data-ttu-id="d4673-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4673-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d4673-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="d4673-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="d4673-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d4673-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="d4673-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<securityTokenHandlers >**</span><span class="sxs-lookup"><span data-stu-id="d4673-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4673-107">语法</span><span class="sxs-lookup"><span data-stu-id="d4673-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4673-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d4673-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d4673-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d4673-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4673-110">特性</span><span class="sxs-lookup"><span data-stu-id="d4673-110">Attributes</span></span>  
  
|<span data-ttu-id="d4673-111">特性</span><span class="sxs-lookup"><span data-stu-id="d4673-111">Attribute</span></span>|<span data-ttu-id="d4673-112">描述</span><span class="sxs-lookup"><span data-stu-id="d4673-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d4673-113">NAME</span><span class="sxs-lookup"><span data-stu-id="d4673-113">name</span></span>|<span data-ttu-id="d4673-114">指定令牌处理程序集合的名称。</span><span class="sxs-lookup"><span data-stu-id="d4673-114">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="d4673-115">框架唯一识别的值为 "ActAs" 和 "OnBehalfOf"。</span><span class="sxs-lookup"><span data-stu-id="d4673-115">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="d4673-116">如果使用上述任一名称指定了标记处理程序集合，则会在处理 ActAs 或 OnBehalfOf 令牌时使用该集合。</span><span class="sxs-lookup"><span data-stu-id="d4673-116">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4673-117">子元素</span><span class="sxs-lookup"><span data-stu-id="d4673-117">Child Elements</span></span>  
  
|<span data-ttu-id="d4673-118">元素</span><span class="sxs-lookup"><span data-stu-id="d4673-118">Element</span></span>|<span data-ttu-id="d4673-119">描述</span><span class="sxs-lookup"><span data-stu-id="d4673-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4673-120">\<add></span><span class="sxs-lookup"><span data-stu-id="d4673-120">\<add></span></span>](add.md)|<span data-ttu-id="d4673-121">将安全标记处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="d4673-121">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="d4673-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="d4673-122">\<clear></span></span>](clear.md)|<span data-ttu-id="d4673-123">清除标记处理程序集合中的所有安全标记处理程序。</span><span class="sxs-lookup"><span data-stu-id="d4673-123">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="d4673-124">\<remove></span><span class="sxs-lookup"><span data-stu-id="d4673-124">\<remove></span></span>](remove.md)|<span data-ttu-id="d4673-125">从标记处理程序集合中移除安全标记处理程序。</span><span class="sxs-lookup"><span data-stu-id="d4673-125">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="d4673-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d4673-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="d4673-127">为标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="d4673-127">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4673-128">父元素</span><span class="sxs-lookup"><span data-stu-id="d4673-128">Parent Elements</span></span>  
  
|<span data-ttu-id="d4673-129">元素</span><span class="sxs-lookup"><span data-stu-id="d4673-129">Element</span></span>|<span data-ttu-id="d4673-130">描述</span><span class="sxs-lookup"><span data-stu-id="d4673-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4673-131">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d4673-131">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="d4673-132">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="d4673-132">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4673-133">备注</span><span class="sxs-lookup"><span data-stu-id="d4673-133">Remarks</span></span>  
 <span data-ttu-id="d4673-134">可以在服务配置中指定安全令牌处理程序的一个或多个命名集合。</span><span class="sxs-lookup"><span data-stu-id="d4673-134">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="d4673-135">可以通过使用`name`属性来指定集合的名称。</span><span class="sxs-lookup"><span data-stu-id="d4673-135">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="d4673-136">框架处理的唯一名称为 "ActAs" 和 "OnBehalfOf"。</span><span class="sxs-lookup"><span data-stu-id="d4673-136">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="d4673-137">如果这些集合中存在处理程序，则在处理`ActAs`和`OnBehalfOf`标记时，它们由 security token service （STS）而不是默认的处理程序使用。</span><span class="sxs-lookup"><span data-stu-id="d4673-137">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="d4673-138">默认情况下，使用以下处理程序类型<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>填充集合：、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>、和<xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>。</span><span class="sxs-lookup"><span data-stu-id="d4673-138">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="d4673-139">您可以使用`<add>`、 `<remove>`和`<clear>`元素来修改集合。</span><span class="sxs-lookup"><span data-stu-id="d4673-139">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="d4673-140">必须确保集合中只存在一个特定类型的处理程序。</span><span class="sxs-lookup"><span data-stu-id="d4673-140">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="d4673-141">例如，如果从<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类派生处理程序，则可以在单个集合中配置处理程序<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>或，但不能同时配置两者。</span><span class="sxs-lookup"><span data-stu-id="d4673-141">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="d4673-142">`<securityTokenHandlerConfiguration>`使用元素指定集合中处理程序的配置设置。</span><span class="sxs-lookup"><span data-stu-id="d4673-142">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="d4673-143">通过此元素指定的设置将[ \<通过 identityConfiguration >](identityconfiguration.md)元素覆盖在服务上指定的设置。</span><span class="sxs-lookup"><span data-stu-id="d4673-143">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="d4673-144">某些处理程序（包括多个内置处理程序类型）可以通过`<add>`元素的子元素支持其他配置。</span><span class="sxs-lookup"><span data-stu-id="d4673-144">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="d4673-145">在处理程序上指定的设置将重写对集合或服务指定的等效设置。</span><span class="sxs-lookup"><span data-stu-id="d4673-145">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
