---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: a5af3893ab72d23c2b3814569decfc50431b8e55
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277519"
---
# <a name="securitytokenhandlers"></a><span data-ttu-id="d7273-101">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d7273-101">\<securityTokenHandlers></span></span>
<span data-ttu-id="d7273-102">指定与该终结点注册的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="d7273-102">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="d7273-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d7273-103">\<system.identityModel></span></span>  
<span data-ttu-id="d7273-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d7273-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d7273-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d7273-105">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7273-106">语法</span><span class="sxs-lookup"><span data-stu-id="d7273-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7273-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d7273-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d7273-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d7273-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7273-109">特性</span><span class="sxs-lookup"><span data-stu-id="d7273-109">Attributes</span></span>  
  
|<span data-ttu-id="d7273-110">特性</span><span class="sxs-lookup"><span data-stu-id="d7273-110">Attribute</span></span>|<span data-ttu-id="d7273-111">描述</span><span class="sxs-lookup"><span data-stu-id="d7273-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7273-112">name</span><span class="sxs-lookup"><span data-stu-id="d7273-112">name</span></span>|<span data-ttu-id="d7273-113">指定的标记处理程序集合的名称。</span><span class="sxs-lookup"><span data-stu-id="d7273-113">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="d7273-114">由框架识别的唯一值是"ActAs"和"OnBehalfOf"。</span><span class="sxs-lookup"><span data-stu-id="d7273-114">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="d7273-115">如果使用这些名称的指定标记处理程序集合，分别处理 ActAs 或 OnBehalfOf 令牌时，将使用集合。</span><span class="sxs-lookup"><span data-stu-id="d7273-115">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7273-116">子元素</span><span class="sxs-lookup"><span data-stu-id="d7273-116">Child Elements</span></span>  
  
|<span data-ttu-id="d7273-117">元素</span><span class="sxs-lookup"><span data-stu-id="d7273-117">Element</span></span>|<span data-ttu-id="d7273-118">描述</span><span class="sxs-lookup"><span data-stu-id="d7273-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7273-119">\<add></span><span class="sxs-lookup"><span data-stu-id="d7273-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="d7273-120">将安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="d7273-120">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="d7273-121">\<clear></span><span class="sxs-lookup"><span data-stu-id="d7273-121">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|<span data-ttu-id="d7273-122">清除所有安全令牌处理程序从令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="d7273-122">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="d7273-123">\<remove></span><span class="sxs-lookup"><span data-stu-id="d7273-123">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|<span data-ttu-id="d7273-124">令牌处理程序集合中删除的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="d7273-124">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="d7273-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d7273-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="d7273-126">提供的令牌处理程序集合的配置。</span><span class="sxs-lookup"><span data-stu-id="d7273-126">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d7273-127">父元素</span><span class="sxs-lookup"><span data-stu-id="d7273-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d7273-128">元素</span><span class="sxs-lookup"><span data-stu-id="d7273-128">Element</span></span>|<span data-ttu-id="d7273-129">描述</span><span class="sxs-lookup"><span data-stu-id="d7273-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7273-130">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d7273-130">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="d7273-131">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="d7273-131">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7273-132">备注</span><span class="sxs-lookup"><span data-stu-id="d7273-132">Remarks</span></span>  
 <span data-ttu-id="d7273-133">在服务配置，可以指定一个或多个安全令牌处理程序的命名的集合。</span><span class="sxs-lookup"><span data-stu-id="d7273-133">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="d7273-134">可以通过使用指定的名称集合`name`属性。</span><span class="sxs-lookup"><span data-stu-id="d7273-134">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="d7273-135">该框架将处理的唯一名称是"ActAs"和"OnBehalfOf"。</span><span class="sxs-lookup"><span data-stu-id="d7273-135">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="d7273-136">如果这些集合中存在处理程序，它们由安全令牌服务 (STS) 而不是默认处理程序处理时`ActAs`和`OnBehalfOf`令牌。</span><span class="sxs-lookup"><span data-stu-id="d7273-136">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="d7273-137">默认情况下，该集合填充以下处理程序类型： <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>， <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>，和<xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>。</span><span class="sxs-lookup"><span data-stu-id="d7273-137">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="d7273-138">可以通过使用修改集合`<add>`， `<remove>`，和`<clear>`元素。</span><span class="sxs-lookup"><span data-stu-id="d7273-138">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="d7273-139">您必须确保仅任何特定类型的单个处理程序集合中存在。</span><span class="sxs-lookup"><span data-stu-id="d7273-139">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="d7273-140">例如，如果派生的处理程序从<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类，或者您的处理程序或<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>可能在单个集合，但不是能同时配置。</span><span class="sxs-lookup"><span data-stu-id="d7273-140">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="d7273-141">使用`<securityTokenHandlerConfiguration>`元素集合中指定的处理程序的配置设置。</span><span class="sxs-lookup"><span data-stu-id="d7273-141">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="d7273-142">通过此元素指定的设置将覆盖指定通过在服务上的那些[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d7273-142">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="d7273-143">一些处理程序 （包括多个内置处理程序类型） 可以支持其他配置的子元素通过`<add>`元素。</span><span class="sxs-lookup"><span data-stu-id="d7273-143">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="d7273-144">上一个处理程序指定设置覆盖指定集合或服务上的等效设置。</span><span class="sxs-lookup"><span data-stu-id="d7273-144">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
