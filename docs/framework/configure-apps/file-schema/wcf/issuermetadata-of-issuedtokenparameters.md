---
title: "&lt;issuedTokenParameters&gt; 的 &lt;issuerMetadata&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ccd0417aeebbaf08d28457dd94a4d1698882c79e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="c61de-102">&lt;issuedTokenParameters&gt; 的 &lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="c61de-102">&lt;issuerMetadata&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="c61de-103">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="c61de-103">\<system.serviceModel></span></span>  
<span data-ttu-id="c61de-104">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="c61de-104">\<bindings></span></span>  
<span data-ttu-id="c61de-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c61de-105">\<customBinding></span></span>  
<span data-ttu-id="c61de-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="c61de-106">\<binding></span></span>  
<span data-ttu-id="c61de-107">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="c61de-107">\<security></span></span>  
<span data-ttu-id="c61de-108">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="c61de-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="c61de-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="c61de-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c61de-110">语法</span><span class="sxs-lookup"><span data-stu-id="c61de-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address=String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c61de-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c61de-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c61de-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c61de-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c61de-113">特性</span><span class="sxs-lookup"><span data-stu-id="c61de-113">Attributes</span></span>  
  
|<span data-ttu-id="c61de-114">特性</span><span class="sxs-lookup"><span data-stu-id="c61de-114">Attribute</span></span>|<span data-ttu-id="c61de-115">描述</span><span class="sxs-lookup"><span data-stu-id="c61de-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c61de-116">address</span><span class="sxs-lookup"><span data-stu-id="c61de-116">address</span></span>|<span data-ttu-id="c61de-117">必需。</span><span class="sxs-lookup"><span data-stu-id="c61de-117">Required.</span></span> <span data-ttu-id="c61de-118">一个指定终结点地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="c61de-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="c61de-119">该地址必须为绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="c61de-119">The address must be an absolute URI.</span></span> <span data-ttu-id="c61de-120">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="c61de-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c61de-121">子元素</span><span class="sxs-lookup"><span data-stu-id="c61de-121">Child Elements</span></span>  
  
|<span data-ttu-id="c61de-122">元素</span><span class="sxs-lookup"><span data-stu-id="c61de-122">Element</span></span>|<span data-ttu-id="c61de-123">描述</span><span class="sxs-lookup"><span data-stu-id="c61de-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c61de-124">\<标头 ></span><span class="sxs-lookup"><span data-stu-id="c61de-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="c61de-125">一个地址标头集合。</span><span class="sxs-lookup"><span data-stu-id="c61de-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="c61de-126">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="c61de-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="c61de-127">一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="c61de-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c61de-128">父元素</span><span class="sxs-lookup"><span data-stu-id="c61de-128">Parent Elements</span></span>  
  
|<span data-ttu-id="c61de-129">元素</span><span class="sxs-lookup"><span data-stu-id="c61de-129">Element</span></span>|<span data-ttu-id="c61de-130">描述</span><span class="sxs-lookup"><span data-stu-id="c61de-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c61de-131">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="c61de-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="c61de-132">指定在联合安全方案中颁发的安全令牌的参数。</span><span class="sxs-lookup"><span data-stu-id="c61de-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c61de-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c61de-133">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="c61de-134">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="c61de-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="c61de-135">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="c61de-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="c61de-136">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="c61de-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="c61de-137">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="c61de-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="c61de-138">绑定</span><span class="sxs-lookup"><span data-stu-id="c61de-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c61de-139">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="c61de-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="c61de-140">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="c61de-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="c61de-141">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c61de-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="c61de-142">如何： 创建自定义绑定使用 SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="c61de-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="c61de-143">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="c61de-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
