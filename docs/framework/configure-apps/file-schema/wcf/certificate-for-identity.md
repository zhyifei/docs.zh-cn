---
title: '&lt;identity&gt; 的 &lt;certificate&gt;'
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: e7d8e7abbc95521d85dc5999c36687f9becea9fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltcertificategt-for-ltidentitygt"></a><span data-ttu-id="4c0cd-102">&lt;identity&gt; 的 &lt;certificate&gt;</span><span class="sxs-lookup"><span data-stu-id="4c0cd-102">&lt;certificate&gt; for &lt;identity&gt;</span></span>
<span data-ttu-id="4c0cd-103">指定用于向客户端验证服务器的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="4c0cd-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="4c0cd-104">有关设置此元素的值的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="4c0cd-104">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="4c0cd-105">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="4c0cd-105">\<identity></span></span>  
<span data-ttu-id="4c0cd-106">\<证书 ></span><span class="sxs-lookup"><span data-stu-id="4c0cd-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c0cd-107">语法</span><span class="sxs-lookup"><span data-stu-id="4c0cd-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c0cd-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4c0cd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4c0cd-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4c0cd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c0cd-110">特性</span><span class="sxs-lookup"><span data-stu-id="4c0cd-110">Attributes</span></span>  
  
|<span data-ttu-id="4c0cd-111">特性</span><span class="sxs-lookup"><span data-stu-id="4c0cd-111">Attribute</span></span>|<span data-ttu-id="4c0cd-112">描述</span><span class="sxs-lookup"><span data-stu-id="4c0cd-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c0cd-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="4c0cd-113">encodedValue</span></span>|<span data-ttu-id="4c0cd-114">证书的 Base64 编码。</span><span class="sxs-lookup"><span data-stu-id="4c0cd-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c0cd-115">子元素</span><span class="sxs-lookup"><span data-stu-id="4c0cd-115">Child Elements</span></span>  
 <span data-ttu-id="4c0cd-116">无。</span><span class="sxs-lookup"><span data-stu-id="4c0cd-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c0cd-117">父元素</span><span class="sxs-lookup"><span data-stu-id="4c0cd-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4c0cd-118">元素</span><span class="sxs-lookup"><span data-stu-id="4c0cd-118">Element</span></span>|<span data-ttu-id="4c0cd-119">描述</span><span class="sxs-lookup"><span data-stu-id="4c0cd-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c0cd-120">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="4c0cd-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="4c0cd-121">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="4c0cd-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4c0cd-122">示例</span><span class="sxs-lookup"><span data-stu-id="4c0cd-122">Example</span></span>  
 <span data-ttu-id="4c0cd-123">下面的代码指定用于向客户端验证服务器的证书的编码表示形式。</span><span class="sxs-lookup"><span data-stu-id="4c0cd-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>  
  <certificate encodedValue = " MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c0cd-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c0cd-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.EndpointIdentity>  
 [<span data-ttu-id="4c0cd-125">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="4c0cd-125">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="4c0cd-126">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="4c0cd-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
