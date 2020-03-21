---
title: <add>元素<claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: f6948052c62684faa734b592f5bdfc2e7827a07a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153095"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="76ca5-102">\<添加\<>索赔类型需求>元素</span><span class="sxs-lookup"><span data-stu-id="76ca5-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="76ca5-103">指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="76ca5-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="76ca5-104">例如，服务规定有关传入凭据的要求，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="76ca5-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="76ca5-105">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="76ca5-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="76ca5-106">&nbsp;&nbsp;[**\<系统.服务模式>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="76ca5-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="76ca5-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<绑定>**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="76ca5-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="76ca5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws 联邦http绑定>**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="76ca5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="76ca5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<绑定>**</span><span class="sxs-lookup"><span data-stu-id="76ca5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="76ca5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全>**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="76ca5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="76ca5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<消息>**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="76ca5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="76ca5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<索赔类型要求>**](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="76ca5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="76ca5-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<添加>**</span><span class="sxs-lookup"><span data-stu-id="76ca5-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="76ca5-114">语法</span><span class="sxs-lookup"><span data-stu-id="76ca5-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76ca5-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="76ca5-115">Attributes and Elements</span></span>  
 <span data-ttu-id="76ca5-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="76ca5-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76ca5-117">属性</span><span class="sxs-lookup"><span data-stu-id="76ca5-117">Attributes</span></span>  
  
|<span data-ttu-id="76ca5-118">Attribute</span><span class="sxs-lookup"><span data-stu-id="76ca5-118">Attribute</span></span>|<span data-ttu-id="76ca5-119">说明</span><span class="sxs-lookup"><span data-stu-id="76ca5-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76ca5-120">claimType</span><span class="sxs-lookup"><span data-stu-id="76ca5-120">claimType</span></span>|<span data-ttu-id="76ca5-121">一个 URI，定义声明类型。</span><span class="sxs-lookup"><span data-stu-id="76ca5-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="76ca5-122">例如，若要从网站上购买产品，用户必须提供具有足够信用额度的有效信用卡。</span><span class="sxs-lookup"><span data-stu-id="76ca5-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="76ca5-123">声明类型将为信用卡 URI。</span><span class="sxs-lookup"><span data-stu-id="76ca5-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="76ca5-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="76ca5-124">isOptional</span></span>|<span data-ttu-id="76ca5-125">一个布尔值，指定声明是否为可选的。</span><span class="sxs-lookup"><span data-stu-id="76ca5-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="76ca5-126">如果声明是必选的，则将此属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="76ca5-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="76ca5-127">当服务请求一些并非必要的信息时，可以使用此属性。</span><span class="sxs-lookup"><span data-stu-id="76ca5-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="76ca5-128">例如，如果要求用户输入其名字、姓氏和地址，但确定该电话号码是可选的。</span><span class="sxs-lookup"><span data-stu-id="76ca5-128">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76ca5-129">子元素</span><span class="sxs-lookup"><span data-stu-id="76ca5-129">Child Elements</span></span>  
 <span data-ttu-id="76ca5-130">无。</span><span class="sxs-lookup"><span data-stu-id="76ca5-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76ca5-131">父元素</span><span class="sxs-lookup"><span data-stu-id="76ca5-131">Parent Elements</span></span>  
  
|<span data-ttu-id="76ca5-132">元素</span><span class="sxs-lookup"><span data-stu-id="76ca5-132">Element</span></span>|<span data-ttu-id="76ca5-133">说明</span><span class="sxs-lookup"><span data-stu-id="76ca5-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76ca5-134">\<索赔类型要求></span><span class="sxs-lookup"><span data-stu-id="76ca5-134">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="76ca5-135">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="76ca5-135">Specifies a collection of required claim types.</span></span> <span data-ttu-id="76ca5-136">每个元素的类型都为 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。</span><span class="sxs-lookup"><span data-stu-id="76ca5-136">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="76ca5-137">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="76ca5-137">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="76ca5-138">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="76ca5-138">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="76ca5-139">此集合中的每个元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="76ca5-139">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76ca5-140">备注</span><span class="sxs-lookup"><span data-stu-id="76ca5-140">Remarks</span></span>  
 <span data-ttu-id="76ca5-141">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="76ca5-141">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="76ca5-142">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="76ca5-142">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="76ca5-143">此要求出现在安全策略中。</span><span class="sxs-lookup"><span data-stu-id="76ca5-143">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="76ca5-144">当客户端请求来自联合服务（例如 CardSpace）的凭据时，它会将需求放置在令牌请求 (RequestSecurityToken) 中，以便联合服务能够相应地颁发符合需求的凭据。</span><span class="sxs-lookup"><span data-stu-id="76ca5-144">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76ca5-145">示例</span><span class="sxs-lookup"><span data-stu-id="76ca5-145">Example</span></span>  
 <span data-ttu-id="76ca5-146">下面的配置将两个声明类型需求添加到安全绑定。</span><span class="sxs-lookup"><span data-stu-id="76ca5-146">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="myFederatedBinding">
      <security mode="Message">
        <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">
          <claimTypeRequirements>
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress" />
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"
                 optional="true" />
          </claimTypeRequirements>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="76ca5-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76ca5-147">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
