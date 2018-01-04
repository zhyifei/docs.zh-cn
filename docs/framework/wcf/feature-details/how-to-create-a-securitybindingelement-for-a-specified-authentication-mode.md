---
title: "如何：为指定的身份验证模式创建 SecurityBindingElement"
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
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 29cbe3c10ac68d508dc22781e46a6041f2d7eab7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a><span data-ttu-id="ba85b-102">如何：为指定的身份验证模式创建 SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ba85b-102">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="ba85b-103"> 提供了几种供客户端和服务互相进行身份验证的模式。</span><span class="sxs-lookup"><span data-stu-id="ba85b-103"> provides several modes by which clients and services authenticate to one another.</span></span> <span data-ttu-id="ba85b-104">您可以通过在 <xref:System.ServiceModel.Channels.SecurityBindingElement> 类上使用静态方法或通过配置来为这些身份验证模式创建安全绑定元素，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="ba85b-104">You can create security binding elements for these authentication modes by using static methods on the <xref:System.ServiceModel.Channels.SecurityBindingElement> class or through configuration, as shown in the following example.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ba85b-105">18 种身份验证模式，请参阅[SecurityBindingElement 身份验证模式](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)。</span><span class="sxs-lookup"><span data-stu-id="ba85b-105"> the 18 authentication modes, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba85b-106">示例</span><span class="sxs-lookup"><span data-stu-id="ba85b-106">Example</span></span>  
 <span data-ttu-id="ba85b-107">下面的代码示例演示用于为各种身份验证模式创建绑定的方法。</span><span class="sxs-lookup"><span data-stu-id="ba85b-107">The following code example shows methods for creating bindings for the various authentication modes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba85b-108">一旦创建了 <xref:System.ServiceModel.Channels.SecurityBindingElement> 对象的实例，大量属性（例如 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> 和 <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>）就是不可变的。</span><span class="sxs-lookup"><span data-stu-id="ba85b-108">Once an instance of the <xref:System.ServiceModel.Channels.SecurityBindingElement> object is created, a number of properties are immutable, such as <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> and <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span></span> <span data-ttu-id="ba85b-109">对此类属性调用 `set` 后，它们不会发生更改。</span><span class="sxs-lookup"><span data-stu-id="ba85b-109">Calling `set` on such properties does not change them.</span></span>  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ba85b-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba85b-110">See Also</span></span>  
 [<span data-ttu-id="ba85b-111">SecurityBindingElement 身份验证模式</span><span class="sxs-lookup"><span data-stu-id="ba85b-111">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 [<span data-ttu-id="ba85b-112">如何：使用 SecurityBindingElement 创建自定义绑定</span><span class="sxs-lookup"><span data-stu-id="ba85b-112">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
