---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 37d935287fa7dfba640c39071295fd660f4db7c1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160818"
---
# <a name="issuer"></a><span data-ttu-id="d255a-101">\<issuer></span><span class="sxs-lookup"><span data-stu-id="d255a-101">\<issuer></span></span>
<span data-ttu-id="d255a-102">指定颁发安全令牌的安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="d255a-102">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="d255a-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d255a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d255a-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d255a-104">\<bindings></span></span>  
<span data-ttu-id="d255a-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d255a-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="d255a-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="d255a-106">\<binding></span></span>  
<span data-ttu-id="d255a-107">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="d255a-107">\<security></span></span>  
<span data-ttu-id="d255a-108">\<message></span><span class="sxs-lookup"><span data-stu-id="d255a-108">\<message></span></span>  
<span data-ttu-id="d255a-109">\<issuer></span><span class="sxs-lookup"><span data-stu-id="d255a-109">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d255a-110">语法</span><span class="sxs-lookup"><span data-stu-id="d255a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d255a-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d255a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d255a-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d255a-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d255a-113">特性</span><span class="sxs-lookup"><span data-stu-id="d255a-113">Attributes</span></span>  
  
|<span data-ttu-id="d255a-114">特性</span><span class="sxs-lookup"><span data-stu-id="d255a-114">Attribute</span></span>|<span data-ttu-id="d255a-115">描述</span><span class="sxs-lookup"><span data-stu-id="d255a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d255a-116">地址</span><span class="sxs-lookup"><span data-stu-id="d255a-116">address</span></span>|<span data-ttu-id="d255a-117">必选字符串。</span><span class="sxs-lookup"><span data-stu-id="d255a-117">Required string.</span></span> <span data-ttu-id="d255a-118">STS 的 URL。</span><span class="sxs-lookup"><span data-stu-id="d255a-118">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d255a-119">子元素</span><span class="sxs-lookup"><span data-stu-id="d255a-119">Child Elements</span></span>  
  
|<span data-ttu-id="d255a-120">元素</span><span class="sxs-lookup"><span data-stu-id="d255a-120">Element</span></span>|<span data-ttu-id="d255a-121">描述</span><span class="sxs-lookup"><span data-stu-id="d255a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d255a-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="d255a-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="d255a-123">生成器可以创建的终结点的地址标头的集合。</span><span class="sxs-lookup"><span data-stu-id="d255a-123">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="d255a-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="d255a-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="d255a-125">在使用颁发的令牌时，指定能够使客户端对服务器进行身份验证的设置。</span><span class="sxs-lookup"><span data-stu-id="d255a-125">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d255a-126">父元素</span><span class="sxs-lookup"><span data-stu-id="d255a-126">Parent Elements</span></span>  
  
|<span data-ttu-id="d255a-127">元素</span><span class="sxs-lookup"><span data-stu-id="d255a-127">Element</span></span>|<span data-ttu-id="d255a-128">描述</span><span class="sxs-lookup"><span data-stu-id="d255a-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d255a-129">\<message></span><span class="sxs-lookup"><span data-stu-id="d255a-129">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="d255a-130">定义的消息级安全性设置[ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d255a-130">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d255a-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="d255a-131">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [<span data-ttu-id="d255a-132">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="d255a-132">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d255a-133">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="d255a-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d255a-134">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="d255a-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d255a-135">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="d255a-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d255a-136">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="d255a-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="d255a-137">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="d255a-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
