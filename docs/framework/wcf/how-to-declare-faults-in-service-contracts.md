---
title: 如何：在服务协定中声明错误
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
ms.openlocfilehash: 2de14a76fd2ce8ad656c2b64f5f9e5b17d81eebc
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216861"
---
# <a name="how-to-declare-faults-in-service-contracts"></a><span data-ttu-id="ffdc4-102">如何：在服务协定中声明错误</span><span class="sxs-lookup"><span data-stu-id="ffdc4-102">How to: Declare Faults in Service Contracts</span></span>

<span data-ttu-id="ffdc4-103">在托管代码中，出现错误条件时引发异常。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-103">In managed code, exceptions are thrown when error conditions occur.</span></span> <span data-ttu-id="ffdc4-104">但在 Windows Communication Foundation （WCF）应用程序中，服务协定通过在服务协定中声明 SOAP 错误来指定向客户端返回的错误信息。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-104">In Windows Communication Foundation (WCF) applications, however, service contracts specify what error information is returned to clients by declaring SOAP faults in the service contract.</span></span> <span data-ttu-id="ffdc4-105">有关异常和错误间关系的概述，请参阅[在协定和服务中指定和处理错误](specifying-and-handling-faults-in-contracts-and-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-105">For an overview of the relationship between exceptions and faults, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md).</span></span>

## <a name="create-a-service-contract-that-specifies-a-soap-fault"></a><span data-ttu-id="ffdc4-106">创建指定 SOAP 错误的服务协定</span><span class="sxs-lookup"><span data-stu-id="ffdc4-106">Create a service contract that specifies a SOAP fault</span></span>

1. <span data-ttu-id="ffdc4-107">创建至少包含一个操作的服务协定。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-107">Create a service contract that contains at least one operation.</span></span> <span data-ttu-id="ffdc4-108">有关示例，请参见 [如何：定义服务协定](how-to-define-a-wcf-service-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-108">For an example, see [How to: Define a Service Contract](how-to-define-a-wcf-service-contract.md).</span></span>

2. <span data-ttu-id="ffdc4-109">选择可以指定希望向客户端通知的错误条件的操作。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-109">Select an operation that can specify an error condition about which clients can expect to be notified.</span></span> <span data-ttu-id="ffdc4-110">若要确定哪些错误条件将 SOAP 错误返回给客户端，请参阅[在协定和服务中指定和处理错误](specifying-and-handling-faults-in-contracts-and-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-110">To decide which error conditions justify returning SOAP faults to clients, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md).</span></span>

3. <span data-ttu-id="ffdc4-111">为所选操作应用 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> 并向构造函数传递可序列化错误类型。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-111">Apply a <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> to the selected operation and pass a serializable fault type to the constructor.</span></span> <span data-ttu-id="ffdc4-112">有关创建和使用可序列化类型的详细信息，请参阅[在服务协定中指定数据传输](./feature-details/specifying-data-transfer-in-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-112">For details about creating and using serializable types, see [Specifying Data Transfer in Service Contracts](./feature-details/specifying-data-transfer-in-service-contracts.md).</span></span> <span data-ttu-id="ffdc4-113">下面的示例演示如何指定 `SampleMethod` 操作可以产生 `GreetingFault`。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-113">The following example shows how to specify that the `SampleMethod` operation can result in a `GreetingFault`.</span></span>

     [!code-csharp[FaultContractAttribute#4](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]

4. <span data-ttu-id="ffdc4-114">为向客户端传达错误条件的协定中的所有操作重复步骤 2 和步骤 3。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-114">Repeat steps 2 and 3 for all operations in the contract that communicate error conditions to clients.</span></span>

## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a><span data-ttu-id="ffdc4-115">实现返回指定 SOAP 错误的操作</span><span class="sxs-lookup"><span data-stu-id="ffdc4-115">Implementing an Operation to Return a Specified SOAP Fault</span></span>
 <span data-ttu-id="ffdc4-116">操作指定可以返回特定 SOAP 错误（例如在前面的过程中）来向调用应用程序传达错误条件后，下一步就是实现该指定。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-116">Once an operation has specified that a specific SOAP fault can be returned (such as in the preceding procedure) to communicate an error condition to a calling application, the next step is to implement that specification.</span></span>

### <a name="throw-the-specified-soap-fault-in-the-operation"></a><span data-ttu-id="ffdc4-117">在操作中引发指定的 SOAP 错误</span><span class="sxs-lookup"><span data-stu-id="ffdc4-117">Throw the specified SOAP fault in the operation</span></span>

1. <span data-ttu-id="ffdc4-118">当操作中出现 <xref:System.ServiceModel.FaultContractAttribute> 指定的错误条件时，将引发一个新的 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>，其中指定的 SOAP 错误是类型参数。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-118">When a <xref:System.ServiceModel.FaultContractAttribute>-specified error condition occurs in an operation, throw a new <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> where the specified SOAP fault is the type parameter.</span></span> <span data-ttu-id="ffdc4-119">下面的示例演示如何在前面的过程和以下代码部分中显示的 `GreetingFault` 中引发 `SampleMethod`。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-119">The following example shows how to throw the `GreetingFault` in the `SampleMethod` shown in the preceding procedure and in the following Code section.</span></span>

     [!code-csharp[FaultContractAttribute#5](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]

## <a name="example"></a><span data-ttu-id="ffdc4-120">示例</span><span class="sxs-lookup"><span data-stu-id="ffdc4-120">Example</span></span>

<span data-ttu-id="ffdc4-121">下面的代码示例演示为 `GreetingFault` 操作指定 `SampleMethod` 的单个操作的实现。</span><span class="sxs-lookup"><span data-stu-id="ffdc4-121">The following code example shows an implementation of a single operation that specifies a `GreetingFault` for the `SampleMethod` operation.</span></span>

[!code-csharp[FaultContractAttribute#1](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
[!code-vb[FaultContractAttribute#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]

## <a name="see-also"></a><span data-ttu-id="ffdc4-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffdc4-122">See also</span></span>

- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
