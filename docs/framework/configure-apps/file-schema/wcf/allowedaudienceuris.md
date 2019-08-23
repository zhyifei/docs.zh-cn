---
title: <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
ms.openlocfilehash: 03888600a89d72f5216c8c8cac21c9da96879ba8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919967"
---
# <a name="allowedaudienceuris"></a><span data-ttu-id="dfb42-101">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="dfb42-101">\<allowedAudienceUris></span></span>
<span data-ttu-id="dfb42-102">表示 <xref:System.IdentityModel.Tokens.SamlSecurityToken> 安全令牌的目标 URI 集合，只有在使用这些目标 URI 时，<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 实例才会将该令牌视为有效令牌。</span><span class="sxs-lookup"><span data-stu-id="dfb42-102">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="dfb42-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dfb42-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="dfb42-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="dfb42-104">\<behaviors></span></span>  
<span data-ttu-id="dfb42-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="dfb42-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="dfb42-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="dfb42-106">\<behavior></span></span>  
<span data-ttu-id="dfb42-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="dfb42-107">\<serviceCredentials></span></span>  
<span data-ttu-id="dfb42-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="dfb42-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="dfb42-109">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="dfb42-109">\<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfb42-110">语法</span><span class="sxs-lookup"><span data-stu-id="dfb42-110">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfb42-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dfb42-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dfb42-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="dfb42-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfb42-113">特性</span><span class="sxs-lookup"><span data-stu-id="dfb42-113">Attributes</span></span>  
 <span data-ttu-id="dfb42-114">无。</span><span class="sxs-lookup"><span data-stu-id="dfb42-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dfb42-115">子元素</span><span class="sxs-lookup"><span data-stu-id="dfb42-115">Child Elements</span></span>  
  
|<span data-ttu-id="dfb42-116">元素</span><span class="sxs-lookup"><span data-stu-id="dfb42-116">Element</span></span>|<span data-ttu-id="dfb42-117">描述</span><span class="sxs-lookup"><span data-stu-id="dfb42-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfb42-118">\<add></span><span class="sxs-lookup"><span data-stu-id="dfb42-118">\<add></span></span>](add-of-allowedaudienceuris.md)|<span data-ttu-id="dfb42-119">添加 <xref:System.IdentityModel.Tokens.SamlSecurityToken> 安全令牌的目标 URI，只有在使用该目标 URI 时，<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 实例才会将该令牌视为有效令牌。</span><span class="sxs-lookup"><span data-stu-id="dfb42-119">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dfb42-120">父元素</span><span class="sxs-lookup"><span data-stu-id="dfb42-120">Parent Elements</span></span>  
  
|<span data-ttu-id="dfb42-121">元素</span><span class="sxs-lookup"><span data-stu-id="dfb42-121">Element</span></span>|<span data-ttu-id="dfb42-122">描述</span><span class="sxs-lookup"><span data-stu-id="dfb42-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfb42-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="dfb42-123">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="dfb42-124">将颁发的令牌指定为服务凭据。</span><span class="sxs-lookup"><span data-stu-id="dfb42-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfb42-125">备注</span><span class="sxs-lookup"><span data-stu-id="dfb42-125">Remarks</span></span>  
 <span data-ttu-id="dfb42-126">在采用颁发 <xref:System.IdentityModel.Tokens.SamlSecurityToken> 安全令牌的安全令牌服务 (STS) 的联合应用程序中，应使用此集合。</span><span class="sxs-lookup"><span data-stu-id="dfb42-126">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="dfb42-127">当 STS 颁发安全令牌时，它可以通过将 <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> 添加到安全令牌中，来指定安全令牌的目标 Web 服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="dfb42-127">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="dfb42-128">这样，通过指定应采用以下方式执行此检查，接收方 Web 服务的 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 将能够验证颁发的安全令牌是否针对此 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="dfb42-128">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
- <span data-ttu-id="dfb42-129">将 `audienceUriMode` 的 `<issuedTokenAuthentication>` 属性设置为 <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> 或 <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>。</span><span class="sxs-lookup"><span data-stu-id="dfb42-129">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
- <span data-ttu-id="dfb42-130">将有效 URI 添加到此集合，以指定有效 URI 集。</span><span class="sxs-lookup"><span data-stu-id="dfb42-130">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="dfb42-131">有关详细信息，请参阅 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 。</span><span class="sxs-lookup"><span data-stu-id="dfb42-131">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="dfb42-132">有关使用此配置元素的详细信息, 请[参阅如何:在联合身份验证服务](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)上配置凭据。</span><span class="sxs-lookup"><span data-stu-id="dfb42-132">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb42-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfb42-133">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="dfb42-134">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="dfb42-134">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="dfb42-135">\<add></span><span class="sxs-lookup"><span data-stu-id="dfb42-135">\<add></span></span>](add-of-allowedaudienceuris.md)
- [<span data-ttu-id="dfb42-136">安全行为</span><span class="sxs-lookup"><span data-stu-id="dfb42-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="dfb42-137">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="dfb42-137">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="dfb42-138">如何：在联合身份验证服务上配置凭据</span><span class="sxs-lookup"><span data-stu-id="dfb42-138">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
