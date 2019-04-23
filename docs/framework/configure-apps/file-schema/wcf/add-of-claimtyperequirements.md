---
title: <add> 的 <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 97d3ecca369aeffb7b2e8464f385eeae13bd470f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168839"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="74107-102">\<添加 > 的\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="74107-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="74107-103">指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="74107-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="74107-104">例如，服务规定有关传入凭据的要求，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="74107-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
 <span data-ttu-id="74107-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="74107-105">\<system.serviceModel></span></span>  
<span data-ttu-id="74107-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="74107-106">\<bindings></span></span>  
<span data-ttu-id="74107-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="74107-107">\<customBinding></span></span>  
<span data-ttu-id="74107-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="74107-108">\<binding></span></span>  
<span data-ttu-id="74107-109">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="74107-109">\<security></span></span>  
<span data-ttu-id="74107-110">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="74107-110">\<issuedTokenParameters></span></span>  
<span data-ttu-id="74107-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="74107-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74107-112">语法</span><span class="sxs-lookup"><span data-stu-id="74107-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74107-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="74107-113">Attributes and Elements</span></span>  
 <span data-ttu-id="74107-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="74107-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74107-115">特性</span><span class="sxs-lookup"><span data-stu-id="74107-115">Attributes</span></span>  
  
|<span data-ttu-id="74107-116">特性</span><span class="sxs-lookup"><span data-stu-id="74107-116">Attribute</span></span>|<span data-ttu-id="74107-117">描述</span><span class="sxs-lookup"><span data-stu-id="74107-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74107-118">claimType</span><span class="sxs-lookup"><span data-stu-id="74107-118">claimType</span></span>|<span data-ttu-id="74107-119">一个 URI，定义声明类型。</span><span class="sxs-lookup"><span data-stu-id="74107-119">A URI that defines the type of a claim.</span></span> <span data-ttu-id="74107-120">例如，若要从网站上购买产品，用户必须提供具有足够信用额度的有效信用卡。</span><span class="sxs-lookup"><span data-stu-id="74107-120">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="74107-121">声明类型将为信用卡 URI。</span><span class="sxs-lookup"><span data-stu-id="74107-121">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="74107-122">isOptional</span><span class="sxs-lookup"><span data-stu-id="74107-122">isOptional</span></span>|<span data-ttu-id="74107-123">一个布尔值，指定声明是否为可选的。</span><span class="sxs-lookup"><span data-stu-id="74107-123">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="74107-124">如果声明是必选的，则将此属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="74107-124">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="74107-125">当服务请求一些并非必要的信息时，可以使用此属性。</span><span class="sxs-lookup"><span data-stu-id="74107-125">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="74107-126">例如，您可以要求用户输入其名、姓和地址，但决定其电话号码是可选的。</span><span class="sxs-lookup"><span data-stu-id="74107-126">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74107-127">子元素</span><span class="sxs-lookup"><span data-stu-id="74107-127">Child Elements</span></span>  
 <span data-ttu-id="74107-128">无。</span><span class="sxs-lookup"><span data-stu-id="74107-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74107-129">父元素</span><span class="sxs-lookup"><span data-stu-id="74107-129">Parent Elements</span></span>  
  
|<span data-ttu-id="74107-130">元素</span><span class="sxs-lookup"><span data-stu-id="74107-130">Element</span></span>|<span data-ttu-id="74107-131">描述</span><span class="sxs-lookup"><span data-stu-id="74107-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74107-132">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="74107-132">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="74107-133">指定所需声明类型的集合。</span><span class="sxs-lookup"><span data-stu-id="74107-133">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="74107-134">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="74107-134">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="74107-135">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="74107-135">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="74107-136">此集合中的每个元素都指定希望出现在联合凭据中的必选和可选的声明类型。</span><span class="sxs-lookup"><span data-stu-id="74107-136">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74107-137">备注</span><span class="sxs-lookup"><span data-stu-id="74107-137">Remarks</span></span>  
 <span data-ttu-id="74107-138">在联合方案中，服务规定有关传入凭据的要求。</span><span class="sxs-lookup"><span data-stu-id="74107-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="74107-139">例如，传入凭据必须具有某组声明类型。</span><span class="sxs-lookup"><span data-stu-id="74107-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="74107-140">此要求出现在安全策略中。</span><span class="sxs-lookup"><span data-stu-id="74107-140">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="74107-141">当客户端请求来自联合服务（例如 CardSpace）的凭据时，它会将需求放置在令牌请求 (RequestSecurityToken) 中，以便联合服务能够相应地颁发符合需求的凭据。</span><span class="sxs-lookup"><span data-stu-id="74107-141">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74107-142">示例</span><span class="sxs-lookup"><span data-stu-id="74107-142">Example</span></span>  
 <span data-ttu-id="74107-143">下面的配置将两个声明类型需求添加到安全绑定。</span><span class="sxs-lookup"><span data-stu-id="74107-143">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="74107-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="74107-144">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="74107-145">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="74107-145">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)
- [<span data-ttu-id="74107-146">绑定</span><span class="sxs-lookup"><span data-stu-id="74107-146">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="74107-147">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="74107-147">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="74107-148">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="74107-148">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="74107-149">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="74107-149">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="74107-150">如何：创建自定义绑定使用 SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="74107-150">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="74107-151">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="74107-151">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
