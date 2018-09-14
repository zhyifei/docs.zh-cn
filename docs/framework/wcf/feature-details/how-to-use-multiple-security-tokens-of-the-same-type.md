---
title: 如何：使用相同类型的多个安全令牌
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 25afbb268a0ef7772585a0f3829b56f135758b61
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45507412"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="8a56e-102">如何：使用相同类型的多个安全令牌</span><span class="sxs-lookup"><span data-stu-id="8a56e-102">How to: Use Multiple Security Tokens of the Same Type</span></span>
-   <span data-ttu-id="8a56e-103">在 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0 中，客户端消息只包含一个任意给定类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="8a56e-103">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, a client message only contained one token of any given type.</span></span> <span data-ttu-id="8a56e-104">现在，客户端消息可以包含某种类型的多个令牌。</span><span class="sxs-lookup"><span data-stu-id="8a56e-104">Now client messages can contain multiple tokens of a type.</span></span> <span data-ttu-id="8a56e-105">本主题演示如何将同一类型的多个令牌包含在客户端消息中。</span><span class="sxs-lookup"><span data-stu-id="8a56e-105">This topic shows how to include multiple tokens of the same type in a client message.</span></span>  
  
-   <span data-ttu-id="8a56e-106">请注意，不能以这种方式配置服务：一个服务只能包含一个支持令牌。</span><span class="sxs-lookup"><span data-stu-id="8a56e-106">Note that you cannot configure a service in this way: a service can contain only one supporting token.</span></span>  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="8a56e-107">使用相同类型的多个安全令牌</span><span class="sxs-lookup"><span data-stu-id="8a56e-107">To use multiple security tokens of the same type</span></span>  
  
1.  <span data-ttu-id="8a56e-108">创建要填充的空绑定元素集合。</span><span class="sxs-lookup"><span data-stu-id="8a56e-108">Create an empty binding element collection to be populated.</span></span>  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  <span data-ttu-id="8a56e-109">通过调用 <xref:System.ServiceModel.Channels.SecurityBindingElement> 创建 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>。</span><span class="sxs-lookup"><span data-stu-id="8a56e-109">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span></span>  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  <span data-ttu-id="8a56e-110">创建一个 <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> 集合。</span><span class="sxs-lookup"><span data-stu-id="8a56e-110">Create a <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  <span data-ttu-id="8a56e-111">将 SAML 令牌添加到集合中。</span><span class="sxs-lookup"><span data-stu-id="8a56e-111">Add SAML tokens to the collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  <span data-ttu-id="8a56e-112">将集合添加到 <xref:System.ServiceModel.Channels.SecurityBindingElement> 中。</span><span class="sxs-lookup"><span data-stu-id="8a56e-112">Add the collection to the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  <span data-ttu-id="8a56e-113">将绑定元素添加到绑定元素集合中。</span><span class="sxs-lookup"><span data-stu-id="8a56e-113">Add binding elements to the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  <span data-ttu-id="8a56e-114">返回从绑定元素集合创建的新自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="8a56e-114">Return a new custom binding created from the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a><span data-ttu-id="8a56e-115">示例</span><span class="sxs-lookup"><span data-stu-id="8a56e-115">Example</span></span>  
 <span data-ttu-id="8a56e-116">下面是前面的过程所描述的整个方法。</span><span class="sxs-lookup"><span data-stu-id="8a56e-116">The following is the entire method described by the preceding procedure.</span></span>  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="8a56e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a56e-117">See Also</span></span>  
 [<span data-ttu-id="8a56e-118">安全体系结构</span><span class="sxs-lookup"><span data-stu-id="8a56e-118">Security Architecture</span></span>](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
