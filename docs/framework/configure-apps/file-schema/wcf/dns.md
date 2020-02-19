---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: e49a564c9793b371425b2b787586bb9d3cbed58b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452222"
---
# <a name="dns"></a><span data-ttu-id="15e41-101">\<dns ></span><span class="sxs-lookup"><span data-stu-id="15e41-101">\<dns></span></span>
<span data-ttu-id="15e41-102">指定服务器的所需标识。</span><span class="sxs-lookup"><span data-stu-id="15e41-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="15e41-103">如果服务器的证书包含具有相同值的 DNS，则此标识对于 X509 证书身份验证模式有效。</span><span class="sxs-lookup"><span data-stu-id="15e41-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="15e41-104">如果 SPN 具有相同值，则它对于 Windows 身份验证模式同样有效。</span><span class="sxs-lookup"><span data-stu-id="15e41-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="15e41-105">有关设置元素值的详细信息，请参阅[服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="15e41-105">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="15e41-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="15e41-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="15e41-107">&nbsp;&nbsp;[ **\<system.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="15e41-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="15e41-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<客户端 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="15e41-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="15e41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpoint >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="15e41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="15e41-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<标识 >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="15e41-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="15e41-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dns >**</span><span class="sxs-lookup"><span data-stu-id="15e41-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15e41-112">语法</span><span class="sxs-lookup"><span data-stu-id="15e41-112">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15e41-113">属性和元素</span><span class="sxs-lookup"><span data-stu-id="15e41-113">Attributes and Elements</span></span>  
 <span data-ttu-id="15e41-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="15e41-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15e41-115">Attributes</span><span class="sxs-lookup"><span data-stu-id="15e41-115">Attributes</span></span>  
  
|<span data-ttu-id="15e41-116">属性</span><span class="sxs-lookup"><span data-stu-id="15e41-116">Attribute</span></span>|<span data-ttu-id="15e41-117">说明</span><span class="sxs-lookup"><span data-stu-id="15e41-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15e41-118">值</span><span class="sxs-lookup"><span data-stu-id="15e41-118">value</span></span>|<span data-ttu-id="15e41-119">证书的 DNS。</span><span class="sxs-lookup"><span data-stu-id="15e41-119">The DNS of the certificate.</span></span> <span data-ttu-id="15e41-120">DNS 是一个用于在基于 IP 网络上定位计算机的行业标准协议。</span><span class="sxs-lookup"><span data-stu-id="15e41-120">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="15e41-121">用户可以记住显示名称，如 `https://go.microsoft.com/fwlink/?prd=10929` 或 `https://go.microsoft.com/fwlink/?LinkID=96165`，比基于数字的地址更简单，如207.46.131.137。</span><span class="sxs-lookup"><span data-stu-id="15e41-121">Users can remember display names, such as `https://go.microsoft.com/fwlink/?prd=10929` or `https://go.microsoft.com/fwlink/?LinkID=96165`, easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15e41-122">子元素</span><span class="sxs-lookup"><span data-stu-id="15e41-122">Child Elements</span></span>  
 <span data-ttu-id="15e41-123">无。</span><span class="sxs-lookup"><span data-stu-id="15e41-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15e41-124">父元素</span><span class="sxs-lookup"><span data-stu-id="15e41-124">Parent Elements</span></span>  
  
|<span data-ttu-id="15e41-125">元素</span><span class="sxs-lookup"><span data-stu-id="15e41-125">Element</span></span>|<span data-ttu-id="15e41-126">说明</span><span class="sxs-lookup"><span data-stu-id="15e41-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15e41-127">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="15e41-127">\<identity></span></span>](identity.md)|<span data-ttu-id="15e41-128">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="15e41-128">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="15e41-129">示例</span><span class="sxs-lookup"><span data-stu-id="15e41-129">Example</span></span>  
 <span data-ttu-id="15e41-130">下面的配置代码指定用于对服务器进行身份验证的 X.509 证书的 DNS。</span><span class="sxs-lookup"><span data-stu-id="15e41-130">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="15e41-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15e41-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="15e41-132">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="15e41-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="15e41-133">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="15e41-133">\<identity></span></span>](identity.md)
