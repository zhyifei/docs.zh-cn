---
title: <remove> <claimTypeRequirements>元素
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 8058a90d61d8f94944d98a26c59bfbe225f611d5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259494"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="da725-102">\<删除 > 的\<claimTypeRequirements > 元素</span><span class="sxs-lookup"><span data-stu-id="da725-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="da725-103">指定要从联合凭据中移除的声明的类型。</span><span class="sxs-lookup"><span data-stu-id="da725-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="da725-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="da725-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="da725-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="da725-105">\<bindings></span></span>  
<span data-ttu-id="da725-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="da725-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="da725-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="da725-107">\<binding></span></span>  
<span data-ttu-id="da725-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="da725-108">\<security></span></span>  
<span data-ttu-id="da725-109">\<message></span><span class="sxs-lookup"><span data-stu-id="da725-109">\<message></span></span>  
<span data-ttu-id="da725-110">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="da725-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da725-111">语法</span><span class="sxs-lookup"><span data-stu-id="da725-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da725-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="da725-112">Attributes and Elements</span></span>  
 <span data-ttu-id="da725-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="da725-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da725-114">特性</span><span class="sxs-lookup"><span data-stu-id="da725-114">Attributes</span></span>  
  
|<span data-ttu-id="da725-115">特性</span><span class="sxs-lookup"><span data-stu-id="da725-115">Attribute</span></span>|<span data-ttu-id="da725-116">描述</span><span class="sxs-lookup"><span data-stu-id="da725-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da725-117">claimType</span><span class="sxs-lookup"><span data-stu-id="da725-117">claimType</span></span>|<span data-ttu-id="da725-118">一个 URI，定义要移除的声明的类型。</span><span class="sxs-lookup"><span data-stu-id="da725-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da725-119">子元素</span><span class="sxs-lookup"><span data-stu-id="da725-119">Child Elements</span></span>  
 <span data-ttu-id="da725-120">无。</span><span class="sxs-lookup"><span data-stu-id="da725-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da725-121">父元素</span><span class="sxs-lookup"><span data-stu-id="da725-121">Parent Elements</span></span>  
  
|<span data-ttu-id="da725-122">元素</span><span class="sxs-lookup"><span data-stu-id="da725-122">Element</span></span>|<span data-ttu-id="da725-123">描述</span><span class="sxs-lookup"><span data-stu-id="da725-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da725-124">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="da725-124">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="da725-125">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="da725-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="da725-126">每个元素的类型都为 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="da725-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="da725-127">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="da725-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="da725-128">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="da725-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="da725-129">此集合中的每个元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="da725-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da725-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="da725-130">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
