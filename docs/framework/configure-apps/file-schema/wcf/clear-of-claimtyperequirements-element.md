---
title: <clear> <claimTypeRequirements>元素
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 35d0391951204bd352918d3004f0cc4f9480b0e8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090309"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="e3d1d-102">\<清除 > 的\<claimTypeRequirements > 元素</span><span class="sxs-lookup"><span data-stu-id="e3d1d-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="e3d1d-103">指定所有声明类型都将从联合凭据中移除。</span><span class="sxs-lookup"><span data-stu-id="e3d1d-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="e3d1d-104">这样可以确保集合最初为空。</span><span class="sxs-lookup"><span data-stu-id="e3d1d-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="e3d1d-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e3d1d-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e3d1d-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e3d1d-106">\<bindings></span></span>  
<span data-ttu-id="e3d1d-107">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="e3d1d-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="e3d1d-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="e3d1d-108">\<binding></span></span>  
<span data-ttu-id="e3d1d-109">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="e3d1d-109">\<security></span></span>  
<span data-ttu-id="e3d1d-110">\<message></span><span class="sxs-lookup"><span data-stu-id="e3d1d-110">\<message></span></span>  
<span data-ttu-id="e3d1d-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="e3d1d-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3d1d-112">语法</span><span class="sxs-lookup"><span data-stu-id="e3d1d-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3d1d-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e3d1d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e3d1d-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e3d1d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3d1d-115">特性</span><span class="sxs-lookup"><span data-stu-id="e3d1d-115">Attributes</span></span>  
 <span data-ttu-id="e3d1d-116">无。</span><span class="sxs-lookup"><span data-stu-id="e3d1d-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e3d1d-117">子元素</span><span class="sxs-lookup"><span data-stu-id="e3d1d-117">Child Elements</span></span>  
 <span data-ttu-id="e3d1d-118">无。</span><span class="sxs-lookup"><span data-stu-id="e3d1d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3d1d-119">父元素</span><span class="sxs-lookup"><span data-stu-id="e3d1d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e3d1d-120">元素</span><span class="sxs-lookup"><span data-stu-id="e3d1d-120">Element</span></span>|<span data-ttu-id="e3d1d-121">描述</span><span class="sxs-lookup"><span data-stu-id="e3d1d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3d1d-122">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="e3d1d-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="e3d1d-123">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="e3d1d-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="e3d1d-124">每个元素的类型都为 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="e3d1d-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="e3d1d-125">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="e3d1d-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="e3d1d-126">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="e3d1d-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="e3d1d-127">此集合中的每个元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="e3d1d-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3d1d-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3d1d-128">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
