---
title: 如何：使用 JoinBlock 从多个源读取数据
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, joining blocks in
- dataflow blocks, joining in TPL
ms.assetid: e9c1ada4-ac57-4704-87cb-2f5117f8151d
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ba353a34306b06e0f1df4696af5545799e7a5b37
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-joinblock-to-read-data-from-multiple-sources"></a><span data-ttu-id="bda2b-102">如何：使用 JoinBlock 从多个源读取数据</span><span class="sxs-lookup"><span data-stu-id="bda2b-102">How to: Use JoinBlock to Read Data From Multiple Sources</span></span>
<span data-ttu-id="bda2b-103">本文档介绍如何在来自多个源的数据可用时使用 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 类执行操作。</span><span class="sxs-lookup"><span data-stu-id="bda2b-103">This document explains how to use the <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> class to perform an operation when data is available from multiple sources.</span></span> <span data-ttu-id="bda2b-104">还演示了如何使用非贪婪模式使多个联接块更有效地共享数据源。</span><span class="sxs-lookup"><span data-stu-id="bda2b-104">It also demonstrates how to use non-greedy mode to enable multiple join blocks to share a data source more efficiently.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a><span data-ttu-id="bda2b-105">示例</span><span class="sxs-lookup"><span data-stu-id="bda2b-105">Example</span></span>  
 <span data-ttu-id="bda2b-106">下面的示例定义了三种资源类型（`NetworkResource`、`FileResource` 和 `MemoryResource`）并在资源可用时执行操作。</span><span class="sxs-lookup"><span data-stu-id="bda2b-106">The following example defines three resource types, `NetworkResource`, `FileResource`, and `MemoryResource`, and performs operations when resources become available.</span></span> <span data-ttu-id="bda2b-107">此示例需要使用 `NetworkResource` 和 `MemoryResource` 对才能执行第一个操作，需要使用 `FileResource` 和 `MemoryResource` 对才能执行第二个操作。</span><span class="sxs-lookup"><span data-stu-id="bda2b-107">This example requires a `NetworkResource` and `MemoryResource` pair in order to perform the first operation and a `FileResource` and `MemoryResource` pair in order to perform the second operation.</span></span> <span data-ttu-id="bda2b-108">为了在所有所需资源可用时启用这些操作，此示例使用 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 类。</span><span class="sxs-lookup"><span data-stu-id="bda2b-108">To enable these operations to occur when all required resources are available, this example uses the <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> class.</span></span> <span data-ttu-id="bda2b-109">当 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 对象从所有源接收数据时，它会将该数据传播到其目标，其目标在本示例中为 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 对象。</span><span class="sxs-lookup"><span data-stu-id="bda2b-109">When a <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> object receives data from all sources, it propagates that data to its target, which in this example is an <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="bda2b-110">两个 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 对象都从 `MemoryResource` 对象的共享池中读取。</span><span class="sxs-lookup"><span data-stu-id="bda2b-110">Both <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objects read from a shared pool of `MemoryResource` objects.</span></span>  
  
 [!code-csharp[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_nongreedyjoin/cs/nongreedyjoin.cs#1)]
 [!code-vb[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_nongreedyjoin/vb/nongreedyjoin.vb#1)]  
  
 <span data-ttu-id="bda2b-111">为了实现 `MemoryResource` 对象共享池的高效使用，此示例指定了一个 <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions> 对象，该对象将 <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> 属性设置为 `False` 以创建在非贪婪模式下运行的 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 对象。</span><span class="sxs-lookup"><span data-stu-id="bda2b-111">To enable efficient use of the shared pool of `MemoryResource` objects, this example specifies a <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> property set to `False` to create <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objects that act in non-greedy mode.</span></span> <span data-ttu-id="bda2b-112">非贪婪联接块会推迟所有传入的消息，直至从每个源收到一条消息。</span><span class="sxs-lookup"><span data-stu-id="bda2b-112">A non-greedy join block postpones all incoming messages until one is available from each source.</span></span> <span data-ttu-id="bda2b-113">如果任何推迟的消息由另一个块接受，联接块将重新启动该进程。</span><span class="sxs-lookup"><span data-stu-id="bda2b-113">If any of the postponed messages were accepted by another block, the join block restarts the process.</span></span> <span data-ttu-id="bda2b-114">非贪婪模式使联接块能够共享一个或多个源块，以便在其他块等待数据时能够使进程向前推进。</span><span class="sxs-lookup"><span data-stu-id="bda2b-114">Non-greedy mode enables join blocks that share one or more source blocks to make forward progress as the other blocks wait for data.</span></span> <span data-ttu-id="bda2b-115">在此示例中，如果将 `MemoryResource` 对象添加到 `memoryResources` 池中，那么要接收第二个数据源的第一个联接块可以将进程向前推进。</span><span class="sxs-lookup"><span data-stu-id="bda2b-115">In this example, if a `MemoryResource` object is added to the `memoryResources` pool, the first join block to receive its second data source can make forward progress.</span></span> <span data-ttu-id="bda2b-116">如果此示例使用贪婪模式（默认模式），一个联接块可能会接受 `MemoryResource` 对象，然后等待第二个资源变为可用。</span><span class="sxs-lookup"><span data-stu-id="bda2b-116">If this example were to use greedy mode, which is the default, one join block might take the `MemoryResource` object and wait for the second resource to become available.</span></span> <span data-ttu-id="bda2b-117">但是，如果另一个联接块有自己的第二个可用数据源，则它无法使进程向前推进，因为 `MemoryResource` 对象已被另一联接块占用。</span><span class="sxs-lookup"><span data-stu-id="bda2b-117">However, if the other join block has its second data source available, it cannot make forward progress because the `MemoryResource` object has been taken by the other join block.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bda2b-118">编译代码</span><span class="sxs-lookup"><span data-stu-id="bda2b-118">Compiling the Code</span></span>  
 <span data-ttu-id="bda2b-119">复制示例代码，并将它粘贴到 Visual Studio 项目中，或粘贴到 `DataflowNonGreedyJoin.cs`（对于 Visual Basic，则为 `DataflowNonGreedyJoin.vb`）文件中，再在 Visual Studio 命令提示符窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="bda2b-119">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowNonGreedyJoin.cs` (`DataflowNonGreedyJoin.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="bda2b-120">Visual C#</span><span class="sxs-lookup"><span data-stu-id="bda2b-120">Visual C#</span></span>  
  
 <span data-ttu-id="bda2b-121">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**</span><span class="sxs-lookup"><span data-stu-id="bda2b-121">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**</span></span>  
  
 <span data-ttu-id="bda2b-122">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bda2b-122">Visual Basic</span></span>  
  
 <span data-ttu-id="bda2b-123">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**</span><span class="sxs-lookup"><span data-stu-id="bda2b-123">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bda2b-124">可靠编程</span><span class="sxs-lookup"><span data-stu-id="bda2b-124">Robust Programming</span></span>  
 <span data-ttu-id="bda2b-125">使用非贪婪联接还有助于防止应用程序中出现死锁。</span><span class="sxs-lookup"><span data-stu-id="bda2b-125">The use of non-greedy joins can also help you prevent deadlock in your application.</span></span> <span data-ttu-id="bda2b-126">在软件应用中，如果两个或多个进程分别留有资源，且相互等待另一进程释放其他资源，就会发生死锁。</span><span class="sxs-lookup"><span data-stu-id="bda2b-126">In a software application, *deadlock* occurs when two or more processes each hold a resource and mutually wait for another process to release some other resource.</span></span> <span data-ttu-id="bda2b-127">考虑一个定义两个 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 对象的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bda2b-127">Consider an application that defines two <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objects.</span></span> <span data-ttu-id="bda2b-128">两个对象都从两个共享源块读取数据。</span><span class="sxs-lookup"><span data-stu-id="bda2b-128">Both objects each read data from two shared source blocks.</span></span> <span data-ttu-id="bda2b-129">在贪婪模式下，如果一个联接块从第一个源读取，第二个联接块从第二个源读取，则应用程序可能发生死锁，原因是两个联接块相互等待另一个联接块释放其资源。</span><span class="sxs-lookup"><span data-stu-id="bda2b-129">In greedy mode, if one join block reads from the first source and the second join block reads from the second source, the application might deadlock because both join blocks mutually wait for the other to release its resource.</span></span> <span data-ttu-id="bda2b-130">在非贪婪模式下，每个联接块只在所有数据可用时才从其源读取，因此消除了死锁风险。</span><span class="sxs-lookup"><span data-stu-id="bda2b-130">In non-greedy mode, each join block reads from its sources only when all data is available, and therefore, the risk of deadlock is eliminated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda2b-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="bda2b-131">See Also</span></span>  
 [<span data-ttu-id="bda2b-132">数据流</span><span class="sxs-lookup"><span data-stu-id="bda2b-132">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
