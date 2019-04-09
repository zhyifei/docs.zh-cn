---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 83061b283c9430af7bcda9cbc832811fa805ed4c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104944"
---
# <a name="issuedtoken"></a><span data-ttu-id="3b777-101">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="3b777-101">\<issuedToken></span></span>
<span data-ttu-id="3b777-102">指定用于向服务验证客户端身份的自定义令牌。</span><span class="sxs-lookup"><span data-stu-id="3b777-102">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
 <span data-ttu-id="3b777-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3b777-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3b777-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="3b777-104">\<behaviors></span></span>  
<span data-ttu-id="3b777-105">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="3b777-105">endpointBehaviors section</span></span>  
<span data-ttu-id="3b777-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3b777-106">\<behavior></span></span>  
<span data-ttu-id="3b777-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="3b777-107">\<clientCredentials></span></span>  
<span data-ttu-id="3b777-108">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="3b777-108">\<issuedToken></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b777-109">语法</span><span class="sxs-lookup"><span data-stu-id="3b777-109">Syntax</span></span>  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b777-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3b777-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3b777-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3b777-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b777-112">特性</span><span class="sxs-lookup"><span data-stu-id="3b777-112">Attributes</span></span>  
  
|<span data-ttu-id="3b777-113">特性</span><span class="sxs-lookup"><span data-stu-id="3b777-113">Attribute</span></span>|<span data-ttu-id="3b777-114">描述</span><span class="sxs-lookup"><span data-stu-id="3b777-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="3b777-115">可选的布尔值属性，指定是否对令牌进行缓存。</span><span class="sxs-lookup"><span data-stu-id="3b777-115">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="3b777-116">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="3b777-116">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="3b777-117">可选的字符串属性，指定用于握手操作的随机值（熵）。</span><span class="sxs-lookup"><span data-stu-id="3b777-117">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="3b777-118">这些值包括 `ClientEntropy`、`ServerEntropy` 和 `CombinedEntropy`，默认值为 `CombinedEntropy`。</span><span class="sxs-lookup"><span data-stu-id="3b777-118">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="3b777-119">此属性的类型为 <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>。</span><span class="sxs-lookup"><span data-stu-id="3b777-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="3b777-120">可选的整数属性，指定在续订令牌之前可经过的有效时间段（由令牌颁发者提供）的百分比。</span><span class="sxs-lookup"><span data-stu-id="3b777-120">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="3b777-121">值的范围是 0 到 100。</span><span class="sxs-lookup"><span data-stu-id="3b777-121">Values are from 0 to 100.</span></span> <span data-ttu-id="3b777-122">默认值为 60，指定尝试续订之前经过了 60% 的时间。</span><span class="sxs-lookup"><span data-stu-id="3b777-122">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="3b777-123">可选属性，指定当与颁发者进行通信时所使用的通道行为。</span><span class="sxs-lookup"><span data-stu-id="3b777-123">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="3b777-124">可选属性，指定当与本地颁发者进行通信时所使用的通道行为。</span><span class="sxs-lookup"><span data-stu-id="3b777-124">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="3b777-125">可选的 Timespan 属性，指定当令牌颁发者 (STS) 未指定时间时，对颁发的令牌进行缓存的持续时间。</span><span class="sxs-lookup"><span data-stu-id="3b777-125">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="3b777-126">默认值是"10675199.02:48:05.4775807。"</span><span class="sxs-lookup"><span data-stu-id="3b777-126">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b777-127">子元素</span><span class="sxs-lookup"><span data-stu-id="3b777-127">Child Elements</span></span>  
  
|<span data-ttu-id="3b777-128">元素</span><span class="sxs-lookup"><span data-stu-id="3b777-128">Element</span></span>|<span data-ttu-id="3b777-129">描述</span><span class="sxs-lookup"><span data-stu-id="3b777-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b777-130">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="3b777-130">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="3b777-131">指定令牌的本地颁发者地址以及用于与终结点进行通信的绑定。</span><span class="sxs-lookup"><span data-stu-id="3b777-131">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[<span data-ttu-id="3b777-132">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="3b777-132">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="3b777-133">指定当联系本地颁发者时所使用的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="3b777-133">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3b777-134">父元素</span><span class="sxs-lookup"><span data-stu-id="3b777-134">Parent Elements</span></span>  
  
|<span data-ttu-id="3b777-135">元素</span><span class="sxs-lookup"><span data-stu-id="3b777-135">Element</span></span>|<span data-ttu-id="3b777-136">描述</span><span class="sxs-lookup"><span data-stu-id="3b777-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b777-137">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="3b777-137">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="3b777-138">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="3b777-138">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b777-139">备注</span><span class="sxs-lookup"><span data-stu-id="3b777-139">Remarks</span></span>  
 <span data-ttu-id="3b777-140">例如，颁发的令牌是在使用联合方案中的安全令牌服务 (STS) 进行身份验证时所使用的自定义凭据类型。</span><span class="sxs-lookup"><span data-stu-id="3b777-140">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="3b777-141">默认情况下，该令牌为 SAML 令牌。</span><span class="sxs-lookup"><span data-stu-id="3b777-141">By default, the token is a SAML token.</span></span> <span data-ttu-id="3b777-142">有关详细信息，请参阅[联合身份验证和颁发令牌](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)。</span><span class="sxs-lookup"><span data-stu-id="3b777-142">For more information, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span> <span data-ttu-id="3b777-143">并[联合身份验证和已颁发的令牌](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)。</span><span class="sxs-lookup"><span data-stu-id="3b777-143">and [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="3b777-144">本节包含用于配置本地令牌颁发者的元素，或者与安全令牌服务一起使用的行为。</span><span class="sxs-lookup"><span data-stu-id="3b777-144">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="3b777-145">有关配置客户端以使用本地颁发者的说明，请参阅[如何：配置本地颁发者](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)。</span><span class="sxs-lookup"><span data-stu-id="3b777-145">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b777-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b777-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="3b777-147">安全行为</span><span class="sxs-lookup"><span data-stu-id="3b777-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="3b777-148">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="3b777-148">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3b777-149">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="3b777-149">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3b777-150">保证客户端的安全</span><span class="sxs-lookup"><span data-stu-id="3b777-150">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="3b777-151">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="3b777-151">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="3b777-152">如何：配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="3b777-152">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="3b777-153">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="3b777-153">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
