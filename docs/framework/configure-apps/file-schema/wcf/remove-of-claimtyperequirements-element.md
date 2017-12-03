---
title: "&lt;claimTypeRequirements&gt; 的 &lt;remove&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dde956ab80a41d15a6496f84432a2ae2a9d09b76
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltremovegt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="13078-102">&lt;claimTypeRequirements&gt; 的 &lt;remove&gt;元素</span><span class="sxs-lookup"><span data-stu-id="13078-102">&lt;remove&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="13078-103">指定要从联合凭据中移除的声明的类型。</span><span class="sxs-lookup"><span data-stu-id="13078-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="13078-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="13078-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="13078-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="13078-105">\<bindings></span></span>  
<span data-ttu-id="13078-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="13078-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="13078-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="13078-107">\<binding></span></span>  
<span data-ttu-id="13078-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="13078-108">\<security></span></span>  
<span data-ttu-id="13078-109">\<消息 ></span><span class="sxs-lookup"><span data-stu-id="13078-109">\<message></span></span>  
<span data-ttu-id="13078-110">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="13078-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13078-111">语法</span><span class="sxs-lookup"><span data-stu-id="13078-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>  
      <remove claimType="URI" />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13078-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="13078-112">Attributes and Elements</span></span>  
 <span data-ttu-id="13078-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="13078-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13078-114">特性</span><span class="sxs-lookup"><span data-stu-id="13078-114">Attributes</span></span>  
  
|<span data-ttu-id="13078-115">特性</span><span class="sxs-lookup"><span data-stu-id="13078-115">Attribute</span></span>|<span data-ttu-id="13078-116">描述</span><span class="sxs-lookup"><span data-stu-id="13078-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13078-117">claimType</span><span class="sxs-lookup"><span data-stu-id="13078-117">claimType</span></span>|<span data-ttu-id="13078-118">一个 URI，定义要移除的声明的类型。</span><span class="sxs-lookup"><span data-stu-id="13078-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13078-119">子元素</span><span class="sxs-lookup"><span data-stu-id="13078-119">Child Elements</span></span>  
 <span data-ttu-id="13078-120">无。</span><span class="sxs-lookup"><span data-stu-id="13078-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13078-121">父元素</span><span class="sxs-lookup"><span data-stu-id="13078-121">Parent Elements</span></span>  
  
|<span data-ttu-id="13078-122">元素</span><span class="sxs-lookup"><span data-stu-id="13078-122">Element</span></span>|<span data-ttu-id="13078-123">描述</span><span class="sxs-lookup"><span data-stu-id="13078-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13078-124">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="13078-124">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="13078-125">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="13078-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="13078-126">每个元素的类型都为 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="13078-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="13078-127">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="13078-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="13078-128">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="13078-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="13078-129">此集合中的每个元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="13078-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13078-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13078-130">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
