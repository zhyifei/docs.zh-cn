---
title: <issuerChannelBehaviors> 元素
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: e0e41b4f6d66cd4455c43dda7c77798553f2b58f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929931"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="46bb4-102">\<issuerChannelBehaviors > 元素</span><span class="sxs-lookup"><span data-stu-id="46bb4-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="46bb4-103">包含与指定的服务令牌服务通信时要使用的 Windows Communication Foundation (WCF) 客户端终结点行为 (在配置中定义) 的集合。</span><span class="sxs-lookup"><span data-stu-id="46bb4-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="46bb4-104">定义的行为不能包含任何[ \<clientCredentials >](clientcredentials.md)元素。</span><span class="sxs-lookup"><span data-stu-id="46bb4-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

## <a name="syntax"></a><span data-ttu-id="46bb4-105">语法</span><span class="sxs-lookup"><span data-stu-id="46bb4-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="46bb4-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="46bb4-106">Attributes and Elements</span></span>

<span data-ttu-id="46bb4-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="46bb4-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="46bb4-108">特性</span><span class="sxs-lookup"><span data-stu-id="46bb4-108">Attributes</span></span>

<span data-ttu-id="46bb4-109">无。</span><span class="sxs-lookup"><span data-stu-id="46bb4-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="46bb4-110">子元素</span><span class="sxs-lookup"><span data-stu-id="46bb4-110">Child Elements</span></span>

|<span data-ttu-id="46bb4-111">元素</span><span class="sxs-lookup"><span data-stu-id="46bb4-111">Element</span></span>|<span data-ttu-id="46bb4-112">描述</span><span class="sxs-lookup"><span data-stu-id="46bb4-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="46bb4-113">\<add></span><span class="sxs-lookup"><span data-stu-id="46bb4-113">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="46bb4-114">向集合中添加行为。</span><span class="sxs-lookup"><span data-stu-id="46bb4-114">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="46bb4-115">父元素</span><span class="sxs-lookup"><span data-stu-id="46bb4-115">Parent Elements</span></span>

|<span data-ttu-id="46bb4-116">元素</span><span class="sxs-lookup"><span data-stu-id="46bb4-116">Element</span></span>|<span data-ttu-id="46bb4-117">描述</span><span class="sxs-lookup"><span data-stu-id="46bb4-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="46bb4-118">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="46bb4-118">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="46bb4-119">指定用于向服务验证客户端身份的自定义令牌。</span><span class="sxs-lookup"><span data-stu-id="46bb4-119">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="46bb4-120">备注</span><span class="sxs-lookup"><span data-stu-id="46bb4-120">Remarks</span></span>

<span data-ttu-id="46bb4-121">当必须使用任何行为（包含 `<clientCredentials>` 元素的行为除外）与某个服务进行通信时，应使用此元素。</span><span class="sxs-lookup"><span data-stu-id="46bb4-121">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="46bb4-122">例如, 如果[ \<必须包含 dataContractSerializer >](datacontractserializer-element.md)行为元素。</span><span class="sxs-lookup"><span data-stu-id="46bb4-122">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="46bb4-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="46bb4-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="46bb4-124">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="46bb4-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="46bb4-125">安全行为</span><span class="sxs-lookup"><span data-stu-id="46bb4-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="46bb4-126">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="46bb4-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="46bb4-127">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="46bb4-127">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="46bb4-128">保护客户端</span><span class="sxs-lookup"><span data-stu-id="46bb4-128">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="46bb4-129">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="46bb4-129">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="46bb4-130">如何：配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="46bb4-130">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="46bb4-131">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="46bb4-131">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
