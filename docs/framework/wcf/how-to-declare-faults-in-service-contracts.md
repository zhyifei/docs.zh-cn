---
title: 如何：在服务协定中声明错误
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
ms.openlocfilehash: 142ad26702f0732bc5103e29d5a44bc57ab37625
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33500215"
---
# <a name="how-to-declare-faults-in-service-contracts"></a><span data-ttu-id="d60c0-102">如何：在服务协定中声明错误</span><span class="sxs-lookup"><span data-stu-id="d60c0-102">How to: Declare Faults in Service Contracts</span></span>
<span data-ttu-id="d60c0-103">在托管代码中，出现错误条件时引发异常。</span><span class="sxs-lookup"><span data-stu-id="d60c0-103">In managed code, exceptions are thrown when error conditions occur.</span></span> <span data-ttu-id="d60c0-104">在 Windows Communication Foundation (WCF) 应用程序，但是，服务协定指定哪些错误信息返回到客户端上，通过声明服务协定中的 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="d60c0-104">In Windows Communication Foundation (WCF) applications, however, service contracts specify what error information is returned to clients by declaring SOAP faults in the service contract.</span></span> <span data-ttu-id="d60c0-105">异常和错误之间的关系的概述，请参阅[指定和处理在协定和服务中的错误](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)。</span><span class="sxs-lookup"><span data-stu-id="d60c0-105">For an overview of the relationship between exceptions and faults, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
### <a name="create-a-service-contract-that-specifies-a-soap-fault"></a><span data-ttu-id="d60c0-106">创建指定 SOAP 错误的服务协定</span><span class="sxs-lookup"><span data-stu-id="d60c0-106">Create a service contract that specifies a SOAP fault</span></span>  
  
1.  <span data-ttu-id="d60c0-107">创建至少包含一个操作的服务协定。</span><span class="sxs-lookup"><span data-stu-id="d60c0-107">Create a service contract that contains at least one operation.</span></span> <span data-ttu-id="d60c0-108">有关示例，请参阅[如何： 定义服务协定](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="d60c0-108">For an example, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2.  <span data-ttu-id="d60c0-109">选择可以指定希望向客户端通知的错误条件的操作。</span><span class="sxs-lookup"><span data-stu-id="d60c0-109">Select an operation that can specify an error condition about which clients can expect to be notified.</span></span> <span data-ttu-id="d60c0-110">若要决定哪些错误条件调整将 SOAP 错误返回到客户端，请参阅[指定和处理在协定和服务中的错误](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)。</span><span class="sxs-lookup"><span data-stu-id="d60c0-110">To decide which error conditions justify returning SOAP faults to clients, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
3.  <span data-ttu-id="d60c0-111">为所选操作应用 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> 并向构造函数传递可序列化错误类型。</span><span class="sxs-lookup"><span data-stu-id="d60c0-111">Apply a <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> to the selected operation and pass a serializable fault type to the constructor.</span></span> <span data-ttu-id="d60c0-112">有关创建和使用可序列化类型的详细信息，请参阅[指定服务协定中的数据传输](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="d60c0-112">For details about creating and using serializable types, see [Specifying Data Transfer in Service Contracts](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).</span></span> <span data-ttu-id="d60c0-113">下面的示例演示如何指定 `SampleMethod` 操作可以产生 `GreetingFault`。</span><span class="sxs-lookup"><span data-stu-id="d60c0-113">The following example shows how to specify that the `SampleMethod` operation can result in a `GreetingFault`.</span></span>  
  
     [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
4.  <span data-ttu-id="d60c0-114">为向客户端传达错误条件的协定中的所有操作重复步骤 2 和步骤 3。</span><span class="sxs-lookup"><span data-stu-id="d60c0-114">Repeat steps 2 and 3 for all operations in the contract that communicate error conditions to clients.</span></span>  
  
## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a><span data-ttu-id="d60c0-115">实现返回指定 SOAP 错误的操作</span><span class="sxs-lookup"><span data-stu-id="d60c0-115">Implementing an Operation to Return a Specified SOAP Fault</span></span>  
 <span data-ttu-id="d60c0-116">操作指定可以返回特定 SOAP 错误（例如在前面的过程中）来向调用应用程序传达错误条件后，下一步就是实现该指定。</span><span class="sxs-lookup"><span data-stu-id="d60c0-116">Once an operation has specified that a specific SOAP fault can be returned (such as in the preceding procedure) to communicate an error condition to a calling application, the next step is to implement that specification.</span></span>  
  
#### <a name="throw-the-specified-soap-fault-in-the-operation"></a><span data-ttu-id="d60c0-117">在操作中引发指定的 SOAP 错误</span><span class="sxs-lookup"><span data-stu-id="d60c0-117">Throw the specified SOAP fault in the operation</span></span>  
  
1.  <span data-ttu-id="d60c0-118">当操作中出现 <xref:System.ServiceModel.FaultContractAttribute> 指定的错误条件时，将引发一个新的 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>，其中指定的 SOAP 错误是类型参数。</span><span class="sxs-lookup"><span data-stu-id="d60c0-118">When a <xref:System.ServiceModel.FaultContractAttribute>-specified error condition occurs in an operation, throw a new <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> where the specified SOAP fault is the type parameter.</span></span> <span data-ttu-id="d60c0-119">下面的示例演示如何在前面的过程和以下代码部分中显示的 `GreetingFault` 中引发 `SampleMethod`。</span><span class="sxs-lookup"><span data-stu-id="d60c0-119">The following example shows how to throw the `GreetingFault` in the `SampleMethod` shown in the preceding procedure and in the following Code section.</span></span>  
  
     [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="d60c0-120">示例</span><span class="sxs-lookup"><span data-stu-id="d60c0-120">Example</span></span>  
 <span data-ttu-id="d60c0-121">下面的代码示例演示为 `GreetingFault` 操作指定 `SampleMethod` 的单个操作的实现。</span><span class="sxs-lookup"><span data-stu-id="d60c0-121">The following code example shows an implementation of a single operation that specifies a `GreetingFault` for the `SampleMethod` operation.</span></span>  
  
 [!code-csharp[FaultContractAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
 [!code-vb[FaultContractAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d60c0-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="d60c0-122">See Also</span></span>  
 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>  
 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
