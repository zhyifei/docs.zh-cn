---
title: 扩展安全性
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 95dacf3ef975be1ddd56db747936cca35db50625
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099633"
---
# <a name="extending-security"></a><span data-ttu-id="eb62a-102">扩展安全性</span><span class="sxs-lookup"><span data-stu-id="eb62a-102">Extending Security</span></span>
<span data-ttu-id="eb62a-103">若要适应新的声明类型和自定义令牌，可以扩展安全基础结构的 Windows Communication Foundation (WCF)。</span><span class="sxs-lookup"><span data-stu-id="eb62a-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="eb62a-104">本节中的主题将向您介绍如何完成此任务。</span><span class="sxs-lookup"><span data-stu-id="eb62a-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb62a-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="eb62a-105">In This Section</span></span>  
  
 [<span data-ttu-id="eb62a-106">自定义凭据和凭据验证</span><span class="sxs-lookup"><span data-stu-id="eb62a-106">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="eb62a-107">说明在验证自定义凭据时如何使用标识模型。</span><span class="sxs-lookup"><span data-stu-id="eb62a-107">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="eb62a-108">自定义令牌</span><span class="sxs-lookup"><span data-stu-id="eb62a-108">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="eb62a-109">安全令牌服务 (STS) 颁发的令牌通常为 SAML 令牌。</span><span class="sxs-lookup"><span data-stu-id="eb62a-109">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="eb62a-110">本主题说明如何创建自定义令牌类型。</span><span class="sxs-lookup"><span data-stu-id="eb62a-110">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="eb62a-111">自定义授权</span><span class="sxs-lookup"><span data-stu-id="eb62a-111">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="eb62a-112">说明如何实现自定义授权。</span><span class="sxs-lookup"><span data-stu-id="eb62a-112">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="eb62a-113">重写服务标识以便进行身份验证</span><span class="sxs-lookup"><span data-stu-id="eb62a-113">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="eb62a-114">介绍如何重写身份验证服务的标识。</span><span class="sxs-lookup"><span data-stu-id="eb62a-114">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="eb62a-115">如何：创建自定义客户端标识验证工具</span><span class="sxs-lookup"><span data-stu-id="eb62a-115">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="eb62a-116">演示如何验证自定义终结点标识。</span><span class="sxs-lookup"><span data-stu-id="eb62a-116">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="eb62a-117">如何：使用独立的 X.509 证书进行签名和加密</span><span class="sxs-lookup"><span data-stu-id="eb62a-117">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="eb62a-118">通常使用单个证书对消息进行签名和加密。</span><span class="sxs-lookup"><span data-stu-id="eb62a-118">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="eb62a-119">本主题说明如何按照要求使用两个证书。</span><span class="sxs-lookup"><span data-stu-id="eb62a-119">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="eb62a-120">如何：更改 X.509 证书的私钥的加密提供程序</span><span class="sxs-lookup"><span data-stu-id="eb62a-120">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="eb62a-121">说明如何更改用于提供 X.509 证书的私钥的加密提供程序以及如何将提供程序集成到 Windows Communication Foundation (WCF) 框架。</span><span class="sxs-lookup"><span data-stu-id="eb62a-121">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="eb62a-122">参考</span><span class="sxs-lookup"><span data-stu-id="eb62a-122">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="eb62a-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="eb62a-123">Related Sections</span></span>  
 [<span data-ttu-id="eb62a-124">安全性</span><span class="sxs-lookup"><span data-stu-id="eb62a-124">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="eb62a-125">基本 WCF 编程</span><span class="sxs-lookup"><span data-stu-id="eb62a-125">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="eb62a-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb62a-126">See also</span></span>

- [<span data-ttu-id="eb62a-127">安全性概述</span><span class="sxs-lookup"><span data-stu-id="eb62a-127">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
