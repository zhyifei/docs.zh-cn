---
title: "&lt;ws2007FederationHttpBinding&gt; 的 &lt;security&gt; 元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 0358b8cd0ddc91baf4028fa8a3f06d032c3f117b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="4f964-102">&lt;ws2007FederationHttpBinding&gt; 的 &lt;security&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="4f964-102">&lt;security&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="4f964-103">定义的安全设置[ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="4f964-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="4f964-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4f964-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4f964-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4f964-105">\<bindings></span></span>  
<span data-ttu-id="4f964-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="4f964-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="4f964-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="4f964-107">\<binding></span></span>  
<span data-ttu-id="4f964-108">\<security></span><span class="sxs-lookup"><span data-stu-id="4f964-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f964-109">语法</span><span class="sxs-lookup"><span data-stu-id="4f964-109">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>  
    <binding >  
        <security mode="None/Message/TransportWithMessageCredential">  
           <message negotiateServiceCredential="Boolean"  
                algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/ Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                defaultProtectionLevel="none/sign/EncryptAndSign"   
                issuedTokenType="string"   
                issuedKeyType="SymmetricKey/PublicKey"  
           </message>  
        </security>  
    </binding>  
</ws2007FederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f964-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4f964-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4f964-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4f964-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f964-112">特性</span><span class="sxs-lookup"><span data-stu-id="4f964-112">Attributes</span></span>  
  
|<span data-ttu-id="4f964-113">特性</span><span class="sxs-lookup"><span data-stu-id="4f964-113">Attribute</span></span>|<span data-ttu-id="4f964-114">描述</span><span class="sxs-lookup"><span data-stu-id="4f964-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="4f964-115">可选。</span><span class="sxs-lookup"><span data-stu-id="4f964-115">Optional.</span></span> <span data-ttu-id="4f964-116">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="4f964-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="4f964-117">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="4f964-117">The default value is `Message`.</span></span> <span data-ttu-id="4f964-118">此属性的类型为 <xref:System.ServiceModel.WSFederationHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="4f964-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4f964-119">mode 属性</span><span class="sxs-lookup"><span data-stu-id="4f964-119">mode Attribute</span></span>  
  
|<span data-ttu-id="4f964-120">值</span><span class="sxs-lookup"><span data-stu-id="4f964-120">Value</span></span>|<span data-ttu-id="4f964-121">描述</span><span class="sxs-lookup"><span data-stu-id="4f964-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4f964-122">无</span><span class="sxs-lookup"><span data-stu-id="4f964-122">None</span></span>|<span data-ttu-id="4f964-123">SOAP 消息在传输过程中并不安全。</span><span class="sxs-lookup"><span data-stu-id="4f964-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="4f964-124">消息</span><span class="sxs-lookup"><span data-stu-id="4f964-124">Message</span></span>|<span data-ttu-id="4f964-125">通过使用 SOAP 消息安全，可以提供完整性、保密性、服务器身份验证和客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="4f964-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="4f964-126">默认情况下，将对正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="4f964-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="4f964-127">此服务必须使用证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="4f964-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="4f964-128">客户端根据由安全令牌服务颁发给客户端的令牌进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="4f964-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="4f964-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="4f964-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="4f964-130">完整性、保密性和服务器身份验证均由 HTTPS 提供。</span><span class="sxs-lookup"><span data-stu-id="4f964-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="4f964-131">此服务必须使用证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="4f964-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="4f964-132">客户端身份验证采用 SOAP 消息安全方式提供，并根据由安全令牌服务颁发给客户端的令牌进行。</span><span class="sxs-lookup"><span data-stu-id="4f964-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f964-133">子元素</span><span class="sxs-lookup"><span data-stu-id="4f964-133">Child Elements</span></span>  
  
|<span data-ttu-id="4f964-134">元素</span><span class="sxs-lookup"><span data-stu-id="4f964-134">Element</span></span>|<span data-ttu-id="4f964-135">描述</span><span class="sxs-lookup"><span data-stu-id="4f964-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f964-136">\<message></span><span class="sxs-lookup"><span data-stu-id="4f964-136">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="4f964-137">定义消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="4f964-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="4f964-138">此元素的类型为 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>。</span><span class="sxs-lookup"><span data-stu-id="4f964-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f964-139">父元素</span><span class="sxs-lookup"><span data-stu-id="4f964-139">Parent Elements</span></span>  
  
|<span data-ttu-id="4f964-140">元素</span><span class="sxs-lookup"><span data-stu-id="4f964-140">Element</span></span>|<span data-ttu-id="4f964-141">描述</span><span class="sxs-lookup"><span data-stu-id="4f964-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f964-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="4f964-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4f964-143">定义的所有绑定功能[ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="4f964-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f964-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f964-144">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="4f964-145">如何：创建 WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="4f964-145">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="4f964-146">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="4f964-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="4f964-147">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="4f964-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="4f964-148">绑定</span><span class="sxs-lookup"><span data-stu-id="4f964-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4f964-149">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="4f964-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="4f964-150">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="4f964-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="4f964-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="4f964-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
