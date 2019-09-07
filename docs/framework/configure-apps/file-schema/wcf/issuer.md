---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 74f5f2fc1a0fa1ffbbb510e4e700c33a13d02ab3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397917"
---
# <a name="issuer"></a><span data-ttu-id="84df5-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="84df5-101">\<issuer></span></span>
<span data-ttu-id="84df5-102">指定颁发安全令牌的安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="84df5-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="84df5-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="84df5-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="84df5-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="84df5-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="84df5-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="84df5-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="84df5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="84df5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="84df5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="84df5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="84df5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="84df5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="84df5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<消息 >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="84df5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="84df5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<颁发者 >**</span><span class="sxs-lookup"><span data-stu-id="84df5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84df5-111">语法</span><span class="sxs-lookup"><span data-stu-id="84df5-111">Syntax</span></span>  
  
```xml  
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
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84df5-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="84df5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="84df5-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="84df5-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84df5-114">特性</span><span class="sxs-lookup"><span data-stu-id="84df5-114">Attributes</span></span>  
  
|<span data-ttu-id="84df5-115">特性</span><span class="sxs-lookup"><span data-stu-id="84df5-115">Attribute</span></span>|<span data-ttu-id="84df5-116">描述</span><span class="sxs-lookup"><span data-stu-id="84df5-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="84df5-117">地址</span><span class="sxs-lookup"><span data-stu-id="84df5-117">address</span></span>|<span data-ttu-id="84df5-118">必选字符串。</span><span class="sxs-lookup"><span data-stu-id="84df5-118">Required string.</span></span> <span data-ttu-id="84df5-119">STS 的 URL。</span><span class="sxs-lookup"><span data-stu-id="84df5-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84df5-120">子元素</span><span class="sxs-lookup"><span data-stu-id="84df5-120">Child Elements</span></span>  
  
|<span data-ttu-id="84df5-121">元素</span><span class="sxs-lookup"><span data-stu-id="84df5-121">Element</span></span>|<span data-ttu-id="84df5-122">描述</span><span class="sxs-lookup"><span data-stu-id="84df5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84df5-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="84df5-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="84df5-124">生成器可以创建的终结点的地址标头的集合。</span><span class="sxs-lookup"><span data-stu-id="84df5-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="84df5-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="84df5-125">\<identity></span></span>](identity.md)|<span data-ttu-id="84df5-126">在使用颁发的令牌时，指定能够使客户端对服务器进行身份验证的设置。</span><span class="sxs-lookup"><span data-stu-id="84df5-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="84df5-127">父元素</span><span class="sxs-lookup"><span data-stu-id="84df5-127">Parent Elements</span></span>  
  
|<span data-ttu-id="84df5-128">元素</span><span class="sxs-lookup"><span data-stu-id="84df5-128">Element</span></span>|<span data-ttu-id="84df5-129">描述</span><span class="sxs-lookup"><span data-stu-id="84df5-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84df5-130">\<message></span><span class="sxs-lookup"><span data-stu-id="84df5-130">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="84df5-131">定义[ \<wsFederationHttpBinding >](wsfederationhttpbinding.md)元素的消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="84df5-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84df5-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="84df5-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="84df5-133">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="84df5-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="84df5-134">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="84df5-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="84df5-135">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="84df5-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="84df5-136">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="84df5-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="84df5-137">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="84df5-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="84df5-138">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="84df5-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
