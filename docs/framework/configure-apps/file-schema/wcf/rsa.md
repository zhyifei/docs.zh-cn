---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 0e1651f563bdb2b2b24eacacf7bfe387e33a82c7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855041"
---
# <a name="rsa"></a><span data-ttu-id="3f573-101">\<rsa ></span><span class="sxs-lookup"><span data-stu-id="3f573-101">\<rsa></span></span>
<span data-ttu-id="3f573-102">通过此标识连接到终结点的安全 WCF 客户端将验证在服务器提供的众多声明中是否具有一个包含用于构建此标识的 RSA 公钥的声明。</span><span class="sxs-lookup"><span data-stu-id="3f573-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
<span data-ttu-id="3f573-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3f573-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3f573-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3f573-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3f573-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<客户端 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="3f573-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="3f573-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<终结点 >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="3f573-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="3f573-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<身份 >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="3f573-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="3f573-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<rsa >**</span><span class="sxs-lookup"><span data-stu-id="3f573-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rsa>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f573-109">语法</span><span class="sxs-lookup"><span data-stu-id="3f573-109">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f573-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3f573-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3f573-111">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3f573-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f573-112">特性</span><span class="sxs-lookup"><span data-stu-id="3f573-112">Attributes</span></span>  
  
|<span data-ttu-id="3f573-113">特性</span><span class="sxs-lookup"><span data-stu-id="3f573-113">Attribute</span></span>|<span data-ttu-id="3f573-114">描述</span><span class="sxs-lookup"><span data-stu-id="3f573-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f573-115">value</span><span class="sxs-lookup"><span data-stu-id="3f573-115">value</span></span>|<span data-ttu-id="3f573-116">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="3f573-116">Optional String.</span></span> <span data-ttu-id="3f573-117">客户端上要进行比较的 RSA 公钥值。</span><span class="sxs-lookup"><span data-stu-id="3f573-117">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f573-118">子元素</span><span class="sxs-lookup"><span data-stu-id="3f573-118">Child Elements</span></span>  
 <span data-ttu-id="3f573-119">无</span><span class="sxs-lookup"><span data-stu-id="3f573-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f573-120">父元素</span><span class="sxs-lookup"><span data-stu-id="3f573-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3f573-121">元素</span><span class="sxs-lookup"><span data-stu-id="3f573-121">Element</span></span>|<span data-ttu-id="3f573-122">描述</span><span class="sxs-lookup"><span data-stu-id="3f573-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f573-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="3f573-123">\<identity></span></span>](identity.md)|<span data-ttu-id="3f573-124">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="3f573-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f573-125">备注</span><span class="sxs-lookup"><span data-stu-id="3f573-125">Remarks</span></span>  
 <span data-ttu-id="3f573-126">您可以通过 RSA 检查将身份验证明确限制为单个基于其 RSA 密钥或生成的个人的 RSA 密钥值的证书。</span><span class="sxs-lookup"><span data-stu-id="3f573-126">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="3f573-127">这样将启用更为严格的特定 RSA 密钥身份验证，不过与此对应的代价是，如果更改 RSA 密钥值，则该服务不可再用于现有客户端。</span><span class="sxs-lookup"><span data-stu-id="3f573-127">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="3f573-128">有关使用标识向客户端验证服务的详细信息，请参阅[服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="3f573-128">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f573-129">示例</span><span class="sxs-lookup"><span data-stu-id="3f573-129">Example</span></span>  
 <span data-ttu-id="3f573-130">下面的配置代码指定用于对服务器进行身份验证的 X.509 证书的公钥值。</span><span class="sxs-lookup"><span data-stu-id="3f573-130">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="3f573-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f573-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="3f573-132">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="3f573-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3f573-133">\<identity></span><span class="sxs-lookup"><span data-stu-id="3f573-133">\<identity></span></span>](identity.md)
