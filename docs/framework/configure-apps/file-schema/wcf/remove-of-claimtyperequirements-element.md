---
title: <remove>of <claimTypeRequirements>元素
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 84f4208d3f4581cf7e8c4455bf3f5d78f7e13b9f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399989"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="bf1bb-102">\<删除 claimTypeRequirements > \<元素的 ></span><span class="sxs-lookup"><span data-stu-id="bf1bb-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="bf1bb-103">指定要从联合凭据中移除的声明的类型。</span><span class="sxs-lookup"><span data-stu-id="bf1bb-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
<span data-ttu-id="bf1bb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bf1bb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bf1bb-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bf1bb-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bf1bb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="bf1bb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="bf1bb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="bf1bb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="bf1bb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="bf1bb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="bf1bb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="bf1bb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="bf1bb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<消息 >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="bf1bb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="bf1bb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimTypeRequirements >** ](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="bf1bb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="bf1bb-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<删除 >**</span><span class="sxs-lookup"><span data-stu-id="bf1bb-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf1bb-113">语法</span><span class="sxs-lookup"><span data-stu-id="bf1bb-113">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf1bb-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bf1bb-114">Attributes and Elements</span></span>  
 <span data-ttu-id="bf1bb-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bf1bb-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf1bb-116">特性</span><span class="sxs-lookup"><span data-stu-id="bf1bb-116">Attributes</span></span>  
  
|<span data-ttu-id="bf1bb-117">特性</span><span class="sxs-lookup"><span data-stu-id="bf1bb-117">Attribute</span></span>|<span data-ttu-id="bf1bb-118">描述</span><span class="sxs-lookup"><span data-stu-id="bf1bb-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf1bb-119">claimType</span><span class="sxs-lookup"><span data-stu-id="bf1bb-119">claimType</span></span>|<span data-ttu-id="bf1bb-120">一个 URI，定义要移除的声明的类型。</span><span class="sxs-lookup"><span data-stu-id="bf1bb-120">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf1bb-121">子元素</span><span class="sxs-lookup"><span data-stu-id="bf1bb-121">Child Elements</span></span>  
 <span data-ttu-id="bf1bb-122">无。</span><span class="sxs-lookup"><span data-stu-id="bf1bb-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bf1bb-123">父元素</span><span class="sxs-lookup"><span data-stu-id="bf1bb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bf1bb-124">元素</span><span class="sxs-lookup"><span data-stu-id="bf1bb-124">Element</span></span>|<span data-ttu-id="bf1bb-125">描述</span><span class="sxs-lookup"><span data-stu-id="bf1bb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf1bb-126">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="bf1bb-126">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="bf1bb-127">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="bf1bb-127">Specifies a collection of required claim types.</span></span> <span data-ttu-id="bf1bb-128">每个元素的类型都为 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="bf1bb-128">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="bf1bb-129">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="bf1bb-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="bf1bb-130">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="bf1bb-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="bf1bb-131">此集合中的每个元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="bf1bb-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf1bb-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf1bb-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
