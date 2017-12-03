---
title: '&lt;knownCertificates&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9f62a43f1f8d3d025f62efca341c35e4af590abd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltknowncertificatesgt"></a><span data-ttu-id="0b05e-102">&lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="0b05e-102">&lt;knownCertificates&gt;</span></span>
<span data-ttu-id="0b05e-103">表示所提供的 X.509 证书的集合，这些证书用于对安全令牌服务 (STS) 颁发的安全凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0b05e-103">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="0b05e-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0b05e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0b05e-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="0b05e-105">\<behaviors></span></span>  
<span data-ttu-id="0b05e-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0b05e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0b05e-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="0b05e-107">\<behavior></span></span>  
<span data-ttu-id="0b05e-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="0b05e-108">\<serviceCredentials></span></span>  
<span data-ttu-id="0b05e-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="0b05e-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="0b05e-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="0b05e-110">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b05e-111">语法</span><span class="sxs-lookup"><span data-stu-id="0b05e-111">Syntax</span></span>  
  
```xml  
<knownCertificates>   
      <add findValue="String"  
         storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
           x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b05e-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0b05e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0b05e-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0b05e-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b05e-114">特性</span><span class="sxs-lookup"><span data-stu-id="0b05e-114">Attributes</span></span>  
 <span data-ttu-id="0b05e-115">无。</span><span class="sxs-lookup"><span data-stu-id="0b05e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0b05e-116">子元素</span><span class="sxs-lookup"><span data-stu-id="0b05e-116">Child Elements</span></span>  
  
|<span data-ttu-id="0b05e-117">元素</span><span class="sxs-lookup"><span data-stu-id="0b05e-117">Element</span></span>|<span data-ttu-id="0b05e-118">说明</span><span class="sxs-lookup"><span data-stu-id="0b05e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b05e-119">\<add></span><span class="sxs-lookup"><span data-stu-id="0b05e-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="0b05e-120">将一个 X.509 证书添加到集合中。</span><span class="sxs-lookup"><span data-stu-id="0b05e-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b05e-121">父元素</span><span class="sxs-lookup"><span data-stu-id="0b05e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0b05e-122">元素</span><span class="sxs-lookup"><span data-stu-id="0b05e-122">Element</span></span>|<span data-ttu-id="0b05e-123">描述</span><span class="sxs-lookup"><span data-stu-id="0b05e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b05e-124">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="0b05e-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="0b05e-125">将颁发的令牌指定为服务凭据。</span><span class="sxs-lookup"><span data-stu-id="0b05e-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b05e-126">备注</span><span class="sxs-lookup"><span data-stu-id="0b05e-126">Remarks</span></span>  
 <span data-ttu-id="0b05e-127">颁发的令牌方案包含三个阶段。</span><span class="sxs-lookup"><span data-stu-id="0b05e-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="0b05e-128">在第一个阶段中，尝试访问服务的客户端被指引到*安全令牌服务*。</span><span class="sxs-lookup"><span data-stu-id="0b05e-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="0b05e-129">然后，安全令牌服务对该客户端进行身份验证，随后向该客户端颁发一个令牌（通常是一个安全断言标记语言 (SAML) 令牌）。</span><span class="sxs-lookup"><span data-stu-id="0b05e-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="0b05e-130">接下来，客户端携带此令牌返回服务。</span><span class="sxs-lookup"><span data-stu-id="0b05e-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="0b05e-131">服务检查该令牌，以获取使其可以对该令牌并进而对该客户端进行身份验证的数据。</span><span class="sxs-lookup"><span data-stu-id="0b05e-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="0b05e-132">若要对令牌进行身份验证，安全令牌服务所使用的证书必须为该服务所知。</span><span class="sxs-lookup"><span data-stu-id="0b05e-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="0b05e-133">[ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)元素是任何此类安全令牌服务证书的存储库。</span><span class="sxs-lookup"><span data-stu-id="0b05e-133">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="0b05e-134">若要添加证书，请使用[ \<knownCertificates > 元素](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)。</span><span class="sxs-lookup"><span data-stu-id="0b05e-134">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="0b05e-135">插入[\<添加 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)为每个证书，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="0b05e-135">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="0b05e-136">默认情况下，必须从安全令牌服务那里获取证书。</span><span class="sxs-lookup"><span data-stu-id="0b05e-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="0b05e-137">这些“已知的”证书可以确保只有合法的客户端才能访问服务。</span><span class="sxs-lookup"><span data-stu-id="0b05e-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="0b05e-138">若要查看条件所需的客户端进行身份验证由联合的服务，以及使用此配置元素的详细信息，请参阅[如何： 在联合身份验证服务上配置凭据](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)。</span><span class="sxs-lookup"><span data-stu-id="0b05e-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="0b05e-139">有关联合方案的详细信息，请参阅[联合身份验证和颁发令牌](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)。</span><span class="sxs-lookup"><span data-stu-id="0b05e-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="0b05e-140">有关演示如何在配置中的在集合中填入示例，请参阅[\<添加 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)。</span><span class="sxs-lookup"><span data-stu-id="0b05e-140">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b05e-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b05e-141">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="0b05e-142">\<add></span><span class="sxs-lookup"><span data-stu-id="0b05e-142">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="0b05e-143">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="0b05e-143">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="0b05e-144">安全行为</span><span class="sxs-lookup"><span data-stu-id="0b05e-144">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="0b05e-145">如何： 在联合身份验证服务上配置凭据</span><span class="sxs-lookup"><span data-stu-id="0b05e-145">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="0b05e-146">使用证书</span><span class="sxs-lookup"><span data-stu-id="0b05e-146">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="0b05e-147">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="0b05e-147">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="0b05e-148">\<add></span><span class="sxs-lookup"><span data-stu-id="0b05e-148">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="0b05e-149">保护服务和客户端</span><span class="sxs-lookup"><span data-stu-id="0b05e-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
