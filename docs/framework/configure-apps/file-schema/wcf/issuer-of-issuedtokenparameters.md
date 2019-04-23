---
title: <issuer> 的 <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 690ab14ea33ba9bef29788b2eb35f86ed945ce2b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113537"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="1c0ea-102">\<issuer> of \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="1c0ea-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="1c0ea-103">指定颁发安全令牌的安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="1c0ea-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="1c0ea-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1c0ea-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1c0ea-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1c0ea-105">\<bindings></span></span>  
<span data-ttu-id="1c0ea-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1c0ea-106">\<customBinding></span></span>  
<span data-ttu-id="1c0ea-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1c0ea-107">\<binding></span></span>  
<span data-ttu-id="1c0ea-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="1c0ea-108">\<security></span></span>  
<span data-ttu-id="1c0ea-109">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="1c0ea-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="1c0ea-110">\<issuer></span><span class="sxs-lookup"><span data-stu-id="1c0ea-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c0ea-111">语法</span><span class="sxs-lookup"><span data-stu-id="1c0ea-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c0ea-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1c0ea-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1c0ea-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1c0ea-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c0ea-114">特性</span><span class="sxs-lookup"><span data-stu-id="1c0ea-114">Attributes</span></span>  
  
|<span data-ttu-id="1c0ea-115">特性</span><span class="sxs-lookup"><span data-stu-id="1c0ea-115">Attribute</span></span>|<span data-ttu-id="1c0ea-116">描述</span><span class="sxs-lookup"><span data-stu-id="1c0ea-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1c0ea-117">地址</span><span class="sxs-lookup"><span data-stu-id="1c0ea-117">address</span></span>|<span data-ttu-id="1c0ea-118">必选字符串。</span><span class="sxs-lookup"><span data-stu-id="1c0ea-118">Required string.</span></span> <span data-ttu-id="1c0ea-119">STS 的 URL。</span><span class="sxs-lookup"><span data-stu-id="1c0ea-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c0ea-120">子元素</span><span class="sxs-lookup"><span data-stu-id="1c0ea-120">Child Elements</span></span>  
  
|<span data-ttu-id="1c0ea-121">元素</span><span class="sxs-lookup"><span data-stu-id="1c0ea-121">Element</span></span>|<span data-ttu-id="1c0ea-122">描述</span><span class="sxs-lookup"><span data-stu-id="1c0ea-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c0ea-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="1c0ea-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="1c0ea-124">生成器可以创建的终结点的地址标头的集合。</span><span class="sxs-lookup"><span data-stu-id="1c0ea-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="1c0ea-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="1c0ea-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="1c0ea-126">在使用颁发的令牌时，指定能够使客户端对服务器进行身份验证的设置。</span><span class="sxs-lookup"><span data-stu-id="1c0ea-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c0ea-127">父元素</span><span class="sxs-lookup"><span data-stu-id="1c0ea-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1c0ea-128">元素</span><span class="sxs-lookup"><span data-stu-id="1c0ea-128">Element</span></span>|<span data-ttu-id="1c0ea-129">描述</span><span class="sxs-lookup"><span data-stu-id="1c0ea-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c0ea-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="1c0ea-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="1c0ea-131">指定当前颁发的令牌。</span><span class="sxs-lookup"><span data-stu-id="1c0ea-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c0ea-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c0ea-132">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="1c0ea-133">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="1c0ea-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="1c0ea-134">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="1c0ea-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="1c0ea-135">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="1c0ea-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="1c0ea-136">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="1c0ea-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="1c0ea-137">绑定</span><span class="sxs-lookup"><span data-stu-id="1c0ea-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="1c0ea-138">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="1c0ea-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1c0ea-139">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="1c0ea-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="1c0ea-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1c0ea-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="1c0ea-141">如何：创建自定义绑定使用 SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1c0ea-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="1c0ea-142">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="1c0ea-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
