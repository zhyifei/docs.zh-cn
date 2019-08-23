---
title: <issuerMetadata> 的 <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: d9d7d41277eff1de43f717816b35fdc10d52192e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928881"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="c670e-102">\<issuedtokenparameters > \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="c670e-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>
<span data-ttu-id="c670e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c670e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="c670e-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c670e-104">\<bindings></span></span>  
<span data-ttu-id="c670e-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c670e-105">\<customBinding></span></span>  
<span data-ttu-id="c670e-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="c670e-106">\<binding></span></span>  
<span data-ttu-id="c670e-107">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="c670e-107">\<security></span></span>  
<span data-ttu-id="c670e-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="c670e-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="c670e-109">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="c670e-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c670e-110">语法</span><span class="sxs-lookup"><span data-stu-id="c670e-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c670e-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c670e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c670e-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c670e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c670e-113">特性</span><span class="sxs-lookup"><span data-stu-id="c670e-113">Attributes</span></span>  
  
|<span data-ttu-id="c670e-114">特性</span><span class="sxs-lookup"><span data-stu-id="c670e-114">Attribute</span></span>|<span data-ttu-id="c670e-115">描述</span><span class="sxs-lookup"><span data-stu-id="c670e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c670e-116">地址</span><span class="sxs-lookup"><span data-stu-id="c670e-116">address</span></span>|<span data-ttu-id="c670e-117">必需。</span><span class="sxs-lookup"><span data-stu-id="c670e-117">Required.</span></span> <span data-ttu-id="c670e-118">一个指定终结点地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="c670e-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="c670e-119">该地址必须为绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="c670e-119">The address must be an absolute URI.</span></span> <span data-ttu-id="c670e-120">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="c670e-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c670e-121">子元素</span><span class="sxs-lookup"><span data-stu-id="c670e-121">Child Elements</span></span>  
  
|<span data-ttu-id="c670e-122">元素</span><span class="sxs-lookup"><span data-stu-id="c670e-122">Element</span></span>|<span data-ttu-id="c670e-123">描述</span><span class="sxs-lookup"><span data-stu-id="c670e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c670e-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="c670e-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="c670e-125">一个地址标头集合。</span><span class="sxs-lookup"><span data-stu-id="c670e-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="c670e-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="c670e-126">\<identity></span></span>](identity.md)|<span data-ttu-id="c670e-127">一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="c670e-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c670e-128">父元素</span><span class="sxs-lookup"><span data-stu-id="c670e-128">Parent Elements</span></span>  
  
|<span data-ttu-id="c670e-129">元素</span><span class="sxs-lookup"><span data-stu-id="c670e-129">Element</span></span>|<span data-ttu-id="c670e-130">描述</span><span class="sxs-lookup"><span data-stu-id="c670e-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c670e-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="c670e-131">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="c670e-132">指定在联合安全方案中颁发的安全令牌的参数。</span><span class="sxs-lookup"><span data-stu-id="c670e-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c670e-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="c670e-133">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c670e-134">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="c670e-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c670e-135">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="c670e-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c670e-136">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="c670e-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="c670e-137">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="c670e-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c670e-138">绑定</span><span class="sxs-lookup"><span data-stu-id="c670e-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c670e-139">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="c670e-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c670e-140">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="c670e-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c670e-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c670e-141">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="c670e-142">如何：使用 SecurityBindingElement 创建自定义绑定</span><span class="sxs-lookup"><span data-stu-id="c670e-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="c670e-143">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="c670e-143">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
