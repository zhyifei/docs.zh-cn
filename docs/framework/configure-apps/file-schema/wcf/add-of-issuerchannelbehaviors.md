---
title: <add> 的 <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: cf7ac2691ad1c641352a8047373ced538b19e983
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398334"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="fb39c-102">\<添加 issuerChannelBehaviors > \<的 ></span><span class="sxs-lookup"><span data-stu-id="fb39c-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="fb39c-103">添加在与 STS 进行通信时要使用的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="fb39c-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="fb39c-104">如果任何终结点行为包含[ \<clientCredentials >](clientcredentials.md)元素，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="fb39c-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="fb39c-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fb39c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fb39c-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fb39c-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fb39c-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="fb39c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="fb39c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="fb39c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="fb39c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="fb39c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="fb39c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="fb39c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="fb39c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedToken >** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="fb39c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="fb39c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuerChannelBehaviors >** ](issuerchannelbehaviors-element.md)</span><span class="sxs-lookup"><span data-stu-id="fb39c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)</span></span>\
<span data-ttu-id="fb39c-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="fb39c-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="fb39c-114">语法</span><span class="sxs-lookup"><span data-stu-id="fb39c-114">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fb39c-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fb39c-115">Attributes and Elements</span></span>

<span data-ttu-id="fb39c-116">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fb39c-116">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="fb39c-117">特性</span><span class="sxs-lookup"><span data-stu-id="fb39c-117">Attributes</span></span>

|<span data-ttu-id="fb39c-118">特性</span><span class="sxs-lookup"><span data-stu-id="fb39c-118">Attribute</span></span>|<span data-ttu-id="fb39c-119">描述</span><span class="sxs-lookup"><span data-stu-id="fb39c-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="fb39c-120">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="fb39c-120">issuerAddress</span></span>|<span data-ttu-id="fb39c-121">要与之通信的安全令牌颁发者的 URI。</span><span class="sxs-lookup"><span data-stu-id="fb39c-121">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="fb39c-122">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="fb39c-122">behaviorConfiguration</span></span>|<span data-ttu-id="fb39c-123">在同一个配置文件中定义的终结点行为的名称。</span><span class="sxs-lookup"><span data-stu-id="fb39c-123">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="fb39c-124">子元素</span><span class="sxs-lookup"><span data-stu-id="fb39c-124">Child Elements</span></span>

<span data-ttu-id="fb39c-125">无。</span><span class="sxs-lookup"><span data-stu-id="fb39c-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fb39c-126">父元素</span><span class="sxs-lookup"><span data-stu-id="fb39c-126">Parent Elements</span></span>

|<span data-ttu-id="fb39c-127">元素</span><span class="sxs-lookup"><span data-stu-id="fb39c-127">Element</span></span>|<span data-ttu-id="fb39c-128">描述</span><span class="sxs-lookup"><span data-stu-id="fb39c-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fb39c-129">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="fb39c-129">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="fb39c-130">包含与指定的服务令牌服务通信时要使用的 Windows Communication Foundation （WCF）客户端终结点行为的集合。</span><span class="sxs-lookup"><span data-stu-id="fb39c-130">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fb39c-131">备注</span><span class="sxs-lookup"><span data-stu-id="fb39c-131">Remarks</span></span>

<span data-ttu-id="fb39c-132">`issuerAddress` 包含客户端希望与之进行通信的安全令牌服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="fb39c-132">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="fb39c-133">`behaviorConfiguration`指向应用程序在 Windows Communication Foundation （WCF）创建的通道中使用的终结点行为，以从安全令牌服务获取已颁发的令牌。</span><span class="sxs-lookup"><span data-stu-id="fb39c-133">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb39c-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb39c-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="fb39c-135">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="fb39c-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fb39c-136">安全行为</span><span class="sxs-lookup"><span data-stu-id="fb39c-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="fb39c-137">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="fb39c-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fb39c-138">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="fb39c-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="fb39c-139">保护客户端</span><span class="sxs-lookup"><span data-stu-id="fb39c-139">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="fb39c-140">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="fb39c-140">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="fb39c-141">如何：配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="fb39c-141">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="fb39c-142">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="fb39c-142">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fb39c-143">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="fb39c-143">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
