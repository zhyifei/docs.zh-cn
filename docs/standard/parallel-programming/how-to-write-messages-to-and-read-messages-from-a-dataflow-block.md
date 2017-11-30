---
title: "如何：将消息写入数据流块和从数据流块读取消息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bf609a8c350a44fc802cce0ec10693431bbf4f42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-write-messages-to-and-read-messages-from-a-dataflow-block"></a><span data-ttu-id="56cd3-102">如何：将消息写入数据流块和从数据流块读取消息</span><span class="sxs-lookup"><span data-stu-id="56cd3-102">How to: Write Messages to and Read Messages from a Dataflow Block</span></span>
<span data-ttu-id="56cd3-103">本文档介绍如何使用 TPL 数据流库从数据流块写入和读取消息。</span><span class="sxs-lookup"><span data-stu-id="56cd3-103">This document describes how to use the TPL Dataflow Library to write messages to and read messages from a dataflow block.</span></span> <span data-ttu-id="56cd3-104">TPL 数据流库同时提供用于从数据流块写入和读取消息的同步和异步方法。</span><span class="sxs-lookup"><span data-stu-id="56cd3-104">The TPL Dataflow Library provides both synchronous and asynchronous methods for writing messages to and reading messages from a dataflow block.</span></span> <span data-ttu-id="56cd3-105">本文档使用 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType> 类。</span><span class="sxs-lookup"><span data-stu-id="56cd3-105">This document uses the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="56cd3-106"><xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 类将缓冲消息，而且其行为方式与消息源相同，也与消息目标相同。</span><span class="sxs-lookup"><span data-stu-id="56cd3-106">The <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class buffers messages and behaves as both a message source and as a message target.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="56cd3-107">TPL 数据流库（<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 命名空间）不是随 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 一起分发的。</span><span class="sxs-lookup"><span data-stu-id="56cd3-107">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="56cd3-108">若要安装<xref:System.Threading.Tasks.Dataflow>命名空间中，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从项目菜单，然后联机搜索`Microsoft.Tpl.Dataflow`包。</span><span class="sxs-lookup"><span data-stu-id="56cd3-108">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-synchronously"></a><span data-ttu-id="56cd3-109">从数据流块同步写入和读取</span><span class="sxs-lookup"><span data-stu-id="56cd3-109">Writing to and Reading from a Dataflow Block Synchronously</span></span>  
 <span data-ttu-id="56cd3-110">下面的示例使用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 方法写入 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 数据流块，使用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> 方法从同一对象读取。</span><span class="sxs-lookup"><span data-stu-id="56cd3-110">The following example uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method to write to a <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> dataflow block and the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> method to read from the same object.</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 <span data-ttu-id="56cd3-111">如以下示例所示，还可以使用 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 方法从数据流块读取。</span><span class="sxs-lookup"><span data-stu-id="56cd3-111">You can also use the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method to read from a dataflow block, as shown in the following example.</span></span> <span data-ttu-id="56cd3-112"><xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 方法不会阻止当前线程，而且在偶尔轮询数据时非常有用。</span><span class="sxs-lookup"><span data-stu-id="56cd3-112">The <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method does not block the current thread and is useful when you occasionally poll for data.</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 <span data-ttu-id="56cd3-113">由于 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> 方法是同步运行的，前面示例中的 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 对象会在第二个循环读取数据之前接收所有数据。</span><span class="sxs-lookup"><span data-stu-id="56cd3-113">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method acts synchronously, the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> object in the previous examples receives all data before the second loop reads data.</span></span> <span data-ttu-id="56cd3-114">下面的示例对第一个示例进行了扩展，使用 <xref:System.Threading.Tasks.Parallel.Invoke%2A> 同时读取和写入消息块。</span><span class="sxs-lookup"><span data-stu-id="56cd3-114">The following example extends the first example by using <xref:System.Threading.Tasks.Parallel.Invoke%2A> to read from and write to the message block concurrently.</span></span> <span data-ttu-id="56cd3-115">由于 <xref:System.Threading.Tasks.Parallel.Invoke%2A> 并发执行操作，因此不会按任何特定的顺序将值写入 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 对象。</span><span class="sxs-lookup"><span data-stu-id="56cd3-115">Because <xref:System.Threading.Tasks.Parallel.Invoke%2A> performs actions concurrently, the values are not written to the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> object in any specific order.</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-asynchronously"></a><span data-ttu-id="56cd3-116">从数据流块异步写入和读取</span><span class="sxs-lookup"><span data-stu-id="56cd3-116">Writing to and Reading from a Dataflow Block Asynchronously</span></span>  
 <span data-ttu-id="56cd3-117">下面的示例使用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> 方法异步写入 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 对象，使用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> 方法从同一对象异步读取。</span><span class="sxs-lookup"><span data-stu-id="56cd3-117">The following example uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> method to asynchronously write to a <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> object and the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> method to asynchronously read from the same object.</span></span> <span data-ttu-id="56cd3-118">本示例使用 [async](~/docs/csharp/language-reference/keywords/async.md) 和 [await](~/docs/csharp/language-reference/keywords/await.md) 运算符（Visual Basic 中为 [Async](~/docs/visual-basic/language-reference/modifiers/async.md) 和 [Await](~/docs/visual-basic/language-reference/operators/await-operator.md)）以异步方式向目标块发送数据以及从中读取数据。</span><span class="sxs-lookup"><span data-stu-id="56cd3-118">This example uses the [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) operators ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic) to asynchronously send data to and read data from the target block.</span></span> <span data-ttu-id="56cd3-119">必须启用数据流块来推迟消息时，<xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> 方法很有用。</span><span class="sxs-lookup"><span data-stu-id="56cd3-119">The <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> method is useful when you must enable a dataflow block to postpone messages.</span></span> <span data-ttu-id="56cd3-120">希望在数据可用时对此数据进行操作时，<xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> 方法很有用。</span><span class="sxs-lookup"><span data-stu-id="56cd3-120">The <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> method is useful when you want to act on data when that data becomes available.</span></span> <span data-ttu-id="56cd3-121">有关消息在消息块之间如何传播的详细信息，请参阅[数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)中的“消息传递”一节。</span><span class="sxs-lookup"><span data-stu-id="56cd3-121">For more information about how messages propagate among message blocks, see the section Message Passing in [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## <a name="a-complete-example"></a><span data-ttu-id="56cd3-122">完整示例</span><span class="sxs-lookup"><span data-stu-id="56cd3-122">A Complete Example</span></span>  
 <span data-ttu-id="56cd3-123">下面的示例显示本文档的完整代码。</span><span class="sxs-lookup"><span data-stu-id="56cd3-123">The following example shows the complete code for this document.</span></span>  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="56cd3-124">编译代码</span><span class="sxs-lookup"><span data-stu-id="56cd3-124">Compiling the Code</span></span>  
 <span data-ttu-id="56cd3-125">复制示例代码并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为 `DataflowReadWrite.cs`（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]，则为 `DataflowReadWrite.vb`）的文件中，然后在 Visual Studio 命令提示符窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="56cd3-125">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowReadWrite.cs` (`DataflowReadWrite.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="56cd3-126">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**</span><span class="sxs-lookup"><span data-stu-id="56cd3-126">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="56cd3-127">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**</span><span class="sxs-lookup"><span data-stu-id="56cd3-127">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="56cd3-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="56cd3-128">Next Steps</span></span>  
 <span data-ttu-id="56cd3-129">本示例演示如何直接从消息块读取和写入。</span><span class="sxs-lookup"><span data-stu-id="56cd3-129">This example shows how to read from and write to a message block directly.</span></span> <span data-ttu-id="56cd3-130">还可以连接数据流块来形成管道（这是数据流块的线性序列）或网络（这是数据流块的图形）。</span><span class="sxs-lookup"><span data-stu-id="56cd3-130">You can also connect dataflow blocks to form *pipelines*, which are linear sequences of dataflow blocks, or *networks*, which are graphs of dataflow blocks.</span></span> <span data-ttu-id="56cd3-131">在管道或网络中，当数据可用时源向目标异步传播数据。</span><span class="sxs-lookup"><span data-stu-id="56cd3-131">In a pipeline or network, sources asynchronously propagate data to targets as that data becomes available.</span></span> <span data-ttu-id="56cd3-132">有关创建基本数据流管道的示例，请参阅[演练：创建数据流管道](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="56cd3-132">For an example that creates a basic dataflow pipeline, see [Walkthrough: Creating a Dataflow Pipeline](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md).</span></span> <span data-ttu-id="56cd3-133">有关创建更复杂的数据流网络的示例，请参阅[演练：在 Windows 窗体应用程序中使用数据流](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)。</span><span class="sxs-lookup"><span data-stu-id="56cd3-133">For an example that creates a more complex dataflow network, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56cd3-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56cd3-134">See Also</span></span>  
 [<span data-ttu-id="56cd3-135">数据流</span><span class="sxs-lookup"><span data-stu-id="56cd3-135">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
