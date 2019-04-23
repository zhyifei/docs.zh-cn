---
title: 如何：使用独立的 X.509 证书进行签名和加密
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, extensibility
- ClientCredentials class
- ClientCredentialsSecurityTokenManager class
ms.assetid: 0b06ce4e-7835-4d82-8baf-d525c71a0e49
ms.openlocfilehash: f95274861f58d1581e4c5439861ebf186b1b3489
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332555"
---
# <a name="how-to-use-separate-x509-certificates-for-signing-and-encryption"></a><span data-ttu-id="292c9-102">如何：使用独立的 X.509 证书进行签名和加密</span><span class="sxs-lookup"><span data-stu-id="292c9-102">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>
<span data-ttu-id="292c9-103">本主题演示如何配置 Windows Communication Foundation (WCF) 以进行消息签名和加密客户端和服务上的使用不同的证书。</span><span class="sxs-lookup"><span data-stu-id="292c9-103">This topic shows how to configure Windows Communication Foundation (WCF) to use different certificates for message signing and encryption on both the client and service.</span></span>  
  
 <span data-ttu-id="292c9-104">若要启用独立的证书用于签名和加密，自定义客户端或服务凭据 （或两者） 必须创建因为 WCF 不提供一个 API 来设置多个客户端或服务证书。</span><span class="sxs-lookup"><span data-stu-id="292c9-104">To enable separate certificates to be used for signing and encryption, a custom client or service credentials (or both) must be created because WCF does not provide an API to set multiple client or service certificates.</span></span> <span data-ttu-id="292c9-105">此外，还必须提供安全令牌管理器，以利用多个证书的信息并为指定的密钥用法和消息方向创建相应的安全令牌提供程序。</span><span class="sxs-lookup"><span data-stu-id="292c9-105">Additionally, a security token manager must be provided to leverage the multiple certificates' information and to create an appropriate security token provider for specified key usage and message direction.</span></span>  
  
 <span data-ttu-id="292c9-106">下图演示所用的主类、它们从其继承的类（由向上箭头指示）以及某些方法和属性的返回类型。</span><span class="sxs-lookup"><span data-stu-id="292c9-106">The following diagram shows the main classes used, the classes they inherit from (shown by an upward-pointing arrow), and the return types of certain methods and properties.</span></span>  
  
-   <span data-ttu-id="292c9-107">`MyClientCredentials` 是 <xref:System.ServiceModel.Description.ClientCredentials> 的自定义实现。</span><span class="sxs-lookup"><span data-stu-id="292c9-107">`MyClientCredentials` is a custom implementation of <xref:System.ServiceModel.Description.ClientCredentials>.</span></span>  
  
    -   <span data-ttu-id="292c9-108">图中显示的其属性都返回 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 的实例。</span><span class="sxs-lookup"><span data-stu-id="292c9-108">Its properties shown in the diagram all return instances of <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.</span></span>  
  
    -   <span data-ttu-id="292c9-109">其方法 <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> 返回 `MyClientCredentialsSecurityTokenManager` 的实例。</span><span class="sxs-lookup"><span data-stu-id="292c9-109">Its method <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> returns an instance of `MyClientCredentialsSecurityTokenManager`.</span></span>  
  
-   <span data-ttu-id="292c9-110">`MyClientCredentialsSecurityTokenManager` 是 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 的自定义实现。</span><span class="sxs-lookup"><span data-stu-id="292c9-110">`MyClientCredentialsSecurityTokenManager` is a custom implementation of <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>.</span></span>  
  
    -   <span data-ttu-id="292c9-111">其方法 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> 返回 <xref:System.IdentityModel.Selectors.X509SecurityTokenProvider> 的实例。</span><span class="sxs-lookup"><span data-stu-id="292c9-111">Its method <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> returns an instance of <xref:System.IdentityModel.Selectors.X509SecurityTokenProvider>.</span></span>  
  
 <span data-ttu-id="292c9-112">![显示如何使用客户端凭据的图表](../../../../docs/framework/wcf/extending/media/e4971edd-a59f-4571-b36f-7e6b2f0d610f.gif "e4971edd-a59f-4571-b36f-7e6b2f0d610f")</span><span class="sxs-lookup"><span data-stu-id="292c9-112">![Chart showing how client credentials are used](../../../../docs/framework/wcf/extending/media/e4971edd-a59f-4571-b36f-7e6b2f0d610f.gif "e4971edd-a59f-4571-b36f-7e6b2f0d610f")</span></span>  
  
 <span data-ttu-id="292c9-113">有关自定义凭据的详细信息，请参阅[演练：创建自定义客户端和服务凭据](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)。</span><span class="sxs-lookup"><span data-stu-id="292c9-113">For more information about custom credentials, see [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
 <span data-ttu-id="292c9-114">此外，必须创建自定义标识验证程序，并将它链接到自定义绑定中的安全绑定元素。</span><span class="sxs-lookup"><span data-stu-id="292c9-114">In addition, you must create a custom identity verifier, and link it to a security binding element in a custom binding.</span></span> <span data-ttu-id="292c9-115">还必须使用自定义凭据而不是默认凭据。</span><span class="sxs-lookup"><span data-stu-id="292c9-115">You must also use the custom credentials instead of the default credentials.</span></span>  
  
 <span data-ttu-id="292c9-116">下图演示在自定义绑定中涉及的类，以及如何链接自定义标识验证程序。</span><span class="sxs-lookup"><span data-stu-id="292c9-116">The following diagram shows the classes involved in the custom binding, and how the custom identity verifier is linked.</span></span> <span data-ttu-id="292c9-117">涉及到几个绑定元素，它们都继承自 <xref:System.ServiceModel.Channels.BindingElement>。</span><span class="sxs-lookup"><span data-stu-id="292c9-117">There are several binding elements involved, all of which inherit from <xref:System.ServiceModel.Channels.BindingElement>.</span></span> <span data-ttu-id="292c9-118"><xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> 具有 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> 属性，该属性返回 <xref:System.ServiceModel.Security.IdentityVerifier> 的实例（从其自定义 `MyIdentityVerifier`）。</span><span class="sxs-lookup"><span data-stu-id="292c9-118">The <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> has the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> property, which returns an instance of <xref:System.ServiceModel.Security.IdentityVerifier>, from which `MyIdentityVerifier` is customized.</span></span>  
  
 <span data-ttu-id="292c9-119">![显示自定义绑定元素的图表](../../../../docs/framework/wcf/extending/media/dddea4a2-0bb4-4921-9bf4-20d4d82c3da5.gif "dddea4a2-0bb4-4921-9bf4-20d4d82c3da5")</span><span class="sxs-lookup"><span data-stu-id="292c9-119">![Chart showing a custom binding element](../../../../docs/framework/wcf/extending/media/dddea4a2-0bb4-4921-9bf4-20d4d82c3da5.gif "dddea4a2-0bb4-4921-9bf4-20d4d82c3da5")</span></span>  
  
 <span data-ttu-id="292c9-120">有关创建自定义标识验证程序的详细信息，请参阅如何：[如何：创建自定义客户端标识验证工具](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)。</span><span class="sxs-lookup"><span data-stu-id="292c9-120">For more information about creating a custom identity verifier, see How to: [How to: Create a Custom Client Identity Verifier](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md).</span></span>  
  
### <a name="to-use-separate-certificates-for-signing-and-encryption"></a><span data-ttu-id="292c9-121">使用独立的证书进行签名和加密</span><span class="sxs-lookup"><span data-stu-id="292c9-121">To use separate certificates for signing and encryption</span></span>  
  
1. <span data-ttu-id="292c9-122">定义从 <xref:System.ServiceModel.Description.ClientCredentials> 类继承的新客户端凭据类。</span><span class="sxs-lookup"><span data-stu-id="292c9-122">Define a new client credentials class that inherits from the <xref:System.ServiceModel.Description.ClientCredentials> class.</span></span> <span data-ttu-id="292c9-123">实现四个新属性以允许指定多个证书：`ClientSigningCertificate`、`ClientEncryptingCertificate`、`ServiceSigningCertificate` 和 `ServiceEncryptingCertificate`。</span><span class="sxs-lookup"><span data-stu-id="292c9-123">Implement four new properties to allow multiple certificates specification: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate`, and `ServiceEncryptingCertificate`.</span></span> <span data-ttu-id="292c9-124">还重写 <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> 方法以返回在下一步中定义的自定义 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="292c9-124">Also override the <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> method to return an instance of the customized <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class that is defined in the next step.</span></span>  
  
     [!code-csharp[c_FourCerts#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#1)]
     [!code-vb[c_FourCerts#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#1)]  
  
2. <span data-ttu-id="292c9-125">定义从 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 类继承的新客户端安全令牌管理器。</span><span class="sxs-lookup"><span data-stu-id="292c9-125">Define a new client security token manager that inherits from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class.</span></span> <span data-ttu-id="292c9-126">重写 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> 方法以创建相应的安全令牌提供程序。</span><span class="sxs-lookup"><span data-stu-id="292c9-126">Override the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> method to create an appropriate security token provider.</span></span> <span data-ttu-id="292c9-127">`requirement` 参数（一个 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>）提供消息方向和密钥用法。</span><span class="sxs-lookup"><span data-stu-id="292c9-127">The `requirement` parameter (a <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>) provides the message direction and key usage.</span></span>  
  
     [!code-csharp[c_FourCerts#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#2)]
     [!code-vb[c_FourCerts#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#2)]  
  
3. <span data-ttu-id="292c9-128">定义从 <xref:System.ServiceModel.Description.ServiceCredentials> 类继承的新服务凭据类。</span><span class="sxs-lookup"><span data-stu-id="292c9-128">Define a new service credentials class that inherits from the <xref:System.ServiceModel.Description.ServiceCredentials> class.</span></span> <span data-ttu-id="292c9-129">实现四个新属性以允许指定多个证书：`ClientSigningCertificate`、`ClientEncryptingCertificate`、`ServiceSigningCertificate` 和 `ServiceEncryptingCertificate`。</span><span class="sxs-lookup"><span data-stu-id="292c9-129">Implement four new properties to allow multiple certificates specification: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate`, and `ServiceEncryptingCertificate`.</span></span> <span data-ttu-id="292c9-130">还重写 <xref:System.ServiceModel.Description.ServiceCredentials.CreateSecurityTokenManager%2A> 方法以返回在下一步中定义的自定义 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="292c9-130">Also override the <xref:System.ServiceModel.Description.ServiceCredentials.CreateSecurityTokenManager%2A> method to return an instance of the customized <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> class that is defined in the next step.</span></span>  
  
     [!code-csharp[c_FourCerts#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#3)]
     [!code-vb[c_FourCerts#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#3)]  
  
4. <span data-ttu-id="292c9-131">定义从 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> 类继承的新服务安全令牌管理器。</span><span class="sxs-lookup"><span data-stu-id="292c9-131">Define a new service security token manager that inherits from the <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> class.</span></span> <span data-ttu-id="292c9-132">如果给定传入消息的方向和密钥用法，则重写 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> 方法以创建相应的安全令牌提供程序。</span><span class="sxs-lookup"><span data-stu-id="292c9-132">Override the <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> method to create an appropriate security token provider given the passed-in message direction and key usage.</span></span>  
  
     [!code-csharp[c_FourCerts#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#4)]
     [!code-vb[c_FourCerts#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#4)]  
  
### <a name="to-use-multiple-certificates-on-the-client"></a><span data-ttu-id="292c9-133">在客户端上使用多个证书</span><span class="sxs-lookup"><span data-stu-id="292c9-133">To use multiple certificates on the client</span></span>  
  
1. <span data-ttu-id="292c9-134">创建自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="292c9-134">Create a custom binding.</span></span> <span data-ttu-id="292c9-135">安全绑定元素必须以双工模式运行，以允许为请求和响应采用不同的安全令牌提供程序。</span><span class="sxs-lookup"><span data-stu-id="292c9-135">The security binding element must operate in duplex mode to allow different security token providers to be present for requests and responses.</span></span> <span data-ttu-id="292c9-136">执行此操作的一种方法是使用具有双工能力的传输，或使用下面的代码所示的 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="292c9-136">One way to do this is to use a duplex-capable transport or to use the <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> as shown in the following code.</span></span> <span data-ttu-id="292c9-137">将在下一步中定义的自定义 <xref:System.ServiceModel.Security.IdentityVerifier> 链接到安全绑定元素。</span><span class="sxs-lookup"><span data-stu-id="292c9-137">Link the customized <xref:System.ServiceModel.Security.IdentityVerifier> which is defined in the next step to the security binding element.</span></span> <span data-ttu-id="292c9-138">将默认客户端凭据替换为以前创建的自定义客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="292c9-138">Replace the default client credentials with the customized client credentials previously created.</span></span>  
  
     [!code-csharp[c_FourCerts#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#5)]
     [!code-vb[c_FourCerts#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#5)]  
  
2. <span data-ttu-id="292c9-139">定义一个自定义的 <xref:System.ServiceModel.Security.IdentityVerifier>。</span><span class="sxs-lookup"><span data-stu-id="292c9-139">Define a custom <xref:System.ServiceModel.Security.IdentityVerifier>.</span></span> <span data-ttu-id="292c9-140">因为使用不同的证书来加密请求和对响应进行签名，所以服务具有多个标识。</span><span class="sxs-lookup"><span data-stu-id="292c9-140">The service has multiple identities because different certificates are used to encrypt the request and to sign the response.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="292c9-141">在下面的示例中，出于演示的目的，提供的自定义标识验证程序不执行任何终结点标识检查。</span><span class="sxs-lookup"><span data-stu-id="292c9-141">In the following sample, the provided custom identity verifier does not perform any endpoint identity checking for demonstration purposes.</span></span> <span data-ttu-id="292c9-142">建议在生产代码中不要这样做。</span><span class="sxs-lookup"><span data-stu-id="292c9-142">This is not recommended practice for production code.</span></span>  
  
     [!code-csharp[c_FourCerts#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#6)]
     [!code-vb[c_FourCerts#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#6)]  
  
### <a name="to-use-multiple-certificates-on-the-service"></a><span data-ttu-id="292c9-143">在服务上使用多个证书</span><span class="sxs-lookup"><span data-stu-id="292c9-143">To use multiple certificates on the service</span></span>  
  
1. <span data-ttu-id="292c9-144">创建自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="292c9-144">Create a custom binding.</span></span> <span data-ttu-id="292c9-145">安全绑定元素必须以双工模式运行，以允许为请求和响应采用不同的安全令牌提供程序。</span><span class="sxs-lookup"><span data-stu-id="292c9-145">The security binding element must operate in a duplex mode to allow different security token providers to be present for requests and responses.</span></span> <span data-ttu-id="292c9-146">像客户端一样使用具有双工能力的传输，或使用下面的代码所示的 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="292c9-146">As with the client, use a duplex-capable transport or use <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> as shown in the following code.</span></span> <span data-ttu-id="292c9-147">将默认服务凭据替换为以前创建的自定义服务凭据。</span><span class="sxs-lookup"><span data-stu-id="292c9-147">Replace the default service credentials with the customized service credentials previously created.</span></span>  
  
     [!code-csharp[c_FourCerts#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#7)]
     [!code-vb[c_FourCerts#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="292c9-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="292c9-148">See also</span></span>

- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>
- <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>
- <xref:System.ServiceModel.Security.IdentityVerifier>
- [<span data-ttu-id="292c9-149">演练：创建自定义客户端和服务凭据</span><span class="sxs-lookup"><span data-stu-id="292c9-149">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)
