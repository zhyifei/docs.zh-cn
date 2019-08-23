---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 08fda249b526961ff711f439cf729a18e15b412b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929377"
---
# <a name="issuer"></a><span data-ttu-id="01855-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="01855-101">\<issuer></span></span>
<span data-ttu-id="01855-102">指定颁发安全令牌的安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="01855-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="01855-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="01855-103">\<system.serviceModel></span></span>  
<span data-ttu-id="01855-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="01855-104">\<bindings></span></span>  
<span data-ttu-id="01855-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="01855-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="01855-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="01855-106">\<binding></span></span>  
<span data-ttu-id="01855-107">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="01855-107">\<security></span></span>  
<span data-ttu-id="01855-108">\<message></span><span class="sxs-lookup"><span data-stu-id="01855-108">\<message></span></span>  
<span data-ttu-id="01855-109">\<issuer></span><span class="sxs-lookup"><span data-stu-id="01855-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01855-110">语法</span><span class="sxs-lookup"><span data-stu-id="01855-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01855-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="01855-111">Attributes and Elements</span></span>  
 <span data-ttu-id="01855-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="01855-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01855-113">特性</span><span class="sxs-lookup"><span data-stu-id="01855-113">Attributes</span></span>  
  
|<span data-ttu-id="01855-114">特性</span><span class="sxs-lookup"><span data-stu-id="01855-114">Attribute</span></span>|<span data-ttu-id="01855-115">描述</span><span class="sxs-lookup"><span data-stu-id="01855-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01855-116">地址</span><span class="sxs-lookup"><span data-stu-id="01855-116">address</span></span>|<span data-ttu-id="01855-117">必选字符串。</span><span class="sxs-lookup"><span data-stu-id="01855-117">Required string.</span></span> <span data-ttu-id="01855-118">STS 的 URL。</span><span class="sxs-lookup"><span data-stu-id="01855-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01855-119">子元素</span><span class="sxs-lookup"><span data-stu-id="01855-119">Child Elements</span></span>  
  
|<span data-ttu-id="01855-120">元素</span><span class="sxs-lookup"><span data-stu-id="01855-120">Element</span></span>|<span data-ttu-id="01855-121">描述</span><span class="sxs-lookup"><span data-stu-id="01855-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01855-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="01855-122">\<headers></span></span>](headers-element.md)|<span data-ttu-id="01855-123">生成器可以创建的终结点的地址标头的集合。</span><span class="sxs-lookup"><span data-stu-id="01855-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="01855-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="01855-124">\<identity></span></span>](identity.md)|<span data-ttu-id="01855-125">在使用颁发的令牌时，指定能够使客户端对服务器进行身份验证的设置。</span><span class="sxs-lookup"><span data-stu-id="01855-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="01855-126">父元素</span><span class="sxs-lookup"><span data-stu-id="01855-126">Parent Elements</span></span>  
  
|<span data-ttu-id="01855-127">元素</span><span class="sxs-lookup"><span data-stu-id="01855-127">Element</span></span>|<span data-ttu-id="01855-128">描述</span><span class="sxs-lookup"><span data-stu-id="01855-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01855-129">\<message></span><span class="sxs-lookup"><span data-stu-id="01855-129">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="01855-130">定义[ \<wsFederationHttpBinding >](wsfederationhttpbinding.md)元素的消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="01855-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01855-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="01855-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="01855-132">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="01855-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="01855-133">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="01855-133">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="01855-134">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="01855-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="01855-135">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="01855-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="01855-136">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="01855-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="01855-137">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="01855-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
