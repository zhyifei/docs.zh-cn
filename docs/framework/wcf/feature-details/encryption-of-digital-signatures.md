---
title: "数字签名的加密"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption of digital signatures [WCF]
- digital signatures [WCF], encryption
- digital signatures [WCF]
ms.assetid: 0868866d-40b4-4341-8e42-eee3b7f15b69
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 88ff9f3536d001054b2a95503b94cdda93f7fafc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="encryption-of-digital-signatures"></a>数字签名的加密
默认情况下，会对消息进行签名和加密，并对签名进行数字加密。 您可以对此进行控制，方法是用 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> 或 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 的实例创建一个自定义绑定，然后将其中一个类的 `MessageProtectionOrder` 属性设置为一个 <xref:System.ServiceModel.Security.MessageProtectionOrder> 枚举值。 默认值为 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>。 此过程要比仅仅签名和加密多花 10% 到 40% 的时间。 但是，禁用签名的加密可能会使攻击者猜出消息的内容。 这种情况是可能的，原因是签名元素包含消息中每个签名部分的纯文本的哈希代码。 例如，尽管默认情况下加密了消息正文，可是未加密的签名包含消息正文的哈希代码。 如果消息简短，攻击者有可能推测出内容。 对签名进行加密可减小或消除这种可能性。  
  
 因此，应仅在内容价值较低时才禁用签名的加密，比如在发送无安全问题的大型二进制文件时，而禁用可以显著提高性能。  
  
### <a name="to-disable-digital-signing"></a>禁用数字签名  
  
1.  创建 <xref:System.ServiceModel.Channels.CustomBinding>。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][如何： 创建自定义绑定使用 SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)。  
  
2.  将 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> 或 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 添加到绑定集合。  
  
3.  将 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> 属性设置为 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>，或将 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> 属性设置为 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>。  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]创建自定义绑定，请参阅[创建用户定义绑定](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]创建自定义绑定为特定身份验证的模式，请参阅[如何： 为指定的身份验证模式创建 SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Security.MessageProtectionOrder>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
 [如何： 创建自定义绑定使用 SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [创建用户定义的绑定](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)  
 [如何： 为指定的身份验证模式创建 SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
