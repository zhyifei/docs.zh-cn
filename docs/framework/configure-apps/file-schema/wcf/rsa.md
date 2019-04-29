---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 0e307069bd3a98153cc66147ba7bcf511cf13a8e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670647"
---
# <a name="rsa"></a><span data-ttu-id="11d9c-101">\<rsa></span><span class="sxs-lookup"><span data-stu-id="11d9c-101">\<rsa></span></span>
<span data-ttu-id="11d9c-102">通过此标识连接到终结点的安全 WCF 客户端将验证在服务器提供的众多声明中是否具有一个包含用于构建此标识的 RSA 公钥的声明。</span><span class="sxs-lookup"><span data-stu-id="11d9c-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="11d9c-103">\<identity></span><span class="sxs-lookup"><span data-stu-id="11d9c-103">\<identity></span></span>  
<span data-ttu-id="11d9c-104">\<rsa></span><span class="sxs-lookup"><span data-stu-id="11d9c-104">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11d9c-105">语法</span><span class="sxs-lookup"><span data-stu-id="11d9c-105">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11d9c-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="11d9c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="11d9c-107">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="11d9c-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11d9c-108">特性</span><span class="sxs-lookup"><span data-stu-id="11d9c-108">Attributes</span></span>  
  
|<span data-ttu-id="11d9c-109">特性</span><span class="sxs-lookup"><span data-stu-id="11d9c-109">Attribute</span></span>|<span data-ttu-id="11d9c-110">描述</span><span class="sxs-lookup"><span data-stu-id="11d9c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="11d9c-111">值</span><span class="sxs-lookup"><span data-stu-id="11d9c-111">value</span></span>|<span data-ttu-id="11d9c-112">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="11d9c-112">Optional String.</span></span> <span data-ttu-id="11d9c-113">客户端上要进行比较的 RSA 公钥值。</span><span class="sxs-lookup"><span data-stu-id="11d9c-113">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11d9c-114">子元素</span><span class="sxs-lookup"><span data-stu-id="11d9c-114">Child Elements</span></span>  
 <span data-ttu-id="11d9c-115">None</span><span class="sxs-lookup"><span data-stu-id="11d9c-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="11d9c-116">父元素</span><span class="sxs-lookup"><span data-stu-id="11d9c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="11d9c-117">元素</span><span class="sxs-lookup"><span data-stu-id="11d9c-117">Element</span></span>|<span data-ttu-id="11d9c-118">描述</span><span class="sxs-lookup"><span data-stu-id="11d9c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11d9c-119">\<identity></span><span class="sxs-lookup"><span data-stu-id="11d9c-119">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="11d9c-120">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="11d9c-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11d9c-121">备注</span><span class="sxs-lookup"><span data-stu-id="11d9c-121">Remarks</span></span>  
 <span data-ttu-id="11d9c-122">您可以通过 RSA 检查将身份验证明确限制为单个基于其 RSA 密钥或生成的个人的 RSA 密钥值的证书。</span><span class="sxs-lookup"><span data-stu-id="11d9c-122">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="11d9c-123">这样将启用更为严格的特定 RSA 密钥身份验证，不过与此对应的代价是，如果更改 RSA 密钥值，则该服务不可再用于现有客户端。</span><span class="sxs-lookup"><span data-stu-id="11d9c-123">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="11d9c-124">有关使用标识来验证客户端到服务的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="11d9c-124">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="11d9c-125">示例</span><span class="sxs-lookup"><span data-stu-id="11d9c-125">Example</span></span>  
 <span data-ttu-id="11d9c-126">下面的配置代码指定用于对服务器进行身份验证的 X.509 证书的公钥值。</span><span class="sxs-lookup"><span data-stu-id="11d9c-126">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="11d9c-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="11d9c-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="11d9c-128">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="11d9c-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="11d9c-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="11d9c-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
