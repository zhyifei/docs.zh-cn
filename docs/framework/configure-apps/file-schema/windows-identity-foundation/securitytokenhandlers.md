---
title: '&lt;securityTokenHandlers&gt;'
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: e63f02add81495e474b59b6c5cc090bd69add3d2
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47206161"
---
# <a name="ltsecuritytokenhandlersgt"></a><span data-ttu-id="a9b36-102">&lt;securityTokenHandlers&gt;</span><span class="sxs-lookup"><span data-stu-id="a9b36-102">&lt;securityTokenHandlers&gt;</span></span>
<span data-ttu-id="a9b36-103">指定与该终结点注册的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="a9b36-103">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="a9b36-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="a9b36-104">\<system.identityModel></span></span>  
<span data-ttu-id="a9b36-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a9b36-105">\<identityConfiguration></span></span>  
<span data-ttu-id="a9b36-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="a9b36-106">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9b36-107">语法</span><span class="sxs-lookup"><span data-stu-id="a9b36-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9b36-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a9b36-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a9b36-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a9b36-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9b36-110">特性</span><span class="sxs-lookup"><span data-stu-id="a9b36-110">Attributes</span></span>  
  
|<span data-ttu-id="a9b36-111">特性</span><span class="sxs-lookup"><span data-stu-id="a9b36-111">Attribute</span></span>|<span data-ttu-id="a9b36-112">描述</span><span class="sxs-lookup"><span data-stu-id="a9b36-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a9b36-113">name</span><span class="sxs-lookup"><span data-stu-id="a9b36-113">name</span></span>|<span data-ttu-id="a9b36-114">指定的标记处理程序集合的名称。</span><span class="sxs-lookup"><span data-stu-id="a9b36-114">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="a9b36-115">由框架识别的唯一值是"ActAs"和"OnBehalfOf"。</span><span class="sxs-lookup"><span data-stu-id="a9b36-115">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="a9b36-116">如果使用这些名称的指定标记处理程序集合，分别处理 ActAs 或 OnBehalfOf 令牌时，将使用集合。</span><span class="sxs-lookup"><span data-stu-id="a9b36-116">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9b36-117">子元素</span><span class="sxs-lookup"><span data-stu-id="a9b36-117">Child Elements</span></span>  
  
|<span data-ttu-id="a9b36-118">元素</span><span class="sxs-lookup"><span data-stu-id="a9b36-118">Element</span></span>|<span data-ttu-id="a9b36-119">描述</span><span class="sxs-lookup"><span data-stu-id="a9b36-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9b36-120">\<add></span><span class="sxs-lookup"><span data-stu-id="a9b36-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="a9b36-121">将安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="a9b36-121">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="a9b36-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="a9b36-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|<span data-ttu-id="a9b36-123">清除所有安全令牌处理程序从令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="a9b36-123">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="a9b36-124">\<remove></span><span class="sxs-lookup"><span data-stu-id="a9b36-124">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|<span data-ttu-id="a9b36-125">令牌处理程序集合中删除的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="a9b36-125">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="a9b36-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a9b36-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="a9b36-127">提供的令牌处理程序集合的配置。</span><span class="sxs-lookup"><span data-stu-id="a9b36-127">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9b36-128">父元素</span><span class="sxs-lookup"><span data-stu-id="a9b36-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a9b36-129">元素</span><span class="sxs-lookup"><span data-stu-id="a9b36-129">Element</span></span>|<span data-ttu-id="a9b36-130">描述</span><span class="sxs-lookup"><span data-stu-id="a9b36-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9b36-131">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a9b36-131">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="a9b36-132">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="a9b36-132">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9b36-133">备注</span><span class="sxs-lookup"><span data-stu-id="a9b36-133">Remarks</span></span>  
 <span data-ttu-id="a9b36-134">在服务配置，可以指定一个或多个安全令牌处理程序的命名的集合。</span><span class="sxs-lookup"><span data-stu-id="a9b36-134">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="a9b36-135">可以通过使用指定的名称集合`name`属性。</span><span class="sxs-lookup"><span data-stu-id="a9b36-135">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="a9b36-136">该框架将处理的唯一名称是"ActAs"和"OnBehalfOf"。</span><span class="sxs-lookup"><span data-stu-id="a9b36-136">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="a9b36-137">如果这些集合中存在处理程序，它们由安全令牌服务 (STS) 而不是默认处理程序处理时`ActAs`和`OnBehalfOf`令牌。</span><span class="sxs-lookup"><span data-stu-id="a9b36-137">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="a9b36-138">默认情况下，该集合填充以下处理程序类型： <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>， <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>，和<xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>。</span><span class="sxs-lookup"><span data-stu-id="a9b36-138">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="a9b36-139">可以通过使用修改集合`<add>`， `<remove>`，和`<clear>`元素。</span><span class="sxs-lookup"><span data-stu-id="a9b36-139">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="a9b36-140">您必须确保仅任何特定类型的单个处理程序集合中存在。</span><span class="sxs-lookup"><span data-stu-id="a9b36-140">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="a9b36-141">例如，如果派生的处理程序从<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类，或者您的处理程序或<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>可能在单个集合，但不是能同时配置。</span><span class="sxs-lookup"><span data-stu-id="a9b36-141">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="a9b36-142">使用`<securityTokenHandlerConfiguration>`元素集合中指定的处理程序的配置设置。</span><span class="sxs-lookup"><span data-stu-id="a9b36-142">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="a9b36-143">通过此元素指定的设置将覆盖指定通过在服务上的那些[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。</span><span class="sxs-lookup"><span data-stu-id="a9b36-143">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="a9b36-144">一些处理程序 （包括多个内置处理程序类型） 可以支持其他配置的子元素通过`<add>`元素。</span><span class="sxs-lookup"><span data-stu-id="a9b36-144">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="a9b36-145">上一个处理程序指定设置覆盖指定集合或服务上的等效设置。</span><span class="sxs-lookup"><span data-stu-id="a9b36-145">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
