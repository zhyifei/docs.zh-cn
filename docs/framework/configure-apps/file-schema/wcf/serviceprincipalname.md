---
title: '&lt;ServicePrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: e5c1f5a6986d57d20180560b12f5c7c5540a590d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750721"
---
# <a name="ltserviceprincipalnamegt"></a><span data-ttu-id="dd9b7-102">&lt;ServicePrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="dd9b7-102">&lt;servicePrincipalName&gt;</span></span>
<span data-ttu-id="dd9b7-103">利用对应的服务主体名称 (SPN) 指定服务的标识。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-103">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="dd9b7-104">有关设置 SPN 的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-104">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="dd9b7-105">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="dd9b7-105">\<identity></span></span>  
<span data-ttu-id="dd9b7-106">\<servicePrincipalName ></span><span class="sxs-lookup"><span data-stu-id="dd9b7-106">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd9b7-107">语法</span><span class="sxs-lookup"><span data-stu-id="dd9b7-107">Syntax</span></span>  
  
```xml  
<servicePrincipalName value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd9b7-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dd9b7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dd9b7-109">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd9b7-110">特性</span><span class="sxs-lookup"><span data-stu-id="dd9b7-110">Attributes</span></span>  
  
|<span data-ttu-id="dd9b7-111">特性</span><span class="sxs-lookup"><span data-stu-id="dd9b7-111">Attribute</span></span>|<span data-ttu-id="dd9b7-112">描述</span><span class="sxs-lookup"><span data-stu-id="dd9b7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd9b7-113">值</span><span class="sxs-lookup"><span data-stu-id="dd9b7-113">value</span></span>|<span data-ttu-id="dd9b7-114">客户端用来唯一地标识服务实例的名称。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-114">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="dd9b7-115">如果在计算机的整个目录林上安装多个服务实例，那么每个实例都必须有自己的 SPN。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-115">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="dd9b7-116">如果客户端有多个名称可用于身份验证，则给定的服务实例可以有多个 SPN。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-116">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd9b7-117">子元素</span><span class="sxs-lookup"><span data-stu-id="dd9b7-117">Child Elements</span></span>  
 <span data-ttu-id="dd9b7-118">无。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd9b7-119">父元素</span><span class="sxs-lookup"><span data-stu-id="dd9b7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="dd9b7-120">元素</span><span class="sxs-lookup"><span data-stu-id="dd9b7-120">Element</span></span>|<span data-ttu-id="dd9b7-121">描述</span><span class="sxs-lookup"><span data-stu-id="dd9b7-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd9b7-122">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="dd9b7-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="dd9b7-123">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd9b7-124">备注</span><span class="sxs-lookup"><span data-stu-id="dd9b7-124">Remarks</span></span>  
 <span data-ttu-id="dd9b7-125">执行与终结点的 SSPI 身份验证时，连接到通过此标识终结点的安全的 Windows Communication Foundation (WCF) 客户端使用 SPN。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-125">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd9b7-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd9b7-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [<span data-ttu-id="dd9b7-127">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="dd9b7-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="dd9b7-128">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="dd9b7-128">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
