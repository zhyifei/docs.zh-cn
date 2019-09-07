---
title: <clear>of <claimTypeRequirements>元素
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 01f101f7d0dd5da6a834a4ffb2c7e09df0e23cd8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400527"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="1ee36-102">\<清除 claimTypeRequirements > \<元素的 ></span><span class="sxs-lookup"><span data-stu-id="1ee36-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="1ee36-103">指定所有声明类型都将从联合凭据中移除。</span><span class="sxs-lookup"><span data-stu-id="1ee36-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="1ee36-104">这样可以确保集合最初为空。</span><span class="sxs-lookup"><span data-stu-id="1ee36-104">This ensures that the collection starts empty.</span></span>  
  
<span data-ttu-id="1ee36-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1ee36-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1ee36-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1ee36-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1ee36-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="1ee36-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="1ee36-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="1ee36-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="1ee36-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="1ee36-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="1ee36-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="1ee36-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="1ee36-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<消息 >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="1ee36-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="1ee36-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimTypeRequirements >** ](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="1ee36-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="1ee36-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<清除 >**</span><span class="sxs-lookup"><span data-stu-id="1ee36-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ee36-114">语法</span><span class="sxs-lookup"><span data-stu-id="1ee36-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ee36-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1ee36-115">Attributes and Elements</span></span>  
 <span data-ttu-id="1ee36-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1ee36-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ee36-117">特性</span><span class="sxs-lookup"><span data-stu-id="1ee36-117">Attributes</span></span>  
 <span data-ttu-id="1ee36-118">无。</span><span class="sxs-lookup"><span data-stu-id="1ee36-118">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1ee36-119">子元素</span><span class="sxs-lookup"><span data-stu-id="1ee36-119">Child Elements</span></span>  
 <span data-ttu-id="1ee36-120">无。</span><span class="sxs-lookup"><span data-stu-id="1ee36-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ee36-121">父元素</span><span class="sxs-lookup"><span data-stu-id="1ee36-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1ee36-122">元素</span><span class="sxs-lookup"><span data-stu-id="1ee36-122">Element</span></span>|<span data-ttu-id="1ee36-123">描述</span><span class="sxs-lookup"><span data-stu-id="1ee36-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ee36-124">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="1ee36-124">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="1ee36-125">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="1ee36-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="1ee36-126">每个元素的类型都为 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="1ee36-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="1ee36-127">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="1ee36-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="1ee36-128">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="1ee36-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="1ee36-129">此集合中的每个元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="1ee36-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ee36-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ee36-130">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
