---
title: "&lt;issuerChannelBehaviors&gt; 元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 051525738f0138955358587a8fd25272dfdb9d28
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="56fba-102">&lt;issuerChannelBehaviors&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="56fba-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="56fba-103">包含与指定的服务令牌服务通信时要使用的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 客户端终结点行为（在配置中进行定义）的集合。</span><span class="sxs-lookup"><span data-stu-id="56fba-103">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="56fba-104">定义的行为不能包含任何[ \<c a t e >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)元素。</span><span class="sxs-lookup"><span data-stu-id="56fba-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="56fba-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="56fba-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="56fba-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="56fba-106">\<behaviors></span></span>  
<span data-ttu-id="56fba-107">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="56fba-107">endpointBehaviors section</span></span>  
<span data-ttu-id="56fba-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="56fba-108">\<behavior></span></span>  
<span data-ttu-id="56fba-109">\<c a t e ></span><span class="sxs-lookup"><span data-stu-id="56fba-109">\<clientCredentials></span></span>  
<span data-ttu-id="56fba-110">\<k e n ></span><span class="sxs-lookup"><span data-stu-id="56fba-110">\<issuedToken></span></span>  
<span data-ttu-id="56fba-111">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="56fba-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56fba-112">语法</span><span class="sxs-lookup"><span data-stu-id="56fba-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56fba-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="56fba-113">Attributes and Elements</span></span>  
 <span data-ttu-id="56fba-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="56fba-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56fba-115">特性</span><span class="sxs-lookup"><span data-stu-id="56fba-115">Attributes</span></span>  
 <span data-ttu-id="56fba-116">无。</span><span class="sxs-lookup"><span data-stu-id="56fba-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="56fba-117">子元素</span><span class="sxs-lookup"><span data-stu-id="56fba-117">Child Elements</span></span>  
  
|<span data-ttu-id="56fba-118">元素</span><span class="sxs-lookup"><span data-stu-id="56fba-118">Element</span></span>|<span data-ttu-id="56fba-119">说明</span><span class="sxs-lookup"><span data-stu-id="56fba-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56fba-120">\<add></span><span class="sxs-lookup"><span data-stu-id="56fba-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="56fba-121">向集合中添加行为。</span><span class="sxs-lookup"><span data-stu-id="56fba-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56fba-122">父元素</span><span class="sxs-lookup"><span data-stu-id="56fba-122">Parent Elements</span></span>  
  
|<span data-ttu-id="56fba-123">元素</span><span class="sxs-lookup"><span data-stu-id="56fba-123">Element</span></span>|<span data-ttu-id="56fba-124">描述</span><span class="sxs-lookup"><span data-stu-id="56fba-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56fba-125">\<k e n ></span><span class="sxs-lookup"><span data-stu-id="56fba-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="56fba-126">指定用于向服务验证客户端身份的自定义令牌。</span><span class="sxs-lookup"><span data-stu-id="56fba-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56fba-127">备注</span><span class="sxs-lookup"><span data-stu-id="56fba-127">Remarks</span></span>  
 <span data-ttu-id="56fba-128">当必须使用任何行为（包含 `<clientCredentials>` 元素的行为除外）与某个服务进行通信时，应使用此元素。</span><span class="sxs-lookup"><span data-stu-id="56fba-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="56fba-129">例如，如果[ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)行为元素必须包含。</span><span class="sxs-lookup"><span data-stu-id="56fba-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56fba-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56fba-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="56fba-131">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="56fba-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="56fba-132">安全行为</span><span class="sxs-lookup"><span data-stu-id="56fba-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="56fba-133">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="56fba-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="56fba-134">保护服务和客户端</span><span class="sxs-lookup"><span data-stu-id="56fba-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="56fba-135">保护客户端</span><span class="sxs-lookup"><span data-stu-id="56fba-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="56fba-136">如何： 创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="56fba-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="56fba-137">如何： 配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="56fba-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="56fba-138">联合身份验证和已颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="56fba-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
