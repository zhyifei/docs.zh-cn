---
title: <ws2007FederationHttpBinding> 的 <message> 元素
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: dde763687dbc62d6fb342a21a4c614208f28d7e8
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738998"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="c2923-102">\<ws2007FederationHttpBinding 的 \<message > 元素 ></span><span class="sxs-lookup"><span data-stu-id="c2923-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="c2923-103">定义[\<ws2007FederationHttpBinding >](ws2007federationhttpbinding.md)元素的消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="c2923-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="c2923-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c2923-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c2923-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="c2923-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c2923-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c2923-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c2923-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007FederationHttpBinding >** ](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="c2923-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="c2923-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="c2923-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c2923-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](security-element-of-ws2007federationhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="c2923-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="c2923-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**消息 >**</span><span class="sxs-lookup"><span data-stu-id="c2923-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2923-111">语法</span><span class="sxs-lookup"><span data-stu-id="c2923-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2923-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c2923-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c2923-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c2923-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2923-114">特性</span><span class="sxs-lookup"><span data-stu-id="c2923-114">Attributes</span></span>  
  
|<span data-ttu-id="c2923-115">特性</span><span class="sxs-lookup"><span data-stu-id="c2923-115">Attribute</span></span>|<span data-ttu-id="c2923-116">描述</span><span class="sxs-lookup"><span data-stu-id="c2923-116">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="c2923-117">可选。</span><span class="sxs-lookup"><span data-stu-id="c2923-117">Optional.</span></span> <span data-ttu-id="c2923-118">设置消息加密、签名和密钥包装算法。</span><span class="sxs-lookup"><span data-stu-id="c2923-118">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="c2923-119">算法和密钥大小由 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 类确定。</span><span class="sxs-lookup"><span data-stu-id="c2923-119">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="c2923-120">这些算法映射到安全策略语言 (WS-SecurityPolicy) 规范中指定的算法。</span><span class="sxs-lookup"><span data-stu-id="c2923-120">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="c2923-121">有关可能的值，请参见下表。</span><span class="sxs-lookup"><span data-stu-id="c2923-121">See the following table for possible values.</span></span> <span data-ttu-id="c2923-122">默认值为 Basic256。</span><span class="sxs-lookup"><span data-stu-id="c2923-122">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="c2923-123">指定要颁发的密钥类型。</span><span class="sxs-lookup"><span data-stu-id="c2923-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="c2923-124">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c2923-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c2923-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="c2923-125">-   SymmetricKey</span></span><br /><span data-ttu-id="c2923-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="c2923-126">-   PublicKey</span></span><br /><span data-ttu-id="c2923-127">-为 bearerkey 并且</span><span class="sxs-lookup"><span data-stu-id="c2923-127">-   BearerKey</span></span><br /><br /> <span data-ttu-id="c2923-128">默认值为 SymmetricKey。</span><span class="sxs-lookup"><span data-stu-id="c2923-128">The default is SymmetricKey.</span></span> <span data-ttu-id="c2923-129">此属性的类型为 <xref:System.IdentityModel.Tokens.SecurityKeyType>。</span><span class="sxs-lookup"><span data-stu-id="c2923-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="c2923-130">一个 URI，指定要颁发的令牌的类型。</span><span class="sxs-lookup"><span data-stu-id="c2923-130">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="c2923-131">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="c2923-131">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="c2923-132">一个值，指定是否应在协商过程中交换服务凭据，或者是否可在带外使用服务凭据。</span><span class="sxs-lookup"><span data-stu-id="c2923-132">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="c2923-133">默认值为 `true`，这意味着对服务凭据进行协商。</span><span class="sxs-lookup"><span data-stu-id="c2923-133">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="c2923-134">algorithmSuite 属性</span><span class="sxs-lookup"><span data-stu-id="c2923-134">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="c2923-135">“值”</span><span class="sxs-lookup"><span data-stu-id="c2923-135">Value</span></span>|<span data-ttu-id="c2923-136">描述</span><span class="sxs-lookup"><span data-stu-id="c2923-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c2923-137">Basic128</span><span class="sxs-lookup"><span data-stu-id="c2923-137">Basic128</span></span>|<span data-ttu-id="c2923-138">使用 Aes128 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="c2923-138">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="c2923-139">Basic192</span><span class="sxs-lookup"><span data-stu-id="c2923-139">Basic192</span></span>|<span data-ttu-id="c2923-140">使用 Aes192 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="c2923-140">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="c2923-141">Basic256</span><span class="sxs-lookup"><span data-stu-id="c2923-141">Basic256</span></span>|<span data-ttu-id="c2923-142">使用 Aes256 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="c2923-142">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="c2923-143">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="c2923-143">Basic256Rsa15</span></span>|<span data-ttu-id="c2923-144">对消息加密使用 Aes256，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="c2923-144">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="c2923-145">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="c2923-145">Basic192Rsa15</span></span>|<span data-ttu-id="c2923-146">对消息加密使用 Aes192，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="c2923-146">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="c2923-147">TripleDes</span><span class="sxs-lookup"><span data-stu-id="c2923-147">TripleDes</span></span>|<span data-ttu-id="c2923-148">使用 TripleDes 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="c2923-148">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="c2923-149">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="c2923-149">Basic128Rsa15</span></span>|<span data-ttu-id="c2923-150">对消息加密使用 Aes128，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="c2923-150">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="c2923-151">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="c2923-151">TripleDesRsa15</span></span>|<span data-ttu-id="c2923-152">使用 TripleDes 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="c2923-152">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="c2923-153">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="c2923-153">Basic128Sha256</span></span>|<span data-ttu-id="c2923-154">对消息加密使用 Aes256，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="c2923-154">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="c2923-155">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="c2923-155">Basic192Sha256</span></span>|<span data-ttu-id="c2923-156">对消息加密使用 Aes192，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="c2923-156">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="c2923-157">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="c2923-157">Basic256Sha256</span></span>|<span data-ttu-id="c2923-158">对消息加密使用 Aes256，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="c2923-158">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="c2923-159">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="c2923-159">TripleDesSha256</span></span>|<span data-ttu-id="c2923-160">对消息加密使用 TripleDes，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="c2923-160">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="c2923-161">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="c2923-161">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="c2923-162">对消息加密使用 Aes128，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="c2923-162">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="c2923-163">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="c2923-163">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="c2923-164">对消息加密使用 Aes192，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="c2923-164">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="c2923-165">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="c2923-165">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="c2923-166">对消息加密使用 Aes256，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="c2923-166">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="c2923-167">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="c2923-167">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="c2923-168">对消息加密使用 TripleDes，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="c2923-168">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2923-169">子元素</span><span class="sxs-lookup"><span data-stu-id="c2923-169">Child Elements</span></span>  
  
|<span data-ttu-id="c2923-170">元素</span><span class="sxs-lookup"><span data-stu-id="c2923-170">Element</span></span>|<span data-ttu-id="c2923-171">描述</span><span class="sxs-lookup"><span data-stu-id="c2923-171">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2923-172">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="c2923-172">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="c2923-173">指定此绑定的声明类型集合。</span><span class="sxs-lookup"><span data-stu-id="c2923-173">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="c2923-174">每个元素的类型都为 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="c2923-174">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="c2923-175">\<颁发者 ></span><span class="sxs-lookup"><span data-stu-id="c2923-175">\<issuer></span></span>](issuer.md)|<span data-ttu-id="c2923-176">指定颁发安全令牌的终结点。</span><span class="sxs-lookup"><span data-stu-id="c2923-176">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="c2923-177">此元素的类型为 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>。</span><span class="sxs-lookup"><span data-stu-id="c2923-177">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="c2923-178">\<Issuedtokenparameters ></span><span class="sxs-lookup"><span data-stu-id="c2923-178">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="c2923-179">指定颁发者的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="c2923-179">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="c2923-180">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="c2923-180">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="c2923-181">令牌请求参数的集合。</span><span class="sxs-lookup"><span data-stu-id="c2923-181">A collection of token request parameters.</span></span> <span data-ttu-id="c2923-182">每个参数都是一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="c2923-182">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c2923-183">父元素</span><span class="sxs-lookup"><span data-stu-id="c2923-183">Parent Elements</span></span>  
  
|<span data-ttu-id="c2923-184">元素</span><span class="sxs-lookup"><span data-stu-id="c2923-184">Element</span></span>|<span data-ttu-id="c2923-185">描述</span><span class="sxs-lookup"><span data-stu-id="c2923-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2923-186">\<security ></span><span class="sxs-lookup"><span data-stu-id="c2923-186">\<security></span></span>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="c2923-187">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="c2923-187">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2923-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2923-188">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="c2923-189">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="c2923-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c2923-190">绑定</span><span class="sxs-lookup"><span data-stu-id="c2923-190">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c2923-191">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="c2923-191">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c2923-192">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="c2923-192">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c2923-193">\<binding ></span><span class="sxs-lookup"><span data-stu-id="c2923-193">\<binding></span></span>](bindings.md)
