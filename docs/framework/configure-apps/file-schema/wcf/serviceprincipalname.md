---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 75e95bcbaee229f19bdfdd119b548ed612f4ddaa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758179"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="fb221-101">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="fb221-101">\<servicePrincipalName></span></span>
<span data-ttu-id="fb221-102">利用对应的服务主体名称 (SPN) 指定服务的标识。</span><span class="sxs-lookup"><span data-stu-id="fb221-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="fb221-103">有关设置 SPN 的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="fb221-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="fb221-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="fb221-104">\<identity></span></span>  
<span data-ttu-id="fb221-105">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="fb221-105">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb221-106">语法</span><span class="sxs-lookup"><span data-stu-id="fb221-106">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb221-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fb221-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fb221-108">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fb221-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb221-109">特性</span><span class="sxs-lookup"><span data-stu-id="fb221-109">Attributes</span></span>  
  
|<span data-ttu-id="fb221-110">特性</span><span class="sxs-lookup"><span data-stu-id="fb221-110">Attribute</span></span>|<span data-ttu-id="fb221-111">描述</span><span class="sxs-lookup"><span data-stu-id="fb221-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb221-112">值</span><span class="sxs-lookup"><span data-stu-id="fb221-112">value</span></span>|<span data-ttu-id="fb221-113">客户端用来唯一地标识服务实例的名称。</span><span class="sxs-lookup"><span data-stu-id="fb221-113">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="fb221-114">如果在计算机的整个目录林上安装多个服务实例，那么每个实例都必须有自己的 SPN。</span><span class="sxs-lookup"><span data-stu-id="fb221-114">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="fb221-115">如果客户端有多个名称可用于身份验证，则给定的服务实例可以有多个 SPN。</span><span class="sxs-lookup"><span data-stu-id="fb221-115">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb221-116">子元素</span><span class="sxs-lookup"><span data-stu-id="fb221-116">Child Elements</span></span>  
 <span data-ttu-id="fb221-117">无。</span><span class="sxs-lookup"><span data-stu-id="fb221-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb221-118">父元素</span><span class="sxs-lookup"><span data-stu-id="fb221-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fb221-119">元素</span><span class="sxs-lookup"><span data-stu-id="fb221-119">Element</span></span>|<span data-ttu-id="fb221-120">描述</span><span class="sxs-lookup"><span data-stu-id="fb221-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb221-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="fb221-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="fb221-122">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="fb221-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb221-123">备注</span><span class="sxs-lookup"><span data-stu-id="fb221-123">Remarks</span></span>  
 <span data-ttu-id="fb221-124">执行使用该终结点进行 SSPI 身份验证时，连接到此标识的终结点的安全 Windows Communication Foundation (WCF) 客户端使用 SPN。</span><span class="sxs-lookup"><span data-stu-id="fb221-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb221-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb221-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="fb221-126">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="fb221-126">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fb221-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="fb221-127">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
