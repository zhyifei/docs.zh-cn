---
title: <issuerChannelBehaviors> 元素
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 2c0e0d8d041565edd25c4b2c2802bfd2a589b4f7
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397905"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="8750b-102">\<issuerChannelBehaviors > 元素</span><span class="sxs-lookup"><span data-stu-id="8750b-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="8750b-103">包含与指定的服务令牌服务通信时要使用的 Windows Communication Foundation （WCF）客户端终结点行为（在配置中定义）的集合。</span><span class="sxs-lookup"><span data-stu-id="8750b-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="8750b-104">定义的行为不能包含任何[ \<clientCredentials >](clientcredentials.md)元素。</span><span class="sxs-lookup"><span data-stu-id="8750b-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

<span data-ttu-id="8750b-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8750b-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8750b-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8750b-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8750b-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8750b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="8750b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8750b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="8750b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8750b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="8750b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="8750b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="8750b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedToken >** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="8750b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="8750b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerChannelBehaviors >**</span><span class="sxs-lookup"><span data-stu-id="8750b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerChannelBehaviors>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="8750b-113">语法</span><span class="sxs-lookup"><span data-stu-id="8750b-113">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8750b-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8750b-114">Attributes and Elements</span></span>

<span data-ttu-id="8750b-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8750b-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8750b-116">特性</span><span class="sxs-lookup"><span data-stu-id="8750b-116">Attributes</span></span>

<span data-ttu-id="8750b-117">无。</span><span class="sxs-lookup"><span data-stu-id="8750b-117">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8750b-118">子元素</span><span class="sxs-lookup"><span data-stu-id="8750b-118">Child Elements</span></span>

|<span data-ttu-id="8750b-119">元素</span><span class="sxs-lookup"><span data-stu-id="8750b-119">Element</span></span>|<span data-ttu-id="8750b-120">描述</span><span class="sxs-lookup"><span data-stu-id="8750b-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8750b-121">\<add></span><span class="sxs-lookup"><span data-stu-id="8750b-121">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="8750b-122">向集合中添加行为。</span><span class="sxs-lookup"><span data-stu-id="8750b-122">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8750b-123">父元素</span><span class="sxs-lookup"><span data-stu-id="8750b-123">Parent Elements</span></span>

|<span data-ttu-id="8750b-124">元素</span><span class="sxs-lookup"><span data-stu-id="8750b-124">Element</span></span>|<span data-ttu-id="8750b-125">描述</span><span class="sxs-lookup"><span data-stu-id="8750b-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8750b-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="8750b-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="8750b-127">指定用于向服务验证客户端身份的自定义令牌。</span><span class="sxs-lookup"><span data-stu-id="8750b-127">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8750b-128">备注</span><span class="sxs-lookup"><span data-stu-id="8750b-128">Remarks</span></span>

<span data-ttu-id="8750b-129">当必须使用任何行为（包含 `<clientCredentials>` 元素的行为除外）与某个服务进行通信时，应使用此元素。</span><span class="sxs-lookup"><span data-stu-id="8750b-129">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="8750b-130">例如，如果[ \<必须包含 dataContractSerializer >](datacontractserializer-element.md)行为元素。</span><span class="sxs-lookup"><span data-stu-id="8750b-130">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="8750b-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="8750b-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="8750b-132">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="8750b-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8750b-133">安全行为</span><span class="sxs-lookup"><span data-stu-id="8750b-133">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="8750b-134">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="8750b-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8750b-135">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="8750b-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8750b-136">保护客户端</span><span class="sxs-lookup"><span data-stu-id="8750b-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="8750b-137">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="8750b-137">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="8750b-138">如何：配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="8750b-138">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="8750b-139">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="8750b-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
