---
title: 如何：将消息写入数据流块和从数据流块读取消息
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47a61a1d01984eeefb2f1f09774374dc29a774d3
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087804"
---
# <a name="how-to-write-messages-to-and-read-messages-from-a-dataflow-block"></a><span data-ttu-id="046b1-102">如何：将消息写入数据流块和从数据流块读取消息</span><span class="sxs-lookup"><span data-stu-id="046b1-102">How to: Write Messages to and Read Messages from a Dataflow Block</span></span>
<span data-ttu-id="046b1-103">本文档介绍如何使用 TPL 数据流库从数据流块写入和读取消息。</span><span class="sxs-lookup"><span data-stu-id="046b1-103">This document describes how to use the TPL Dataflow Library to write messages to and read messages from a dataflow block.</span></span> <span data-ttu-id="046b1-104">TPL 数据流库同时提供用于从数据流块写入和读取消息的同步和异步方法。</span><span class="sxs-lookup"><span data-stu-id="046b1-104">The TPL Dataflow Library provides both synchronous and asynchronous methods for writing messages to and reading messages from a dataflow block.</span></span> <span data-ttu-id="046b1-105">本文档使用 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType> 类。</span><span class="sxs-lookup"><span data-stu-id="046b1-105">This document uses the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="046b1-106"><xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 类将缓冲消息，而且其行为方式与消息源相同，也与消息目标相同。</span><span class="sxs-lookup"><span data-stu-id="046b1-106">The <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class buffers messages and behaves as both a message source and as a message target.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="writing-to-and-reading-from-a-dataflow-block-synchronously"></a><span data-ttu-id="046b1-107">从数据流块同步写入和读取</span><span class="sxs-lookup"><span data-stu-id="046b1-107">Writing to and Reading from a Dataflow Block Synchronously</span></span>  
 <span data-ttu-id="046b1-108">下面的示例使用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 方法写入 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 数据流块，使用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> 方法从同一对象读取。</span><span class="sxs-lookup"><span data-stu-id="046b1-108">The following example uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method to write to a <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> dataflow block and the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> method to read from the same object.</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 <span data-ttu-id="046b1-109">如以下示例所示，还可以使用 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 方法从数据流块读取。</span><span class="sxs-lookup"><span data-stu-id="046b1-109">You can also use the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method to read from a dataflow block, as shown in the following example.</span></span> <span data-ttu-id="046b1-110"><xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 方法不会阻止当前线程，而且在偶尔轮询数据时非常有用。</span><span class="sxs-lookup"><span data-stu-id="046b1-110">The <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method does not block the current thread and is useful when you occasionally poll for data.</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 <span data-ttu-id="046b1-111">由于 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 方法是同步运行的，前面示例中的 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 对象会在第二个循环读取数据之前接收所有数据。</span><span class="sxs-lookup"><span data-stu-id="046b1-111">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method acts synchronously, the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> object in the previous examples receives all data before the second loop reads data.</span></span> <span data-ttu-id="046b1-112">下面的示例对第一个示例进行了扩展，使用 <xref:System.Threading.Tasks.Parallel.Invoke%2A> 同时读取和写入消息块。</span><span class="sxs-lookup"><span data-stu-id="046b1-112">The following example extends the first example by using <xref:System.Threading.Tasks.Parallel.Invoke%2A> to read from and write to the message block concurrently.</span></span> <span data-ttu-id="046b1-113">由于 <xref:System.Threading.Tasks.Parallel.Invoke%2A> 并发执行操作，因此不会按任何特定的顺序将值写入 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 对象。</span><span class="sxs-lookup"><span data-stu-id="046b1-113">Because <xref:System.Threading.Tasks.Parallel.Invoke%2A> performs actions concurrently, the values are not written to the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> object in any specific order.</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-asynchronously"></a><span data-ttu-id="046b1-114">从数据流块异步写入和读取</span><span class="sxs-lookup"><span data-stu-id="046b1-114">Writing to and Reading from a Dataflow Block Asynchronously</span></span>  
 <span data-ttu-id="046b1-115">下面的示例使用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> 方法异步写入 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 对象，使用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> 方法从同一对象异步读取。</span><span class="sxs-lookup"><span data-stu-id="046b1-115">The following example uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> method to asynchronously write to a <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> object and the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> method to asynchronously read from the same object.</span></span> <span data-ttu-id="046b1-116">本示例使用 [async](~/docs/csharp/language-reference/keywords/async.md) 和 [await](~/docs/csharp/language-reference/keywords/await.md) 运算符（Visual Basic 中为 [Async](~/docs/visual-basic/language-reference/modifiers/async.md) 和 [Await](~/docs/visual-basic/language-reference/operators/await-operator.md)）以异步方式向目标块发送数据以及从中读取数据。</span><span class="sxs-lookup"><span data-stu-id="046b1-116">This example uses the [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) operators ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic) to asynchronously send data to and read data from the target block.</span></span> <span data-ttu-id="046b1-117">必须启用数据流块来推迟消息时，<xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> 方法很有用。</span><span class="sxs-lookup"><span data-stu-id="046b1-117">The <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> method is useful when you must enable a dataflow block to postpone messages.</span></span> <span data-ttu-id="046b1-118">希望在数据可用时对此数据进行操作时，<xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> 方法很有用。</span><span class="sxs-lookup"><span data-stu-id="046b1-118">The <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> method is useful when you want to act on data when that data becomes available.</span></span> <span data-ttu-id="046b1-119">有关消息在消息块之间如何传播的详细信息，请参阅[数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)中的“消息传递”一节。</span><span class="sxs-lookup"><span data-stu-id="046b1-119">For more information about how messages propagate among message blocks, see the section Message Passing in [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## <a name="a-complete-example"></a><span data-ttu-id="046b1-120">完整示例</span><span class="sxs-lookup"><span data-stu-id="046b1-120">A Complete Example</span></span>  
 <span data-ttu-id="046b1-121">下面的示例显示本文档的完整代码。</span><span class="sxs-lookup"><span data-stu-id="046b1-121">The following example shows the complete code for this document.</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="046b1-122">编译代码</span><span class="sxs-lookup"><span data-stu-id="046b1-122">Compiling the Code</span></span>  
 <span data-ttu-id="046b1-123">复制示例代码，并将它粘贴到 Visual Studio 项目中，或粘贴到 `DataflowReadWrite.cs`（对于 Visual Basic，则为 `DataflowReadWrite.vb`）文件中，再在 Visual Studio 命令提示符窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="046b1-123">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowReadWrite.cs` (`DataflowReadWrite.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="046b1-124">Visual C#</span><span class="sxs-lookup"><span data-stu-id="046b1-124">Visual C#</span></span>  
  
 <span data-ttu-id="046b1-125">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**</span><span class="sxs-lookup"><span data-stu-id="046b1-125">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**</span></span>  
  
 <span data-ttu-id="046b1-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="046b1-126">Visual Basic</span></span>  
  
 <span data-ttu-id="046b1-127">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**</span><span class="sxs-lookup"><span data-stu-id="046b1-127">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="046b1-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="046b1-128">Next Steps</span></span>  
 <span data-ttu-id="046b1-129">本示例演示如何直接从消息块读取和写入。</span><span class="sxs-lookup"><span data-stu-id="046b1-129">This example shows how to read from and write to a message block directly.</span></span> <span data-ttu-id="046b1-130">还可以连接数据流块来形成管道（这是数据流块的线性序列）或网络（这是数据流块的图形）。</span><span class="sxs-lookup"><span data-stu-id="046b1-130">You can also connect dataflow blocks to form *pipelines*, which are linear sequences of dataflow blocks, or *networks*, which are graphs of dataflow blocks.</span></span> <span data-ttu-id="046b1-131">在管道或网络中，当数据可用时源向目标异步传播数据。</span><span class="sxs-lookup"><span data-stu-id="046b1-131">In a pipeline or network, sources asynchronously propagate data to targets as that data becomes available.</span></span> <span data-ttu-id="046b1-132">有关创建基本数据流管道的示例，请参阅[演练：创建数据流管道](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="046b1-132">For an example that creates a basic dataflow pipeline, see [Walkthrough: Creating a Dataflow Pipeline](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md).</span></span> <span data-ttu-id="046b1-133">有关创建更复杂的数据流网络的示例，请参阅[演练：在 Windows 窗体应用程序中使用数据流](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)。</span><span class="sxs-lookup"><span data-stu-id="046b1-133">For an example that creates a more complex dataflow network, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="046b1-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="046b1-134">See also</span></span>

- [<span data-ttu-id="046b1-135">数据流</span><span class="sxs-lookup"><span data-stu-id="046b1-135">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
