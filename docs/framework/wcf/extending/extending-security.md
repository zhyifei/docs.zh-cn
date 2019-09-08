---
title: 扩展安全性
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 45216493a3afa23f24a085964a2c43e19b197d4b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797131"
---
# <a name="extending-security"></a>扩展安全性
为了容纳新的声明类型和自定义令牌，你可以扩展 Windows Communication Foundation （WCF）的安全基础结构。 本节中的主题将向您介绍如何完成此任务。  
  
## <a name="in-this-section"></a>本节内容  
  
 [自定义凭据和凭据验证](custom-credential-and-credential-validation.md)  
 说明在验证自定义凭据时如何使用标识模型。  
  
 [自定义令牌](custom-tokens.md)  
 安全令牌服务 (STS) 颁发的令牌通常为 SAML 令牌。 本主题说明如何创建自定义令牌类型。  
  
 [自定义授权](custom-authorization.md)  
 说明如何实现自定义授权。  
  
 [重写服务标识以便进行身份验证](overriding-the-identity-of-a-service-for-authentication.md)  
 介绍如何重写身份验证服务的标识。  
  
 [如何：创建自定义客户端标识验证程序](how-to-create-a-custom-client-identity-verifier.md)  
 演示如何验证自定义终结点标识。  
  
 [如何：使用单独的 x.509 证书进行签名和加密](how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 通常使用单个证书对消息进行签名和加密。 本主题说明如何按照要求使用两个证书。  
  
 [如何：更改 x.509 证书的私钥的加密提供程序](change-cryptographic-provider-x509-certificate-private-key.md)  
 说明如何更改用于提供 x.509 证书的私钥的加密提供程序，以及如何将该提供程序集成到 Windows Communication Foundation （WCF）框架中。  
  
## <a name="reference"></a>参考  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a>相关章节  
 [安全性](../feature-details/security.md)  
  
 [基本 WCF 编程](../basic-wcf-programming.md)  
  
## <a name="see-also"></a>请参阅

- [安全性概述](../feature-details/security-overview.md)
