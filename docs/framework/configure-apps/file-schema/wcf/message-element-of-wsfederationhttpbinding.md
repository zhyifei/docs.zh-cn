---
title: "&lt;wsFederationHttpBinding&gt; 的 &lt;message&gt; 元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 548e5ec5369c697d2b35723a0778ccaf95c3b535
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ltmessagegt-element-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="a1bd4-102">&lt;wsFederationHttpBinding&gt; 的 &lt;message&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="a1bd4-102">&lt;message&gt; element of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="a1bd4-103">定义的消息级安全性设置[ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="a1bd4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a1bd4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a1bd4-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a1bd4-105">\<bindings></span></span>  
<span data-ttu-id="a1bd4-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="a1bd4-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="a1bd4-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="a1bd4-107">\<binding></span></span>  
<span data-ttu-id="a1bd4-108">\<security></span><span class="sxs-lookup"><span data-stu-id="a1bd4-108">\<security></span></span>  
<span data-ttu-id="a1bd4-109">\<message></span><span class="sxs-lookup"><span data-stu-id="a1bd4-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1bd4-110">语法</span><span class="sxs-lookup"><span data-stu-id="a1bd4-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
     <binding >  
         <security>  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
                        <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
                          </headers>  
                              <identity>  
                              <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1bd4-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a1bd4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a1bd4-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1bd4-113">特性</span><span class="sxs-lookup"><span data-stu-id="a1bd4-113">Attributes</span></span>  
  
|<span data-ttu-id="a1bd4-114">特性</span><span class="sxs-lookup"><span data-stu-id="a1bd4-114">Attribute</span></span>|<span data-ttu-id="a1bd4-115">描述</span><span class="sxs-lookup"><span data-stu-id="a1bd4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1bd4-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="a1bd4-116">algorithmSuite</span></span>|<span data-ttu-id="a1bd4-117">设置消息加密和密钥包装算法。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="a1bd4-118">有关此属性的有效值，请参见“algorithmSuite 属性”表。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="a1bd4-119">默认值为 `Basic256`。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="a1bd4-120">此属性的类型为 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="a1bd4-121">这些算法映射到安全策略语言 (WS-SecurityPolicy) 规范中指定的算法。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="a1bd4-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="a1bd4-122">issuedKeyType</span></span>|<span data-ttu-id="a1bd4-123">指定要颁发的密钥类型。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="a1bd4-124">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="a1bd4-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a1bd4-125">-   SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="a1bd4-125">-   SymmetricKey</span></span><br /><span data-ttu-id="a1bd4-126">-   PublicKey</span><span class="sxs-lookup"><span data-stu-id="a1bd4-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="a1bd4-127">默认值为 `SymmetricKey`。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="a1bd4-128">此属性的类型为 <xref:System.IdentityModel.Tokens.SecurityKeyType>。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="a1bd4-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="a1bd4-129">issuedTokenType</span></span>|<span data-ttu-id="a1bd4-130">一个字符串，它所包含的 URI 指定要颁发的令牌的类型。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="a1bd4-131">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-131">The default is `null`.</span></span>|  
|<span data-ttu-id="a1bd4-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="a1bd4-132">negotiateServiceCredential</span></span>|<span data-ttu-id="a1bd4-133">一个布尔值，指定是否应在协商过程中交换服务凭据，或者是否可在带外使用服务凭据。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="a1bd4-134">默认值为 `true`，这意味着对服务凭据进行协商。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="a1bd4-135">algorithmSuite 属性</span><span class="sxs-lookup"><span data-stu-id="a1bd4-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="a1bd4-136">值</span><span class="sxs-lookup"><span data-stu-id="a1bd4-136">Value</span></span>|<span data-ttu-id="a1bd4-137">描述</span><span class="sxs-lookup"><span data-stu-id="a1bd4-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a1bd4-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="a1bd4-138">Basic128</span></span>|<span data-ttu-id="a1bd4-139">使用 Basic128 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="a1bd4-140">Basic192</span></span>|<span data-ttu-id="a1bd4-141">使用 Basic192 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="a1bd4-142">Basic256</span></span>|<span data-ttu-id="a1bd4-143">使用 Basic256 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a1bd4-144">Basic256Rsa15</span></span>|<span data-ttu-id="a1bd4-145">对消息加密使用 Basic256，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="a1bd4-146">Basic192Rsa15</span></span>|<span data-ttu-id="a1bd4-147">对消息加密使用 Basic192，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="a1bd4-148">TripleDes</span></span>|<span data-ttu-id="a1bd4-149">使用 TripleDes 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="a1bd4-150">Basic128Rsa15</span></span>|<span data-ttu-id="a1bd4-151">对消息加密使用 Basic128，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="a1bd4-152">TripleDesRsa15</span></span>|<span data-ttu-id="a1bd4-153">使用 TripleDes 加密，对消息摘要使用 Sha1，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="a1bd4-154">Basic128Sha256</span></span>|<span data-ttu-id="a1bd4-155">对消息加密使用 Basic128，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="a1bd4-156">Basic192Sha256</span></span>|<span data-ttu-id="a1bd4-157">对消息加密使用 Basic192，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="a1bd4-158">Basic256Sha256</span></span>|<span data-ttu-id="a1bd4-159">对消息加密使用 Basic256，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="a1bd4-160">TripleDesSha256</span></span>|<span data-ttu-id="a1bd4-161">对消息加密使用 TripleDes，对消息摘要使用 Sha256，对密钥包装使用 Rsa-oaep-mgf1p。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a1bd4-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="a1bd4-163">对消息加密使用 Basic128，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a1bd4-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="a1bd4-165">对消息加密使用 Aes192，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a1bd4-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="a1bd4-167">对消息加密使用 Basic256，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a1bd4-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a1bd4-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="a1bd4-169">对消息加密使用 TripleDes，对消息摘要使用 Sha256，对密钥包装使用 Rsa15。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1bd4-170">子元素</span><span class="sxs-lookup"><span data-stu-id="a1bd4-170">Child Elements</span></span>  
  
|<span data-ttu-id="a1bd4-171">元素</span><span class="sxs-lookup"><span data-stu-id="a1bd4-171">Element</span></span>|<span data-ttu-id="a1bd4-172">描述</span><span class="sxs-lookup"><span data-stu-id="a1bd4-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1bd4-173">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="a1bd4-173">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="a1bd4-174">指定此绑定的声明类型集合。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="a1bd4-175">每个元素的类型都为 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="a1bd4-176">issuer</span><span class="sxs-lookup"><span data-stu-id="a1bd4-176">issuer</span></span>|<span data-ttu-id="a1bd4-177">指定颁发安全令牌的终结点。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="a1bd4-178">此元素的类型为 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="a1bd4-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="a1bd4-179">issuerMetadata</span></span>|<span data-ttu-id="a1bd4-180">指定颁发者的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="a1bd4-181">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="a1bd4-181">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="a1bd4-182">令牌请求参数的集合。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-182">A collection of token request parameters.</span></span> <span data-ttu-id="a1bd4-183">每个参数都是一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a1bd4-184">父元素</span><span class="sxs-lookup"><span data-stu-id="a1bd4-184">Parent Elements</span></span>  
  
|<span data-ttu-id="a1bd4-185">元素</span><span class="sxs-lookup"><span data-stu-id="a1bd4-185">Element</span></span>|<span data-ttu-id="a1bd4-186">描述</span><span class="sxs-lookup"><span data-stu-id="a1bd4-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1bd4-187">\<security></span><span class="sxs-lookup"><span data-stu-id="a1bd4-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="a1bd4-188">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="a1bd4-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1bd4-189">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1bd4-189">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>  
 <span data-ttu-id="a1bd4-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement`[保护服务和客户端](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span><span class="sxs-lookup"><span data-stu-id="a1bd4-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Securing Services and Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span></span>  
 [<span data-ttu-id="a1bd4-191">绑定</span><span class="sxs-lookup"><span data-stu-id="a1bd4-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a1bd4-192">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="a1bd4-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a1bd4-193">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="a1bd4-193">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a1bd4-194">\<binding></span><span class="sxs-lookup"><span data-stu-id="a1bd4-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
