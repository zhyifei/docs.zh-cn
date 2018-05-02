---
title: 如何：在数据流块收到数据时执行操作
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, receiving data
ms.assetid: fc2585dc-965e-4632-ace7-73dd02684ed3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 99f2f7184f869902f89eb0ac0fc8427533978cc3
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-perform-action-when-a-dataflow-block-receives-data"></a><span data-ttu-id="05ae9-102">如何：在数据流块收到数据时执行操作</span><span class="sxs-lookup"><span data-stu-id="05ae9-102">How to: Perform Action When a Dataflow Block Receives Data</span></span>
<span data-ttu-id="05ae9-103">在接收数据时，执行数据流块类型会调用用户提供的委托。</span><span class="sxs-lookup"><span data-stu-id="05ae9-103">*Execution dataflow block* types call a user-provided delegate when they receive data.</span></span> <span data-ttu-id="05ae9-104"><xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType>、<xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> 和 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType> 类是执行数据流块类型。</span><span class="sxs-lookup"><span data-stu-id="05ae9-104">The <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType> classes are execution dataflow block types.</span></span> <span data-ttu-id="05ae9-105">当为执行数据流块提供工作函数时，可以使用 `delegate` 关键字（Visual Basic 中为 `Sub`）、<xref:System.Action%601>、<xref:System.Func%602> 或 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="05ae9-105">You can use the `delegate` keyword (`Sub` in Visual Basic), <xref:System.Action%601>, <xref:System.Func%602>, or a lambda expression when you provide a work function to an execution dataflow block.</span></span> <span data-ttu-id="05ae9-106">本文档描述如何使用 <xref:System.Func%602> 和 lambda 表达式在执行块中执行操作。</span><span class="sxs-lookup"><span data-stu-id="05ae9-106">This document describes how to use <xref:System.Func%602> and lambda expressions to perform action in execution blocks.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a><span data-ttu-id="05ae9-107">示例</span><span class="sxs-lookup"><span data-stu-id="05ae9-107">Example</span></span>  
 <span data-ttu-id="05ae9-108">下面的示例使用数据流从磁盘读取一个文件并计算该文件中等于零的字节的数量。</span><span class="sxs-lookup"><span data-stu-id="05ae9-108">The following example uses dataflow to read a file from disk and computes the number of bytes in that file that are equal to zero.</span></span> <span data-ttu-id="05ae9-109">它使用 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 读取文件并计算零字节的数量，并使用 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 将零字节的数量输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="05ae9-109">It uses <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> to read the file and compute the number of zero bytes, and <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> to print the number of zero bytes to the console.</span></span> <span data-ttu-id="05ae9-110">当块收到数据时，<xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 对象会指定一个 <xref:System.Func%602> 对象来执行工作。</span><span class="sxs-lookup"><span data-stu-id="05ae9-110">The <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> object specifies a <xref:System.Func%602> object to perform work when the blocks receive data.</span></span> <span data-ttu-id="05ae9-111"><xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 对象使用 lambda 表达式将读取到的零字节的数量输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="05ae9-111">The <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object uses a lambda expression to print to the console the number of zero bytes that are read.</span></span>  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#1)]
 [!code-vb[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#1)]  
  
 <span data-ttu-id="05ae9-112">虽然可以为 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 对象提供 lambda 表达式，但是本示例使用 <xref:System.Func%602> 来允许其他代码使用 `CountBytes` 方法。</span><span class="sxs-lookup"><span data-stu-id="05ae9-112">Although you can provide a lambda expression to a <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> object, this example uses <xref:System.Func%602> to enable other code to use the `CountBytes` method.</span></span> <span data-ttu-id="05ae9-113">因为要执行的工作是此任务特有的，使用其他代码不可能有用，所以 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 对象使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="05ae9-113">The <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object uses a lambda expression because the work to be performed is specific to this task and is not likely to be useful from other code.</span></span> <span data-ttu-id="05ae9-114">有关 lambda 表达式如何在任务并行库中工作的详细信息，请参阅 [PLINQ 和 TPL 中的 Lambda 表达式](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)。</span><span class="sxs-lookup"><span data-stu-id="05ae9-114">For more information about how lambda expressions work in the Task Parallel Library, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
 <span data-ttu-id="05ae9-115">[Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) 文档中的“委托类型摘要”汇总了可以提供给 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>、<xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 和 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 对象的委托类型。</span><span class="sxs-lookup"><span data-stu-id="05ae9-115">The section Summary of Delegate Types in the [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) document summarizes the delegate types that you can provide to <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, and <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> objects.</span></span> <span data-ttu-id="05ae9-116">该表还指出委托类型是同步执行还是异步执行。</span><span class="sxs-lookup"><span data-stu-id="05ae9-116">The table also specifies whether the delegate type operates synchronously or asynchronously.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="05ae9-117">编译代码</span><span class="sxs-lookup"><span data-stu-id="05ae9-117">Compiling the Code</span></span>  
 <span data-ttu-id="05ae9-118">复制示例代码，并将它粘贴到 Visual Studio 项目中，或粘贴到 `DataflowExecutionBlocks.cs`（对于 Visual Basic，则为 `DataflowExecutionBlocks.vb`）文件中，再在 Visual Studio 命令提示符窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="05ae9-118">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowExecutionBlocks.cs` (`DataflowExecutionBlocks.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="05ae9-119">Visual C#</span><span class="sxs-lookup"><span data-stu-id="05ae9-119">Visual C#</span></span>  
  
 <span data-ttu-id="05ae9-120">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.cs**</span><span class="sxs-lookup"><span data-stu-id="05ae9-120">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.cs**</span></span>  
  
 <span data-ttu-id="05ae9-121">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="05ae9-121">Visual Basic</span></span>  
  
 <span data-ttu-id="05ae9-122">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.vb**</span><span class="sxs-lookup"><span data-stu-id="05ae9-122">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="05ae9-123">可靠编程</span><span class="sxs-lookup"><span data-stu-id="05ae9-123">Robust Programming</span></span>  
 <span data-ttu-id="05ae9-124">此示例为 <xref:System.Func%602> 对象提供类型 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 的委托，以同步执行数据流块的任务。</span><span class="sxs-lookup"><span data-stu-id="05ae9-124">This example provides a delegate of type <xref:System.Func%602> to the <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> object to perform the task of the dataflow block synchronously.</span></span> <span data-ttu-id="05ae9-125">为了使数据流块异步执行操作，请为数据流块提供类型 <xref:System.Func%601> 的委托。</span><span class="sxs-lookup"><span data-stu-id="05ae9-125">To enable the dataflow block to behave asynchronously, provide a delegate of type <xref:System.Func%601> to the dataflow block.</span></span> <span data-ttu-id="05ae9-126">当数据流块异步执行操作时，数据流块的任务只有在返回的 <xref:System.Threading.Tasks.Task%601> 对象完成时才会完成。</span><span class="sxs-lookup"><span data-stu-id="05ae9-126">When a dataflow block behaves asynchronously, the task of the dataflow block is complete only when the returned <xref:System.Threading.Tasks.Task%601> object finishes.</span></span> <span data-ttu-id="05ae9-127">下面的示例修改了 `CountBytes` 方法，并使用 [async](~/docs/csharp/language-reference/keywords/async.md) 和 [await](~/docs/csharp/language-reference/keywords/await.md) 运算符（Visual Basic 中为 [Async](~/docs/visual-basic/language-reference/modifiers/async.md) 和 [Await](~/docs/visual-basic/language-reference/operators/await-operator.md)）异步计算所提供文件中为零的字节的总数。</span><span class="sxs-lookup"><span data-stu-id="05ae9-127">The following example modifies the `CountBytes` method and uses the [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) operators ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic) to asynchronously compute the total number of bytes that are zero in the provided file.</span></span> <span data-ttu-id="05ae9-128"><xref:System.IO.FileStream.ReadAsync%2A> 方法异步执行文件读取操作。</span><span class="sxs-lookup"><span data-stu-id="05ae9-128">The <xref:System.IO.FileStream.ReadAsync%2A> method performs file read operations asynchronously.</span></span>  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#2)]
 [!code-vb[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#2)]  
  
 <span data-ttu-id="05ae9-129">还可以使用异步的 lambda 表达式在执行数据流块中执行操作。</span><span class="sxs-lookup"><span data-stu-id="05ae9-129">You can also use asynchronous lambda expressions to perform action in an execution dataflow block.</span></span> <span data-ttu-id="05ae9-130">下面的示例修改了上一示例中使用的 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 对象，以便使用 lambda 表达式异步执行工作。</span><span class="sxs-lookup"><span data-stu-id="05ae9-130">The following example modifies the <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> object that is used in the previous example so that it uses a lambda expression to perform the work asynchronously.</span></span>  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#3)]
 [!code-vb[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="05ae9-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="05ae9-131">See Also</span></span>  
 [<span data-ttu-id="05ae9-132">数据流</span><span class="sxs-lookup"><span data-stu-id="05ae9-132">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
