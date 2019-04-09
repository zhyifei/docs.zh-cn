---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 0dffad6a17720dd0506acbcd60efe4aafe24ed28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090103"
---
# <a name="issuermetadata"></a><span data-ttu-id="79720-101">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="79720-101">\<issuerMetadata></span></span>
<span data-ttu-id="79720-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="79720-102">\<system.serviceModel></span></span>  
<span data-ttu-id="79720-103">\<bindings></span><span class="sxs-lookup"><span data-stu-id="79720-103">\<bindings></span></span>  
<span data-ttu-id="79720-104">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="79720-104">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="79720-105">\<binding></span><span class="sxs-lookup"><span data-stu-id="79720-105">\<binding></span></span>  
<span data-ttu-id="79720-106">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="79720-106">\<security></span></span>  
<span data-ttu-id="79720-107">\<message></span><span class="sxs-lookup"><span data-stu-id="79720-107">\<message></span></span>  
<span data-ttu-id="79720-108">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="79720-108">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79720-109">语法</span><span class="sxs-lookup"><span data-stu-id="79720-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79720-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="79720-110">Attributes and Elements</span></span>  
 <span data-ttu-id="79720-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="79720-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79720-112">特性</span><span class="sxs-lookup"><span data-stu-id="79720-112">Attributes</span></span>  
  
|<span data-ttu-id="79720-113">特性</span><span class="sxs-lookup"><span data-stu-id="79720-113">Attribute</span></span>|<span data-ttu-id="79720-114">描述</span><span class="sxs-lookup"><span data-stu-id="79720-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79720-115">地址</span><span class="sxs-lookup"><span data-stu-id="79720-115">address</span></span>|<span data-ttu-id="79720-116">必选的 `string` 特性。</span><span class="sxs-lookup"><span data-stu-id="79720-116">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="79720-117">指定终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="79720-117">Specifies the address of the endpoint.</span></span> <span data-ttu-id="79720-118">该地址必须为绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="79720-118">The address must be an absolute URI.</span></span> <span data-ttu-id="79720-119">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="79720-119">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79720-120">子元素</span><span class="sxs-lookup"><span data-stu-id="79720-120">Child Elements</span></span>  
  
|<span data-ttu-id="79720-121">元素</span><span class="sxs-lookup"><span data-stu-id="79720-121">Element</span></span>|<span data-ttu-id="79720-122">描述</span><span class="sxs-lookup"><span data-stu-id="79720-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79720-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="79720-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="79720-124">一个地址标头集合。</span><span class="sxs-lookup"><span data-stu-id="79720-124">A collection of address headers.</span></span>|  
|[<span data-ttu-id="79720-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="79720-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="79720-126">一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="79720-126">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="79720-127">父元素</span><span class="sxs-lookup"><span data-stu-id="79720-127">Parent Elements</span></span>  
  
|<span data-ttu-id="79720-128">元素</span><span class="sxs-lookup"><span data-stu-id="79720-128">Element</span></span>|<span data-ttu-id="79720-129">描述</span><span class="sxs-lookup"><span data-stu-id="79720-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79720-130">\<message></span><span class="sxs-lookup"><span data-stu-id="79720-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="79720-131">定义的消息级安全性设置[ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="79720-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79720-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="79720-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="79720-133">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="79720-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="79720-134">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="79720-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="79720-135">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="79720-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="79720-136">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="79720-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
