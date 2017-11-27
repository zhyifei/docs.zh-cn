---
title: "&lt;issuerChannelBehaviors&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7dca60a5bf1b3dd81502f9fd48d2881c3a9b71dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a><span data-ttu-id="ac087-102">&lt;issuerChannelBehaviors&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="ac087-102">&lt;add&gt; of &lt;issuerChannelBehaviors&gt;</span></span>
<span data-ttu-id="ac087-103">添加在与 STS 进行通信时要使用的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="ac087-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac087-104">如果任何终结点行为包含[ \<c a t e >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)元素，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="ac087-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="ac087-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ac087-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="ac087-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="ac087-106">\<behaviors></span></span>  
<span data-ttu-id="ac087-107">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="ac087-107">endpointBehaviors section</span></span>  
<span data-ttu-id="ac087-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="ac087-108">\<behavior></span></span>  
<span data-ttu-id="ac087-109">\<c a t e ></span><span class="sxs-lookup"><span data-stu-id="ac087-109">\<clientCredentials></span></span>  
<span data-ttu-id="ac087-110">\<k e n ></span><span class="sxs-lookup"><span data-stu-id="ac087-110">\<issuedToken></span></span>  
<span data-ttu-id="ac087-111">\<issuerChannelBehaviors > 元素</span><span class="sxs-lookup"><span data-stu-id="ac087-111">\<issuerChannelBehaviors> Element</span></span>  
<span data-ttu-id="ac087-112">\<add></span><span class="sxs-lookup"><span data-stu-id="ac087-112">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac087-113">语法</span><span class="sxs-lookup"><span data-stu-id="ac087-113">Syntax</span></span>  
  
```xml  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac087-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ac087-114">Attributes and Elements</span></span>  
 <span data-ttu-id="ac087-115">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ac087-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac087-116">特性</span><span class="sxs-lookup"><span data-stu-id="ac087-116">Attributes</span></span>  
  
|<span data-ttu-id="ac087-117">特性</span><span class="sxs-lookup"><span data-stu-id="ac087-117">Attribute</span></span>|<span data-ttu-id="ac087-118">描述</span><span class="sxs-lookup"><span data-stu-id="ac087-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac087-119">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="ac087-119">issuerAddress</span></span>|<span data-ttu-id="ac087-120">要与之通信的安全令牌颁发者的 URI。</span><span class="sxs-lookup"><span data-stu-id="ac087-120">The URI of the security token issuer to communicate with.</span></span>|  
|<span data-ttu-id="ac087-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="ac087-121">behaviorConfiguration</span></span>|<span data-ttu-id="ac087-122">在同一个配置文件中定义的终结点行为的名称。</span><span class="sxs-lookup"><span data-stu-id="ac087-122">The name of an endpoint behavior defined in the same configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac087-123">子元素</span><span class="sxs-lookup"><span data-stu-id="ac087-123">Child Elements</span></span>  
 <span data-ttu-id="ac087-124">无。</span><span class="sxs-lookup"><span data-stu-id="ac087-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac087-125">父元素</span><span class="sxs-lookup"><span data-stu-id="ac087-125">Parent Elements</span></span>  
  
|<span data-ttu-id="ac087-126">元素</span><span class="sxs-lookup"><span data-stu-id="ac087-126">Element</span></span>|<span data-ttu-id="ac087-127">描述</span><span class="sxs-lookup"><span data-stu-id="ac087-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac087-128">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ac087-128">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="ac087-129">包含与指定的服务令牌服务通信时要使用的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 客户端终结点行为的集合。</span><span class="sxs-lookup"><span data-stu-id="ac087-129">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac087-130">备注</span><span class="sxs-lookup"><span data-stu-id="ac087-130">Remarks</span></span>  
 <span data-ttu-id="ac087-131">`issuerAddress` 包含客户端希望与之进行通信的安全令牌服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="ac087-131">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="ac087-132">`behaviorConfiguration` 指向终结点行为，应用程序会在由 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 创建的通道中使用它，以从本地安全令牌服务获取已颁发的令牌。</span><span class="sxs-lookup"><span data-stu-id="ac087-132">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] to get the issued tokens from the Security Token Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac087-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac087-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="ac087-134">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="ac087-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="ac087-135">安全行为</span><span class="sxs-lookup"><span data-stu-id="ac087-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="ac087-136">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="ac087-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="ac087-137">保护服务和客户端</span><span class="sxs-lookup"><span data-stu-id="ac087-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="ac087-138">保护客户端</span><span class="sxs-lookup"><span data-stu-id="ac087-138">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="ac087-139">如何： 创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="ac087-139">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="ac087-140">如何： 配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="ac087-140">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="ac087-141">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="ac087-141">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="ac087-142">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ac087-142">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
