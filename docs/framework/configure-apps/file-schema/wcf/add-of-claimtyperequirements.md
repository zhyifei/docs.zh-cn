---
title: <add> 的 <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 53da9dacbd3277bd8b608296a1515e3da7296f1c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398372"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="63e01-102">\<添加 claimTypeRequirements > \<的 ></span><span class="sxs-lookup"><span data-stu-id="63e01-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="63e01-103">指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="63e01-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="63e01-104">例如，服务规定有关传入凭据的要求，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="63e01-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="63e01-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="63e01-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="63e01-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="63e01-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="63e01-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="63e01-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="63e01-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="63e01-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="63e01-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="63e01-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="63e01-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="63e01-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="63e01-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenParameters >** ](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="63e01-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="63e01-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimTypeRequirements >** ](claimtyperequirements-element.md)</span><span class="sxs-lookup"><span data-stu-id="63e01-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)</span></span>\
<span data-ttu-id="63e01-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="63e01-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63e01-114">语法</span><span class="sxs-lookup"><span data-stu-id="63e01-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63e01-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="63e01-115">Attributes and Elements</span></span>  
 <span data-ttu-id="63e01-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="63e01-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63e01-117">特性</span><span class="sxs-lookup"><span data-stu-id="63e01-117">Attributes</span></span>  
  
|<span data-ttu-id="63e01-118">特性</span><span class="sxs-lookup"><span data-stu-id="63e01-118">Attribute</span></span>|<span data-ttu-id="63e01-119">描述</span><span class="sxs-lookup"><span data-stu-id="63e01-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63e01-120">claimType</span><span class="sxs-lookup"><span data-stu-id="63e01-120">claimType</span></span>|<span data-ttu-id="63e01-121">一个 URI，定义声明类型。</span><span class="sxs-lookup"><span data-stu-id="63e01-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="63e01-122">例如，若要从网站上购买产品，用户必须提供具有足够信用额度的有效信用卡。</span><span class="sxs-lookup"><span data-stu-id="63e01-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="63e01-123">声明类型将为信用卡 URI。</span><span class="sxs-lookup"><span data-stu-id="63e01-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="63e01-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="63e01-124">isOptional</span></span>|<span data-ttu-id="63e01-125">一个布尔值，指定声明是否为可选的。</span><span class="sxs-lookup"><span data-stu-id="63e01-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="63e01-126">如果声明是必选的，则将此属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="63e01-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="63e01-127">当服务请求一些并非必要的信息时，可以使用此属性。</span><span class="sxs-lookup"><span data-stu-id="63e01-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="63e01-128">例如，您可以要求用户输入其名、姓和地址，但决定其电话号码是可选的。</span><span class="sxs-lookup"><span data-stu-id="63e01-128">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63e01-129">子元素</span><span class="sxs-lookup"><span data-stu-id="63e01-129">Child Elements</span></span>  
 <span data-ttu-id="63e01-130">无。</span><span class="sxs-lookup"><span data-stu-id="63e01-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63e01-131">父元素</span><span class="sxs-lookup"><span data-stu-id="63e01-131">Parent Elements</span></span>  
  
|<span data-ttu-id="63e01-132">元素</span><span class="sxs-lookup"><span data-stu-id="63e01-132">Element</span></span>|<span data-ttu-id="63e01-133">描述</span><span class="sxs-lookup"><span data-stu-id="63e01-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63e01-134">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="63e01-134">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="63e01-135">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="63e01-135">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="63e01-136">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="63e01-136">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="63e01-137">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="63e01-137">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="63e01-138">此集合中的每个元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="63e01-138">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63e01-139">备注</span><span class="sxs-lookup"><span data-stu-id="63e01-139">Remarks</span></span>  
 <span data-ttu-id="63e01-140">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="63e01-140">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="63e01-141">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="63e01-141">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="63e01-142">此要求出现在安全策略中。</span><span class="sxs-lookup"><span data-stu-id="63e01-142">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="63e01-143">当客户端请求来自联合服务（例如 CardSpace）的凭据时，它会将需求放置在令牌请求 (RequestSecurityToken) 中，以便联合服务能够相应地颁发符合需求的凭据。</span><span class="sxs-lookup"><span data-stu-id="63e01-143">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63e01-144">示例</span><span class="sxs-lookup"><span data-stu-id="63e01-144">Example</span></span>  
 <span data-ttu-id="63e01-145">下面的配置将两个声明类型需求添加到安全绑定。</span><span class="sxs-lookup"><span data-stu-id="63e01-145">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="63e01-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="63e01-146">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="63e01-147">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="63e01-147">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)
- [<span data-ttu-id="63e01-148">绑定</span><span class="sxs-lookup"><span data-stu-id="63e01-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="63e01-149">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="63e01-149">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="63e01-150">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="63e01-150">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="63e01-151">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="63e01-151">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="63e01-152">如何：使用 SecurityBindingElement 创建自定义绑定</span><span class="sxs-lookup"><span data-stu-id="63e01-152">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="63e01-153">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="63e01-153">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
