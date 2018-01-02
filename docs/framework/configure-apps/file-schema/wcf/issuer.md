---
title: "&lt;颁发者&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e034b3ed0813d621ed86c2c3e86bb901ab39e40b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuergt"></a><span data-ttu-id="22cdb-102">&lt;颁发者&gt;</span><span class="sxs-lookup"><span data-stu-id="22cdb-102">&lt;issuer&gt;</span></span>
<span data-ttu-id="22cdb-103">指定颁发安全令牌的安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="22cdb-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="22cdb-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="22cdb-104">\<system.serviceModel></span></span>  
<span data-ttu-id="22cdb-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="22cdb-105">\<bindings></span></span>  
<span data-ttu-id="22cdb-106">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="22cdb-106">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="22cdb-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="22cdb-107">\<binding></span></span>  
<span data-ttu-id="22cdb-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="22cdb-108">\<security></span></span>  
<span data-ttu-id="22cdb-109">\<消息 ></span><span class="sxs-lookup"><span data-stu-id="22cdb-109">\<message></span></span>  
<span data-ttu-id="22cdb-110">\<颁发者 ></span><span class="sxs-lookup"><span data-stu-id="22cdb-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22cdb-111">语法</span><span class="sxs-lookup"><span data-stu-id="22cdb-111">Syntax</span></span>  
  
```xml  
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
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22cdb-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="22cdb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="22cdb-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="22cdb-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22cdb-114">特性</span><span class="sxs-lookup"><span data-stu-id="22cdb-114">Attributes</span></span>  
  
|<span data-ttu-id="22cdb-115">特性</span><span class="sxs-lookup"><span data-stu-id="22cdb-115">Attribute</span></span>|<span data-ttu-id="22cdb-116">描述</span><span class="sxs-lookup"><span data-stu-id="22cdb-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22cdb-117">address</span><span class="sxs-lookup"><span data-stu-id="22cdb-117">address</span></span>|<span data-ttu-id="22cdb-118">必选字符串。</span><span class="sxs-lookup"><span data-stu-id="22cdb-118">Required string.</span></span> <span data-ttu-id="22cdb-119">STS 的 URL。</span><span class="sxs-lookup"><span data-stu-id="22cdb-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22cdb-120">子元素</span><span class="sxs-lookup"><span data-stu-id="22cdb-120">Child Elements</span></span>  
  
|<span data-ttu-id="22cdb-121">元素</span><span class="sxs-lookup"><span data-stu-id="22cdb-121">Element</span></span>|<span data-ttu-id="22cdb-122">描述</span><span class="sxs-lookup"><span data-stu-id="22cdb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22cdb-123">\<标头 ></span><span class="sxs-lookup"><span data-stu-id="22cdb-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="22cdb-124">生成器可以创建的终结点的地址标头的集合。</span><span class="sxs-lookup"><span data-stu-id="22cdb-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="22cdb-125">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="22cdb-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="22cdb-126">在使用颁发的令牌时，指定能够使客户端对服务器进行身份验证的设置。</span><span class="sxs-lookup"><span data-stu-id="22cdb-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22cdb-127">父元素</span><span class="sxs-lookup"><span data-stu-id="22cdb-127">Parent Elements</span></span>  
  
|<span data-ttu-id="22cdb-128">元素</span><span class="sxs-lookup"><span data-stu-id="22cdb-128">Element</span></span>|<span data-ttu-id="22cdb-129">描述</span><span class="sxs-lookup"><span data-stu-id="22cdb-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22cdb-130">\<消息 ></span><span class="sxs-lookup"><span data-stu-id="22cdb-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="22cdb-131">定义的消息级安全性设置[ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="22cdb-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22cdb-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="22cdb-132">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 [<span data-ttu-id="22cdb-133">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="22cdb-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="22cdb-134">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="22cdb-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="22cdb-135">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="22cdb-135">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="22cdb-136">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="22cdb-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="22cdb-137">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="22cdb-137">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="22cdb-138">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="22cdb-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
