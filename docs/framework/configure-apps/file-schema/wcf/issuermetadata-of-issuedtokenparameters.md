---
title: '&lt;issuedTokenParameters&gt; 的 &lt;issuerMetadata&gt;'
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: 76956c54739219bbde78f378a12d59563ab785c4
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148742"
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="b4d47-102">&lt;issuedTokenParameters&gt; 的 &lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="b4d47-102">&lt;issuerMetadata&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="b4d47-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b4d47-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b4d47-104">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="b4d47-104">\<bindings></span></span>  
<span data-ttu-id="b4d47-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b4d47-105">\<customBinding></span></span>  
<span data-ttu-id="b4d47-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="b4d47-106">\<binding></span></span>  
<span data-ttu-id="b4d47-107">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="b4d47-107">\<security></span></span>  
<span data-ttu-id="b4d47-108">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="b4d47-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="b4d47-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="b4d47-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4d47-110">语法</span><span class="sxs-lookup"><span data-stu-id="b4d47-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4d47-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b4d47-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b4d47-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b4d47-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4d47-113">特性</span><span class="sxs-lookup"><span data-stu-id="b4d47-113">Attributes</span></span>  
  
|<span data-ttu-id="b4d47-114">特性</span><span class="sxs-lookup"><span data-stu-id="b4d47-114">Attribute</span></span>|<span data-ttu-id="b4d47-115">描述</span><span class="sxs-lookup"><span data-stu-id="b4d47-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b4d47-116">address</span><span class="sxs-lookup"><span data-stu-id="b4d47-116">address</span></span>|<span data-ttu-id="b4d47-117">必需。</span><span class="sxs-lookup"><span data-stu-id="b4d47-117">Required.</span></span> <span data-ttu-id="b4d47-118">一个指定终结点地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="b4d47-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="b4d47-119">该地址必须为绝对 URI。</span><span class="sxs-lookup"><span data-stu-id="b4d47-119">The address must be an absolute URI.</span></span> <span data-ttu-id="b4d47-120">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="b4d47-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4d47-121">子元素</span><span class="sxs-lookup"><span data-stu-id="b4d47-121">Child Elements</span></span>  
  
|<span data-ttu-id="b4d47-122">元素</span><span class="sxs-lookup"><span data-stu-id="b4d47-122">Element</span></span>|<span data-ttu-id="b4d47-123">描述</span><span class="sxs-lookup"><span data-stu-id="b4d47-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4d47-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="b4d47-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="b4d47-125">一个地址标头集合。</span><span class="sxs-lookup"><span data-stu-id="b4d47-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="b4d47-126">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="b4d47-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="b4d47-127">一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b4d47-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b4d47-128">父元素</span><span class="sxs-lookup"><span data-stu-id="b4d47-128">Parent Elements</span></span>  
  
|<span data-ttu-id="b4d47-129">元素</span><span class="sxs-lookup"><span data-stu-id="b4d47-129">Element</span></span>|<span data-ttu-id="b4d47-130">描述</span><span class="sxs-lookup"><span data-stu-id="b4d47-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4d47-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="b4d47-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="b4d47-132">指定在联合安全方案中颁发的安全令牌的参数。</span><span class="sxs-lookup"><span data-stu-id="b4d47-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4d47-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4d47-133">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="b4d47-134">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="b4d47-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="b4d47-135">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="b4d47-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="b4d47-136">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="b4d47-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="b4d47-137">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="b4d47-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="b4d47-138">绑定</span><span class="sxs-lookup"><span data-stu-id="b4d47-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b4d47-139">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="b4d47-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="b4d47-140">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="b4d47-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="b4d47-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b4d47-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="b4d47-142">如何：创建自定义绑定使用 SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="b4d47-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="b4d47-143">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="b4d47-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
