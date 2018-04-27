---
title: 如何：使用协定接口创建服务
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c31f149a28d6b2b323881439fc89aa60cf6fbf17
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a><span data-ttu-id="6cdd9-102">如何：使用协定接口创建服务</span><span class="sxs-lookup"><span data-stu-id="6cdd9-102">How to: Create a Service with a Contract Interface</span></span>
<span data-ttu-id="6cdd9-103">创建 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 协定的首选方式是使用接口。</span><span class="sxs-lookup"><span data-stu-id="6cdd9-103">The preferred way to create a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] contract is by using an interface.</span></span> <span data-ttu-id="6cdd9-104">此协定指定访问服务提供的操作所必需的消息的集合和结构。</span><span class="sxs-lookup"><span data-stu-id="6cdd9-104">This contract specifies the collection and structure of messages required to access the operations the service offers.</span></span> <span data-ttu-id="6cdd9-105">此接口通过将 <xref:System.ServiceModel.ServiceContractAttribute> 类应用到该接口并将 <xref:System.ServiceModel.OperationContractAttribute> 类应用到要公开的方法来定义输入和输出类型。</span><span class="sxs-lookup"><span data-stu-id="6cdd9-105">This interface defines the input and output types by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface and the <xref:System.ServiceModel.OperationContractAttribute> class to the methods that you want to expose.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="6cdd9-106"> 服务协定，请参阅[设计服务协定](../../../../docs/framework/wcf/designing-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="6cdd9-106"> service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a><span data-ttu-id="6cdd9-107">使用接口创建 WCF 协定</span><span class="sxs-lookup"><span data-stu-id="6cdd9-107">Creating a WCF contract with an interface</span></span>  
  
1.  <span data-ttu-id="6cdd9-108">创建一个新的接口，使用 Visual Basic、 C# 中，或任何将其他公共语言运行时语言。</span><span class="sxs-lookup"><span data-stu-id="6cdd9-108">Create a new interface using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="6cdd9-109">将 <xref:System.ServiceModel.ServiceContractAttribute> 类应用到该接口。</span><span class="sxs-lookup"><span data-stu-id="6cdd9-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
3.  <span data-ttu-id="6cdd9-110">定义该接口中的方法。</span><span class="sxs-lookup"><span data-stu-id="6cdd9-110">Define the methods in the interface.</span></span>  
  
4.  <span data-ttu-id="6cdd9-111">对必须作为公共 <xref:System.ServiceModel.OperationContractAttribute> 协定的一部分公开的每个方法应用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 类。</span><span class="sxs-lookup"><span data-stu-id="6cdd9-111">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cdd9-112">示例</span><span class="sxs-lookup"><span data-stu-id="6cdd9-112">Example</span></span>  
 <span data-ttu-id="6cdd9-113">下面的代码示例演示一个定义服务协定的接口。</span><span class="sxs-lookup"><span data-stu-id="6cdd9-113">The following code example shows an interface that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 <span data-ttu-id="6cdd9-114">默认情况下，应用了 <xref:System.ServiceModel.OperationContractAttribute> 类的方法使用请求-答复消息模式。</span><span class="sxs-lookup"><span data-stu-id="6cdd9-114">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="6cdd9-115"> 此消息模式，请参阅[如何： 创建请求-答复协定](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="6cdd9-115"> this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="6cdd9-116">您还可以通过设置属性 (Attribute) 的属性 (Property) 来创建和使用其他消息模式。</span><span class="sxs-lookup"><span data-stu-id="6cdd9-116">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="6cdd9-117">有关更多示例，请参阅[如何： 创建单向协定](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md)和[如何： 创建双工协定](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="6cdd9-117">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cdd9-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6cdd9-118">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
