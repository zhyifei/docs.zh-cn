---
title: '&lt;claimTypeRequirements&gt; 的 &lt;remove&gt;元素'
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 7610a8e95996f15133ae58ec33c4afd9e2309cac
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146207"
---
# <a name="ltremovegt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="afb05-102">&lt;claimTypeRequirements&gt; 的 &lt;remove&gt;元素</span><span class="sxs-lookup"><span data-stu-id="afb05-102">&lt;remove&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="afb05-103">指定要从联合凭据中移除的声明的类型。</span><span class="sxs-lookup"><span data-stu-id="afb05-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="afb05-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="afb05-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="afb05-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="afb05-105">\<bindings></span></span>  
<span data-ttu-id="afb05-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="afb05-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="afb05-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="afb05-107">\<binding></span></span>  
<span data-ttu-id="afb05-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="afb05-108">\<security></span></span>  
<span data-ttu-id="afb05-109">\<message></span><span class="sxs-lookup"><span data-stu-id="afb05-109">\<message></span></span>  
<span data-ttu-id="afb05-110">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="afb05-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afb05-111">语法</span><span class="sxs-lookup"><span data-stu-id="afb05-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afb05-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="afb05-112">Attributes and Elements</span></span>  
 <span data-ttu-id="afb05-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="afb05-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afb05-114">特性</span><span class="sxs-lookup"><span data-stu-id="afb05-114">Attributes</span></span>  
  
|<span data-ttu-id="afb05-115">特性</span><span class="sxs-lookup"><span data-stu-id="afb05-115">Attribute</span></span>|<span data-ttu-id="afb05-116">描述</span><span class="sxs-lookup"><span data-stu-id="afb05-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="afb05-117">claimType</span><span class="sxs-lookup"><span data-stu-id="afb05-117">claimType</span></span>|<span data-ttu-id="afb05-118">一个 URI，定义要移除的声明的类型。</span><span class="sxs-lookup"><span data-stu-id="afb05-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="afb05-119">子元素</span><span class="sxs-lookup"><span data-stu-id="afb05-119">Child Elements</span></span>  
 <span data-ttu-id="afb05-120">无。</span><span class="sxs-lookup"><span data-stu-id="afb05-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="afb05-121">父元素</span><span class="sxs-lookup"><span data-stu-id="afb05-121">Parent Elements</span></span>  
  
|<span data-ttu-id="afb05-122">元素</span><span class="sxs-lookup"><span data-stu-id="afb05-122">Element</span></span>|<span data-ttu-id="afb05-123">描述</span><span class="sxs-lookup"><span data-stu-id="afb05-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afb05-124">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="afb05-124">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="afb05-125">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="afb05-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="afb05-126">每个元素的类型都为 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="afb05-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="afb05-127">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="afb05-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="afb05-128">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="afb05-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="afb05-129">此集合中的每个元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="afb05-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="afb05-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="afb05-130">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
