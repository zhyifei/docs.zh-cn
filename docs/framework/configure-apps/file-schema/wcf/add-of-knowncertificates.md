---
title: <add> 的 <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 29b067e6ec20992084f9ab3bab087222bdd56da2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400612"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="39da5-102">\<添加 knownCertificates > \<的 ></span><span class="sxs-lookup"><span data-stu-id="39da5-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="39da5-103">向已知证书集合添加 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="39da5-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
<span data-ttu-id="39da5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="39da5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="39da5-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="39da5-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="39da5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="39da5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="39da5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="39da5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="39da5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="39da5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="39da5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="39da5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="39da5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenAuthentication >** ](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="39da5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="39da5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<knownCertificates >** ](knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="39da5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)</span></span>\
<span data-ttu-id="39da5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="39da5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39da5-113">语法</span><span class="sxs-lookup"><span data-stu-id="39da5-113">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39da5-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="39da5-114">Attributes and Elements</span></span>  
 <span data-ttu-id="39da5-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="39da5-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39da5-116">特性</span><span class="sxs-lookup"><span data-stu-id="39da5-116">Attributes</span></span>  
  
|<span data-ttu-id="39da5-117">特性</span><span class="sxs-lookup"><span data-stu-id="39da5-117">Attribute</span></span>|<span data-ttu-id="39da5-118">描述</span><span class="sxs-lookup"><span data-stu-id="39da5-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39da5-119">findValue</span><span class="sxs-lookup"><span data-stu-id="39da5-119">findValue</span></span>|<span data-ttu-id="39da5-120">字符串。</span><span class="sxs-lookup"><span data-stu-id="39da5-120">String.</span></span> <span data-ttu-id="39da5-121">要搜索的值。</span><span class="sxs-lookup"><span data-stu-id="39da5-121">The value to search for.</span></span>|  
|<span data-ttu-id="39da5-122">storeLocation</span><span class="sxs-lookup"><span data-stu-id="39da5-122">storeLocation</span></span>|<span data-ttu-id="39da5-123">枚举。</span><span class="sxs-lookup"><span data-stu-id="39da5-123">Enumeration.</span></span> <span data-ttu-id="39da5-124">要搜索的两个存储位置之一。</span><span class="sxs-lookup"><span data-stu-id="39da5-124">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="39da5-125">storeName</span><span class="sxs-lookup"><span data-stu-id="39da5-125">storeName</span></span>|<span data-ttu-id="39da5-126">枚举。</span><span class="sxs-lookup"><span data-stu-id="39da5-126">Enumeration.</span></span> <span data-ttu-id="39da5-127">要搜索的系统存储之一。</span><span class="sxs-lookup"><span data-stu-id="39da5-127">One of the system stores to search.</span></span>|  
|<span data-ttu-id="39da5-128">x509FindType</span><span class="sxs-lookup"><span data-stu-id="39da5-128">x509FindType</span></span>|<span data-ttu-id="39da5-129">枚举。</span><span class="sxs-lookup"><span data-stu-id="39da5-129">Enumeration.</span></span> <span data-ttu-id="39da5-130">要搜索的证书字段之一。</span><span class="sxs-lookup"><span data-stu-id="39da5-130">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="39da5-131">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="39da5-131">findValue Attribute</span></span>  
  
|<span data-ttu-id="39da5-132">值</span><span class="sxs-lookup"><span data-stu-id="39da5-132">Value</span></span>|<span data-ttu-id="39da5-133">描述</span><span class="sxs-lookup"><span data-stu-id="39da5-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="39da5-134">String</span><span class="sxs-lookup"><span data-stu-id="39da5-134">String</span></span>|<span data-ttu-id="39da5-135">值取决于搜索的字段（由 X509FindType 属性指定）。</span><span class="sxs-lookup"><span data-stu-id="39da5-135">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="39da5-136">例如，如果搜索指纹，则此值必须为十六进制数字字符串。</span><span class="sxs-lookup"><span data-stu-id="39da5-136">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="39da5-137">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="39da5-137">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="39da5-138">值</span><span class="sxs-lookup"><span data-stu-id="39da5-138">Value</span></span>|<span data-ttu-id="39da5-139">描述</span><span class="sxs-lookup"><span data-stu-id="39da5-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="39da5-140">枚举</span><span class="sxs-lookup"><span data-stu-id="39da5-140">Enumeration</span></span>|<span data-ttu-id="39da5-141">值包括：FindByThumbprint、Findbysubjectname)、FindBySubjectDistinguishedName、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="39da5-141">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="39da5-142">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="39da5-142">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="39da5-143">值</span><span class="sxs-lookup"><span data-stu-id="39da5-143">Value</span></span>|<span data-ttu-id="39da5-144">描述</span><span class="sxs-lookup"><span data-stu-id="39da5-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="39da5-145">枚举</span><span class="sxs-lookup"><span data-stu-id="39da5-145">Enumeration</span></span>|<span data-ttu-id="39da5-146">CurrentUser 或 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="39da5-146">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="39da5-147">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="39da5-147">storeName Attribute</span></span>  
  
|<span data-ttu-id="39da5-148">值</span><span class="sxs-lookup"><span data-stu-id="39da5-148">Value</span></span>|<span data-ttu-id="39da5-149">描述</span><span class="sxs-lookup"><span data-stu-id="39da5-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="39da5-150">枚举</span><span class="sxs-lookup"><span data-stu-id="39da5-150">Enumeration</span></span>|<span data-ttu-id="39da5-151">值包括：通讯簿、AuthRoot、CertificateAuthority、不允许、My、Root、TrustedPeople 和 TrustedPublisher。</span><span class="sxs-lookup"><span data-stu-id="39da5-151">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39da5-152">子元素</span><span class="sxs-lookup"><span data-stu-id="39da5-152">Child Elements</span></span>  
 <span data-ttu-id="39da5-153">无。</span><span class="sxs-lookup"><span data-stu-id="39da5-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39da5-154">父元素</span><span class="sxs-lookup"><span data-stu-id="39da5-154">Parent Elements</span></span>  
  
|<span data-ttu-id="39da5-155">元素</span><span class="sxs-lookup"><span data-stu-id="39da5-155">Element</span></span>|<span data-ttu-id="39da5-156">描述</span><span class="sxs-lookup"><span data-stu-id="39da5-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39da5-157">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="39da5-157">\<knownCertificates></span></span>](knowncertificates.md)|<span data-ttu-id="39da5-158">表示一个 X.509 证书集合，这些证书由安全令牌服务 (STS) 提供以用于验证安全令牌。</span><span class="sxs-lookup"><span data-stu-id="39da5-158">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39da5-159">备注</span><span class="sxs-lookup"><span data-stu-id="39da5-159">Remarks</span></span>  
 <span data-ttu-id="39da5-160">颁发的令牌方案包含三个阶段。</span><span class="sxs-lookup"><span data-stu-id="39da5-160">The issued token scenario has three stages.</span></span> <span data-ttu-id="39da5-161">在第一阶段中，尝试访问服务的客户端被称为 "*安全令牌服务*"。</span><span class="sxs-lookup"><span data-stu-id="39da5-161">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="39da5-162">然后，安全令牌服务对该客户端进行身份验证，随后向该客户端颁发一个令牌（通常是一个安全断言标记语言 (SAML) 令牌）。</span><span class="sxs-lookup"><span data-stu-id="39da5-162">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="39da5-163">接下来，客户端携带此令牌返回服务。</span><span class="sxs-lookup"><span data-stu-id="39da5-163">The client then returns to the service with the token.</span></span> <span data-ttu-id="39da5-164">服务检查该令牌，以获取使其可以对该令牌并进而对该客户端进行身份验证的数据。</span><span class="sxs-lookup"><span data-stu-id="39da5-164">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="39da5-165">若要对令牌进行身份验证，安全令牌服务所使用的证书必须为该服务所知。</span><span class="sxs-lookup"><span data-stu-id="39da5-165">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="39da5-166">IssuedTokenAuthentication > 元素是适用于任何此类安全令牌服务证书的存储库。 [ \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="39da5-166">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="39da5-167">若要添加证书，请使用[ \<knownCertificates >](knowncertificates.md)。</span><span class="sxs-lookup"><span data-stu-id="39da5-167">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="39da5-168">为每个证书插入[ \<add > 元素 knownCertificates > 元素，如下面的示例中所示。 \<](add-of-knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="39da5-168">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 <span data-ttu-id="39da5-169">默认情况下，必须从安全令牌服务那里获取证书。</span><span class="sxs-lookup"><span data-stu-id="39da5-169">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="39da5-170">这些“已知的”证书可以确保只有合法的客户端才能访问服务。</span><span class="sxs-lookup"><span data-stu-id="39da5-170">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="39da5-171">若要查看客户端通过联合服务进行身份验证所需的条件，以及有关使用此配置元素的详细信息，请[参阅如何：在联合身份验证服务](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)上配置凭据。</span><span class="sxs-lookup"><span data-stu-id="39da5-171">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="39da5-172">有关联合方案的详细信息，请参阅[联合和颁发的令牌](../../../wcf/feature-details/federation-and-issued-tokens.md)。</span><span class="sxs-lookup"><span data-stu-id="39da5-172">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="39da5-173">示例</span><span class="sxs-lookup"><span data-stu-id="39da5-173">Example</span></span>  
 <span data-ttu-id="39da5-174">下面的示例将证书添加到任意 STS 证书的存储库。</span><span class="sxs-lookup"><span data-stu-id="39da5-174">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <serviceCredentials>
      <issuedTokenAuthentication>
        <knownCertificates>
          <add findValue="www.contoso.com"
               storeLocation="LocalMachine"
               storeName="CertificateAuthority"
               x509FindType="FindByIssuerName" />
        </knownCertificates>
      </issuedTokenAuthentication>
    </serviceCredentials>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="39da5-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="39da5-175">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="39da5-176">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="39da5-176">\<knownCertificates></span></span>](knowncertificates.md)
- [<span data-ttu-id="39da5-177">使用证书</span><span class="sxs-lookup"><span data-stu-id="39da5-177">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="39da5-178">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="39da5-178">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="39da5-179">如何：在联合身份验证服务上配置凭据</span><span class="sxs-lookup"><span data-stu-id="39da5-179">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="39da5-180">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="39da5-180">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
