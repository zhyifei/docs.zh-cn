---
title: '&lt;d d&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bd3b197ffe771f72544dc3e61f49583c08fa5821
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltallowedaudienceurisgt"></a><span data-ttu-id="28e57-102">&lt;d d&gt;</span><span class="sxs-lookup"><span data-stu-id="28e57-102">&lt;allowedAudienceUris&gt;</span></span>
<span data-ttu-id="28e57-103">表示 <xref:System.IdentityModel.Tokens.SamlSecurityToken> 安全令牌的目标 URI 集合，只有在使用这些目标 URI 时，<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 实例才会将该令牌视为有效令牌。</span><span class="sxs-lookup"><span data-stu-id="28e57-103">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="28e57-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="28e57-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="28e57-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="28e57-105">\<behaviors></span></span>  
<span data-ttu-id="28e57-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="28e57-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="28e57-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="28e57-107">\<behavior></span></span>  
<span data-ttu-id="28e57-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="28e57-108">\<serviceCredentials></span></span>  
<span data-ttu-id="28e57-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="28e57-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="28e57-110">\<d d ></span><span class="sxs-lookup"><span data-stu-id="28e57-110">\<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28e57-111">语法</span><span class="sxs-lookup"><span data-stu-id="28e57-111">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>  
      <add allowedAudienceUri="String"/>  
</allowedAudienceUris>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28e57-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="28e57-112">Attributes and Elements</span></span>  
 <span data-ttu-id="28e57-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="28e57-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28e57-114">特性</span><span class="sxs-lookup"><span data-stu-id="28e57-114">Attributes</span></span>  
 <span data-ttu-id="28e57-115">无。</span><span class="sxs-lookup"><span data-stu-id="28e57-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="28e57-116">子元素</span><span class="sxs-lookup"><span data-stu-id="28e57-116">Child Elements</span></span>  
  
|<span data-ttu-id="28e57-117">元素</span><span class="sxs-lookup"><span data-stu-id="28e57-117">Element</span></span>|<span data-ttu-id="28e57-118">描述</span><span class="sxs-lookup"><span data-stu-id="28e57-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28e57-119">\<add></span><span class="sxs-lookup"><span data-stu-id="28e57-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)|<span data-ttu-id="28e57-120">添加 <xref:System.IdentityModel.Tokens.SamlSecurityToken> 安全令牌的目标 URI，只有在使用该目标 URI 时，<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 实例才会将该令牌视为有效令牌。</span><span class="sxs-lookup"><span data-stu-id="28e57-120">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28e57-121">父元素</span><span class="sxs-lookup"><span data-stu-id="28e57-121">Parent Elements</span></span>  
  
|<span data-ttu-id="28e57-122">元素</span><span class="sxs-lookup"><span data-stu-id="28e57-122">Element</span></span>|<span data-ttu-id="28e57-123">描述</span><span class="sxs-lookup"><span data-stu-id="28e57-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28e57-124">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="28e57-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="28e57-125">将颁发的令牌指定为服务凭据。</span><span class="sxs-lookup"><span data-stu-id="28e57-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28e57-126">备注</span><span class="sxs-lookup"><span data-stu-id="28e57-126">Remarks</span></span>  
 <span data-ttu-id="28e57-127">在采用颁发 <xref:System.IdentityModel.Tokens.SamlSecurityToken> 安全令牌的安全令牌服务 (STS) 的联合应用程序中，应使用此集合。</span><span class="sxs-lookup"><span data-stu-id="28e57-127">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="28e57-128">当 STS 颁发安全令牌时，它可以通过将 <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> 添加到安全令牌中，来指定安全令牌的目标 Web 服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="28e57-128">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="28e57-129">这样，通过指定应采用以下方式执行此检查，接收方 Web 服务的 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 将能够验证颁发的安全令牌是否针对此 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="28e57-129">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="28e57-130">将 `audienceUriMode` 的 `<issuedTokenAuthentication>` 属性设置为 <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> 或 <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>。</span><span class="sxs-lookup"><span data-stu-id="28e57-130">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="28e57-131">将有效 URI 添加到此集合，以指定有效 URI 集。</span><span class="sxs-lookup"><span data-stu-id="28e57-131">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="28e57-132">有关详细信息，请参阅<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>。</span><span class="sxs-lookup"><span data-stu-id="28e57-132">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="28e57-133">使用此配置元素的详细信息，请参阅[如何： 在联合身份验证服务上配置凭据](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)。</span><span class="sxs-lookup"><span data-stu-id="28e57-133">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e57-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="28e57-134">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>  
 [<span data-ttu-id="28e57-135">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="28e57-135">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="28e57-136">\<add></span><span class="sxs-lookup"><span data-stu-id="28e57-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)  
 [<span data-ttu-id="28e57-137">安全行为</span><span class="sxs-lookup"><span data-stu-id="28e57-137">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="28e57-138">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="28e57-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="28e57-139">如何：在联合身份验证服务上配置凭据</span><span class="sxs-lookup"><span data-stu-id="28e57-139">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
