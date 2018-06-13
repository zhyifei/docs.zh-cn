---
title: 如何：使用协定接口创建服务
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
ms.openlocfilehash: 796870b80ed72db2353e79db3e4e3fc164c22875
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489789"
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a><span data-ttu-id="ecaf5-102">如何：使用协定接口创建服务</span><span class="sxs-lookup"><span data-stu-id="ecaf5-102">How to: Create a Service with a Contract Interface</span></span>
<span data-ttu-id="ecaf5-103">创建 Windows Communication Foundation (WCF) 协定的首选的方法是使用接口。</span><span class="sxs-lookup"><span data-stu-id="ecaf5-103">The preferred way to create a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="ecaf5-104">此协定指定访问服务提供的操作所必需的消息的集合和结构。</span><span class="sxs-lookup"><span data-stu-id="ecaf5-104">This contract specifies the collection and structure of messages required to access the operations the service offers.</span></span> <span data-ttu-id="ecaf5-105">此接口通过将 <xref:System.ServiceModel.ServiceContractAttribute> 类应用到该接口并将 <xref:System.ServiceModel.OperationContractAttribute> 类应用到要公开的方法来定义输入和输出类型。</span><span class="sxs-lookup"><span data-stu-id="ecaf5-105">This interface defines the input and output types by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface and the <xref:System.ServiceModel.OperationContractAttribute> class to the methods that you want to expose.</span></span>  
  
 <span data-ttu-id="ecaf5-106">有关服务协定的详细信息，请参阅[设计服务协定](../../../../docs/framework/wcf/designing-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="ecaf5-106">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a><span data-ttu-id="ecaf5-107">使用接口创建 WCF 协定</span><span class="sxs-lookup"><span data-stu-id="ecaf5-107">Creating a WCF contract with an interface</span></span>  
  
1.  <span data-ttu-id="ecaf5-108">创建一个新的接口，使用 Visual Basic、 C# 中，或任何将其他公共语言运行时语言。</span><span class="sxs-lookup"><span data-stu-id="ecaf5-108">Create a new interface using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="ecaf5-109">将 <xref:System.ServiceModel.ServiceContractAttribute> 类应用到该接口。</span><span class="sxs-lookup"><span data-stu-id="ecaf5-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
3.  <span data-ttu-id="ecaf5-110">定义该接口中的方法。</span><span class="sxs-lookup"><span data-stu-id="ecaf5-110">Define the methods in the interface.</span></span>  
  
4.  <span data-ttu-id="ecaf5-111">应用<xref:System.ServiceModel.OperationContractAttribute>到每个方法都必须作为公共 WCF 协定的一部分进行公开的类。</span><span class="sxs-lookup"><span data-stu-id="ecaf5-111">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecaf5-112">示例</span><span class="sxs-lookup"><span data-stu-id="ecaf5-112">Example</span></span>  
 <span data-ttu-id="ecaf5-113">下面的代码示例演示一个定义服务协定的接口。</span><span class="sxs-lookup"><span data-stu-id="ecaf5-113">The following code example shows an interface that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 <span data-ttu-id="ecaf5-114">默认情况下，应用了 <xref:System.ServiceModel.OperationContractAttribute> 类的方法使用请求-答复消息模式。</span><span class="sxs-lookup"><span data-stu-id="ecaf5-114">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="ecaf5-115">有关此消息模式的详细信息，请参阅[如何： 创建请求-答复协定](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="ecaf5-115">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="ecaf5-116">您还可以通过设置属性 (Attribute) 的属性 (Property) 来创建和使用其他消息模式。</span><span class="sxs-lookup"><span data-stu-id="ecaf5-116">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="ecaf5-117">有关更多示例，请参阅[如何： 创建单向协定](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md)和[如何： 创建双工协定](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="ecaf5-117">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecaf5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecaf5-118">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
