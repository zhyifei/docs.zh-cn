---
title: "扩展安全性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: cdd9b91ba7ff9b1e431f7d9107e72df084ba8af3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="extending-security"></a><span data-ttu-id="349c6-102">扩展安全性</span><span class="sxs-lookup"><span data-stu-id="349c6-102">Extending Security</span></span>
<span data-ttu-id="349c6-103">若要容纳新的声明类型和自定义令牌，您可以扩展 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 的安全基础结构。</span><span class="sxs-lookup"><span data-stu-id="349c6-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="349c6-104">本节中的主题将向您介绍如何完成此任务。</span><span class="sxs-lookup"><span data-stu-id="349c6-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="349c6-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="349c6-105">In This Section</span></span>  
 [<span data-ttu-id="349c6-106">安全体系结构</span><span class="sxs-lookup"><span data-stu-id="349c6-106">Security Architecture</span></span>](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)  
 <span data-ttu-id="349c6-107">浏览 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 安全系统的体系结构。</span><span class="sxs-lookup"><span data-stu-id="349c6-107">Walks through the architecture of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security system.</span></span>  
  
 [<span data-ttu-id="349c6-108">自定义凭据和凭据验证</span><span class="sxs-lookup"><span data-stu-id="349c6-108">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="349c6-109">说明在验证自定义凭据时如何使用标识模型。</span><span class="sxs-lookup"><span data-stu-id="349c6-109">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="349c6-110">自定义令牌</span><span class="sxs-lookup"><span data-stu-id="349c6-110">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="349c6-111">安全令牌服务 (STS) 颁发的令牌通常为 SAML 令牌。</span><span class="sxs-lookup"><span data-stu-id="349c6-111">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="349c6-112">本主题说明如何创建自定义令牌类型。</span><span class="sxs-lookup"><span data-stu-id="349c6-112">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="349c6-113">自定义授权</span><span class="sxs-lookup"><span data-stu-id="349c6-113">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="349c6-114">说明如何实现自定义授权。</span><span class="sxs-lookup"><span data-stu-id="349c6-114">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="349c6-115">重写服务标识以便进行身份验证</span><span class="sxs-lookup"><span data-stu-id="349c6-115">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="349c6-116">介绍如何重写身份验证服务的标识。</span><span class="sxs-lookup"><span data-stu-id="349c6-116">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="349c6-117">如何：创建自定义客户端标识验证工具</span><span class="sxs-lookup"><span data-stu-id="349c6-117">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="349c6-118">演示如何验证自定义终结点标识。</span><span class="sxs-lookup"><span data-stu-id="349c6-118">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="349c6-119">如何：使用独立的 X.509 证书进行签名和加密</span><span class="sxs-lookup"><span data-stu-id="349c6-119">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="349c6-120">通常使用单个证书对消息进行签名和加密。</span><span class="sxs-lookup"><span data-stu-id="349c6-120">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="349c6-121">本主题说明如何按照要求使用两个证书。</span><span class="sxs-lookup"><span data-stu-id="349c6-121">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="349c6-122">如何：更改 X.509 证书私钥的加密提供程序</span><span class="sxs-lookup"><span data-stu-id="349c6-122">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="349c6-123">说明如何更改用于提供 X.509 证书的私钥的加密提供程序以及如何将该提供程序集成到 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 框架中。</span><span class="sxs-lookup"><span data-stu-id="349c6-123">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="349c6-124">参考</span><span class="sxs-lookup"><span data-stu-id="349c6-124">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="349c6-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="349c6-125">Related Sections</span></span>  
 [<span data-ttu-id="349c6-126">安全性</span><span class="sxs-lookup"><span data-stu-id="349c6-126">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="349c6-127">基本 WCF 编程</span><span class="sxs-lookup"><span data-stu-id="349c6-127">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="349c6-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="349c6-128">See Also</span></span>  
 [<span data-ttu-id="349c6-129">安全性概述</span><span class="sxs-lookup"><span data-stu-id="349c6-129">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
