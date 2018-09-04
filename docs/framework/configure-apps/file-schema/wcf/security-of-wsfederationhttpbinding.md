---
title: '&lt;wsFederationHttpBinding&gt; 的 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 81d0f17971653c3e3ecd27ddde745a65c8b4f26d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514228"
---
# <a name="ltsecuritygt-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="16f39-102">&lt;wsFederationHttpBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="16f39-102">&lt;security&gt; of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="16f39-103">定义的安全设置[ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="16f39-103">Defines the security settings of the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="16f39-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="16f39-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="16f39-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="16f39-105">\<bindings></span></span>  
<span data-ttu-id="16f39-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="16f39-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="16f39-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="16f39-107">\<binding></span></span>  
<span data-ttu-id="16f39-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="16f39-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16f39-109">语法</span><span class="sxs-lookup"><span data-stu-id="16f39-109">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
    <binding >  
       <security mode="None/Message/TransportWithMessageCredential">  
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
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16f39-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="16f39-110">Attributes and Elements</span></span>  
 <span data-ttu-id="16f39-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="16f39-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16f39-112">特性</span><span class="sxs-lookup"><span data-stu-id="16f39-112">Attributes</span></span>  
  
|<span data-ttu-id="16f39-113">特性</span><span class="sxs-lookup"><span data-stu-id="16f39-113">Attribute</span></span>|<span data-ttu-id="16f39-114">描述</span><span class="sxs-lookup"><span data-stu-id="16f39-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="16f39-115">模式</span><span class="sxs-lookup"><span data-stu-id="16f39-115">Mode</span></span>|<span data-ttu-id="16f39-116">可选。</span><span class="sxs-lookup"><span data-stu-id="16f39-116">Optional.</span></span> <span data-ttu-id="16f39-117">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="16f39-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="16f39-118">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="16f39-118">The default value is `Message`.</span></span> <span data-ttu-id="16f39-119">此属性的类型为 <xref:System.ServiceModel.WSFederationHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="16f39-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="16f39-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="16f39-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="16f39-121">值</span><span class="sxs-lookup"><span data-stu-id="16f39-121">Value</span></span>|<span data-ttu-id="16f39-122">描述</span><span class="sxs-lookup"><span data-stu-id="16f39-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="16f39-123">无</span><span class="sxs-lookup"><span data-stu-id="16f39-123">None</span></span>|<span data-ttu-id="16f39-124">SOAP 消息在传输过程中并不安全。</span><span class="sxs-lookup"><span data-stu-id="16f39-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="16f39-125">消息</span><span class="sxs-lookup"><span data-stu-id="16f39-125">Message</span></span>|<span data-ttu-id="16f39-126">通过使用 SOAP 消息安全，可以提供完整性、保密性、服务器身份验证和客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="16f39-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="16f39-127">默认情况下，将对正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="16f39-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="16f39-128">此服务需要使用证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="16f39-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="16f39-129">客户端根据由安全令牌服务颁发给客户端的令牌进行身份验证</span><span class="sxs-lookup"><span data-stu-id="16f39-129">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="16f39-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="16f39-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="16f39-131">完整性、保密性和服务器身份验证均由 HTTPS 提供。</span><span class="sxs-lookup"><span data-stu-id="16f39-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="16f39-132">此服务需要使用证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="16f39-132">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="16f39-133">客户端身份验证采用 SOAP 消息安全方式提供，并根据由安全令牌服务颁发给客户端的令牌进行。</span><span class="sxs-lookup"><span data-stu-id="16f39-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16f39-134">子元素</span><span class="sxs-lookup"><span data-stu-id="16f39-134">Child Elements</span></span>  
  
|<span data-ttu-id="16f39-135">元素</span><span class="sxs-lookup"><span data-stu-id="16f39-135">Element</span></span>|<span data-ttu-id="16f39-136">描述</span><span class="sxs-lookup"><span data-stu-id="16f39-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16f39-137">\<message></span><span class="sxs-lookup"><span data-stu-id="16f39-137">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="16f39-138">定义消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="16f39-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="16f39-139">此元素的类型为 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>。</span><span class="sxs-lookup"><span data-stu-id="16f39-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="16f39-140">父元素</span><span class="sxs-lookup"><span data-stu-id="16f39-140">Parent Elements</span></span>  
  
|<span data-ttu-id="16f39-141">元素</span><span class="sxs-lookup"><span data-stu-id="16f39-141">Element</span></span>|<span data-ttu-id="16f39-142">描述</span><span class="sxs-lookup"><span data-stu-id="16f39-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16f39-143">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="16f39-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="16f39-144">定义的所有绑定功能[ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="16f39-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16f39-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="16f39-145">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="16f39-146">如何：创建 WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="16f39-146">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="16f39-147">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="16f39-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="16f39-148">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="16f39-148">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="16f39-149">绑定</span><span class="sxs-lookup"><span data-stu-id="16f39-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="16f39-150">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="16f39-150">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="16f39-151">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="16f39-151">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="16f39-152">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="16f39-152">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
