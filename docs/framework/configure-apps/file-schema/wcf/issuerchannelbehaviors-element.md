---
title: '&lt;issuerChannelBehaviors&gt; 元素'
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: b77d0ce79557dff4b5a243da4d24703ed45fde07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677103"
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="85185-102">&lt;issuerChannelBehaviors&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="85185-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="85185-103">包含一系列 Windows Communication Foundation (WCF) 客户端终结点行为 （在配置中定义） 以与指定的服务令牌服务通信时使用。</span><span class="sxs-lookup"><span data-stu-id="85185-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="85185-104">所定义的行为不能包含任何[ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)元素。</span><span class="sxs-lookup"><span data-stu-id="85185-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="85185-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="85185-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="85185-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="85185-106">\<behaviors></span></span>  
<span data-ttu-id="85185-107">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="85185-107">endpointBehaviors section</span></span>  
<span data-ttu-id="85185-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="85185-108">\<behavior></span></span>  
<span data-ttu-id="85185-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="85185-109">\<clientCredentials></span></span>  
<span data-ttu-id="85185-110">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="85185-110">\<issuedToken></span></span>  
<span data-ttu-id="85185-111">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="85185-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85185-112">语法</span><span class="sxs-lookup"><span data-stu-id="85185-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>
  <add behaviorConfiguraton="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85185-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="85185-113">Attributes and Elements</span></span>  
 <span data-ttu-id="85185-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="85185-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85185-115">特性</span><span class="sxs-lookup"><span data-stu-id="85185-115">Attributes</span></span>  
 <span data-ttu-id="85185-116">无。</span><span class="sxs-lookup"><span data-stu-id="85185-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="85185-117">子元素</span><span class="sxs-lookup"><span data-stu-id="85185-117">Child Elements</span></span>  
  
|<span data-ttu-id="85185-118">元素</span><span class="sxs-lookup"><span data-stu-id="85185-118">Element</span></span>|<span data-ttu-id="85185-119">描述</span><span class="sxs-lookup"><span data-stu-id="85185-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85185-120">\<add></span><span class="sxs-lookup"><span data-stu-id="85185-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="85185-121">向集合中添加行为。</span><span class="sxs-lookup"><span data-stu-id="85185-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85185-122">父元素</span><span class="sxs-lookup"><span data-stu-id="85185-122">Parent Elements</span></span>  
  
|<span data-ttu-id="85185-123">元素</span><span class="sxs-lookup"><span data-stu-id="85185-123">Element</span></span>|<span data-ttu-id="85185-124">描述</span><span class="sxs-lookup"><span data-stu-id="85185-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85185-125">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="85185-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="85185-126">指定用于向服务验证客户端身份的自定义令牌。</span><span class="sxs-lookup"><span data-stu-id="85185-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85185-127">备注</span><span class="sxs-lookup"><span data-stu-id="85185-127">Remarks</span></span>  
 <span data-ttu-id="85185-128">当必须使用任何行为（包含 `<clientCredentials>` 元素的行为除外）与某个服务进行通信时，应使用此元素。</span><span class="sxs-lookup"><span data-stu-id="85185-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="85185-129">例如，如果[ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)行为元素必须包含。</span><span class="sxs-lookup"><span data-stu-id="85185-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85185-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="85185-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="85185-131">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="85185-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="85185-132">安全行为</span><span class="sxs-lookup"><span data-stu-id="85185-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="85185-133">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="85185-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="85185-134">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="85185-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="85185-135">保护客户端</span><span class="sxs-lookup"><span data-stu-id="85185-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="85185-136">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="85185-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="85185-137">如何：配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="85185-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="85185-138">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="85185-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
