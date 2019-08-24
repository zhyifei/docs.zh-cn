---
title: 如何：使用类创建 Windows Communication Foundation 协定
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 2cd757107d9f62ce749d98db1d4968c02a09c5d2
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988751"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="93c33-102">如何：使用类创建 Windows Communication Foundation 协定</span><span class="sxs-lookup"><span data-stu-id="93c33-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="93c33-103">创建 Windows Communication Foundation (WCF) 协定的首选方式是使用接口。</span><span class="sxs-lookup"><span data-stu-id="93c33-103">The preferred way of creating a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="93c33-104">有关详细信息，请参阅[如何：定义服务协定](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="93c33-104">For more information, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="93c33-105">本文介绍另一种方式，即创建一个类，然后直接对该类应用 <xref:System.ServiceModel.ServiceContractAttribute> 特性，并对该类中作为协定一部分的每个方法应用 <xref:System.ServiceModel.OperationContractAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="93c33-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="93c33-106">`[ServiceContract]` 和 `[ServiceContractAttribute]` 的作用一样。</span><span class="sxs-lookup"><span data-stu-id="93c33-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="93c33-107">对于`[OperationContract]` 和`[OperationContractAttribute]`也是如此。</span><span class="sxs-lookup"><span data-stu-id="93c33-107">The same thing is true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="93c33-108">在每种情况下, 前者是后者的简写形式。</span><span class="sxs-lookup"><span data-stu-id="93c33-108">In each case, the former is shorthand for the latter.</span></span>  
  
 <span data-ttu-id="93c33-109">有关服务协定的详细信息, 请参阅[设计服务协定](../../../../docs/framework/wcf/designing-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="93c33-109">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="93c33-110">通过类创建 Windows Communication Foundation 协定</span><span class="sxs-lookup"><span data-stu-id="93c33-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1. <span data-ttu-id="93c33-111">使用 Visual Basic、 C#或任何其他公共语言运行时语言创建新类。</span><span class="sxs-lookup"><span data-stu-id="93c33-111">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2. <span data-ttu-id="93c33-112">对该类应用 <xref:System.ServiceModel.ServiceContractAttribute> 类。</span><span class="sxs-lookup"><span data-stu-id="93c33-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3. <span data-ttu-id="93c33-113">创建该类中的方法。</span><span class="sxs-lookup"><span data-stu-id="93c33-113">Create methods in the class.</span></span>  
  
4. <span data-ttu-id="93c33-114"><xref:System.ServiceModel.OperationContractAttribute>将类应用于必须作为公共 WCF 协定的一部分公开的每个方法。</span><span class="sxs-lookup"><span data-stu-id="93c33-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93c33-115">示例</span><span class="sxs-lookup"><span data-stu-id="93c33-115">Example</span></span>  
 <span data-ttu-id="93c33-116">下面的代码示例演示定义服务协定的类。</span><span class="sxs-lookup"><span data-stu-id="93c33-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="93c33-117">默认情况下，应用了 <xref:System.ServiceModel.OperationContractAttribute> 类的方法使用请求-答复消息模式。</span><span class="sxs-lookup"><span data-stu-id="93c33-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="93c33-118">有关此消息模式的详细信息, 请[参阅如何:创建请求-答复协定](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="93c33-118">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="93c33-119">您还可以通过设置属性 (Attribute) 的属性 (Property) 来创建和使用其他消息模式。</span><span class="sxs-lookup"><span data-stu-id="93c33-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="93c33-120">有关更多示例，请参见[如何：创建单向协定](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) , 以及[如何:创建双工协定](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="93c33-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93c33-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="93c33-121">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
