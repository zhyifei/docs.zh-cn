---
title: <add> 的 <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 325d6b8111115384b18547bd11ccec8a4a8af711
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920115"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="920fd-102">\<添加 issuerChannelBehaviors > \<的 ></span><span class="sxs-lookup"><span data-stu-id="920fd-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="920fd-103">添加在与 STS 进行通信时要使用的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="920fd-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="920fd-104">如果任何终结点行为包含[ \<clientCredentials >](clientcredentials.md)元素, 则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="920fd-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="920fd-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="920fd-105">\<system.ServiceModel></span></span>\
<span data-ttu-id="920fd-106">\<行为 > </span><span class="sxs-lookup"><span data-stu-id="920fd-106">\<behaviors></span></span>\
<span data-ttu-id="920fd-107">endpointBehaviors 部分\<行为 > </span><span class="sxs-lookup"><span data-stu-id="920fd-107">endpointBehaviors section \<behavior></span></span>\
<span data-ttu-id="920fd-108">\<clientCredentials > </span><span class="sxs-lookup"><span data-stu-id="920fd-108">\<clientCredentials></span></span>\
<span data-ttu-id="920fd-109">\<issuedToken > </span><span class="sxs-lookup"><span data-stu-id="920fd-109">\<issuedToken></span></span>\
<span data-ttu-id="920fd-110">\<issuerChannelBehaviors > 元素 </span><span class="sxs-lookup"><span data-stu-id="920fd-110">\<issuerChannelBehaviors> Element</span></span>\
<span data-ttu-id="920fd-111">\<add></span><span class="sxs-lookup"><span data-stu-id="920fd-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="920fd-112">语法</span><span class="sxs-lookup"><span data-stu-id="920fd-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="920fd-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="920fd-113">Attributes and Elements</span></span>

<span data-ttu-id="920fd-114">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="920fd-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="920fd-115">特性</span><span class="sxs-lookup"><span data-stu-id="920fd-115">Attributes</span></span>

|<span data-ttu-id="920fd-116">特性</span><span class="sxs-lookup"><span data-stu-id="920fd-116">Attribute</span></span>|<span data-ttu-id="920fd-117">描述</span><span class="sxs-lookup"><span data-stu-id="920fd-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="920fd-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="920fd-118">issuerAddress</span></span>|<span data-ttu-id="920fd-119">要与之通信的安全令牌颁发者的 URI。</span><span class="sxs-lookup"><span data-stu-id="920fd-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="920fd-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="920fd-120">behaviorConfiguration</span></span>|<span data-ttu-id="920fd-121">在同一个配置文件中定义的终结点行为的名称。</span><span class="sxs-lookup"><span data-stu-id="920fd-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="920fd-122">子元素</span><span class="sxs-lookup"><span data-stu-id="920fd-122">Child Elements</span></span>

<span data-ttu-id="920fd-123">无。</span><span class="sxs-lookup"><span data-stu-id="920fd-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="920fd-124">父元素</span><span class="sxs-lookup"><span data-stu-id="920fd-124">Parent Elements</span></span>

|<span data-ttu-id="920fd-125">元素</span><span class="sxs-lookup"><span data-stu-id="920fd-125">Element</span></span>|<span data-ttu-id="920fd-126">描述</span><span class="sxs-lookup"><span data-stu-id="920fd-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="920fd-127">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="920fd-127">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="920fd-128">包含与指定的服务令牌服务通信时要使用的 Windows Communication Foundation (WCF) 客户端终结点行为的集合。</span><span class="sxs-lookup"><span data-stu-id="920fd-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="920fd-129">备注</span><span class="sxs-lookup"><span data-stu-id="920fd-129">Remarks</span></span>

<span data-ttu-id="920fd-130">`issuerAddress` 包含客户端希望与之进行通信的安全令牌服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="920fd-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="920fd-131">`behaviorConfiguration`指向应用程序在 Windows Communication Foundation (WCF) 创建的通道中使用的终结点行为, 以从安全令牌服务获取已颁发的令牌。</span><span class="sxs-lookup"><span data-stu-id="920fd-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="920fd-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="920fd-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="920fd-133">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="920fd-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="920fd-134">安全行为</span><span class="sxs-lookup"><span data-stu-id="920fd-134">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="920fd-135">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="920fd-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="920fd-136">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="920fd-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="920fd-137">保护客户端</span><span class="sxs-lookup"><span data-stu-id="920fd-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="920fd-138">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="920fd-138">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="920fd-139">如何：配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="920fd-139">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="920fd-140">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="920fd-140">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="920fd-141">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="920fd-141">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
