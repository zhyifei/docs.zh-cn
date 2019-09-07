---
title: <issuer> 的 <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bdd5ad45984fae7b39defe82c4af75845dfda1b6
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397935"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="c2d4b-102">\<issuedTokenParameters > 的\<颁发者 ></span><span class="sxs-lookup"><span data-stu-id="c2d4b-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="c2d4b-103">指定颁发安全令牌的安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="c2d4b-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="c2d4b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c2d4b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c2d4b-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c2d4b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c2d4b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c2d4b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c2d4b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c2d4b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="c2d4b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="c2d4b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c2d4b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c2d4b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="c2d4b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenParameters >** ](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="c2d4b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="c2d4b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<颁发者 >**</span><span class="sxs-lookup"><span data-stu-id="c2d4b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2d4b-112">语法</span><span class="sxs-lookup"><span data-stu-id="c2d4b-112">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2d4b-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c2d4b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c2d4b-114">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c2d4b-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2d4b-115">特性</span><span class="sxs-lookup"><span data-stu-id="c2d4b-115">Attributes</span></span>  
  
|<span data-ttu-id="c2d4b-116">特性</span><span class="sxs-lookup"><span data-stu-id="c2d4b-116">Attribute</span></span>|<span data-ttu-id="c2d4b-117">描述</span><span class="sxs-lookup"><span data-stu-id="c2d4b-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c2d4b-118">地址</span><span class="sxs-lookup"><span data-stu-id="c2d4b-118">address</span></span>|<span data-ttu-id="c2d4b-119">必选字符串。</span><span class="sxs-lookup"><span data-stu-id="c2d4b-119">Required string.</span></span> <span data-ttu-id="c2d4b-120">STS 的 URL。</span><span class="sxs-lookup"><span data-stu-id="c2d4b-120">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2d4b-121">子元素</span><span class="sxs-lookup"><span data-stu-id="c2d4b-121">Child Elements</span></span>  
  
|<span data-ttu-id="c2d4b-122">元素</span><span class="sxs-lookup"><span data-stu-id="c2d4b-122">Element</span></span>|<span data-ttu-id="c2d4b-123">描述</span><span class="sxs-lookup"><span data-stu-id="c2d4b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2d4b-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="c2d4b-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="c2d4b-125">生成器可以创建的终结点的地址标头的集合。</span><span class="sxs-lookup"><span data-stu-id="c2d4b-125">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="c2d4b-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="c2d4b-126">\<identity></span></span>](identity.md)|<span data-ttu-id="c2d4b-127">在使用颁发的令牌时，指定能够使客户端对服务器进行身份验证的设置。</span><span class="sxs-lookup"><span data-stu-id="c2d4b-127">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c2d4b-128">父元素</span><span class="sxs-lookup"><span data-stu-id="c2d4b-128">Parent Elements</span></span>  
  
|<span data-ttu-id="c2d4b-129">元素</span><span class="sxs-lookup"><span data-stu-id="c2d4b-129">Element</span></span>|<span data-ttu-id="c2d4b-130">描述</span><span class="sxs-lookup"><span data-stu-id="c2d4b-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2d4b-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="c2d4b-131">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="c2d4b-132">指定当前颁发的令牌。</span><span class="sxs-lookup"><span data-stu-id="c2d4b-132">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2d4b-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2d4b-133">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c2d4b-134">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="c2d4b-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c2d4b-135">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="c2d4b-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c2d4b-136">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="c2d4b-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="c2d4b-137">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="c2d4b-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c2d4b-138">绑定</span><span class="sxs-lookup"><span data-stu-id="c2d4b-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c2d4b-139">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="c2d4b-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c2d4b-140">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="c2d4b-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c2d4b-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c2d4b-141">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="c2d4b-142">如何：使用 SecurityBindingElement 创建自定义绑定</span><span class="sxs-lookup"><span data-stu-id="c2d4b-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="c2d4b-143">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="c2d4b-143">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
