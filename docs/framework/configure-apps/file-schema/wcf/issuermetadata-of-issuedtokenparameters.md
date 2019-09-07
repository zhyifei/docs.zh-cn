---
title: <issuerMetadata> 的 <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: fcdd66ecd162dff5be86a1d4ab1b196f50dbd445
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400346"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="253e6-102">\<issuedtokenparameters > \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="253e6-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

<span data-ttu-id="253e6-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="253e6-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="253e6-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="253e6-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="253e6-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="253e6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="253e6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="253e6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="253e6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="253e6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="253e6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="253e6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="253e6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenParameters >** ](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="253e6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="253e6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Issuedtokenparameters >**</span><span class="sxs-lookup"><span data-stu-id="253e6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="253e6-111">语法</span><span class="sxs-lookup"><span data-stu-id="253e6-111">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="253e6-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="253e6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="253e6-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="253e6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="253e6-114">特性</span><span class="sxs-lookup"><span data-stu-id="253e6-114">Attributes</span></span>  
  
|<span data-ttu-id="253e6-115">特性</span><span class="sxs-lookup"><span data-stu-id="253e6-115">Attribute</span></span>|<span data-ttu-id="253e6-116">描述</span><span class="sxs-lookup"><span data-stu-id="253e6-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="253e6-117">地址</span><span class="sxs-lookup"><span data-stu-id="253e6-117">address</span></span>|<span data-ttu-id="253e6-118">必需。</span><span class="sxs-lookup"><span data-stu-id="253e6-118">Required.</span></span> <span data-ttu-id="253e6-119">一个指定终结点地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="253e6-119">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="253e6-120">该地址必须为绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="253e6-120">The address must be an absolute URI.</span></span> <span data-ttu-id="253e6-121">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="253e6-121">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="253e6-122">子元素</span><span class="sxs-lookup"><span data-stu-id="253e6-122">Child Elements</span></span>  
  
|<span data-ttu-id="253e6-123">元素</span><span class="sxs-lookup"><span data-stu-id="253e6-123">Element</span></span>|<span data-ttu-id="253e6-124">描述</span><span class="sxs-lookup"><span data-stu-id="253e6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="253e6-125">\<headers></span><span class="sxs-lookup"><span data-stu-id="253e6-125">\<headers></span></span>](headers-element.md)|<span data-ttu-id="253e6-126">一个地址标头集合。</span><span class="sxs-lookup"><span data-stu-id="253e6-126">A collection of address headers.</span></span>|  
|[<span data-ttu-id="253e6-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="253e6-127">\<identity></span></span>](identity.md)|<span data-ttu-id="253e6-128">一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="253e6-128">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="253e6-129">父元素</span><span class="sxs-lookup"><span data-stu-id="253e6-129">Parent Elements</span></span>  
  
|<span data-ttu-id="253e6-130">元素</span><span class="sxs-lookup"><span data-stu-id="253e6-130">Element</span></span>|<span data-ttu-id="253e6-131">描述</span><span class="sxs-lookup"><span data-stu-id="253e6-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="253e6-132">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="253e6-132">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="253e6-133">指定在联合安全方案中颁发的安全令牌的参数。</span><span class="sxs-lookup"><span data-stu-id="253e6-133">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="253e6-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="253e6-134">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="253e6-135">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="253e6-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="253e6-136">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="253e6-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="253e6-137">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="253e6-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="253e6-138">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="253e6-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="253e6-139">绑定</span><span class="sxs-lookup"><span data-stu-id="253e6-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="253e6-140">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="253e6-140">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="253e6-141">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="253e6-141">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="253e6-142">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="253e6-142">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="253e6-143">如何：使用 SecurityBindingElement 创建自定义绑定</span><span class="sxs-lookup"><span data-stu-id="253e6-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="253e6-144">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="253e6-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
