---
title: <message>的元素<wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: e26e1f94fb38e0654fd0bc9f06c6096a488bccfe
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400286"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="a464b-102">\<wsFederationHttpBinding > 的\<消息 > 元素</span><span class="sxs-lookup"><span data-stu-id="a464b-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="a464b-103">定义[ \<wsFederationHttpBinding >](wsfederationhttpbinding.md)的消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="a464b-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="a464b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a464b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a464b-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a464b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a464b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a464b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a464b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a464b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="a464b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="a464b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a464b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a464b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="a464b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<消息 >**</span><span class="sxs-lookup"><span data-stu-id="a464b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a464b-111">语法</span><span class="sxs-lookup"><span data-stu-id="a464b-111">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
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
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a464b-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a464b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a464b-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a464b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a464b-114">特性</span><span class="sxs-lookup"><span data-stu-id="a464b-114">Attributes</span></span>  
  
|<span data-ttu-id="a464b-115">特性</span><span class="sxs-lookup"><span data-stu-id="a464b-115">Attribute</span></span>|<span data-ttu-id="a464b-116">描述</span><span class="sxs-lookup"><span data-stu-id="a464b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a464b-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="a464b-117">algorithmSuite</span></span>|<span data-ttu-id="a464b-118">设置消息加密和密钥包装算法。</span><span class="sxs-lookup"><span data-stu-id="a464b-118">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="a464b-119">有关此属性的有效值，请参见“algorithmSuite 属性”表。</span><span class="sxs-lookup"><span data-stu-id="a464b-119">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="a464b-120">默认值为 `Basic256`。</span><span class="sxs-lookup"><span data-stu-id="a464b-120">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="a464b-121">此属性的类型为 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>。</span><span class="sxs-lookup"><span data-stu-id="a464b-121">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="a464b-122">这些算法映射到安全策略语言 (WS-SecurityPolicy) 规范中指定的算法。</span><span class="sxs-lookup"><span data-stu-id="a464b-122">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="a464b-123">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="a464b-123">issuedKeyType</span></span>|<span data-ttu-id="a464b-124">指定要颁发的密钥类型。</span><span class="sxs-lookup"><span data-stu-id="a464b-124">Specifies the type of key to be issued.</span></span> <span data-ttu-id="a464b-125">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="a464b-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a464b-126">-   SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="a464b-126">-   SymmetricKey</span></span><br /><span data-ttu-id="a464b-127">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="a464b-127">-   PublicKey</span></span><br /><br /> <span data-ttu-id="a464b-128">默认值为 `SymmetricKey`。</span><span class="sxs-lookup"><span data-stu-id="a464b-128">The default is `SymmetricKey`.</span></span> <span data-ttu-id="a464b-129">此属性的类型为 <xref:System.IdentityModel.Tokens.SecurityKeyType>。</span><span class="sxs-lookup"><span data-stu-id="a464b-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="a464b-130">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="a464b-130">issuedTokenType</span></span>|<span data-ttu-id="a464b-131">一个字符串，它所包含的 URI 指定要颁发的令牌的类型。</span><span class="sxs-lookup"><span data-stu-id="a464b-131">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="a464b-132">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="a464b-132">The default is `null`.</span></span>|  
|<span data-ttu-id="a464b-133">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="a464b-133">negotiateServiceCredential</span></span>|<span data-ttu-id="a464b-134">一个布尔值，指定是否应在协商过程中交换服务凭据，或者是否可在带外使用服务凭据。</span><span class="sxs-lookup"><span data-stu-id="a464b-134">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="a464b-135">默认值为 `true`，这意味着对服务凭据进行协商。</span><span class="sxs-lookup"><span data-stu-id="a464b-135">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="a464b-136">algorithmSuite 属性</span><span class="sxs-lookup"><span data-stu-id="a464b-136">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="a464b-137">值</span><span class="sxs-lookup"><span data-stu-id="a464b-137">Value</span></span>|<span data-ttu-id="a464b-138">描述</span><span class="sxs-lookup"><span data-stu-id="a464b-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a464b-139">Basic128</span><span class="sxs-lookup"><span data-stu-id="a464b-139">Basic128</span></span>|<span data-ttu-id="a464b-140">使用 Basic128 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a464b-140">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a464b-141">Basic192</span><span class="sxs-lookup"><span data-stu-id="a464b-141">Basic192</span></span>|<span data-ttu-id="a464b-142">使用 Basic192 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a464b-142">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a464b-143">Basic256</span><span class="sxs-lookup"><span data-stu-id="a464b-143">Basic256</span></span>|<span data-ttu-id="a464b-144">使用 Basic256 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a464b-144">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a464b-145">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a464b-145">Basic256Rsa15</span></span>|<span data-ttu-id="a464b-146">对消息加密使用 Basic256，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a464b-146">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a464b-147">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="a464b-147">Basic192Rsa15</span></span>|<span data-ttu-id="a464b-148">对消息加密使用 Basic192，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a464b-148">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a464b-149">TripleDes</span><span class="sxs-lookup"><span data-stu-id="a464b-149">TripleDes</span></span>|<span data-ttu-id="a464b-150">使用 TripleDes 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a464b-150">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a464b-151">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="a464b-151">Basic128Rsa15</span></span>|<span data-ttu-id="a464b-152">对消息加密使用 Basic128，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a464b-152">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a464b-153">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="a464b-153">TripleDesRsa15</span></span>|<span data-ttu-id="a464b-154">使用 TripleDes 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a464b-154">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a464b-155">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="a464b-155">Basic128Sha256</span></span>|<span data-ttu-id="a464b-156">对消息加密使用 Basic128，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a464b-156">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a464b-157">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="a464b-157">Basic192Sha256</span></span>|<span data-ttu-id="a464b-158">对消息加密使用 Basic192，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a464b-158">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a464b-159">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="a464b-159">Basic256Sha256</span></span>|<span data-ttu-id="a464b-160">对消息加密使用 Basic256，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a464b-160">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a464b-161">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="a464b-161">TripleDesSha256</span></span>|<span data-ttu-id="a464b-162">对消息加密使用 TripleDes，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a464b-162">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a464b-163">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a464b-163">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="a464b-164">对消息加密使用 Basic128，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a464b-164">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a464b-165">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a464b-165">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="a464b-166">对消息加密使用 Aes192，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a464b-166">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a464b-167">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a464b-167">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="a464b-168">对消息加密使用 Basic256，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a464b-168">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a464b-169">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a464b-169">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="a464b-170">对消息加密使用 TripleDes，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a464b-170">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a464b-171">子元素</span><span class="sxs-lookup"><span data-stu-id="a464b-171">Child Elements</span></span>  
  
|<span data-ttu-id="a464b-172">元素</span><span class="sxs-lookup"><span data-stu-id="a464b-172">Element</span></span>|<span data-ttu-id="a464b-173">描述</span><span class="sxs-lookup"><span data-stu-id="a464b-173">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a464b-174">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="a464b-174">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="a464b-175">指定此绑定的声明类型集合。</span><span class="sxs-lookup"><span data-stu-id="a464b-175">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="a464b-176">每个元素的类型都为 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="a464b-176">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="a464b-177">issuer</span><span class="sxs-lookup"><span data-stu-id="a464b-177">issuer</span></span>|<span data-ttu-id="a464b-178">指定颁发安全令牌的终结点。</span><span class="sxs-lookup"><span data-stu-id="a464b-178">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="a464b-179">此元素的类型为 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>。</span><span class="sxs-lookup"><span data-stu-id="a464b-179">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="a464b-180">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="a464b-180">issuerMetadata</span></span>|<span data-ttu-id="a464b-181">指定颁发者的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="a464b-181">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="a464b-182">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="a464b-182">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="a464b-183">令牌请求参数的集合。</span><span class="sxs-lookup"><span data-stu-id="a464b-183">A collection of token request parameters.</span></span> <span data-ttu-id="a464b-184">每个参数都是一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="a464b-184">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a464b-185">父元素</span><span class="sxs-lookup"><span data-stu-id="a464b-185">Parent Elements</span></span>  
  
|<span data-ttu-id="a464b-186">元素</span><span class="sxs-lookup"><span data-stu-id="a464b-186">Element</span></span>|<span data-ttu-id="a464b-187">描述</span><span class="sxs-lookup"><span data-stu-id="a464b-187">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a464b-188">\<security></span><span class="sxs-lookup"><span data-stu-id="a464b-188">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="a464b-189">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="a464b-189">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a464b-190">请参阅</span><span class="sxs-lookup"><span data-stu-id="a464b-190">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="a464b-191">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="a464b-191">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a464b-192">绑定</span><span class="sxs-lookup"><span data-stu-id="a464b-192">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a464b-193">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="a464b-193">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a464b-194">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="a464b-194">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a464b-195">\<binding></span><span class="sxs-lookup"><span data-stu-id="a464b-195">\<binding></span></span>](../../../misc/binding.md)
