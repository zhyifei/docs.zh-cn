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
ms.workload: dotnet
ms.openlocfilehash: ee0f6b2abe6ddfa81f236da47425ae586b56f0ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="19a57-102">&lt;issuedTokenParameters&gt; 的 &lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="19a57-102">&lt;issuerMetadata&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="19a57-103">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="19a57-103">\<system.serviceModel></span></span>  
<span data-ttu-id="19a57-104">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="19a57-104">\<bindings></span></span>  
<span data-ttu-id="19a57-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="19a57-105">\<customBinding></span></span>  
<span data-ttu-id="19a57-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="19a57-106">\<binding></span></span>  
<span data-ttu-id="19a57-107">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="19a57-107">\<security></span></span>  
<span data-ttu-id="19a57-108">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="19a57-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="19a57-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="19a57-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19a57-110">语法</span><span class="sxs-lookup"><span data-stu-id="19a57-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address=String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19a57-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="19a57-111">Attributes and Elements</span></span>  
 <span data-ttu-id="19a57-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="19a57-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19a57-113">特性</span><span class="sxs-lookup"><span data-stu-id="19a57-113">Attributes</span></span>  
  
|<span data-ttu-id="19a57-114">特性</span><span class="sxs-lookup"><span data-stu-id="19a57-114">Attribute</span></span>|<span data-ttu-id="19a57-115">描述</span><span class="sxs-lookup"><span data-stu-id="19a57-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19a57-116">address</span><span class="sxs-lookup"><span data-stu-id="19a57-116">address</span></span>|<span data-ttu-id="19a57-117">必需。</span><span class="sxs-lookup"><span data-stu-id="19a57-117">Required.</span></span> <span data-ttu-id="19a57-118">一个指定终结点地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="19a57-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="19a57-119">该地址必须为绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="19a57-119">The address must be an absolute URI.</span></span> <span data-ttu-id="19a57-120">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="19a57-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19a57-121">子元素</span><span class="sxs-lookup"><span data-stu-id="19a57-121">Child Elements</span></span>  
  
|<span data-ttu-id="19a57-122">元素</span><span class="sxs-lookup"><span data-stu-id="19a57-122">Element</span></span>|<span data-ttu-id="19a57-123">描述</span><span class="sxs-lookup"><span data-stu-id="19a57-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19a57-124">\<标头 ></span><span class="sxs-lookup"><span data-stu-id="19a57-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="19a57-125">一个地址标头集合。</span><span class="sxs-lookup"><span data-stu-id="19a57-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="19a57-126">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="19a57-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="19a57-127">一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="19a57-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19a57-128">父元素</span><span class="sxs-lookup"><span data-stu-id="19a57-128">Parent Elements</span></span>  
  
|<span data-ttu-id="19a57-129">元素</span><span class="sxs-lookup"><span data-stu-id="19a57-129">Element</span></span>|<span data-ttu-id="19a57-130">描述</span><span class="sxs-lookup"><span data-stu-id="19a57-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19a57-131">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="19a57-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="19a57-132">指定在联合安全方案中颁发的安全令牌的参数。</span><span class="sxs-lookup"><span data-stu-id="19a57-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19a57-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="19a57-133">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="19a57-134">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="19a57-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="19a57-135">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="19a57-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="19a57-136">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="19a57-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="19a57-137">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="19a57-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="19a57-138">绑定</span><span class="sxs-lookup"><span data-stu-id="19a57-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="19a57-139">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="19a57-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="19a57-140">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="19a57-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="19a57-141">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="19a57-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="19a57-142">如何：使用 SecurityBindingElement 创建自定义绑定</span><span class="sxs-lookup"><span data-stu-id="19a57-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="19a57-143">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="19a57-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
