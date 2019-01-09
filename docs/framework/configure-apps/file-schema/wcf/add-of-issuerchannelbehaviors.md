---
title: '&lt;issuerChannelBehaviors&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 072e3f4e961f6bf45e7c8b48c64cda36d385cf2b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149535"
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a><span data-ttu-id="38e55-102">&lt;issuerChannelBehaviors&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="38e55-102">&lt;add&gt; of &lt;issuerChannelBehaviors&gt;</span></span>
<span data-ttu-id="38e55-103">添加在与 STS 进行通信时要使用的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="38e55-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38e55-104">如果任何终结点行为包含[ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)元素中，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="38e55-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="38e55-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="38e55-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="38e55-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="38e55-106">\<behaviors></span></span>  
<span data-ttu-id="38e55-107">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="38e55-107">endpointBehaviors section</span></span>  
<span data-ttu-id="38e55-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="38e55-108">\<behavior></span></span>  
<span data-ttu-id="38e55-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="38e55-109">\<clientCredentials></span></span>  
<span data-ttu-id="38e55-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="38e55-110">\<issuedToken></span></span>  
<span data-ttu-id="38e55-111">\<issuerChannelBehaviors > 元素</span><span class="sxs-lookup"><span data-stu-id="38e55-111">\<issuerChannelBehaviors> Element</span></span>  
<span data-ttu-id="38e55-112">\<add></span><span class="sxs-lookup"><span data-stu-id="38e55-112">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38e55-113">语法</span><span class="sxs-lookup"><span data-stu-id="38e55-113">Syntax</span></span>  
  
```xml  
<add issuerAddress="string"
     behaviorConfiguraton="string" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38e55-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="38e55-114">Attributes and Elements</span></span>  
 <span data-ttu-id="38e55-115">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="38e55-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38e55-116">特性</span><span class="sxs-lookup"><span data-stu-id="38e55-116">Attributes</span></span>  
  
|<span data-ttu-id="38e55-117">特性</span><span class="sxs-lookup"><span data-stu-id="38e55-117">Attribute</span></span>|<span data-ttu-id="38e55-118">描述</span><span class="sxs-lookup"><span data-stu-id="38e55-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38e55-119">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="38e55-119">issuerAddress</span></span>|<span data-ttu-id="38e55-120">要与之通信的安全令牌颁发者的 URI。</span><span class="sxs-lookup"><span data-stu-id="38e55-120">The URI of the security token issuer to communicate with.</span></span>|  
|<span data-ttu-id="38e55-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="38e55-121">behaviorConfiguration</span></span>|<span data-ttu-id="38e55-122">在同一个配置文件中定义的终结点行为的名称。</span><span class="sxs-lookup"><span data-stu-id="38e55-122">The name of an endpoint behavior defined in the same configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38e55-123">子元素</span><span class="sxs-lookup"><span data-stu-id="38e55-123">Child Elements</span></span>  
 <span data-ttu-id="38e55-124">无。</span><span class="sxs-lookup"><span data-stu-id="38e55-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38e55-125">父元素</span><span class="sxs-lookup"><span data-stu-id="38e55-125">Parent Elements</span></span>  
  
|<span data-ttu-id="38e55-126">元素</span><span class="sxs-lookup"><span data-stu-id="38e55-126">Element</span></span>|<span data-ttu-id="38e55-127">描述</span><span class="sxs-lookup"><span data-stu-id="38e55-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38e55-128">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="38e55-128">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="38e55-129">包含与指定的服务令牌服务通信时要使用 Windows Communication Foundation (WCF) 客户端终结点行为的集合。</span><span class="sxs-lookup"><span data-stu-id="38e55-129">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38e55-130">备注</span><span class="sxs-lookup"><span data-stu-id="38e55-130">Remarks</span></span>  
 <span data-ttu-id="38e55-131">`issuerAddress` 包含客户端希望与之进行通信的安全令牌服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="38e55-131">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="38e55-132">`behaviorConfiguration` 指向应用程序用于创建由 Windows Communication Foundation (WCF) 的通道中从安全令牌服务获取已颁发的令牌的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="38e55-132">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e55-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="38e55-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="38e55-134">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="38e55-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="38e55-135">安全行为</span><span class="sxs-lookup"><span data-stu-id="38e55-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="38e55-136">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="38e55-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="38e55-137">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="38e55-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="38e55-138">保护客户端</span><span class="sxs-lookup"><span data-stu-id="38e55-138">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="38e55-139">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="38e55-139">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="38e55-140">如何：配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="38e55-140">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="38e55-141">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="38e55-141">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="38e55-142">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="38e55-142">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
