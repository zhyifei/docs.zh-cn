---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: bf512c427637ca65a7271ec8300a373a38632108
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913518"
---
# <a name="issuermetadata"></a><span data-ttu-id="20a10-101">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="20a10-101">\<issuerMetadata></span></span>
<span data-ttu-id="20a10-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="20a10-102">\<system.serviceModel></span></span>  
<span data-ttu-id="20a10-103">\<bindings></span><span class="sxs-lookup"><span data-stu-id="20a10-103">\<bindings></span></span>  
<span data-ttu-id="20a10-104">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="20a10-104">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="20a10-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="20a10-105">\<binding></span></span>  
<span data-ttu-id="20a10-106">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="20a10-106">\<security></span></span>  
<span data-ttu-id="20a10-107">\<message></span><span class="sxs-lookup"><span data-stu-id="20a10-107">\<message></span></span>  
<span data-ttu-id="20a10-108">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="20a10-108">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20a10-109">语法</span><span class="sxs-lookup"><span data-stu-id="20a10-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20a10-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="20a10-110">Attributes and Elements</span></span>  
 <span data-ttu-id="20a10-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="20a10-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20a10-112">特性</span><span class="sxs-lookup"><span data-stu-id="20a10-112">Attributes</span></span>  
  
|<span data-ttu-id="20a10-113">特性</span><span class="sxs-lookup"><span data-stu-id="20a10-113">Attribute</span></span>|<span data-ttu-id="20a10-114">描述</span><span class="sxs-lookup"><span data-stu-id="20a10-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="20a10-115">地址</span><span class="sxs-lookup"><span data-stu-id="20a10-115">address</span></span>|<span data-ttu-id="20a10-116">必选的 `string` 特性。</span><span class="sxs-lookup"><span data-stu-id="20a10-116">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="20a10-117">指定终结点的地址。</span><span class="sxs-lookup"><span data-stu-id="20a10-117">Specifies the address of the endpoint.</span></span> <span data-ttu-id="20a10-118">该地址必须为绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="20a10-118">The address must be an absolute URI.</span></span> <span data-ttu-id="20a10-119">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="20a10-119">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20a10-120">子元素</span><span class="sxs-lookup"><span data-stu-id="20a10-120">Child Elements</span></span>  
  
|<span data-ttu-id="20a10-121">元素</span><span class="sxs-lookup"><span data-stu-id="20a10-121">Element</span></span>|<span data-ttu-id="20a10-122">描述</span><span class="sxs-lookup"><span data-stu-id="20a10-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20a10-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="20a10-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="20a10-124">一个地址标头集合。</span><span class="sxs-lookup"><span data-stu-id="20a10-124">A collection of address headers.</span></span>|  
|[<span data-ttu-id="20a10-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="20a10-125">\<identity></span></span>](identity.md)|<span data-ttu-id="20a10-126">一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="20a10-126">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20a10-127">父元素</span><span class="sxs-lookup"><span data-stu-id="20a10-127">Parent Elements</span></span>  
  
|<span data-ttu-id="20a10-128">元素</span><span class="sxs-lookup"><span data-stu-id="20a10-128">Element</span></span>|<span data-ttu-id="20a10-129">描述</span><span class="sxs-lookup"><span data-stu-id="20a10-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20a10-130">\<message></span><span class="sxs-lookup"><span data-stu-id="20a10-130">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="20a10-131">定义[ \<wsFederationHttpBinding >](wsfederationhttpbinding.md)元素的消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="20a10-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20a10-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="20a10-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="20a10-133">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="20a10-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="20a10-134">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="20a10-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="20a10-135">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="20a10-135">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="20a10-136">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="20a10-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
