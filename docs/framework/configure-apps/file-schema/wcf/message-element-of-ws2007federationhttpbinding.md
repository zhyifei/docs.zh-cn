---
title: <message> 元素 <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: f05bd90bd2e4c7e1fd606518d9e5cb8d4e5ad974
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092989"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="dd39f-102">\<消息 > 元素的\<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="dd39f-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="dd39f-103">定义消息级安全性设置[ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="dd39f-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="dd39f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dd39f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dd39f-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="dd39f-105">\<bindings></span></span>  
<span data-ttu-id="dd39f-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="dd39f-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="dd39f-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="dd39f-107">\<binding></span></span>  
<span data-ttu-id="dd39f-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="dd39f-108">\<security></span></span>  
<span data-ttu-id="dd39f-109">\<message></span><span class="sxs-lookup"><span data-stu-id="dd39f-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd39f-110">语法</span><span class="sxs-lookup"><span data-stu-id="dd39f-110">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd39f-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dd39f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dd39f-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="dd39f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd39f-113">特性</span><span class="sxs-lookup"><span data-stu-id="dd39f-113">Attributes</span></span>  
  
|<span data-ttu-id="dd39f-114">特性</span><span class="sxs-lookup"><span data-stu-id="dd39f-114">Attribute</span></span>|<span data-ttu-id="dd39f-115">描述</span><span class="sxs-lookup"><span data-stu-id="dd39f-115">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="dd39f-116">可选。</span><span class="sxs-lookup"><span data-stu-id="dd39f-116">Optional.</span></span> <span data-ttu-id="dd39f-117">设置消息加密、签名和密钥包装算法。</span><span class="sxs-lookup"><span data-stu-id="dd39f-117">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="dd39f-118">算法和密钥大小由 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 类确定。</span><span class="sxs-lookup"><span data-stu-id="dd39f-118">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="dd39f-119">这些算法映射到安全策略语言 (WS-SecurityPolicy) 规范中指定的算法。</span><span class="sxs-lookup"><span data-stu-id="dd39f-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="dd39f-120">有关可能的值，请参见下表。</span><span class="sxs-lookup"><span data-stu-id="dd39f-120">See the following table for possible values.</span></span> <span data-ttu-id="dd39f-121">默认值为 Basic256。</span><span class="sxs-lookup"><span data-stu-id="dd39f-121">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="dd39f-122">指定要颁发的密钥类型。</span><span class="sxs-lookup"><span data-stu-id="dd39f-122">Specifies the type of key to be issued.</span></span> <span data-ttu-id="dd39f-123">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="dd39f-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dd39f-124">-   SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="dd39f-124">-   SymmetricKey</span></span><br /><span data-ttu-id="dd39f-125">-   PublicKey</span><span class="sxs-lookup"><span data-stu-id="dd39f-125">-   PublicKey</span></span><br /><span data-ttu-id="dd39f-126">-   BearerKey</span><span class="sxs-lookup"><span data-stu-id="dd39f-126">-   BearerKey</span></span><br /><br /> <span data-ttu-id="dd39f-127">默认值为 SymmetricKey。</span><span class="sxs-lookup"><span data-stu-id="dd39f-127">The default is SymmetricKey.</span></span> <span data-ttu-id="dd39f-128">此属性的类型为 <xref:System.IdentityModel.Tokens.SecurityKeyType>。</span><span class="sxs-lookup"><span data-stu-id="dd39f-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="dd39f-129">一个 URI，指定要颁发的令牌的类型。</span><span class="sxs-lookup"><span data-stu-id="dd39f-129">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="dd39f-130">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="dd39f-130">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="dd39f-131">一个值，指定是否应在协商过程中交换服务凭据，或者是否可在带外使用服务凭据。</span><span class="sxs-lookup"><span data-stu-id="dd39f-131">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="dd39f-132">默认值为 `true`，这意味着对服务凭据进行协商。</span><span class="sxs-lookup"><span data-stu-id="dd39f-132">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="dd39f-133">algorithmSuite 属性</span><span class="sxs-lookup"><span data-stu-id="dd39f-133">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="dd39f-134">“值”</span><span class="sxs-lookup"><span data-stu-id="dd39f-134">Value</span></span>|<span data-ttu-id="dd39f-135">描述</span><span class="sxs-lookup"><span data-stu-id="dd39f-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dd39f-136">Basic128</span><span class="sxs-lookup"><span data-stu-id="dd39f-136">Basic128</span></span>|<span data-ttu-id="dd39f-137">使用 Aes128 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="dd39f-137">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-138">Basic192</span><span class="sxs-lookup"><span data-stu-id="dd39f-138">Basic192</span></span>|<span data-ttu-id="dd39f-139">使用 Aes192 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="dd39f-139">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-140">Basic256</span><span class="sxs-lookup"><span data-stu-id="dd39f-140">Basic256</span></span>|<span data-ttu-id="dd39f-141">使用 Aes256 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="dd39f-141">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-142">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd39f-142">Basic256Rsa15</span></span>|<span data-ttu-id="dd39f-143">对消息加密使用 Aes256，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="dd39f-143">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-144">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd39f-144">Basic192Rsa15</span></span>|<span data-ttu-id="dd39f-145">对消息加密使用 Aes192，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="dd39f-145">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-146">TripleDes</span><span class="sxs-lookup"><span data-stu-id="dd39f-146">TripleDes</span></span>|<span data-ttu-id="dd39f-147">使用 TripleDes 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="dd39f-147">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-148">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd39f-148">Basic128Rsa15</span></span>|<span data-ttu-id="dd39f-149">对消息加密使用 Aes128，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="dd39f-149">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-150">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="dd39f-150">TripleDesRsa15</span></span>|<span data-ttu-id="dd39f-151">使用 TripleDes 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="dd39f-151">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-152">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="dd39f-152">Basic128Sha256</span></span>|<span data-ttu-id="dd39f-153">对消息加密使用 Aes256，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="dd39f-153">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-154">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="dd39f-154">Basic192Sha256</span></span>|<span data-ttu-id="dd39f-155">对消息加密使用 Aes192，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="dd39f-155">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-156">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="dd39f-156">Basic256Sha256</span></span>|<span data-ttu-id="dd39f-157">对消息加密使用 Aes256，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="dd39f-157">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-158">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="dd39f-158">TripleDesSha256</span></span>|<span data-ttu-id="dd39f-159">对消息加密使用 TripleDes，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="dd39f-159">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-160">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd39f-160">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="dd39f-161">对消息加密使用 Aes128，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="dd39f-161">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-162">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd39f-162">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="dd39f-163">对消息加密使用 Aes192，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="dd39f-163">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-164">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd39f-164">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="dd39f-165">对消息加密使用 Aes256，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="dd39f-165">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="dd39f-166">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="dd39f-166">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="dd39f-167">对消息加密使用 TripleDes，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="dd39f-167">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd39f-168">子元素</span><span class="sxs-lookup"><span data-stu-id="dd39f-168">Child Elements</span></span>  
  
|<span data-ttu-id="dd39f-169">元素</span><span class="sxs-lookup"><span data-stu-id="dd39f-169">Element</span></span>|<span data-ttu-id="dd39f-170">描述</span><span class="sxs-lookup"><span data-stu-id="dd39f-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd39f-171">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="dd39f-171">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="dd39f-172">指定此绑定的声明类型集合。</span><span class="sxs-lookup"><span data-stu-id="dd39f-172">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="dd39f-173">每个元素的类型都为 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="dd39f-173">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="dd39f-174">\<issuer></span><span class="sxs-lookup"><span data-stu-id="dd39f-174">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="dd39f-175">指定颁发安全令牌的终结点。</span><span class="sxs-lookup"><span data-stu-id="dd39f-175">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="dd39f-176">此元素的类型为 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>。</span><span class="sxs-lookup"><span data-stu-id="dd39f-176">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="dd39f-177">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="dd39f-177">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="dd39f-178">指定颁发者的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="dd39f-178">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="dd39f-179">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="dd39f-179">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="dd39f-180">令牌请求参数的集合。</span><span class="sxs-lookup"><span data-stu-id="dd39f-180">A collection of token request parameters.</span></span> <span data-ttu-id="dd39f-181">每个参数都是一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="dd39f-181">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dd39f-182">父元素</span><span class="sxs-lookup"><span data-stu-id="dd39f-182">Parent Elements</span></span>  
  
|<span data-ttu-id="dd39f-183">元素</span><span class="sxs-lookup"><span data-stu-id="dd39f-183">Element</span></span>|<span data-ttu-id="dd39f-184">描述</span><span class="sxs-lookup"><span data-stu-id="dd39f-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd39f-185">\<security></span><span class="sxs-lookup"><span data-stu-id="dd39f-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="dd39f-186">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="dd39f-186">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd39f-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd39f-187">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="dd39f-188">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="dd39f-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="dd39f-189">绑定</span><span class="sxs-lookup"><span data-stu-id="dd39f-189">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="dd39f-190">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="dd39f-190">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="dd39f-191">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="dd39f-191">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="dd39f-192">\<binding></span><span class="sxs-lookup"><span data-stu-id="dd39f-192">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
