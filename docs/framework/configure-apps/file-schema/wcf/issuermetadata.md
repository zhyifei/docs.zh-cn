---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: a28223127f7987a80bdf12d2dcf42878f717a377
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397882"
---
# <a name="issuermetadata"></a><span data-ttu-id="855c3-101">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="855c3-101">\<issuerMetadata></span></span>

<span data-ttu-id="855c3-102">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="855c3-102">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="855c3-103">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="855c3-103">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="855c3-104">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="855c3-104">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="855c3-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="855c3-105">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="855c3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="855c3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="855c3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="855c3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="855c3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<消息 >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="855c3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="855c3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Issuedtokenparameters >**</span><span class="sxs-lookup"><span data-stu-id="855c3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="855c3-110">语法</span><span class="sxs-lookup"><span data-stu-id="855c3-110">Syntax</span></span>  
  
```xml  
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
                          x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
    <dns value="String" />
    <rsa value="String" />
    <servicePrincipalName value="String" />
    <usePrincipalName value="String" />
  </identity>
</issuerMetadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="855c3-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="855c3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="855c3-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="855c3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="855c3-113">特性</span><span class="sxs-lookup"><span data-stu-id="855c3-113">Attributes</span></span>  
  
|<span data-ttu-id="855c3-114">特性</span><span class="sxs-lookup"><span data-stu-id="855c3-114">Attribute</span></span>|<span data-ttu-id="855c3-115">描述</span><span class="sxs-lookup"><span data-stu-id="855c3-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="855c3-116">地址</span><span class="sxs-lookup"><span data-stu-id="855c3-116">address</span></span>|<span data-ttu-id="855c3-117">必选的 `string` 特性。</span><span class="sxs-lookup"><span data-stu-id="855c3-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="855c3-118">指定终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="855c3-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="855c3-119">该地址必须为绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="855c3-119">The address must be an absolute URI.</span></span> <span data-ttu-id="855c3-120">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="855c3-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="855c3-121">子元素</span><span class="sxs-lookup"><span data-stu-id="855c3-121">Child Elements</span></span>  
  
|<span data-ttu-id="855c3-122">元素</span><span class="sxs-lookup"><span data-stu-id="855c3-122">Element</span></span>|<span data-ttu-id="855c3-123">描述</span><span class="sxs-lookup"><span data-stu-id="855c3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="855c3-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="855c3-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="855c3-125">一个地址标头集合。</span><span class="sxs-lookup"><span data-stu-id="855c3-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="855c3-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="855c3-126">\<identity></span></span>](identity.md)|<span data-ttu-id="855c3-127">一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="855c3-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="855c3-128">父元素</span><span class="sxs-lookup"><span data-stu-id="855c3-128">Parent Elements</span></span>  
  
|<span data-ttu-id="855c3-129">元素</span><span class="sxs-lookup"><span data-stu-id="855c3-129">Element</span></span>|<span data-ttu-id="855c3-130">描述</span><span class="sxs-lookup"><span data-stu-id="855c3-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="855c3-131">\<message></span><span class="sxs-lookup"><span data-stu-id="855c3-131">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="855c3-132">定义[ \<wsFederationHttpBinding >](wsfederationhttpbinding.md)元素的消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="855c3-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="855c3-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="855c3-133">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="855c3-134">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="855c3-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="855c3-135">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="855c3-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="855c3-136">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="855c3-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="855c3-137">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="855c3-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
