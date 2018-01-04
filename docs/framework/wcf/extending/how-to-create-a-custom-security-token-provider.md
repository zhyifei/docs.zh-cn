---
title: "如何：创建自定义安全令牌提供程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e776b04c626fac134e2fc9c1b9fd0ae63a50b5d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-security-token-provider"></a><span data-ttu-id="e1d37-102">如何：创建自定义安全令牌提供程序</span><span class="sxs-lookup"><span data-stu-id="e1d37-102">How to: Create a Custom Security Token Provider</span></span>
<span data-ttu-id="e1d37-103">本主题介绍如何使用自定义安全令牌提供程序来创建新令牌类型，以及如何将该提供程序与自定义安全令牌管理器集成。</span><span class="sxs-lookup"><span data-stu-id="e1d37-103">This topic shows how to create new token types with a custom security token provider and how to integrate the provider with a custom security token manager.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1d37-104">如果在 <xref:System.IdentityModel.Tokens> 命名空间中找到的系统提供的令牌不符合要求，请创建一个自定义令牌提供程序。</span><span class="sxs-lookup"><span data-stu-id="e1d37-104">Create a custom token provider if the system-provided tokens found in the <xref:System.IdentityModel.Tokens> namespace do not match your requirements.</span></span>  
  
 <span data-ttu-id="e1d37-105">安全令牌提供程序会基于客户端或服务凭据中的信息创建一个安全令牌表示形式。</span><span class="sxs-lookup"><span data-stu-id="e1d37-105">The security token provider creates a security token representation based on information in the client or service credentials.</span></span> <span data-ttu-id="e1d37-106">若要在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 安全中使用自定义安全令牌提供程序，则必须创建自定义凭据和安全令牌管理器实现。</span><span class="sxs-lookup"><span data-stu-id="e1d37-106">To use the custom security token provider in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] security, you must create custom credentials and security token manager implementations.</span></span>  
  
 <span data-ttu-id="e1d37-107">有关自定义凭据和安全令牌管理器的详细信息请参阅[演练： 创建自定义客户端和服务凭据](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)。</span><span class="sxs-lookup"><span data-stu-id="e1d37-107">For more information about custom credentials and security token manager see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
 <span data-ttu-id="e1d37-108">安全令牌的经理、 提供程序和身份验证器类，有关凭据的详细信息，请参阅[安全体系结构](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)。</span><span class="sxs-lookup"><span data-stu-id="e1d37-108">For more information about credentials, security token manager, provider and authenticator classes, see the [Security Architecture](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f).</span></span>  
  
### <a name="to-create-a-custom-security-token-provider"></a><span data-ttu-id="e1d37-109">创建自定义安全令牌提供程序</span><span class="sxs-lookup"><span data-stu-id="e1d37-109">To create a custom security token provider</span></span>  
  
1.  <span data-ttu-id="e1d37-110">定义一个从 <xref:System.IdentityModel.Selectors.SecurityTokenProvider> 类派生的新类。</span><span class="sxs-lookup"><span data-stu-id="e1d37-110">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class.</span></span>  
  
2.  <span data-ttu-id="e1d37-111">实现 <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> 方法。</span><span class="sxs-lookup"><span data-stu-id="e1d37-111">Implement the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method.</span></span> <span data-ttu-id="e1d37-112">该方法负责创建和返回安全令牌的实例。</span><span class="sxs-lookup"><span data-stu-id="e1d37-112">The method is responsible for creating and returning an instance of the security token.</span></span> <span data-ttu-id="e1d37-113">下面的示例创建一个名为 `MySecurityTokenProvider` 的类，并重写 <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> 方法以返回 <xref:System.IdentityModel.Tokens.X509SecurityToken> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="e1d37-113">The following example creates a class named `MySecurityTokenProvider`, and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method to return an instance of the <xref:System.IdentityModel.Tokens.X509SecurityToken> class.</span></span> <span data-ttu-id="e1d37-114">该类构造函数需要 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="e1d37-114">The class constructor requires an instance of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> class.</span></span>  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a><span data-ttu-id="e1d37-115">将自定义安全令牌提供程序与自定义安全令牌管理器集成</span><span class="sxs-lookup"><span data-stu-id="e1d37-115">To integrate a custom security token provider with a custom security token manager</span></span>  
  
1.  <span data-ttu-id="e1d37-116">定义一个从 <xref:System.IdentityModel.Selectors.SecurityTokenManager> 类派生的新类。</span><span class="sxs-lookup"><span data-stu-id="e1d37-116">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.</span></span> <span data-ttu-id="e1d37-117">（下面的示例从 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 类派生，而该类又从 <xref:System.IdentityModel.Selectors.SecurityTokenManager> 类派生。）</span><span class="sxs-lookup"><span data-stu-id="e1d37-117">(The example below derives from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class, which derives from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.)</span></span>  
  
2.  <span data-ttu-id="e1d37-118">重写 <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> 方法（如果尚未重写它）。</span><span class="sxs-lookup"><span data-stu-id="e1d37-118">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method if is not already overridden.</span></span>  
  
     <span data-ttu-id="e1d37-119"><xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> 方法负责返回 <xref:System.IdentityModel.Selectors.SecurityTokenProvider> 类的一个实例，该实例与通过 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> 安全框架传递给该方法的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 参数相对应。</span><span class="sxs-lookup"><span data-stu-id="e1d37-119">The <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method is responsible for returning an instance of the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class appropriate to the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter passed to the method by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework.</span></span> <span data-ttu-id="e1d37-120">修改此方法，以便在用相应的安全令牌参数调用它时，可以返回所实现的自定义安全令牌提供程序（在上一个过程中创建的）。</span><span class="sxs-lookup"><span data-stu-id="e1d37-120">Modify the method to return the custom security token provider implementation (created in the previous procedure) when the method is called with an appropriate security token parameter.</span></span> <span data-ttu-id="e1d37-121">有关安全令牌管理器的详细信息，请参阅[演练： 创建自定义客户端和服务凭据](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)。</span><span class="sxs-lookup"><span data-stu-id="e1d37-121">For more information about the security token manager, see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
3.  <span data-ttu-id="e1d37-122">向该方法中添加自定义逻辑，使其可以基于 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> 参数返回自定义安全令牌提供程序。</span><span class="sxs-lookup"><span data-stu-id="e1d37-122">Add custom logic to the method to enable it to return your custom security token provider based on the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter.</span></span> <span data-ttu-id="e1d37-123">下面的示例在满足令牌要求时返回自定义安全令牌提供程序。</span><span class="sxs-lookup"><span data-stu-id="e1d37-123">The following sample returns the custom security token provider if the token requirements are met.</span></span> <span data-ttu-id="e1d37-124">这些要求包括一个 X.509 安全令牌以及消息方向（使用令牌进行消息输出）。</span><span class="sxs-lookup"><span data-stu-id="e1d37-124">The requirements include an X.509 security token and the message direction (that the token is used for message output).</span></span> <span data-ttu-id="e1d37-125">对于其他所有情况，该代码通过调用基类，针对其他安全令牌需求来维护系统提供的行为。</span><span class="sxs-lookup"><span data-stu-id="e1d37-125">For all other cases, the code calls the base class to maintain the system-provided behavior for other security token requirements.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="e1d37-126">示例</span><span class="sxs-lookup"><span data-stu-id="e1d37-126">Example</span></span>  
 <span data-ttu-id="e1d37-127">下面演示了一个完整的 <xref:System.IdentityModel.Selectors.SecurityTokenProvider> 实现，连同相应的 <xref:System.IdentityModel.Selectors.SecurityTokenManager> 实现。</span><span class="sxs-lookup"><span data-stu-id="e1d37-127">The following shows a complete <xref:System.IdentityModel.Selectors.SecurityTokenProvider> implementation along with a corresponding <xref:System.IdentityModel.Selectors.SecurityTokenManager> implementation.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="e1d37-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1d37-128">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SecurityTokenProvider>  
 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>  
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>  
 <xref:System.IdentityModel.Tokens.X509SecurityToken>  
 [<span data-ttu-id="e1d37-129">演练：创建自定义客户端和服务凭据</span><span class="sxs-lookup"><span data-stu-id="e1d37-129">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [<span data-ttu-id="e1d37-130">如何：创建自定义安全令牌验证器</span><span class="sxs-lookup"><span data-stu-id="e1d37-130">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [<span data-ttu-id="e1d37-131">安全体系结构</span><span class="sxs-lookup"><span data-stu-id="e1d37-131">Security Architecture</span></span>](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)
