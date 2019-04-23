---
title: 自定义凭据和凭据验证
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: 3b1ff700010f471a4d9be117f363083b6cbed493
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210628"
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="9aa5f-102">自定义凭据和凭据验证</span><span class="sxs-lookup"><span data-stu-id="9aa5f-102">Custom Credential and Credential Validation</span></span>
<span data-ttu-id="9aa5f-103">安全性在 Windows Communication Foundation (WCF) 基于服务和客户端之间的凭据交换。</span><span class="sxs-lookup"><span data-stu-id="9aa5f-103">Security in Windows Communication Foundation (WCF) is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="9aa5f-104">大多数安全方案均可使用常见的凭据类型来实现，如 Windows (Kerberos)、用户名和密码以及证书。</span><span class="sxs-lookup"><span data-stu-id="9aa5f-104">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="9aa5f-105">而本节中的主题针对需要使用新类型的凭据的情况说明如何处理和验证这些新类型。</span><span class="sxs-lookup"><span data-stu-id="9aa5f-105">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9aa5f-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="9aa5f-106">In This Section</span></span>  
 [<span data-ttu-id="9aa5f-107">如何：创建使用自定义证书验证程序的服务</span><span class="sxs-lookup"><span data-stu-id="9aa5f-107">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="9aa5f-108">说明如何通过继承自定义 WCF 验证<xref:System.IdentityModel.Selectors.X509CertificateValidator>类。</span><span class="sxs-lookup"><span data-stu-id="9aa5f-108">Explains how to customize WCF validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="9aa5f-109">演练：创建自定义客户端和服务凭据</span><span class="sxs-lookup"><span data-stu-id="9aa5f-109">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="9aa5f-110">演示如何扩展<xref:System.ServiceModel.Description.ClientCredentials>和<xref:System.ServiceModel.Description.ServiceCredentials>类以容纳新凭据类型。</span><span class="sxs-lookup"><span data-stu-id="9aa5f-110">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="9aa5f-111">这是介绍如何创建自定义凭据类型的系列主题中的第一个主题。</span><span class="sxs-lookup"><span data-stu-id="9aa5f-111">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="9aa5f-112">如何：创建自定义安全令牌提供程序</span><span class="sxs-lookup"><span data-stu-id="9aa5f-112">How to: Create a Custom Security Token Provider</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="9aa5f-113">说明如何创建安全令牌提供程序来处理新的凭据类型并返回凭据的新令牌。</span><span class="sxs-lookup"><span data-stu-id="9aa5f-113">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="9aa5f-114">这是该系列主题中的第二个主题。</span><span class="sxs-lookup"><span data-stu-id="9aa5f-114">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="9aa5f-115">如何：创建自定义安全令牌身份验证器</span><span class="sxs-lookup"><span data-stu-id="9aa5f-115">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="9aa5f-116">说明如何创建自定义身份验证器来验证新的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="9aa5f-116">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="9aa5f-117">这是该系列主题中的第三个主题。</span><span class="sxs-lookup"><span data-stu-id="9aa5f-117">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9aa5f-118">参考</span><span class="sxs-lookup"><span data-stu-id="9aa5f-118">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="9aa5f-119">相关章节</span><span class="sxs-lookup"><span data-stu-id="9aa5f-119">Related Sections</span></span>  
 [<span data-ttu-id="9aa5f-120">身份验证</span><span class="sxs-lookup"><span data-stu-id="9aa5f-120">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="9aa5f-121">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="9aa5f-121">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="9aa5f-122">授权</span><span class="sxs-lookup"><span data-stu-id="9aa5f-122">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="9aa5f-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="9aa5f-123">See also</span></span>

- [<span data-ttu-id="9aa5f-124">安全性</span><span class="sxs-lookup"><span data-stu-id="9aa5f-124">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
