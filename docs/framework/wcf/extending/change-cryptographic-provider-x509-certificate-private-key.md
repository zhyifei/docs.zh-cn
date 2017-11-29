---
title: "如何： 更改加密提供程序的 X.509 证书 （&） #39; s 私钥"
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
- cryptographic provider [WCF], changing
- cryptographic provider [WCF]
ms.assetid: b4254406-272e-4774-bd61-27e39bbb6c12
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1158d1fc2d906737087fa4bdf7d2070e5ff4cfae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-cryptographic-provider-for-an-x509-certificate39s-private-key"></a><span data-ttu-id="3cc0c-102">如何： 更改加密提供程序的 X.509 证书 （&） #39; s 私钥</span><span class="sxs-lookup"><span data-stu-id="3cc0c-102">How to: Change the Cryptographic Provider for an X.509 Certificate&#39;s Private Key</span></span>
<span data-ttu-id="3cc0c-103">本主题说明如何更改用于提供 X.509 证书私钥的加密提供程序以及如何将该提供程序集成到 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 安全框架中。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-103">This topic shows how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] security framework.</span></span> <span data-ttu-id="3cc0c-104">有关使用证书的详细信息，请参阅[使用证书](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-104">For more information about using certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="3cc0c-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]安全框架提供了引入新的安全令牌类型中所述的方法[如何： 创建自定义令牌](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-105">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework provides a way to introduce new security token types as described in [How to: Create a Custom Token](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).</span></span> <span data-ttu-id="3cc0c-106">还可以使用自定义令牌替换系统提供的现有令牌类型。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-106">It is also possible to use a custom token to replace existing system-provided token types.</span></span>  
  
 <span data-ttu-id="3cc0c-107">在本主题中，系统提供的 X.509 安全令牌替换为自定义 X.509 令牌，此自定义令牌提供了一种不同的证书私钥的实现。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-107">In this topic, the system-provided X.509 security token is replaced by a custom X.509 token that provides a different implementation for the certificate private key.</span></span> <span data-ttu-id="3cc0c-108">当实际私钥是由默认 Windows 加密提供程序之外的其他加密提供程序提供时，这是非常有用的。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-108">This is useful in scenarios where the actual private key is provided by a different cryptographic provider than the default Windows cryptographic provider.</span></span> <span data-ttu-id="3cc0c-109">可选的加密提供程序的一个示例是硬件安全模块，该模块执行所有私钥相关的加密操作并且没有将私钥存储在内存中，从而提高了系统的安全性。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-109">One example of an alternative cryptographic provider is a hardware security module that performs all private key related cryptographic operations, and does not store the private keys in memory, thus improving security of the system.</span></span>  
  
 <span data-ttu-id="3cc0c-110">下面的示例仅供演示使用。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-110">The following example is for demonstration purposes only.</span></span> <span data-ttu-id="3cc0c-111">它不会替换默认的 Windows 加密提供程序，而只是演示在哪种情况下可以集成这样一个提供程序。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-111">It does not replace the default Windows cryptographic provider, but it shows where such a provider could be integrated.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="3cc0c-112">过程</span><span class="sxs-lookup"><span data-stu-id="3cc0c-112">Procedures</span></span>  
 <span data-ttu-id="3cc0c-113">每个具有一个或多个关联的安全密钥的安全令牌都必须实现 <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A> 属性，以便从此安全令牌实例返回一个密钥集合。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-113">Every security token that has an associated security key or keys must implement the <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A> property, which returns a collection of keys from the security token instance.</span></span> <span data-ttu-id="3cc0c-114">如果此令牌为 X.509 安全令牌，则集合包含一个 <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> 类的实例，此类表示与证书关联的公钥和私钥。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-114">If the token is an X.509 security token, the collection contains a single instance of the <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> class that represents both public and private keys associated with the certificate.</span></span> <span data-ttu-id="3cc0c-115">若要替换用于提供证书密钥的默认的加密提供程序，请创建此类的一个新实现。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-115">To replace the default cryptographic provider used to provide the certificate's keys, create a new implementation of this class.</span></span>  
  
#### <a name="to-create-a-custom-x509-asymmetric-key"></a><span data-ttu-id="3cc0c-116">创建自定义 X.509 非对称密钥</span><span class="sxs-lookup"><span data-stu-id="3cc0c-116">To create a custom X.509 asymmetric key</span></span>  
  
1.  <span data-ttu-id="3cc0c-117">定义一个从 <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> 类派生的新类。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-117">Define a new class derived from the <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> class.</span></span>  
  
2.  <span data-ttu-id="3cc0c-118">重写 <xref:System.IdentityModel.Tokens.SecurityKey.KeySize%2A> 只读属性。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-118">Override the <xref:System.IdentityModel.Tokens.SecurityKey.KeySize%2A> read-only property.</span></span> <span data-ttu-id="3cc0c-119">此属性返回证书的公钥/私钥对的实际密钥大小。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-119">This property returns the actual key size of the certificate's public/private key pair.</span></span>  
  
3.  <span data-ttu-id="3cc0c-120">重写 <xref:System.IdentityModel.Tokens.SecurityKey.DecryptKey%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-120">Override the <xref:System.IdentityModel.Tokens.SecurityKey.DecryptKey%2A> method.</span></span> <span data-ttu-id="3cc0c-121">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 安全框架调用此方法以使用证书的私钥来解密对称密钥。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-121">This method is called by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework to decrypt a symmetric key with the certificate's private key.</span></span> <span data-ttu-id="3cc0c-122">（此密钥之前使用证书的公钥进行加密。）</span><span class="sxs-lookup"><span data-stu-id="3cc0c-122">(The key was previously encrypted with the certificate's public key.)</span></span>  
  
4.  <span data-ttu-id="3cc0c-123">重写 <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetAsymmetricAlgorithm%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-123">Override the <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetAsymmetricAlgorithm%2A> method.</span></span> <span data-ttu-id="3cc0c-124">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 安全框架调用此方法以获取 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 类的实例，此类表示证书私钥或公钥的加密提供程序，具体取决于传递到此方法的参数。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-124">This method is called by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework to obtain an instance of the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class that represents the cryptographic provider for either the certificate's private or public key, depending on the parameters passed to the method.</span></span>  
  
5.  <span data-ttu-id="3cc0c-125">可选。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-125">Optional.</span></span> <span data-ttu-id="3cc0c-126">重写 <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetHashAlgorithmForSignature%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-126">Override the <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetHashAlgorithmForSignature%2A> method.</span></span> <span data-ttu-id="3cc0c-127">如果需要 <xref:System.Security.Cryptography.HashAlgorithm> 类的另一个实现，请重写此方法。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-127">Override this method if a different implementation of the <xref:System.Security.Cryptography.HashAlgorithm> class is required.</span></span>  
  
6.  <span data-ttu-id="3cc0c-128">重写 <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetSignatureFormatter%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-128">Override the <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetSignatureFormatter%2A> method.</span></span> <span data-ttu-id="3cc0c-129">此方法返回与证书私钥关联的 <xref:System.Security.Cryptography.AsymmetricSignatureFormatter> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-129">This method returns an instance of the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter> class that is associated with the certificate's private key.</span></span>  
  
7.  <span data-ttu-id="3cc0c-130">重写 <xref:System.IdentityModel.Tokens.SecurityKey.IsSupportedAlgorithm%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-130">Override the <xref:System.IdentityModel.Tokens.SecurityKey.IsSupportedAlgorithm%2A> method.</span></span> <span data-ttu-id="3cc0c-131">此方法用于指示安全密钥实现是否支持某个特定的加密算法。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-131">This method is used to indicate whether a particular cryptographic algorithm is supported by the security key implementation.</span></span>  
  
     [!code-csharp[c_CustomX509Token#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#1)]
     [!code-vb[c_CustomX509Token#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#1)]  
  
 <span data-ttu-id="3cc0c-132">下面的过程演示如何将上面的过程中创建的自定义 X.509 非对称安全密钥实现与 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 安全框架集成，以替换系统提供的 X.509 安全令牌。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-132">The following procedure shows how to integrate the custom X.509 asymmetric security key implementation created in the preceding procedure with the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework in order to replace the system-provided X.509 security token.</span></span>  
  
#### <a name="to-replace-the-system-provided-x509-security-token-with-a-custom-x509-asymmetric-security-key-token"></a><span data-ttu-id="3cc0c-133">将系统提供的 X.509 安全令牌替换为自定义 X.509 非对称安全密钥令牌</span><span class="sxs-lookup"><span data-stu-id="3cc0c-133">To replace the system-provided X.509 security token with a custom X.509 asymmetric security key token</span></span>  
  
1.  <span data-ttu-id="3cc0c-134">创建一个自定义 X.509 安全令牌，此令牌返回自定义 X.509 非对称安全密钥而不是系统提供的安全密钥，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-134">Create a custom X.509 security token that returns the custom X.509 asymmetric security key instead of the system-provided security key, as shown in the following example.</span></span> <span data-ttu-id="3cc0c-135">有关自定义安全令牌的详细信息，请参阅[如何： 创建自定义令牌](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-135">For more information about custom security tokens, see [How to: Create a Custom Token](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).</span></span>  
  
     [!code-csharp[c_CustomX509Token#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#2)]
     [!code-vb[c_CustomX509Token#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#2)]  
  
2.  <span data-ttu-id="3cc0c-136">创建一个自定义安全令牌提供程序以返回一个自定义 X.509 安全令牌，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-136">Create a custom security token provider that returns a custom X.509 security token, as shown in the example.</span></span> <span data-ttu-id="3cc0c-137">有关自定义安全令牌提供程序的详细信息，请参阅[如何： 创建自定义安全令牌提供程序](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-137">For more information about custom security token providers, see [How to: Create a Custom Security Token Provider](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md).</span></span>  
  
     [!code-csharp[c_CustomX509Token#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#3)]
     [!code-vb[c_CustomX509Token#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#3)]  
  
3.  <span data-ttu-id="3cc0c-138">如果自定义安全密钥需要在发起方端使用，请创建一个自定义客户端安全令牌管理器和若干自定义客户端凭据类，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-138">If the custom security key needs to be used on the initiator side, create a custom client security token manager and custom client credentials classes, as shown in the following example.</span></span> <span data-ttu-id="3cc0c-139">有关自定义客户端凭据和客户端安全令牌管理器的详细信息，请参阅[演练： 创建自定义客户端和服务凭据](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-139">For more information about custom client credentials and client security token managers, see [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
     [!code-csharp[c_CustomX509Token#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#4)]
     [!code-vb[c_CustomX509Token#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#4)]  
  
     [!code-csharp[c_CustomX509Token#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#6)]
     [!code-vb[c_CustomX509Token#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#6)]  
  
4.  <span data-ttu-id="3cc0c-140">如果自定义安全密钥需要在接收方端使用，请创建一个自定义服务安全令牌管理器和若干自定义服务凭据，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-140">If the custom security key needs to be used on the recipient side, create a custom service security token manager and custom service credentials, as shown in the following example.</span></span> <span data-ttu-id="3cc0c-141">有关自定义服务凭据和服务安全令牌管理器的详细信息，请参阅[演练： 创建自定义客户端和服务凭据](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc0c-141">For more information about custom service credentials and service security token managers, see [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
     [!code-csharp[c_CustomX509Token#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#5)]
     [!code-vb[c_CustomX509Token#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#5)]  
  
     [!code-csharp[c_CustomX509Token#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#7)]
     [!code-vb[c_CustomX509Token#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="3cc0c-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cc0c-142">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>  
 <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey>  
 <xref:System.IdentityModel.Tokens.SecurityKey>  
 <xref:System.Security.Cryptography.AsymmetricAlgorithm>  
 <xref:System.Security.Cryptography.HashAlgorithm>  
 <xref:System.Security.Cryptography.AsymmetricSignatureFormatter>  
 [<span data-ttu-id="3cc0c-143">演练： 创建自定义客户端和服务凭据</span><span class="sxs-lookup"><span data-stu-id="3cc0c-143">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [<span data-ttu-id="3cc0c-144">如何： 创建自定义安全令牌身份验证器</span><span class="sxs-lookup"><span data-stu-id="3cc0c-144">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [<span data-ttu-id="3cc0c-145">如何： 创建自定义安全令牌提供程序</span><span class="sxs-lookup"><span data-stu-id="3cc0c-145">How to: Create a Custom Security Token Provider</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 [<span data-ttu-id="3cc0c-146">如何： 创建自定义令牌</span><span class="sxs-lookup"><span data-stu-id="3cc0c-146">How to: Create a Custom Token</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)  
 [<span data-ttu-id="3cc0c-147">安全体系结构</span><span class="sxs-lookup"><span data-stu-id="3cc0c-147">Security Architecture</span></span>](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)
