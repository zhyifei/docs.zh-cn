---
title: <clear> <claimTypeRequirements>元素
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: b20d5c1808bf41d1ecd6b3e3a61606ae45b0fbdd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270333"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="5f485-102">\<清除 > 的\<claimTypeRequirements > 元素</span><span class="sxs-lookup"><span data-stu-id="5f485-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="5f485-103">指定所有声明类型都将从联合凭据中移除。</span><span class="sxs-lookup"><span data-stu-id="5f485-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="5f485-104">这样可以确保集合最初为空。</span><span class="sxs-lookup"><span data-stu-id="5f485-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="5f485-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5f485-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5f485-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5f485-106">\<bindings></span></span>  
<span data-ttu-id="5f485-107">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="5f485-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="5f485-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="5f485-108">\<binding></span></span>  
<span data-ttu-id="5f485-109">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="5f485-109">\<security></span></span>  
<span data-ttu-id="5f485-110">\<message></span><span class="sxs-lookup"><span data-stu-id="5f485-110">\<message></span></span>  
<span data-ttu-id="5f485-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="5f485-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f485-112">语法</span><span class="sxs-lookup"><span data-stu-id="5f485-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f485-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5f485-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5f485-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5f485-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f485-115">特性</span><span class="sxs-lookup"><span data-stu-id="5f485-115">Attributes</span></span>  
 <span data-ttu-id="5f485-116">无。</span><span class="sxs-lookup"><span data-stu-id="5f485-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5f485-117">子元素</span><span class="sxs-lookup"><span data-stu-id="5f485-117">Child Elements</span></span>  
 <span data-ttu-id="5f485-118">无。</span><span class="sxs-lookup"><span data-stu-id="5f485-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5f485-119">父元素</span><span class="sxs-lookup"><span data-stu-id="5f485-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5f485-120">元素</span><span class="sxs-lookup"><span data-stu-id="5f485-120">Element</span></span>|<span data-ttu-id="5f485-121">描述</span><span class="sxs-lookup"><span data-stu-id="5f485-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f485-122">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="5f485-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="5f485-123">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="5f485-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="5f485-124">每个元素的类型都为 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="5f485-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="5f485-125">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="5f485-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="5f485-126">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="5f485-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="5f485-127">此集合中的每个元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="5f485-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f485-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f485-128">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
