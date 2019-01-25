---
title: 如何：为指定的身份验证模式创建 SecurityBindingElement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
ms.openlocfilehash: 62006397db3155d26a2c7bd327251b870a3b8460
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619923"
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a><span data-ttu-id="b7f9b-102">如何：为指定的身份验证模式创建 SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="b7f9b-102">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>
<span data-ttu-id="b7f9b-103">Windows Communication Foundation (WCF) 提供了多个模式的客户端和服务互相进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b7f9b-103">Windows Communication Foundation (WCF) provides several modes by which clients and services authenticate to one another.</span></span> <span data-ttu-id="b7f9b-104">你可以通过在 <xref:System.ServiceModel.Channels.SecurityBindingElement> 类上使用静态方法或通过配置来为这些身份验证模式创建安全绑定元素，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="b7f9b-104">You can create security binding elements for these authentication modes by using static methods on the <xref:System.ServiceModel.Channels.SecurityBindingElement> class or through configuration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="b7f9b-105">18 种身份验证模式的详细信息，请参阅[SecurityBindingElement 身份验证模式](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)。</span><span class="sxs-lookup"><span data-stu-id="b7f9b-105">For more information about the 18 authentication modes, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7f9b-106">示例</span><span class="sxs-lookup"><span data-stu-id="b7f9b-106">Example</span></span>  
 <span data-ttu-id="b7f9b-107">下面的代码示例演示用于为各种身份验证模式创建绑定的方法。</span><span class="sxs-lookup"><span data-stu-id="b7f9b-107">The following code example shows methods for creating bindings for the various authentication modes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7f9b-108">一旦创建了 <xref:System.ServiceModel.Channels.SecurityBindingElement> 对象的实例，大量属性（例如 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> 和 <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>）就是不可变的。</span><span class="sxs-lookup"><span data-stu-id="b7f9b-108">Once an instance of the <xref:System.ServiceModel.Channels.SecurityBindingElement> object is created, a number of properties are immutable, such as <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> and <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span></span> <span data-ttu-id="b7f9b-109">对此类属性调用 `set` 后，它们不会发生更改。</span><span class="sxs-lookup"><span data-stu-id="b7f9b-109">Calling `set` on such properties does not change them.</span></span>  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b7f9b-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7f9b-110">See also</span></span>
- [<span data-ttu-id="b7f9b-111">SecurityBindingElement 身份验证模式</span><span class="sxs-lookup"><span data-stu-id="b7f9b-111">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)
- [<span data-ttu-id="b7f9b-112">如何：创建自定义绑定使用 SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="b7f9b-112">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
