---
title: '&lt;securityTokenHandlers&gt;'
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 16827aa774a8a76f16106a8650423d0d7f084982
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltsecuritytokenhandlersgt"></a><span data-ttu-id="59308-102">&lt;securityTokenHandlers&gt;</span><span class="sxs-lookup"><span data-stu-id="59308-102">&lt;securityTokenHandlers&gt;</span></span>
<span data-ttu-id="59308-103">指定与终结点注册的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="59308-103">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="59308-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="59308-104">\<system.identityModel></span></span>  
<span data-ttu-id="59308-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="59308-105">\<identityConfiguration></span></span>  
<span data-ttu-id="59308-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="59308-106">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59308-107">语法</span><span class="sxs-lookup"><span data-stu-id="59308-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59308-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="59308-108">Attributes and Elements</span></span>  
 <span data-ttu-id="59308-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="59308-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59308-110">特性</span><span class="sxs-lookup"><span data-stu-id="59308-110">Attributes</span></span>  
  
|<span data-ttu-id="59308-111">特性</span><span class="sxs-lookup"><span data-stu-id="59308-111">Attribute</span></span>|<span data-ttu-id="59308-112">描述</span><span class="sxs-lookup"><span data-stu-id="59308-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59308-113">name</span><span class="sxs-lookup"><span data-stu-id="59308-113">name</span></span>|<span data-ttu-id="59308-114">指定令牌处理程序集合的名称。</span><span class="sxs-lookup"><span data-stu-id="59308-114">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="59308-115">由框架识别的唯一值是"ActAs"和"OnBehalfOf"。</span><span class="sxs-lookup"><span data-stu-id="59308-115">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="59308-116">如果使用的这些名称指定令牌处理程序集合，在处理 ActAs 或 OnBehalfOf 分别令牌时，将使用集合。</span><span class="sxs-lookup"><span data-stu-id="59308-116">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59308-117">子元素</span><span class="sxs-lookup"><span data-stu-id="59308-117">Child Elements</span></span>  
  
|<span data-ttu-id="59308-118">元素</span><span class="sxs-lookup"><span data-stu-id="59308-118">Element</span></span>|<span data-ttu-id="59308-119">描述</span><span class="sxs-lookup"><span data-stu-id="59308-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59308-120">\<add></span><span class="sxs-lookup"><span data-stu-id="59308-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="59308-121">向令牌处理程序集合中添加的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="59308-121">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="59308-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="59308-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|<span data-ttu-id="59308-123">清除所有安全令牌处理程序从标记处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="59308-123">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="59308-124">\<remove></span><span class="sxs-lookup"><span data-stu-id="59308-124">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|<span data-ttu-id="59308-125">从标记处理程序集合中移除的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="59308-125">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="59308-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="59308-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="59308-127">提供配置令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="59308-127">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59308-128">父元素</span><span class="sxs-lookup"><span data-stu-id="59308-128">Parent Elements</span></span>  
  
|<span data-ttu-id="59308-129">元素</span><span class="sxs-lookup"><span data-stu-id="59308-129">Element</span></span>|<span data-ttu-id="59308-130">描述</span><span class="sxs-lookup"><span data-stu-id="59308-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59308-131">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="59308-131">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="59308-132">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="59308-132">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59308-133">备注</span><span class="sxs-lookup"><span data-stu-id="59308-133">Remarks</span></span>  
 <span data-ttu-id="59308-134">你可以在服务配置中指定一个或多个安全令牌处理程序的命名的集合。</span><span class="sxs-lookup"><span data-stu-id="59308-134">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="59308-135">你可以通过使用指定集合的名称`name`属性。</span><span class="sxs-lookup"><span data-stu-id="59308-135">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="59308-136">该框架将处理的唯一名称是"ActAs"和"OnBehalfOf"。</span><span class="sxs-lookup"><span data-stu-id="59308-136">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="59308-137">如果处理程序存在这些集合中，它们由安全令牌服务 (STS) 而不是默认处理程序处理时`ActAs`和`OnBehalfOf`令牌。</span><span class="sxs-lookup"><span data-stu-id="59308-137">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="59308-138">默认情况下，使用以下处理程序类型填充集合： <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>， <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>，和<xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>。</span><span class="sxs-lookup"><span data-stu-id="59308-138">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="59308-139">你可以通过修改该集合`<add>`， `<remove>`，和`<clear>`元素。</span><span class="sxs-lookup"><span data-stu-id="59308-139">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="59308-140">你必须确保仅属于任何特定类型的单个处理程序集合中存在。</span><span class="sxs-lookup"><span data-stu-id="59308-140">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="59308-141">例如，如果你是派生的处理程序<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类，或者您的处理程序或<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>可能单个集合，但不同时配置。</span><span class="sxs-lookup"><span data-stu-id="59308-141">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="59308-142">使用`<securityTokenHandlerConfiguration>`元素集合中指定的处理程序的配置设置。</span><span class="sxs-lookup"><span data-stu-id="59308-142">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="59308-143">通过此元素指定的设置会覆盖通过服务上指定的那些[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="59308-143">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="59308-144">一些处理程序 （包括多个内置的处理程序类型） 可以支持通过的子元素的其他配置`<add>`元素。</span><span class="sxs-lookup"><span data-stu-id="59308-144">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="59308-145">上一个处理程序指定的设置重写指定集合或服务上的等效设置。</span><span class="sxs-lookup"><span data-stu-id="59308-145">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
