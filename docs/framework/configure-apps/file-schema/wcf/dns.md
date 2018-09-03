---
title: '&lt;dns&gt;'
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 2f5b9d5e1bc57230adbb32664e9ae15d3c71d46f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43472028"
---
# <a name="ltdnsgt"></a><span data-ttu-id="751af-102">&lt;dns&gt;</span><span class="sxs-lookup"><span data-stu-id="751af-102">&lt;dns&gt;</span></span>
<span data-ttu-id="751af-103">指定服务器的所需标识。</span><span class="sxs-lookup"><span data-stu-id="751af-103">Specifies the expected identity of the server.</span></span> <span data-ttu-id="751af-104">如果服务器的证书包含具有相同值的 DNS，则此标识对于 X509 证书身份验证模式有效。</span><span class="sxs-lookup"><span data-stu-id="751af-104">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="751af-105">如果 SPN 具有相同值，则它对于 Windows 身份验证模式同样有效。</span><span class="sxs-lookup"><span data-stu-id="751af-105">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="751af-106">有关设置元素值的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="751af-106">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="751af-107">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="751af-107">\<identity></span></span>  
<span data-ttu-id="751af-108">\<dns ></span><span class="sxs-lookup"><span data-stu-id="751af-108">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="751af-109">语法</span><span class="sxs-lookup"><span data-stu-id="751af-109">Syntax</span></span>  
  
```xml  
<dns value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="751af-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="751af-110">Attributes and Elements</span></span>  
 <span data-ttu-id="751af-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="751af-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="751af-112">特性</span><span class="sxs-lookup"><span data-stu-id="751af-112">Attributes</span></span>  
  
|<span data-ttu-id="751af-113">特性</span><span class="sxs-lookup"><span data-stu-id="751af-113">Attribute</span></span>|<span data-ttu-id="751af-114">描述</span><span class="sxs-lookup"><span data-stu-id="751af-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="751af-115">值</span><span class="sxs-lookup"><span data-stu-id="751af-115">value</span></span>|<span data-ttu-id="751af-116">证书的 DNS。</span><span class="sxs-lookup"><span data-stu-id="751af-116">The DNS of the certificate.</span></span> <span data-ttu-id="751af-117">DNS 是一个用于在基于 IP 网络上定位计算机的行业标准协议。</span><span class="sxs-lookup"><span data-stu-id="751af-117">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="751af-118">用户可以记住显示名称，如[ https://go.microsoft.com/fwlink/?prd=10929 ](https://go.microsoft.com/fwlink/?prd=10929)或[ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165)、 比基于数字的地址，如 207.46.131.137 更容易。</span><span class="sxs-lookup"><span data-stu-id="751af-118">Users can remember display names, such as [https://go.microsoft.com/fwlink/?prd=10929](https://go.microsoft.com/fwlink/?prd=10929) or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="751af-119">子元素</span><span class="sxs-lookup"><span data-stu-id="751af-119">Child Elements</span></span>  
 <span data-ttu-id="751af-120">无。</span><span class="sxs-lookup"><span data-stu-id="751af-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="751af-121">父元素</span><span class="sxs-lookup"><span data-stu-id="751af-121">Parent Elements</span></span>  
  
|<span data-ttu-id="751af-122">元素</span><span class="sxs-lookup"><span data-stu-id="751af-122">Element</span></span>|<span data-ttu-id="751af-123">描述</span><span class="sxs-lookup"><span data-stu-id="751af-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="751af-124">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="751af-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="751af-125">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="751af-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="751af-126">示例</span><span class="sxs-lookup"><span data-stu-id="751af-126">Example</span></span>  
 <span data-ttu-id="751af-127">下面的配置代码指定用于对服务器进行身份验证的 X.509 证书的 DNS。</span><span class="sxs-lookup"><span data-stu-id="751af-127">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>  
  <dns value = "www.cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="751af-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="751af-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.DnsEndpointIdentity>  
 [<span data-ttu-id="751af-129">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="751af-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="751af-130">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="751af-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
