---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: da865a19a91d4af6221a13b53a174637d5fb8139
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854991"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="52f61-101">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="52f61-101">\<servicePrincipalName></span></span>
<span data-ttu-id="52f61-102">利用对应的服务主体名称 (SPN) 指定服务的标识。</span><span class="sxs-lookup"><span data-stu-id="52f61-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="52f61-103">有关设置 SPN 的详细信息，请参阅[服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="52f61-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="52f61-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="52f61-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="52f61-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="52f61-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="52f61-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<客户端 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="52f61-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="52f61-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<终结点 >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="52f61-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="52f61-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<身份 >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="52f61-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="52f61-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<servicePrincipalName >**</span><span class="sxs-lookup"><span data-stu-id="52f61-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52f61-110">语法</span><span class="sxs-lookup"><span data-stu-id="52f61-110">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52f61-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="52f61-111">Attributes and Elements</span></span>  
 <span data-ttu-id="52f61-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="52f61-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52f61-113">特性</span><span class="sxs-lookup"><span data-stu-id="52f61-113">Attributes</span></span>  
  
|<span data-ttu-id="52f61-114">特性</span><span class="sxs-lookup"><span data-stu-id="52f61-114">Attribute</span></span>|<span data-ttu-id="52f61-115">描述</span><span class="sxs-lookup"><span data-stu-id="52f61-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52f61-116">value</span><span class="sxs-lookup"><span data-stu-id="52f61-116">value</span></span>|<span data-ttu-id="52f61-117">客户端用来唯一地标识服务实例的名称。</span><span class="sxs-lookup"><span data-stu-id="52f61-117">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="52f61-118">如果在计算机的整个目录林上安装多个服务实例，那么每个实例都必须有自己的 SPN。</span><span class="sxs-lookup"><span data-stu-id="52f61-118">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="52f61-119">如果客户端有多个名称可用于身份验证，则给定的服务实例可以有多个 SPN。</span><span class="sxs-lookup"><span data-stu-id="52f61-119">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52f61-120">子元素</span><span class="sxs-lookup"><span data-stu-id="52f61-120">Child Elements</span></span>  
 <span data-ttu-id="52f61-121">无。</span><span class="sxs-lookup"><span data-stu-id="52f61-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52f61-122">父元素</span><span class="sxs-lookup"><span data-stu-id="52f61-122">Parent Elements</span></span>  
  
|<span data-ttu-id="52f61-123">元素</span><span class="sxs-lookup"><span data-stu-id="52f61-123">Element</span></span>|<span data-ttu-id="52f61-124">描述</span><span class="sxs-lookup"><span data-stu-id="52f61-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52f61-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="52f61-125">\<identity></span></span>](identity.md)|<span data-ttu-id="52f61-126">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="52f61-126">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52f61-127">备注</span><span class="sxs-lookup"><span data-stu-id="52f61-127">Remarks</span></span>  
 <span data-ttu-id="52f61-128">使用此标识连接到终结点的安全 Windows Communication Foundation （WCF）客户端在使用终结点进行 SSPI 身份验证时使用 SPN。</span><span class="sxs-lookup"><span data-stu-id="52f61-128">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52f61-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="52f61-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="52f61-130">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="52f61-130">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="52f61-131">\<identity></span><span class="sxs-lookup"><span data-stu-id="52f61-131">\<identity></span></span>](identity.md)
