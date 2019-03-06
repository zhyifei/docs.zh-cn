---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: eb5459625cf58feeef5ba29d76e74691a4f87cc8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364692"
---
# <a name="dns"></a><span data-ttu-id="9b139-101">\<dns></span><span class="sxs-lookup"><span data-stu-id="9b139-101">\<dns></span></span>
<span data-ttu-id="9b139-102">指定服务器的所需标识。</span><span class="sxs-lookup"><span data-stu-id="9b139-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="9b139-103">如果服务器的证书包含具有相同值的 DNS，则此标识对于 X509 证书身份验证模式有效。</span><span class="sxs-lookup"><span data-stu-id="9b139-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="9b139-104">如果 SPN 具有相同值，则它对于 Windows 身份验证模式同样有效。</span><span class="sxs-lookup"><span data-stu-id="9b139-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="9b139-105">有关设置元素值的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="9b139-105">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="9b139-106">\<identity></span><span class="sxs-lookup"><span data-stu-id="9b139-106">\<identity></span></span>  
<span data-ttu-id="9b139-107">\<dns></span><span class="sxs-lookup"><span data-stu-id="9b139-107">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b139-108">语法</span><span class="sxs-lookup"><span data-stu-id="9b139-108">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b139-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9b139-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9b139-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9b139-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b139-111">特性</span><span class="sxs-lookup"><span data-stu-id="9b139-111">Attributes</span></span>  
  
|<span data-ttu-id="9b139-112">特性</span><span class="sxs-lookup"><span data-stu-id="9b139-112">Attribute</span></span>|<span data-ttu-id="9b139-113">描述</span><span class="sxs-lookup"><span data-stu-id="9b139-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b139-114">值</span><span class="sxs-lookup"><span data-stu-id="9b139-114">value</span></span>|<span data-ttu-id="9b139-115">证书的 DNS。</span><span class="sxs-lookup"><span data-stu-id="9b139-115">The DNS of the certificate.</span></span> <span data-ttu-id="9b139-116">DNS 是一个用于在基于 IP 网络上定位计算机的行业标准协议。</span><span class="sxs-lookup"><span data-stu-id="9b139-116">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="9b139-117">用户可以记住显示名称，如[ https://go.microsoft.com/fwlink/?prd=10929 ](https://go.microsoft.com/fwlink/?prd=10929)或[ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165)、 比基于数字的地址，如 207.46.131.137 更容易。</span><span class="sxs-lookup"><span data-stu-id="9b139-117">Users can remember display names, such as [https://go.microsoft.com/fwlink/?prd=10929](https://go.microsoft.com/fwlink/?prd=10929) or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b139-118">子元素</span><span class="sxs-lookup"><span data-stu-id="9b139-118">Child Elements</span></span>  
 <span data-ttu-id="9b139-119">无。</span><span class="sxs-lookup"><span data-stu-id="9b139-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b139-120">父元素</span><span class="sxs-lookup"><span data-stu-id="9b139-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9b139-121">元素</span><span class="sxs-lookup"><span data-stu-id="9b139-121">Element</span></span>|<span data-ttu-id="9b139-122">描述</span><span class="sxs-lookup"><span data-stu-id="9b139-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b139-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="9b139-123">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="9b139-124">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="9b139-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9b139-125">示例</span><span class="sxs-lookup"><span data-stu-id="9b139-125">Example</span></span>  
 <span data-ttu-id="9b139-126">下面的配置代码指定用于对服务器进行身份验证的 X.509 证书的 DNS。</span><span class="sxs-lookup"><span data-stu-id="9b139-126">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="9b139-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b139-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="9b139-128">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="9b139-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="9b139-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="9b139-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
