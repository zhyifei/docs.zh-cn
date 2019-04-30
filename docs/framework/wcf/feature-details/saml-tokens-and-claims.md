---
title: SAML 令牌和声明
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
- issued tokens
- SAML token
ms.assetid: 930b6e34-9eab-4e95-826c-4e06659bb977
ms.openlocfilehash: 04517e5089f55c2d2b08a492439026d33ed9069d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991049"
---
# <a name="saml-tokens-and-claims"></a><span data-ttu-id="40b91-102">SAML 令牌和声明</span><span class="sxs-lookup"><span data-stu-id="40b91-102">SAML Tokens and Claims</span></span>
<span data-ttu-id="40b91-103">安全断言标记语言 (SAML)*令牌*的声明的 XML 表示形式。</span><span class="sxs-lookup"><span data-stu-id="40b91-103">Security Assertions Markup Language (SAML) *tokens* are XML representations of claims.</span></span> <span data-ttu-id="40b91-104">默认情况下，Windows Communication Foundation (WCF) 在联合的安全方案中使用的 SAML 令牌是*颁发的令牌*。</span><span class="sxs-lookup"><span data-stu-id="40b91-104">By default, SAML tokens Windows Communication Foundation (WCF) uses in federated security scenarios are *issued tokens*.</span></span>  
  
 <span data-ttu-id="40b91-105">SAML 令牌包含由一个实体所生成的关于另一实体的多组声明的语句。</span><span class="sxs-lookup"><span data-stu-id="40b91-105">SAML tokens carry statements that are sets of claims made by one entity about another entity.</span></span> <span data-ttu-id="40b91-106">例如，在联合安全方案中，语句是由安全令牌服务针对系统中的某一用户所生成的。</span><span class="sxs-lookup"><span data-stu-id="40b91-106">For example, in federated security scenarios, the statements are made by a security token service about a user in the system.</span></span> <span data-ttu-id="40b91-107">安全令牌服务将对 SAML 令牌进行签名，以指示令牌中所包含语句的真实性。</span><span class="sxs-lookup"><span data-stu-id="40b91-107">The security token service signs the SAML token to indicate the veracity of the statements contained in the token.</span></span> <span data-ttu-id="40b91-108">此外，SAML 令牌与 SAML 令牌用户确实了解的加密密钥材料关联。</span><span class="sxs-lookup"><span data-stu-id="40b91-108">In addition, the SAML token is associated with cryptographic key material that the user of the SAML token proves knowledge of.</span></span> <span data-ttu-id="40b91-109">这就向依赖方证明了 SAML 令牌实际上是颁发给该用户的。</span><span class="sxs-lookup"><span data-stu-id="40b91-109">This proof satisfies the relying party that the SAML token was, in fact, issued to that user.</span></span> <span data-ttu-id="40b91-110">例如，在典型的方案中：</span><span class="sxs-lookup"><span data-stu-id="40b91-110">For example, in a typical scenario:</span></span>  
  
1. <span data-ttu-id="40b91-111">客户端向安全令牌服务请求 SAML 令牌，并通过使用 Windows 证书对该安全令牌服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="40b91-111">A client requests a SAML token from a security token service, authenticating to that security token service by using Windows credentials.</span></span>  
  
2. <span data-ttu-id="40b91-112">安全令牌服务向客户端颁发 SAML 令牌。</span><span class="sxs-lookup"><span data-stu-id="40b91-112">The security token service issues a SAML token to the client.</span></span> <span data-ttu-id="40b91-113">SAML 令牌使用与安全令牌服务关联的证书进行签名，并包含针对目标服务所加密的校验密钥。</span><span class="sxs-lookup"><span data-stu-id="40b91-113">The SAML token is signed with a certificate associated with the security token service and contains a proof key encrypted for the target service.</span></span>  
  
3. <span data-ttu-id="40b91-114">客户端还会收到一份*校验密钥*。</span><span class="sxs-lookup"><span data-stu-id="40b91-114">The client also receives a copy of the *proof key*.</span></span> <span data-ttu-id="40b91-115">客户端然后将 SAML 令牌提供给应用程序服务 (*信赖方*) 和使用该校验密钥对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="40b91-115">The client then presents the SAML token to the application service (the *relying party*) and signs the message with that proof key.</span></span>  
  
4. <span data-ttu-id="40b91-116">依赖方可通过 SAML 令牌上的签名了解到，该令牌是由安全令牌服务颁发的；</span><span class="sxs-lookup"><span data-stu-id="40b91-116">The signature over the SAML token tells the relying party that the security token service issued the token.</span></span> <span data-ttu-id="40b91-117">依赖方还可通过使用校验密钥创建的消息签名了解到，该令牌是颁发给客户端的。</span><span class="sxs-lookup"><span data-stu-id="40b91-117">The message signature created with the proof key tells the relying party that the token was issued to the client.</span></span>  
  
## <a name="from-claims-to-samlattributes"></a><span data-ttu-id="40b91-118">从 Claim 到 SamlAttribute</span><span class="sxs-lookup"><span data-stu-id="40b91-118">From Claims to SamlAttributes</span></span>  
 <span data-ttu-id="40b91-119">在 WCF 中，在 SAML 令牌中的语句被建模为<xref:System.IdentityModel.Tokens.SamlAttribute>对象，可以直接从填充<xref:System.IdentityModel.Claims.Claim>提供的对象<xref:System.IdentityModel.Claims.Claim>对象具有<xref:System.IdentityModel.Claims.Claim.Right%2A>属性<xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>和<xref:System.IdentityModel.Claims.Claim.Resource%2A>属性属于类型<xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="40b91-119">In WCF, statements in SAML tokens are modeled as <xref:System.IdentityModel.Tokens.SamlAttribute> objects, which can be populated directly from <xref:System.IdentityModel.Claims.Claim> objects, provided the <xref:System.IdentityModel.Claims.Claim> object has a <xref:System.IdentityModel.Claims.Claim.Right%2A> property of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> and the <xref:System.IdentityModel.Claims.Claim.Resource%2A> property is of type <xref:System.String>.</span></span> <span data-ttu-id="40b91-120">例如：</span><span class="sxs-lookup"><span data-stu-id="40b91-120">For example:</span></span>  
  
 [!code-csharp[c_CreateSTS#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#8)]
 [!code-vb[c_CreateSTS#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#8)]  
  
> [!NOTE]
>  <span data-ttu-id="40b91-121">如果 SAML 令牌在消息中序列化，无论是在安全令牌服务颁发这些令牌时，还是在客户端将其作为身份验证的一部分提交到服务中时，最大消息大小配额都必须足够大，以便能够容纳 SAML 令牌和其他消息部分。</span><span class="sxs-lookup"><span data-stu-id="40b91-121">When SAML tokens are serialized in messages, either when they are issued by a security token service or when they are presented by clients to services as part of authentication, the maximum message size quota must be sufficiently large to accommodate the SAML token and the other message parts.</span></span> <span data-ttu-id="40b91-122">正常情况下，默认消息大小配额足够使用。</span><span class="sxs-lookup"><span data-stu-id="40b91-122">In normal cases, the default message size quotas are sufficient.</span></span> <span data-ttu-id="40b91-123">但是，如果 SAML 令牌由于包含数以百计的声明而过于庞大，您可能需要提高配额，以便容纳序列化的令牌。</span><span class="sxs-lookup"><span data-stu-id="40b91-123">However, in cases where a SAML token is large because it contains hundreds of claims, you may need to increase the quotas to accommodate the serialized token.</span></span> <span data-ttu-id="40b91-124">有关详细信息，请参阅[数据的安全注意事项](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)。</span><span class="sxs-lookup"><span data-stu-id="40b91-124">For more information, see [Security Considerations for Data](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span></span>  
  
## <a name="from-samlattributes-to-claims"></a><span data-ttu-id="40b91-125">从 SamlAttribute 到 Claim</span><span class="sxs-lookup"><span data-stu-id="40b91-125">From SamlAttributes to Claims</span></span>  
 <span data-ttu-id="40b91-126">在消息中接收到 SAML 令牌时，SAML 令牌中的各种语句将转换为 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 对象，并放置在 <xref:System.IdentityModel.Policy.AuthorizationContext> 中。</span><span class="sxs-lookup"><span data-stu-id="40b91-126">When SAML tokens are received in messages, the various statements in the SAML token are turned into <xref:System.IdentityModel.Policy.IAuthorizationPolicy> objects that are placed into the <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="40b91-127">来自每个 SAML 语句的声明将由 <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> 的 <xref:System.IdentityModel.Policy.AuthorizationContext> 属性返回，并可对这些声明进行检查，以确定是否对该用户进行身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="40b91-127">The claims from each SAML statement are returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> and can be examined to determine whether to authenticate and authorize the user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b91-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="40b91-128">See also</span></span>

- <xref:System.IdentityModel.Policy.AuthorizationContext>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [<span data-ttu-id="40b91-129">联合</span><span class="sxs-lookup"><span data-stu-id="40b91-129">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)
- [<span data-ttu-id="40b91-130">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="40b91-130">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="40b91-131">如何：联合身份验证服务上配置凭据</span><span class="sxs-lookup"><span data-stu-id="40b91-131">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="40b91-132">使用标识模型管理声明和授权</span><span class="sxs-lookup"><span data-stu-id="40b91-132">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [<span data-ttu-id="40b91-133">声明和令牌</span><span class="sxs-lookup"><span data-stu-id="40b91-133">Claims and Tokens</span></span>](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
- [<span data-ttu-id="40b91-134">声明创建和资源值</span><span class="sxs-lookup"><span data-stu-id="40b91-134">Claim Creation and Resource Values</span></span>](../../../../docs/framework/wcf/feature-details/claim-creation-and-resource-values.md)
- [<span data-ttu-id="40b91-135">如何：创建自定义声明</span><span class="sxs-lookup"><span data-stu-id="40b91-135">How to: Create a Custom Claim</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
