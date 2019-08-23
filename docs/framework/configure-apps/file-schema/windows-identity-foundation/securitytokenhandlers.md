---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 678e5c705181c55257b1ddb853690ada60ecd17a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942462"
---
# <a name="securitytokenhandlers"></a><span data-ttu-id="859bf-101">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="859bf-101">\<securityTokenHandlers></span></span>
<span data-ttu-id="859bf-102">指定注册到终结点的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="859bf-102">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="859bf-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="859bf-103">\<system.identityModel></span></span>  
<span data-ttu-id="859bf-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="859bf-104">\<identityConfiguration></span></span>  
<span data-ttu-id="859bf-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="859bf-105">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="859bf-106">语法</span><span class="sxs-lookup"><span data-stu-id="859bf-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="859bf-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="859bf-107">Attributes and Elements</span></span>  
 <span data-ttu-id="859bf-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="859bf-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="859bf-109">特性</span><span class="sxs-lookup"><span data-stu-id="859bf-109">Attributes</span></span>  
  
|<span data-ttu-id="859bf-110">特性</span><span class="sxs-lookup"><span data-stu-id="859bf-110">Attribute</span></span>|<span data-ttu-id="859bf-111">描述</span><span class="sxs-lookup"><span data-stu-id="859bf-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="859bf-112">NAME</span><span class="sxs-lookup"><span data-stu-id="859bf-112">name</span></span>|<span data-ttu-id="859bf-113">指定令牌处理程序集合的名称。</span><span class="sxs-lookup"><span data-stu-id="859bf-113">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="859bf-114">框架唯一识别的值为 "ActAs" 和 "OnBehalfOf"。</span><span class="sxs-lookup"><span data-stu-id="859bf-114">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="859bf-115">如果使用上述任一名称指定了标记处理程序集合, 则会在处理 ActAs 或 OnBehalfOf 令牌时使用该集合。</span><span class="sxs-lookup"><span data-stu-id="859bf-115">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="859bf-116">子元素</span><span class="sxs-lookup"><span data-stu-id="859bf-116">Child Elements</span></span>  
  
|<span data-ttu-id="859bf-117">元素</span><span class="sxs-lookup"><span data-stu-id="859bf-117">Element</span></span>|<span data-ttu-id="859bf-118">描述</span><span class="sxs-lookup"><span data-stu-id="859bf-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="859bf-119">\<add></span><span class="sxs-lookup"><span data-stu-id="859bf-119">\<add></span></span>](add.md)|<span data-ttu-id="859bf-120">将安全标记处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="859bf-120">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="859bf-121">\<clear></span><span class="sxs-lookup"><span data-stu-id="859bf-121">\<clear></span></span>](clear.md)|<span data-ttu-id="859bf-122">清除标记处理程序集合中的所有安全标记处理程序。</span><span class="sxs-lookup"><span data-stu-id="859bf-122">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="859bf-123">\<remove></span><span class="sxs-lookup"><span data-stu-id="859bf-123">\<remove></span></span>](remove.md)|<span data-ttu-id="859bf-124">从标记处理程序集合中移除安全标记处理程序。</span><span class="sxs-lookup"><span data-stu-id="859bf-124">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="859bf-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="859bf-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="859bf-126">为标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="859bf-126">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="859bf-127">父元素</span><span class="sxs-lookup"><span data-stu-id="859bf-127">Parent Elements</span></span>  
  
|<span data-ttu-id="859bf-128">元素</span><span class="sxs-lookup"><span data-stu-id="859bf-128">Element</span></span>|<span data-ttu-id="859bf-129">描述</span><span class="sxs-lookup"><span data-stu-id="859bf-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="859bf-130">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="859bf-130">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="859bf-131">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="859bf-131">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="859bf-132">备注</span><span class="sxs-lookup"><span data-stu-id="859bf-132">Remarks</span></span>  
 <span data-ttu-id="859bf-133">可以在服务配置中指定安全令牌处理程序的一个或多个命名集合。</span><span class="sxs-lookup"><span data-stu-id="859bf-133">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="859bf-134">可以通过使用`name`属性来指定集合的名称。</span><span class="sxs-lookup"><span data-stu-id="859bf-134">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="859bf-135">框架处理的唯一名称为 "ActAs" 和 "OnBehalfOf"。</span><span class="sxs-lookup"><span data-stu-id="859bf-135">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="859bf-136">如果这些集合中存在处理程序, 则在处理`ActAs`和`OnBehalfOf`标记时, 它们由 security token service (STS) 而不是默认的处理程序使用。</span><span class="sxs-lookup"><span data-stu-id="859bf-136">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="859bf-137">默认情况下, 使用以下处理程序类型<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>填充集合:、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>、和<xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>。</span><span class="sxs-lookup"><span data-stu-id="859bf-137">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="859bf-138">您可以使用`<add>`、 `<remove>`和`<clear>`元素来修改集合。</span><span class="sxs-lookup"><span data-stu-id="859bf-138">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="859bf-139">必须确保集合中只存在一个特定类型的处理程序。</span><span class="sxs-lookup"><span data-stu-id="859bf-139">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="859bf-140">例如, 如果从<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类派生处理程序, 则可以在单个集合中配置处理程序<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>或, 但不能同时配置两者。</span><span class="sxs-lookup"><span data-stu-id="859bf-140">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="859bf-141">`<securityTokenHandlerConfiguration>`使用元素指定集合中处理程序的配置设置。</span><span class="sxs-lookup"><span data-stu-id="859bf-141">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="859bf-142">通过此元素指定的设置将[ \<通过 identityConfiguration >](identityconfiguration.md)元素覆盖在服务上指定的设置。</span><span class="sxs-lookup"><span data-stu-id="859bf-142">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="859bf-143">某些处理程序 (包括多个内置处理程序类型) 可以通过`<add>`元素的子元素支持其他配置。</span><span class="sxs-lookup"><span data-stu-id="859bf-143">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="859bf-144">在处理程序上指定的设置将重写对集合或服务指定的等效设置。</span><span class="sxs-lookup"><span data-stu-id="859bf-144">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
