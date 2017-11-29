---
title: "&lt;issuedTokenParameters&gt; 的 &lt;issuer&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1eae3b472e33d4d0504ba487c8c871165af8cdf9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="f50a5-102">&lt;issuedTokenParameters&gt; 的 &lt;issuer&gt;</span><span class="sxs-lookup"><span data-stu-id="f50a5-102">&lt;issuer&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="f50a5-103">指定颁发安全令牌的安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="f50a5-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="f50a5-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f50a5-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f50a5-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="f50a5-105">\<bindings></span></span>  
<span data-ttu-id="f50a5-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f50a5-106">\<customBinding></span></span>  
<span data-ttu-id="f50a5-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="f50a5-107">\<binding></span></span>  
<span data-ttu-id="f50a5-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="f50a5-108">\<security></span></span>  
<span data-ttu-id="f50a5-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="f50a5-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="f50a5-110">\<颁发者 ></span><span class="sxs-lookup"><span data-stu-id="f50a5-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f50a5-111">语法</span><span class="sxs-lookup"><span data-stu-id="f50a5-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f50a5-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f50a5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f50a5-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f50a5-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f50a5-114">特性</span><span class="sxs-lookup"><span data-stu-id="f50a5-114">Attributes</span></span>  
  
|<span data-ttu-id="f50a5-115">特性</span><span class="sxs-lookup"><span data-stu-id="f50a5-115">Attribute</span></span>|<span data-ttu-id="f50a5-116">描述</span><span class="sxs-lookup"><span data-stu-id="f50a5-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f50a5-117">address</span><span class="sxs-lookup"><span data-stu-id="f50a5-117">address</span></span>|<span data-ttu-id="f50a5-118">必选字符串。</span><span class="sxs-lookup"><span data-stu-id="f50a5-118">Required string.</span></span> <span data-ttu-id="f50a5-119">STS 的 URL。</span><span class="sxs-lookup"><span data-stu-id="f50a5-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f50a5-120">子元素</span><span class="sxs-lookup"><span data-stu-id="f50a5-120">Child Elements</span></span>  
  
|<span data-ttu-id="f50a5-121">元素</span><span class="sxs-lookup"><span data-stu-id="f50a5-121">Element</span></span>|<span data-ttu-id="f50a5-122">描述</span><span class="sxs-lookup"><span data-stu-id="f50a5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f50a5-123">\<标头 ></span><span class="sxs-lookup"><span data-stu-id="f50a5-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="f50a5-124">生成器可以创建的终结点的地址标头的集合。</span><span class="sxs-lookup"><span data-stu-id="f50a5-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="f50a5-125">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="f50a5-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="f50a5-126">在使用颁发的令牌时，指定能够使客户端对服务器进行身份验证的设置。</span><span class="sxs-lookup"><span data-stu-id="f50a5-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f50a5-127">父元素</span><span class="sxs-lookup"><span data-stu-id="f50a5-127">Parent Elements</span></span>  
  
|<span data-ttu-id="f50a5-128">元素</span><span class="sxs-lookup"><span data-stu-id="f50a5-128">Element</span></span>|<span data-ttu-id="f50a5-129">描述</span><span class="sxs-lookup"><span data-stu-id="f50a5-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f50a5-130">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="f50a5-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="f50a5-131">指定当前颁发的令牌。</span><span class="sxs-lookup"><span data-stu-id="f50a5-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f50a5-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f50a5-132">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="f50a5-133">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="f50a5-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="f50a5-134">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="f50a5-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="f50a5-135">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="f50a5-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="f50a5-136">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="f50a5-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="f50a5-137">绑定</span><span class="sxs-lookup"><span data-stu-id="f50a5-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f50a5-138">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="f50a5-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="f50a5-139">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="f50a5-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="f50a5-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f50a5-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="f50a5-141">如何： 创建自定义绑定使用 SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f50a5-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="f50a5-142">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="f50a5-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
