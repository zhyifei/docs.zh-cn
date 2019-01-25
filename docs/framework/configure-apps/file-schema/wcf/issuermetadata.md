---
title: '&lt;issuerMetadata&gt;'
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 22e30e0962ec8d2eb0f7e52f4db143fba9bbf703
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491553"
---
# <a name="ltissuermetadatagt"></a><span data-ttu-id="78fad-102">&lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="78fad-102">&lt;issuerMetadata&gt;</span></span>
<span data-ttu-id="78fad-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="78fad-103">\<system.serviceModel></span></span>  
<span data-ttu-id="78fad-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="78fad-104">\<bindings></span></span>  
<span data-ttu-id="78fad-105">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="78fad-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="78fad-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="78fad-106">\<binding></span></span>  
<span data-ttu-id="78fad-107">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="78fad-107">\<security></span></span>  
<span data-ttu-id="78fad-108">\<message></span><span class="sxs-lookup"><span data-stu-id="78fad-108">\<message></span></span>  
<span data-ttu-id="78fad-109">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="78fad-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78fad-110">语法</span><span class="sxs-lookup"><span data-stu-id="78fad-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78fad-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="78fad-111">Attributes and Elements</span></span>  
 <span data-ttu-id="78fad-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="78fad-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78fad-113">特性</span><span class="sxs-lookup"><span data-stu-id="78fad-113">Attributes</span></span>  
  
|<span data-ttu-id="78fad-114">特性</span><span class="sxs-lookup"><span data-stu-id="78fad-114">Attribute</span></span>|<span data-ttu-id="78fad-115">描述</span><span class="sxs-lookup"><span data-stu-id="78fad-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78fad-116">address</span><span class="sxs-lookup"><span data-stu-id="78fad-116">address</span></span>|<span data-ttu-id="78fad-117">必选的 `string` 特性。</span><span class="sxs-lookup"><span data-stu-id="78fad-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="78fad-118">指定终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="78fad-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="78fad-119">该地址必须为绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="78fad-119">The address must be an absolute URI.</span></span> <span data-ttu-id="78fad-120">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="78fad-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78fad-121">子元素</span><span class="sxs-lookup"><span data-stu-id="78fad-121">Child Elements</span></span>  
  
|<span data-ttu-id="78fad-122">元素</span><span class="sxs-lookup"><span data-stu-id="78fad-122">Element</span></span>|<span data-ttu-id="78fad-123">描述</span><span class="sxs-lookup"><span data-stu-id="78fad-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78fad-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="78fad-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="78fad-125">一个地址标头集合。</span><span class="sxs-lookup"><span data-stu-id="78fad-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="78fad-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="78fad-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="78fad-127">一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="78fad-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="78fad-128">父元素</span><span class="sxs-lookup"><span data-stu-id="78fad-128">Parent Elements</span></span>  
  
|<span data-ttu-id="78fad-129">元素</span><span class="sxs-lookup"><span data-stu-id="78fad-129">Element</span></span>|<span data-ttu-id="78fad-130">描述</span><span class="sxs-lookup"><span data-stu-id="78fad-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78fad-131">\<message></span><span class="sxs-lookup"><span data-stu-id="78fad-131">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="78fad-132">定义的消息级安全性设置[ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="78fad-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78fad-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="78fad-133">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="78fad-134">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="78fad-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="78fad-135">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="78fad-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="78fad-136">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="78fad-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="78fad-137">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="78fad-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
