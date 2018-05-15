---
title: '&lt;k e n&gt;'
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 9a8d701e0806aae0a17a1c5ff7284606dd080f85
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuedtokengt"></a><span data-ttu-id="5f2c4-102">&lt;k e n&gt;</span><span class="sxs-lookup"><span data-stu-id="5f2c4-102">&lt;issuedToken&gt;</span></span>
<span data-ttu-id="5f2c4-103">指定用于向服务验证客户端身份的自定义令牌。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-103">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
 <span data-ttu-id="5f2c4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5f2c4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5f2c4-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="5f2c4-105">\<behaviors></span></span>  
<span data-ttu-id="5f2c4-106">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="5f2c4-106">endpointBehaviors section</span></span>  
<span data-ttu-id="5f2c4-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="5f2c4-107">\<behavior></span></span>  
<span data-ttu-id="5f2c4-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="5f2c4-108">\<clientCredentials></span></span>  
<span data-ttu-id="5f2c4-109">\<k e n ></span><span class="sxs-lookup"><span data-stu-id="5f2c4-109">\<issuedToken></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f2c4-110">语法</span><span class="sxs-lookup"><span data-stu-id="5f2c4-110">Syntax</span></span>  
  
```xml  
<issuedToken   
   cacheIssuedTokens="Boolean"  
   defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"  
   issuedTokenRenewalThresholdPercentage = "0 to 100"  
   issuerChannelBehaviors="String"  
      localIssuerChannelBehaviors="String"  
   maxIssuedTokenCachingTime="TimeSpan"  
</issuedToken>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f2c4-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5f2c4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5f2c4-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f2c4-113">特性</span><span class="sxs-lookup"><span data-stu-id="5f2c4-113">Attributes</span></span>  
  
|<span data-ttu-id="5f2c4-114">特性</span><span class="sxs-lookup"><span data-stu-id="5f2c4-114">Attribute</span></span>|<span data-ttu-id="5f2c4-115">描述</span><span class="sxs-lookup"><span data-stu-id="5f2c4-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="5f2c4-116">可选的布尔值属性，指定是否对令牌进行缓存。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-116">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="5f2c4-117">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-117">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="5f2c4-118">可选的字符串属性，指定用于握手操作的随机值（熵）。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-118">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="5f2c4-119">这些值包括 `ClientEntropy`、`ServerEntropy` 和 `CombinedEntropy`，默认值为 `CombinedEntropy`。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-119">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="5f2c4-120">此属性的类型为 <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="5f2c4-121">可选的整数属性，指定在续订令牌之前可经过的有效时间段（由令牌颁发者提供）的百分比。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-121">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="5f2c4-122">值的范围是 0 到 100。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-122">Values are from 0 to 100.</span></span> <span data-ttu-id="5f2c4-123">默认值为 60，指定尝试续订之前经过了 60% 的时间。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-123">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="5f2c4-124">可选属性，指定当与颁发者进行通信时所使用的通道行为。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-124">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="5f2c4-125">可选属性，指定当与本地颁发者进行通信时所使用的通道行为。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-125">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="5f2c4-126">可选的 Timespan 属性，指定当令牌颁发者 (STS) 未指定时间时，对颁发的令牌进行缓存的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-126">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="5f2c4-127">默认值是"10675199.02:48:05.4775807。"</span><span class="sxs-lookup"><span data-stu-id="5f2c4-127">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f2c4-128">子元素</span><span class="sxs-lookup"><span data-stu-id="5f2c4-128">Child Elements</span></span>  
  
|<span data-ttu-id="5f2c4-129">元素</span><span class="sxs-lookup"><span data-stu-id="5f2c4-129">Element</span></span>|<span data-ttu-id="5f2c4-130">描述</span><span class="sxs-lookup"><span data-stu-id="5f2c4-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f2c4-131">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="5f2c4-131">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="5f2c4-132">指定令牌的本地颁发者地址以及用于与终结点进行通信的绑定。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-132">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[<span data-ttu-id="5f2c4-133">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5f2c4-133">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="5f2c4-134">指定当联系本地颁发者时所使用的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-134">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5f2c4-135">父元素</span><span class="sxs-lookup"><span data-stu-id="5f2c4-135">Parent Elements</span></span>  
  
|<span data-ttu-id="5f2c4-136">元素</span><span class="sxs-lookup"><span data-stu-id="5f2c4-136">Element</span></span>|<span data-ttu-id="5f2c4-137">描述</span><span class="sxs-lookup"><span data-stu-id="5f2c4-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f2c4-138">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="5f2c4-138">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="5f2c4-139">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-139">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f2c4-140">备注</span><span class="sxs-lookup"><span data-stu-id="5f2c4-140">Remarks</span></span>  
 <span data-ttu-id="5f2c4-141">例如，颁发的令牌是在使用联合方案中的安全令牌服务 (STS) 进行身份验证时所使用的自定义凭据类型。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-141">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="5f2c4-142">默认情况下，该令牌为 SAML 令牌。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-142">By default, the token is a SAML token.</span></span> <span data-ttu-id="5f2c4-143">有关详细信息，请参阅[联合身份验证和颁发令牌](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-143">For more information, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span> <span data-ttu-id="5f2c4-144">和[联合身份验证和已颁发的令牌](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-144">and [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="5f2c4-145">本节包含用于配置本地令牌颁发者的元素，或者与安全令牌服务一起使用的行为。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-145">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="5f2c4-146">有关配置客户端使用本地颁发者的说明，请参阅[如何： 配置本地颁发者](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)。</span><span class="sxs-lookup"><span data-stu-id="5f2c4-146">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f2c4-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f2c4-147">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [<span data-ttu-id="5f2c4-148">安全行为</span><span class="sxs-lookup"><span data-stu-id="5f2c4-148">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="5f2c4-149">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="5f2c4-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="5f2c4-150">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="5f2c4-150">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="5f2c4-151">保护客户端</span><span class="sxs-lookup"><span data-stu-id="5f2c4-151">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="5f2c4-152">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="5f2c4-152">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="5f2c4-153">如何：配置本地证书颁发者</span><span class="sxs-lookup"><span data-stu-id="5f2c4-153">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="5f2c4-154">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="5f2c4-154">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
