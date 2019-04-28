---
title: <security> 的 <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 75e3910473a353c2ef110106c34b4e92c018b51c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670412"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="db996-102">\<security> of \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="db996-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="db996-103">定义的安全设置[ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="db996-103">Defines the security settings of the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="db996-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="db996-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="db996-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="db996-105">\<bindings></span></span>  
<span data-ttu-id="db996-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="db996-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="db996-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="db996-107">\<binding></span></span>  
<span data-ttu-id="db996-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="db996-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db996-109">语法</span><span class="sxs-lookup"><span data-stu-id="db996-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db996-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="db996-110">Attributes and Elements</span></span>  
 <span data-ttu-id="db996-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="db996-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db996-112">特性</span><span class="sxs-lookup"><span data-stu-id="db996-112">Attributes</span></span>  
  
|<span data-ttu-id="db996-113">特性</span><span class="sxs-lookup"><span data-stu-id="db996-113">Attribute</span></span>|<span data-ttu-id="db996-114">描述</span><span class="sxs-lookup"><span data-stu-id="db996-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db996-115">模式</span><span class="sxs-lookup"><span data-stu-id="db996-115">Mode</span></span>|<span data-ttu-id="db996-116">可选。</span><span class="sxs-lookup"><span data-stu-id="db996-116">Optional.</span></span> <span data-ttu-id="db996-117">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="db996-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="db996-118">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="db996-118">The default value is `Message`.</span></span> <span data-ttu-id="db996-119">此属性的类型为 <xref:System.ServiceModel.WSFederationHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="db996-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="db996-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="db996-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="db996-121">“值”</span><span class="sxs-lookup"><span data-stu-id="db996-121">Value</span></span>|<span data-ttu-id="db996-122">描述</span><span class="sxs-lookup"><span data-stu-id="db996-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="db996-123">None</span><span class="sxs-lookup"><span data-stu-id="db996-123">None</span></span>|<span data-ttu-id="db996-124">SOAP 消息在传输过程中并不安全。</span><span class="sxs-lookup"><span data-stu-id="db996-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="db996-125">消息</span><span class="sxs-lookup"><span data-stu-id="db996-125">Message</span></span>|<span data-ttu-id="db996-126">通过使用 SOAP 消息安全，可以提供完整性、保密性、服务器身份验证和客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="db996-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="db996-127">默认情况下，将对正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="db996-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="db996-128">此服务需要使用证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="db996-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="db996-129">客户端根据由安全令牌服务颁发给客户端的令牌进行身份验证</span><span class="sxs-lookup"><span data-stu-id="db996-129">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="db996-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="db996-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="db996-131">完整性、保密性和服务器身份验证均由 HTTPS 提供。</span><span class="sxs-lookup"><span data-stu-id="db996-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="db996-132">此服务需要使用证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="db996-132">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="db996-133">客户端身份验证采用 SOAP 消息安全方式提供，并根据由安全令牌服务颁发给客户端的令牌进行。</span><span class="sxs-lookup"><span data-stu-id="db996-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db996-134">子元素</span><span class="sxs-lookup"><span data-stu-id="db996-134">Child Elements</span></span>  
  
|<span data-ttu-id="db996-135">元素</span><span class="sxs-lookup"><span data-stu-id="db996-135">Element</span></span>|<span data-ttu-id="db996-136">描述</span><span class="sxs-lookup"><span data-stu-id="db996-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db996-137">\<message></span><span class="sxs-lookup"><span data-stu-id="db996-137">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="db996-138">定义消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="db996-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="db996-139">此元素的类型为 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>。</span><span class="sxs-lookup"><span data-stu-id="db996-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="db996-140">父元素</span><span class="sxs-lookup"><span data-stu-id="db996-140">Parent Elements</span></span>  
  
|<span data-ttu-id="db996-141">元素</span><span class="sxs-lookup"><span data-stu-id="db996-141">Element</span></span>|<span data-ttu-id="db996-142">描述</span><span class="sxs-lookup"><span data-stu-id="db996-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db996-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="db996-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="db996-144">定义的所有绑定功能[ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="db996-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db996-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="db996-145">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="db996-146">如何：创建 WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="db996-146">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="db996-147">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="db996-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="db996-148">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="db996-148">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="db996-149">绑定</span><span class="sxs-lookup"><span data-stu-id="db996-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="db996-150">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="db996-150">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="db996-151">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="db996-151">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="db996-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="db996-152">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
