---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: ce12d0a82c8a443994559ed772496897f359b4e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166668"
---
# <a name="dns"></a><span data-ttu-id="d4a57-101">\<dns></span><span class="sxs-lookup"><span data-stu-id="d4a57-101">\<dns></span></span>
<span data-ttu-id="d4a57-102">指定服务器的所需标识。</span><span class="sxs-lookup"><span data-stu-id="d4a57-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="d4a57-103">如果服务器的证书包含具有相同值的 DNS，则此标识对于 X509 证书身份验证模式有效。</span><span class="sxs-lookup"><span data-stu-id="d4a57-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="d4a57-104">如果 SPN 具有相同值，则它对于 Windows 身份验证模式同样有效。</span><span class="sxs-lookup"><span data-stu-id="d4a57-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="d4a57-105">有关设置元素值的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="d4a57-105">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="d4a57-106">\<identity></span><span class="sxs-lookup"><span data-stu-id="d4a57-106">\<identity></span></span>  
<span data-ttu-id="d4a57-107">\<dns></span><span class="sxs-lookup"><span data-stu-id="d4a57-107">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4a57-108">语法</span><span class="sxs-lookup"><span data-stu-id="d4a57-108">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4a57-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d4a57-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d4a57-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d4a57-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4a57-111">特性</span><span class="sxs-lookup"><span data-stu-id="d4a57-111">Attributes</span></span>  
  
|<span data-ttu-id="d4a57-112">特性</span><span class="sxs-lookup"><span data-stu-id="d4a57-112">Attribute</span></span>|<span data-ttu-id="d4a57-113">描述</span><span class="sxs-lookup"><span data-stu-id="d4a57-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d4a57-114">值</span><span class="sxs-lookup"><span data-stu-id="d4a57-114">value</span></span>|<span data-ttu-id="d4a57-115">证书的 DNS。</span><span class="sxs-lookup"><span data-stu-id="d4a57-115">The DNS of the certificate.</span></span> <span data-ttu-id="d4a57-116">DNS 是一个用于在基于 IP 网络上定位计算机的行业标准协议。</span><span class="sxs-lookup"><span data-stu-id="d4a57-116">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="d4a57-117">用户可以记住显示名称，如[ https://go.microsoft.com/fwlink/?prd=10929 ](https://go.microsoft.com/fwlink/?prd=10929)或[ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165)、 比基于数字的地址，如 207.46.131.137 更容易。</span><span class="sxs-lookup"><span data-stu-id="d4a57-117">Users can remember display names, such as [https://go.microsoft.com/fwlink/?prd=10929](https://go.microsoft.com/fwlink/?prd=10929) or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4a57-118">子元素</span><span class="sxs-lookup"><span data-stu-id="d4a57-118">Child Elements</span></span>  
 <span data-ttu-id="d4a57-119">无。</span><span class="sxs-lookup"><span data-stu-id="d4a57-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4a57-120">父元素</span><span class="sxs-lookup"><span data-stu-id="d4a57-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d4a57-121">元素</span><span class="sxs-lookup"><span data-stu-id="d4a57-121">Element</span></span>|<span data-ttu-id="d4a57-122">描述</span><span class="sxs-lookup"><span data-stu-id="d4a57-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4a57-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="d4a57-123">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="d4a57-124">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="d4a57-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d4a57-125">示例</span><span class="sxs-lookup"><span data-stu-id="d4a57-125">Example</span></span>  
 <span data-ttu-id="d4a57-126">下面的配置代码指定用于对服务器进行身份验证的 X.509 证书的 DNS。</span><span class="sxs-lookup"><span data-stu-id="d4a57-126">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="d4a57-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4a57-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="d4a57-128">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="d4a57-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d4a57-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="d4a57-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
