---
title: '&lt;servicePrincipalName&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f9b4ec506097cf010af78b3504def08102e0774
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceprincipalnamegt"></a><span data-ttu-id="f7048-102">&lt;servicePrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="f7048-102">&lt;servicePrincipalName&gt;</span></span>
<span data-ttu-id="f7048-103">利用对应的服务主体名称 (SPN) 指定服务的标识。</span><span class="sxs-lookup"><span data-stu-id="f7048-103">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="f7048-104">有关设置 SPN 的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="f7048-104">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="f7048-105">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="f7048-105">\<identity></span></span>  
<span data-ttu-id="f7048-106">\<servicePrincipalName ></span><span class="sxs-lookup"><span data-stu-id="f7048-106">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7048-107">语法</span><span class="sxs-lookup"><span data-stu-id="f7048-107">Syntax</span></span>  
  
```xml  
<servicePrincipalName value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7048-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f7048-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f7048-109">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f7048-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7048-110">特性</span><span class="sxs-lookup"><span data-stu-id="f7048-110">Attributes</span></span>  
  
|<span data-ttu-id="f7048-111">特性</span><span class="sxs-lookup"><span data-stu-id="f7048-111">Attribute</span></span>|<span data-ttu-id="f7048-112">描述</span><span class="sxs-lookup"><span data-stu-id="f7048-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7048-113">值</span><span class="sxs-lookup"><span data-stu-id="f7048-113">value</span></span>|<span data-ttu-id="f7048-114">客户端用来唯一地标识服务实例的名称。</span><span class="sxs-lookup"><span data-stu-id="f7048-114">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="f7048-115">如果在计算机的整个目录林上安装多个服务实例，那么每个实例都必须有自己的 SPN。</span><span class="sxs-lookup"><span data-stu-id="f7048-115">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="f7048-116">如果客户端有多个名称可用于身份验证，则给定的服务实例可以有多个 SPN。</span><span class="sxs-lookup"><span data-stu-id="f7048-116">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7048-117">子元素</span><span class="sxs-lookup"><span data-stu-id="f7048-117">Child Elements</span></span>  
 <span data-ttu-id="f7048-118">无。</span><span class="sxs-lookup"><span data-stu-id="f7048-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7048-119">父元素</span><span class="sxs-lookup"><span data-stu-id="f7048-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f7048-120">元素</span><span class="sxs-lookup"><span data-stu-id="f7048-120">Element</span></span>|<span data-ttu-id="f7048-121">描述</span><span class="sxs-lookup"><span data-stu-id="f7048-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7048-122">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="f7048-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="f7048-123">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="f7048-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7048-124">备注</span><span class="sxs-lookup"><span data-stu-id="f7048-124">Remarks</span></span>  
 <span data-ttu-id="f7048-125">通过此标识连接到终结点的安全 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 客户端在使用终结点进行 SSPI 身份验证时将使用 SPN。</span><span class="sxs-lookup"><span data-stu-id="f7048-125">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7048-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7048-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [<span data-ttu-id="f7048-127">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="f7048-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="f7048-128">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="f7048-128">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
