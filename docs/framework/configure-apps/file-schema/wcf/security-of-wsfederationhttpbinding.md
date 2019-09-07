---
title: <security> 的 <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 6c07d1ca18837f66548411262b84b9a326f5ec4a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399734"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="7c529-102">\<wsFederationHttpBinding 的\<安全 > ></span><span class="sxs-lookup"><span data-stu-id="7c529-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="7c529-103">定义[ \<wsFederationHttpBinding >](wsfederationhttpbinding.md)的安全设置。</span><span class="sxs-lookup"><span data-stu-id="7c529-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="7c529-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7c529-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7c529-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7c529-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7c529-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="7c529-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="7c529-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="7c529-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="7c529-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="7c529-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="7c529-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<安全 >**</span><span class="sxs-lookup"><span data-stu-id="7c529-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c529-110">语法</span><span class="sxs-lookup"><span data-stu-id="7c529-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c529-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7c529-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7c529-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7c529-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c529-113">特性</span><span class="sxs-lookup"><span data-stu-id="7c529-113">Attributes</span></span>  
  
|<span data-ttu-id="7c529-114">特性</span><span class="sxs-lookup"><span data-stu-id="7c529-114">Attribute</span></span>|<span data-ttu-id="7c529-115">描述</span><span class="sxs-lookup"><span data-stu-id="7c529-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c529-116">模式</span><span class="sxs-lookup"><span data-stu-id="7c529-116">Mode</span></span>|<span data-ttu-id="7c529-117">可选。</span><span class="sxs-lookup"><span data-stu-id="7c529-117">Optional.</span></span> <span data-ttu-id="7c529-118">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="7c529-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="7c529-119">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="7c529-119">The default value is `Message`.</span></span> <span data-ttu-id="7c529-120">此属性的类型为 <xref:System.ServiceModel.WSFederationHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="7c529-120">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="7c529-121">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="7c529-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="7c529-122">值</span><span class="sxs-lookup"><span data-stu-id="7c529-122">Value</span></span>|<span data-ttu-id="7c529-123">描述</span><span class="sxs-lookup"><span data-stu-id="7c529-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7c529-124">无</span><span class="sxs-lookup"><span data-stu-id="7c529-124">None</span></span>|<span data-ttu-id="7c529-125">SOAP 消息在传输过程中并不安全。</span><span class="sxs-lookup"><span data-stu-id="7c529-125">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="7c529-126">消息</span><span class="sxs-lookup"><span data-stu-id="7c529-126">Message</span></span>|<span data-ttu-id="7c529-127">通过使用 SOAP 消息安全，可以提供完整性、保密性、服务器身份验证和客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="7c529-127">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="7c529-128">默认情况下，将对正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="7c529-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="7c529-129">此服务需要使用证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="7c529-129">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="7c529-130">客户端根据由安全令牌服务颁发给客户端的令牌进行身份验证</span><span class="sxs-lookup"><span data-stu-id="7c529-130">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="7c529-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="7c529-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="7c529-132">完整性、保密性和服务器身份验证均由 HTTPS 提供。</span><span class="sxs-lookup"><span data-stu-id="7c529-132">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="7c529-133">此服务需要使用证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="7c529-133">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="7c529-134">客户端身份验证采用 SOAP 消息安全方式提供，并根据由安全令牌服务颁发给客户端的令牌进行。</span><span class="sxs-lookup"><span data-stu-id="7c529-134">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c529-135">子元素</span><span class="sxs-lookup"><span data-stu-id="7c529-135">Child Elements</span></span>  
  
|<span data-ttu-id="7c529-136">元素</span><span class="sxs-lookup"><span data-stu-id="7c529-136">Element</span></span>|<span data-ttu-id="7c529-137">描述</span><span class="sxs-lookup"><span data-stu-id="7c529-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c529-138">\<message></span><span class="sxs-lookup"><span data-stu-id="7c529-138">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="7c529-139">定义消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="7c529-139">Defines the settings for the message-level security.</span></span> <span data-ttu-id="7c529-140">此元素的类型为 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>。</span><span class="sxs-lookup"><span data-stu-id="7c529-140">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7c529-141">父元素</span><span class="sxs-lookup"><span data-stu-id="7c529-141">Parent Elements</span></span>  
  
|<span data-ttu-id="7c529-142">元素</span><span class="sxs-lookup"><span data-stu-id="7c529-142">Element</span></span>|<span data-ttu-id="7c529-143">描述</span><span class="sxs-lookup"><span data-stu-id="7c529-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c529-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="7c529-144">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="7c529-145">定义[ \<wsDualHttpBinding >](wsdualhttpbinding.md)的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="7c529-145">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c529-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c529-146">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="7c529-147">如何：创建 WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="7c529-147">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="7c529-148">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="7c529-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7c529-149">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="7c529-149">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="7c529-150">绑定</span><span class="sxs-lookup"><span data-stu-id="7c529-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7c529-151">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="7c529-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7c529-152">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="7c529-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7c529-153">\<binding></span><span class="sxs-lookup"><span data-stu-id="7c529-153">\<binding></span></span>](../../../misc/binding.md)
