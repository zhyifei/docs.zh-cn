---
title: "如何：使用类创建 Windows Communication Foundation 约定"
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
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44418d9d7ec88ea5cd340312fd1ebe42ef8d20a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="5d436-102">如何：使用类创建 Windows Communication Foundation 约定</span><span class="sxs-lookup"><span data-stu-id="5d436-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="5d436-103">创建 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 协定的首选方式是使用接口。</span><span class="sxs-lookup"><span data-stu-id="5d436-103">The preferred way of creating a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] contract is by using an interface.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="5d436-104">[如何： 定义服务协定](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="5d436-104"> [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="5d436-105">本文介绍另一种方式，即创建一个类，然后直接对该类应用 <xref:System.ServiceModel.ServiceContractAttribute> 特性，并对该类中作为协定一部分的每个方法应用 <xref:System.ServiceModel.OperationContractAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="5d436-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5d436-106">`[ServiceContract]` 和 `[ServiceContractAttribute]` 的作用一样。</span><span class="sxs-lookup"><span data-stu-id="5d436-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="5d436-107">`[OperationContract]` 和 `[OperationContractAttribute]` 的作用一样。</span><span class="sxs-lookup"><span data-stu-id="5d436-107">The same thing it true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="5d436-108">在每种情况下，前者都是后者的简写。</span><span class="sxs-lookup"><span data-stu-id="5d436-108">In each case the former is shorthand for the latter.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5d436-109">服务协定，请参阅[设计服务协定](../../../../docs/framework/wcf/designing-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="5d436-109"> service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="5d436-110">通过类创建 Windows Communication Foundation 协定</span><span class="sxs-lookup"><span data-stu-id="5d436-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1.  <span data-ttu-id="5d436-111">使用 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]、C# 或任何其他公共语言运行时语言创建一个新类。</span><span class="sxs-lookup"><span data-stu-id="5d436-111">Create a new class using [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="5d436-112">对该类应用 <xref:System.ServiceModel.ServiceContractAttribute> 类。</span><span class="sxs-lookup"><span data-stu-id="5d436-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3.  <span data-ttu-id="5d436-113">创建该类中的方法。</span><span class="sxs-lookup"><span data-stu-id="5d436-113">Create methods in the class.</span></span>  
  
4.  <span data-ttu-id="5d436-114">对必须作为公共 <xref:System.ServiceModel.OperationContractAttribute> 协定的一部分公开的每个方法应用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 类。</span><span class="sxs-lookup"><span data-stu-id="5d436-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d436-115">示例</span><span class="sxs-lookup"><span data-stu-id="5d436-115">Example</span></span>  
 <span data-ttu-id="5d436-116">下面的代码示例演示定义服务协定的类。</span><span class="sxs-lookup"><span data-stu-id="5d436-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="5d436-117">默认情况下，应用了 <xref:System.ServiceModel.OperationContractAttribute> 类的方法使用请求-答复消息模式。</span><span class="sxs-lookup"><span data-stu-id="5d436-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5d436-118">此消息模式，请参阅[如何： 创建请求-答复协定](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="5d436-118"> this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="5d436-119">您还可以通过设置属性 (Attribute) 的属性 (Property) 来创建和使用其他消息模式。</span><span class="sxs-lookup"><span data-stu-id="5d436-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="5d436-120">有关更多示例，请参阅[如何： 创建单向协定](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md)和[如何： 创建双工协定](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="5d436-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d436-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d436-121">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
