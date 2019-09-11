---
title: <certificate> 的 <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 1cfd207afc72cc71359d9d262e30b0696ba63d2b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850012"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="ecc43-102">\<标识 > 的\<证书 ></span><span class="sxs-lookup"><span data-stu-id="ecc43-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="ecc43-103">指定用于向客户端验证服务器的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="ecc43-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
<span data-ttu-id="ecc43-104">有关设置元素值的详细信息，请参阅[服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="ecc43-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="ecc43-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ecc43-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ecc43-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ecc43-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ecc43-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<客户端 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="ecc43-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="ecc43-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<终结点 >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="ecc43-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="ecc43-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<身份 >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="ecc43-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="ecc43-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<证书 >**</span><span class="sxs-lookup"><span data-stu-id="ecc43-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecc43-111">语法</span><span class="sxs-lookup"><span data-stu-id="ecc43-111">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ecc43-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ecc43-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ecc43-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ecc43-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ecc43-114">特性</span><span class="sxs-lookup"><span data-stu-id="ecc43-114">Attributes</span></span>  
  
|<span data-ttu-id="ecc43-115">特性</span><span class="sxs-lookup"><span data-stu-id="ecc43-115">Attribute</span></span>|<span data-ttu-id="ecc43-116">描述</span><span class="sxs-lookup"><span data-stu-id="ecc43-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ecc43-117">encodedValue</span><span class="sxs-lookup"><span data-stu-id="ecc43-117">encodedValue</span></span>|<span data-ttu-id="ecc43-118">证书的 Base64 编码。</span><span class="sxs-lookup"><span data-stu-id="ecc43-118">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ecc43-119">子元素</span><span class="sxs-lookup"><span data-stu-id="ecc43-119">Child Elements</span></span>  
 <span data-ttu-id="ecc43-120">无。</span><span class="sxs-lookup"><span data-stu-id="ecc43-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ecc43-121">父元素</span><span class="sxs-lookup"><span data-stu-id="ecc43-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ecc43-122">元素</span><span class="sxs-lookup"><span data-stu-id="ecc43-122">Element</span></span>|<span data-ttu-id="ecc43-123">描述</span><span class="sxs-lookup"><span data-stu-id="ecc43-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ecc43-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="ecc43-124">\<identity></span></span>](identity.md)|<span data-ttu-id="ecc43-125">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="ecc43-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ecc43-126">示例</span><span class="sxs-lookup"><span data-stu-id="ecc43-126">Example</span></span>  
 <span data-ttu-id="ecc43-127">下面的代码指定用于向客户端验证服务器的证书的编码表示形式。</span><span class="sxs-lookup"><span data-stu-id="ecc43-127">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="ecc43-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecc43-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="ecc43-129">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="ecc43-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ecc43-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="ecc43-130">\<identity></span></span>](identity.md)
