---
title: "如何：使用独立的 X.509 证书进行签名和加密"
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
helpviewer_keywords:
- WCF, extensibility
- ClientCredentials class
- ClientCredentialsSecurityTokenManager class
ms.assetid: 0b06ce4e-7835-4d82-8baf-d525c71a0e49
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 944e9974ac5cb84aa0dd7e732c35752cb4ea749e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-separate-x509-certificates-for-signing-and-encryption"></a><span data-ttu-id="c024b-102">如何：使用独立的 X.509 证书进行签名和加密</span><span class="sxs-lookup"><span data-stu-id="c024b-102">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>
<span data-ttu-id="c024b-103">本主题演示如何配置 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 以使用不同的证书在客户端和服务上进行消息签名和加密。</span><span class="sxs-lookup"><span data-stu-id="c024b-103">This topic shows how to configure [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to use different certificates for message signing and encryption on both the client and service.</span></span>  
  
 <span data-ttu-id="c024b-104">若要实现在签名和加密时使用独立的证书，必须创建自定义客户端或服务凭据（或者两者都创建），因为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不提供设置多个客户端或服务证书的 API。</span><span class="sxs-lookup"><span data-stu-id="c024b-104">To enable separate certificates to be used for signing and encryption, a custom client or service credentials (or both) must be created because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not provide an API to set multiple client or service certificates.</span></span> <span data-ttu-id="c024b-105">此外，还必须提供安全令牌管理器，以利用多个证书的信息并为指定的密钥用法和消息方向创建相应的安全令牌提供程序。</span><span class="sxs-lookup"><span data-stu-id="c024b-105">Additionally, a security token manager must be provided to leverage the multiple certificates' information and to create an appropriate security token provider for specified key usage and message direction.</span></span>  
  
 <span data-ttu-id="c024b-106">下图演示所用的主类、它们从其继承的类（由向上箭头指示）以及某些方法和属性的返回类型。</span><span class="sxs-lookup"><span data-stu-id="c024b-106">The following diagram shows the main classes used, the classes they inherit from (shown by an upward-pointing arrow), and the return types of certain methods and properties.</span></span>  
  
-   <span data-ttu-id="c024b-107">`MyClientCredentials` 是 <xref:System.ServiceModel.Description.ClientCredentials> 的自定义实现。</span><span class="sxs-lookup"><span data-stu-id="c024b-107">`MyClientCredentials` is a custom implementation of <xref:System.ServiceModel.Description.ClientCredentials>.</span></span>  
  
    -   <span data-ttu-id="c024b-108">图中显示的其属性都返回 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 的实例。</span><span class="sxs-lookup"><span data-stu-id="c024b-108">Its properties shown in the diagram all return instances of <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.</span></span>  
  
    -   <span data-ttu-id="c024b-109">其方法 <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> 返回 `MyClientCredentialsSecurityTokenManager` 的实例。</span><span class="sxs-lookup"><span data-stu-id="c024b-109">Its method <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> returns an instance of `MyClientCredentialsSecurityTokenManager`.</span></span>  
  
-   <span data-ttu-id="c024b-110">`MyClientCredentialsSecurityTokenManager` 是 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 的自定义实现。</span><span class="sxs-lookup"><span data-stu-id="c024b-110">`MyClientCredentialsSecurityTokenManager` is a custom implementation of <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>.</span></span>  
  
    -   <span data-ttu-id="c024b-111">其方法 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> 返回 <xref:System.IdentityModel.Selectors.X509SecurityTokenProvider> 的实例。</span><span class="sxs-lookup"><span data-stu-id="c024b-111">Its method <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> returns an instance of <xref:System.IdentityModel.Selectors.X509SecurityTokenProvider>.</span></span>  
  
 <span data-ttu-id="c024b-112">![显示如何使用客户端凭据的图表](../../../../docs/framework/wcf/extending/media/e4971edd-a59f-4571-b36f-7e6b2f0d610f.gif "e4971edd-a59f-4571-b36f-7e6b2f0d610f")</span><span class="sxs-lookup"><span data-stu-id="c024b-112">![Chart showing how client credentials are used](../../../../docs/framework/wcf/extending/media/e4971edd-a59f-4571-b36f-7e6b2f0d610f.gif "e4971edd-a59f-4571-b36f-7e6b2f0d610f")</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c024b-113">自定义凭据，请参阅[演练： 创建自定义客户端和服务凭据](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)。</span><span class="sxs-lookup"><span data-stu-id="c024b-113"> custom credentials, see [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
 <span data-ttu-id="c024b-114">此外，必须创建自定义标识验证程序，并将它链接到自定义绑定中的安全绑定元素。</span><span class="sxs-lookup"><span data-stu-id="c024b-114">In addition, you must create a custom identity verifier, and link it to a security binding element in a custom binding.</span></span> <span data-ttu-id="c024b-115">还必须使用自定义凭据而不是默认凭据。</span><span class="sxs-lookup"><span data-stu-id="c024b-115">You must also use the custom credentials instead of the default credentials.</span></span>  
  
 <span data-ttu-id="c024b-116">下图演示在自定义绑定中涉及的类，以及如何链接自定义标识验证程序。</span><span class="sxs-lookup"><span data-stu-id="c024b-116">The following diagram shows the classes involved in the custom binding, and how the custom identity verifier is linked.</span></span> <span data-ttu-id="c024b-117">涉及到几个绑定元素，它们都继承自 <xref:System.ServiceModel.Channels.BindingElement>。</span><span class="sxs-lookup"><span data-stu-id="c024b-117">There are several binding elements involved, all of which inherit from <xref:System.ServiceModel.Channels.BindingElement>.</span></span> <span data-ttu-id="c024b-118"><xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> 具有 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> 属性，该属性返回 <xref:System.ServiceModel.Security.IdentityVerifier> 的实例（从其自定义 `MyIdentityVerifier`）。</span><span class="sxs-lookup"><span data-stu-id="c024b-118">The <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> has the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> property, which returns an instance of <xref:System.ServiceModel.Security.IdentityVerifier>, from which `MyIdentityVerifier` is customized.</span></span>  
  
 <span data-ttu-id="c024b-119">![显示自定义绑定元素的图表](../../../../docs/framework/wcf/extending/media/dddea4a2-0bb4-4921-9bf4-20d4d82c3da5.gif "dddea4a2-0bb4-4921-9bf4-20d4d82c3da5")</span><span class="sxs-lookup"><span data-stu-id="c024b-119">![Chart showing a custom binding element](../../../../docs/framework/wcf/extending/media/dddea4a2-0bb4-4921-9bf4-20d4d82c3da5.gif "dddea4a2-0bb4-4921-9bf4-20d4d82c3da5")</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c024b-120">创建自定义标识验证程序，请参阅如何：[如何： 创建自定义客户端标识验证程序](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)。</span><span class="sxs-lookup"><span data-stu-id="c024b-120"> creating a custom identity verifier, see How to: [How to: Create a Custom Client Identity Verifier](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md).</span></span>  
  
### <a name="to-use-separate-certificates-for-signing-and-encryption"></a><span data-ttu-id="c024b-121">使用独立的证书进行签名和加密</span><span class="sxs-lookup"><span data-stu-id="c024b-121">To use separate certificates for signing and encryption</span></span>  
  
1.  <span data-ttu-id="c024b-122">定义从 <xref:System.ServiceModel.Description.ClientCredentials> 类继承的新客户端凭据类。</span><span class="sxs-lookup"><span data-stu-id="c024b-122">Define a new client credentials class that inherits from the <xref:System.ServiceModel.Description.ClientCredentials> class.</span></span> <span data-ttu-id="c024b-123">实现四个新属性以允许指定多个证书：`ClientSigningCertificate`、`ClientEncryptingCertificate`、`ServiceSigningCertificate` 和 `ServiceEncryptingCertificate`。</span><span class="sxs-lookup"><span data-stu-id="c024b-123">Implement four new properties to allow multiple certificates specification: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate`, and `ServiceEncryptingCertificate`.</span></span> <span data-ttu-id="c024b-124">还重写 <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> 方法以返回在下一步中定义的自定义 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="c024b-124">Also override the <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> method to return an instance of the customized <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class that is defined in the next step.</span></span>  
  
     [!code-csharp[c_FourCerts#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#1)]
     [!code-vb[c_FourCerts#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#1)]  
  
2.  <span data-ttu-id="c024b-125">定义从 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 类继承的新客户端安全令牌管理器。</span><span class="sxs-lookup"><span data-stu-id="c024b-125">Define a new client security token manager that inherits from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class.</span></span> <span data-ttu-id="c024b-126">重写 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> 方法以创建相应的安全令牌提供程序。</span><span class="sxs-lookup"><span data-stu-id="c024b-126">Override the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> method to create an appropriate security token provider.</span></span> <span data-ttu-id="c024b-127">`requirement` 参数（一个 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>）提供消息方向和密钥用法。</span><span class="sxs-lookup"><span data-stu-id="c024b-127">The `requirement` parameter (a <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>) provides the message direction and key usage.</span></span>  
  
     [!code-csharp[c_FourCerts#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#2)]
     [!code-vb[c_FourCerts#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#2)]  
  
3.  <span data-ttu-id="c024b-128">定义从 <xref:System.ServiceModel.Description.ServiceCredentials> 类继承的新服务凭据类。</span><span class="sxs-lookup"><span data-stu-id="c024b-128">Define a new service credentials class that inherits from the <xref:System.ServiceModel.Description.ServiceCredentials> class.</span></span> <span data-ttu-id="c024b-129">实现四个新属性以允许指定多个证书：`ClientSigningCertificate`、`ClientEncryptingCertificate`、`ServiceSigningCertificate` 和 `ServiceEncryptingCertificate`。</span><span class="sxs-lookup"><span data-stu-id="c024b-129">Implement four new properties to allow multiple certificates specification: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate`, and `ServiceEncryptingCertificate`.</span></span> <span data-ttu-id="c024b-130">还重写 <xref:System.ServiceModel.Description.ServiceCredentials.CreateSecurityTokenManager%2A> 方法以返回在下一步中定义的自定义 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="c024b-130">Also override the <xref:System.ServiceModel.Description.ServiceCredentials.CreateSecurityTokenManager%2A> method to return an instance of the customized <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> class that is defined in the next step.</span></span>  
  
     [!code-csharp[c_FourCerts#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#3)]
     [!code-vb[c_FourCerts#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#3)]  
  
4.  <span data-ttu-id="c024b-131">定义从 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> 类继承的新服务安全令牌管理器。</span><span class="sxs-lookup"><span data-stu-id="c024b-131">Define a new service security token manager that inherits from the <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> class.</span></span> <span data-ttu-id="c024b-132">如果给定传入消息的方向和密钥用法，则重写 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> 方法以创建相应的安全令牌提供程序。</span><span class="sxs-lookup"><span data-stu-id="c024b-132">Override the <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> method to create an appropriate security token provider given the passed-in message direction and key usage.</span></span>  
  
     [!code-csharp[c_FourCerts#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#4)]
     [!code-vb[c_FourCerts#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#4)]  
  
### <a name="to-use-multiple-certificates-on-the-client"></a><span data-ttu-id="c024b-133">在客户端上使用多个证书</span><span class="sxs-lookup"><span data-stu-id="c024b-133">To use multiple certificates on the client</span></span>  
  
1.  <span data-ttu-id="c024b-134">创建自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="c024b-134">Create a custom binding.</span></span> <span data-ttu-id="c024b-135">安全绑定元素必须以双工模式运行，以允许为请求和响应采用不同的安全令牌提供程序。</span><span class="sxs-lookup"><span data-stu-id="c024b-135">The security binding element must operate in duplex mode to allow different security token providers to be present for requests and responses.</span></span> <span data-ttu-id="c024b-136">执行此操作的一种方法是使用具有双工能力的传输，或使用下面的代码所示的 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="c024b-136">One way to do this is to use a duplex-capable transport or to use the <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> as shown in the following code.</span></span> <span data-ttu-id="c024b-137">将在下一步中定义的自定义 <xref:System.ServiceModel.Security.IdentityVerifier> 链接到安全绑定元素。</span><span class="sxs-lookup"><span data-stu-id="c024b-137">Link the customized <xref:System.ServiceModel.Security.IdentityVerifier> which is defined in the next step to the security binding element.</span></span> <span data-ttu-id="c024b-138">将默认客户端凭据替换为以前创建的自定义客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="c024b-138">Replace the default client credentials with the customized client credentials previously created.</span></span>  
  
     [!code-csharp[c_FourCerts#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#5)]
     [!code-vb[c_FourCerts#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#5)]  
  
2.  <span data-ttu-id="c024b-139">定义一个自定义的 <xref:System.ServiceModel.Security.IdentityVerifier>。</span><span class="sxs-lookup"><span data-stu-id="c024b-139">Define a custom <xref:System.ServiceModel.Security.IdentityVerifier>.</span></span> <span data-ttu-id="c024b-140">因为使用不同的证书来加密请求和对响应进行签名，所以服务具有多个标识。</span><span class="sxs-lookup"><span data-stu-id="c024b-140">The service has multiple identities because different certificates are used to encrypt the request and to sign the response.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c024b-141">在下面的示例中，出于演示的目的，提供的自定义标识验证程序不执行任何终结点标识检查。</span><span class="sxs-lookup"><span data-stu-id="c024b-141">In the following sample, the provided custom identity verifier does not perform any endpoint identity checking for demonstration purposes.</span></span> <span data-ttu-id="c024b-142">建议在生产代码中不要这样做。</span><span class="sxs-lookup"><span data-stu-id="c024b-142">This is not recommended practice for production code.</span></span>  
  
     [!code-csharp[c_FourCerts#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#6)]
     [!code-vb[c_FourCerts#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#6)]  
  
### <a name="to-use-multiple-certificates-on-the-service"></a><span data-ttu-id="c024b-143">在服务上使用多个证书</span><span class="sxs-lookup"><span data-stu-id="c024b-143">To use multiple certificates on the service</span></span>  
  
1.  <span data-ttu-id="c024b-144">创建自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="c024b-144">Create a custom binding.</span></span> <span data-ttu-id="c024b-145">安全绑定元素必须以双工模式运行，以允许为请求和响应采用不同的安全令牌提供程序。</span><span class="sxs-lookup"><span data-stu-id="c024b-145">The security binding element must operate in a duplex mode to allow different security token providers to be present for requests and responses.</span></span> <span data-ttu-id="c024b-146">像客户端一样使用具有双工能力的传输，或使用下面的代码所示的 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="c024b-146">As with the client, use a duplex-capable transport or use <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> as shown in the following code.</span></span> <span data-ttu-id="c024b-147">将默认服务凭据替换为以前创建的自定义服务凭据。</span><span class="sxs-lookup"><span data-stu-id="c024b-147">Replace the default service credentials with the customized service credentials previously created.</span></span>  
  
     [!code-csharp[c_FourCerts#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#7)]
     [!code-vb[c_FourCerts#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="c024b-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="c024b-148">See Also</span></span>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>  
 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>  
 <xref:System.ServiceModel.Security.IdentityVerifier>  
 [<span data-ttu-id="c024b-149">演练：创建自定义客户端和服务凭据</span><span class="sxs-lookup"><span data-stu-id="c024b-149">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)
