---
title: 数字签名的加密
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- encryption of digital signatures [WCF]
- digital signatures [WCF], encryption
- digital signatures [WCF]
ms.assetid: 0868866d-40b4-4341-8e42-eee3b7f15b69
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 630465367eb4cee164a222bb5449070ac0726d5e
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="encryption-of-digital-signatures"></a><span data-ttu-id="5222e-102">数字签名的加密</span><span class="sxs-lookup"><span data-stu-id="5222e-102">Encryption of Digital Signatures</span></span>
<span data-ttu-id="5222e-103">默认情况下，会对消息进行签名和加密，并对签名进行数字加密。</span><span class="sxs-lookup"><span data-stu-id="5222e-103">By default, a message is signed and encrypted, and the signature is digitally encrypted.</span></span> <span data-ttu-id="5222e-104">您可以对此进行控制，方法是用 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> 或 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 的实例创建一个自定义绑定，然后将其中一个类的 `MessageProtectionOrder` 属性设置为一个 <xref:System.ServiceModel.Security.MessageProtectionOrder> 枚举值。</span><span class="sxs-lookup"><span data-stu-id="5222e-104">You can control this by creating a custom binding with an instance of the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> or the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and then setting the `MessageProtectionOrder` property of either class to a <xref:System.ServiceModel.Security.MessageProtectionOrder> enumeration value.</span></span> <span data-ttu-id="5222e-105">默认值为 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>。</span><span class="sxs-lookup"><span data-stu-id="5222e-105">The default is <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>.</span></span> <span data-ttu-id="5222e-106">此过程要比仅仅签名和加密多花 10% 到 40% 的时间。</span><span class="sxs-lookup"><span data-stu-id="5222e-106">This process takes 10 to 40 percent longer than simply signing and encrypting.</span></span> <span data-ttu-id="5222e-107">但是，禁用签名的加密可能会使攻击者猜出消息的内容。</span><span class="sxs-lookup"><span data-stu-id="5222e-107">Disabling encryption of the signature, however, might allow an attacker to guess the contents of the message.</span></span> <span data-ttu-id="5222e-108">这种情况是可能的，原因是签名元素包含消息中每个签名部分的纯文本的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="5222e-108">This is possible because the signature element contains the hash code of the plain text of every signed part in the message.</span></span> <span data-ttu-id="5222e-109">例如，尽管默认情况下加密了消息正文，可是未加密的签名包含消息正文的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="5222e-109">For example, although the message body is encrypted by default, the unencrypted signature contains the hash code of the message body.</span></span> <span data-ttu-id="5222e-110">如果消息简短，攻击者有可能推测出内容。</span><span class="sxs-lookup"><span data-stu-id="5222e-110">If the message is small, an attacker might be able to deduce the contents.</span></span> <span data-ttu-id="5222e-111">对签名进行加密可减小或消除这种可能性。</span><span class="sxs-lookup"><span data-stu-id="5222e-111">Encrypting the signature reduces or eliminates this possibility.</span></span>  
  
 <span data-ttu-id="5222e-112">因此，应仅在内容价值较低时才禁用签名的加密，比如在发送无安全问题的大型二进制文件时，而禁用可以显著提高性能。</span><span class="sxs-lookup"><span data-stu-id="5222e-112">Therefore, disable encryption of the signature only when the value of the content is low, and the performance gain will be significant, for example, when sending large binary files that have no security implications.</span></span>  
  
### <a name="to-disable-digital-signing"></a><span data-ttu-id="5222e-113">禁用数字签名</span><span class="sxs-lookup"><span data-stu-id="5222e-113">To disable digital signing</span></span>  
  
1.  <span data-ttu-id="5222e-114">创建 <xref:System.ServiceModel.Channels.CustomBinding>。</span><span class="sxs-lookup"><span data-stu-id="5222e-114">Create a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span> <span data-ttu-id="5222e-115">有关详细信息，请参阅[如何： 自定义绑定使用 SecurityBindingElement 创建](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)。</span><span class="sxs-lookup"><span data-stu-id="5222e-115">For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
2.  <span data-ttu-id="5222e-116">将 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> 或 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 添加到绑定集合。</span><span class="sxs-lookup"><span data-stu-id="5222e-116">Add either an <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> or a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> to the binding collection.</span></span>  
  
3.  <span data-ttu-id="5222e-117">将 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> 属性设置为 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>，或将 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> 属性设置为 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>。</span><span class="sxs-lookup"><span data-stu-id="5222e-117">Set the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> property to <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>, or set the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> property to <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.</span></span>  
  
 <span data-ttu-id="5222e-118">有关创建自定义绑定的详细信息，请参阅[创建用户定义绑定](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="5222e-118">For more information about creating custom bindings, see [Creating User-Defined Bindings](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).</span></span> <span data-ttu-id="5222e-119">有关创建自定义绑定的特定身份验证模式的详细信息，请参阅[如何： 为指定的身份验证模式创建 SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="5222e-119">For more information about creating a custom binding for a specific authentication mode, see [How to: Create a SecurityBindingElement for a Specified Authentication Mode](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5222e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="5222e-120">See Also</span></span>  
 <xref:System.ServiceModel.Security.MessageProtectionOrder>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
 [<span data-ttu-id="5222e-121">如何：使用 SecurityBindingElement 创建自定义绑定</span><span class="sxs-lookup"><span data-stu-id="5222e-121">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="5222e-122">创建用户定义的绑定</span><span class="sxs-lookup"><span data-stu-id="5222e-122">Creating User-Defined Bindings</span></span>](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)  
 [<span data-ttu-id="5222e-123">如何：为指定的身份验证模式创建 SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5222e-123">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
