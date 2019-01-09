---
title: '&lt;claimTypeRequirements&gt; 的 &lt;clear&gt; 元素'
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 1e77e3c978c1e385aec983d5e2d4bea64697c43e
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145284"
---
# <a name="ltcleargt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="1b102-102">&lt;claimTypeRequirements&gt; 的 &lt;clear&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="1b102-102">&lt;clear&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="1b102-103">指定所有声明类型都将从联合凭据中移除。</span><span class="sxs-lookup"><span data-stu-id="1b102-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="1b102-104">这样可以确保集合最初为空。</span><span class="sxs-lookup"><span data-stu-id="1b102-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="1b102-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1b102-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="1b102-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="1b102-106">\<bindings></span></span>  
<span data-ttu-id="1b102-107">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="1b102-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="1b102-108">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="1b102-108">\<binding></span></span>  
<span data-ttu-id="1b102-109">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="1b102-109">\<security></span></span>  
<span data-ttu-id="1b102-110">\<message></span><span class="sxs-lookup"><span data-stu-id="1b102-110">\<message></span></span>  
<span data-ttu-id="1b102-111">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="1b102-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b102-112">语法</span><span class="sxs-lookup"><span data-stu-id="1b102-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b102-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1b102-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1b102-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1b102-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b102-115">特性</span><span class="sxs-lookup"><span data-stu-id="1b102-115">Attributes</span></span>  
 <span data-ttu-id="1b102-116">无。</span><span class="sxs-lookup"><span data-stu-id="1b102-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1b102-117">子元素</span><span class="sxs-lookup"><span data-stu-id="1b102-117">Child Elements</span></span>  
 <span data-ttu-id="1b102-118">无。</span><span class="sxs-lookup"><span data-stu-id="1b102-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b102-119">父元素</span><span class="sxs-lookup"><span data-stu-id="1b102-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1b102-120">元素</span><span class="sxs-lookup"><span data-stu-id="1b102-120">Element</span></span>|<span data-ttu-id="1b102-121">描述</span><span class="sxs-lookup"><span data-stu-id="1b102-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b102-122">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="1b102-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="1b102-123">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="1b102-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="1b102-124">每个元素的类型都为 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="1b102-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="1b102-125">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="1b102-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="1b102-126">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="1b102-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="1b102-127">此集合中的每个元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="1b102-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b102-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b102-128">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
