---
title: <certificate> 的 <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 52d1fa31cebd949c91809464976739ef1334af29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919620"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="cd083-102">\<标识 > 的\<证书 ></span><span class="sxs-lookup"><span data-stu-id="cd083-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="cd083-103">指定用于向客户端验证服务器的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="cd083-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="cd083-104">有关设置元素值的详细信息, 请参阅[服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="cd083-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="cd083-105">\<身份 ></span><span class="sxs-lookup"><span data-stu-id="cd083-105">\<identity></span></span>  
<span data-ttu-id="cd083-106">\<证书 ></span><span class="sxs-lookup"><span data-stu-id="cd083-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd083-107">语法</span><span class="sxs-lookup"><span data-stu-id="cd083-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd083-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cd083-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cd083-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cd083-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd083-110">特性</span><span class="sxs-lookup"><span data-stu-id="cd083-110">Attributes</span></span>  
  
|<span data-ttu-id="cd083-111">特性</span><span class="sxs-lookup"><span data-stu-id="cd083-111">Attribute</span></span>|<span data-ttu-id="cd083-112">描述</span><span class="sxs-lookup"><span data-stu-id="cd083-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd083-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="cd083-113">encodedValue</span></span>|<span data-ttu-id="cd083-114">证书的 Base64 编码。</span><span class="sxs-lookup"><span data-stu-id="cd083-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd083-115">子元素</span><span class="sxs-lookup"><span data-stu-id="cd083-115">Child Elements</span></span>  
 <span data-ttu-id="cd083-116">无。</span><span class="sxs-lookup"><span data-stu-id="cd083-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd083-117">父元素</span><span class="sxs-lookup"><span data-stu-id="cd083-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cd083-118">元素</span><span class="sxs-lookup"><span data-stu-id="cd083-118">Element</span></span>|<span data-ttu-id="cd083-119">描述</span><span class="sxs-lookup"><span data-stu-id="cd083-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd083-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="cd083-120">\<identity></span></span>](identity.md)|<span data-ttu-id="cd083-121">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="cd083-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cd083-122">示例</span><span class="sxs-lookup"><span data-stu-id="cd083-122">Example</span></span>  
 <span data-ttu-id="cd083-123">下面的代码指定用于向客户端验证服务器的证书的编码表示形式。</span><span class="sxs-lookup"><span data-stu-id="cd083-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="cd083-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd083-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="cd083-125">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="cd083-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="cd083-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="cd083-126">\<identity></span></span>](identity.md)
