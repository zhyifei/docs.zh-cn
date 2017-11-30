---
title: "如何：使用 JoinBlock 从多个源读取数据"
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
- TPL dataflow library, joining blocks in
- dataflow blocks, joining in TPL
ms.assetid: e9c1ada4-ac57-4704-87cb-2f5117f8151d
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41445e4874b94809840ecf9ebda6f27ccc955c9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-joinblock-to-read-data-from-multiple-sources"></a><span data-ttu-id="f42c3-102">如何：使用 JoinBlock 从多个源读取数据</span><span class="sxs-lookup"><span data-stu-id="f42c3-102">How to: Use JoinBlock to Read Data From Multiple Sources</span></span>
<span data-ttu-id="f42c3-103">本文档介绍如何在来自多个源的数据可用时使用 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 类执行操作。</span><span class="sxs-lookup"><span data-stu-id="f42c3-103">This document explains how to use the <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> class to perform an operation when data is available from multiple sources.</span></span> <span data-ttu-id="f42c3-104">还演示了如何使用非贪婪模式使多个联接块更有效地共享数据源。</span><span class="sxs-lookup"><span data-stu-id="f42c3-104">It also demonstrates how to use non-greedy mode to enable multiple join blocks to share a data source more efficiently.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="f42c3-105">TPL 数据流库（<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 命名空间）不是随 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 一起分发的。</span><span class="sxs-lookup"><span data-stu-id="f42c3-105">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="f42c3-106">若要安装<xref:System.Threading.Tasks.Dataflow>命名空间中，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从项目菜单，然后联机搜索`Microsoft.Tpl.Dataflow`包。</span><span class="sxs-lookup"><span data-stu-id="f42c3-106">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f42c3-107">示例</span><span class="sxs-lookup"><span data-stu-id="f42c3-107">Example</span></span>  
 <span data-ttu-id="f42c3-108">下面的示例定义了三种资源类型（`NetworkResource`、`FileResource` 和 `MemoryResource`）并在资源可用时执行操作。</span><span class="sxs-lookup"><span data-stu-id="f42c3-108">The following example defines three resource types, `NetworkResource`, `FileResource`, and `MemoryResource`, and performs operations when resources become available.</span></span> <span data-ttu-id="f42c3-109">此示例需要使用 `NetworkResource` 和 `MemoryResource` 对才能执行第一个操作，需要使用 `FileResource` 和 `MemoryResource` 对才能执行第二个操作。</span><span class="sxs-lookup"><span data-stu-id="f42c3-109">This example requires a `NetworkResource` and `MemoryResource` pair in order to perform the first operation and a `FileResource` and `MemoryResource` pair in order to perform the second operation.</span></span> <span data-ttu-id="f42c3-110">为了在所有所需资源可用时启用这些操作，此示例使用 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 类。</span><span class="sxs-lookup"><span data-stu-id="f42c3-110">To enable these operations to occur when all required resources are available, this example uses the <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> class.</span></span> <span data-ttu-id="f42c3-111">当 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 对象从所有源接收数据时，它会将该数据传播到其目标，其目标在本示例中为 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 对象。</span><span class="sxs-lookup"><span data-stu-id="f42c3-111">When a <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> object receives data from all sources, it propagates that data to its target, which in this example is an <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="f42c3-112">两个 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 对象都从 `MemoryResource` 对象的共享池中读取。</span><span class="sxs-lookup"><span data-stu-id="f42c3-112">Both <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objects read from a shared pool of `MemoryResource` objects.</span></span>  
  
 [!code-csharp[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_nongreedyjoin/cs/nongreedyjoin.cs#1)]
 [!code-vb[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_nongreedyjoin/vb/nongreedyjoin.vb#1)]  
  
 <span data-ttu-id="f42c3-113">为了实现 `MemoryResource` 对象共享池的高效使用，此示例指定了一个 <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions> 对象，该对象将 <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> 属性设置为 `False` 以创建在非贪婪模式下运行的 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 对象。</span><span class="sxs-lookup"><span data-stu-id="f42c3-113">To enable efficient use of the shared pool of `MemoryResource` objects, this example specifies a <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> property set to `False` to create <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objects that act in non-greedy mode.</span></span> <span data-ttu-id="f42c3-114">非贪婪联接块会推迟所有传入的消息，直至从每个源收到一条消息。</span><span class="sxs-lookup"><span data-stu-id="f42c3-114">A non-greedy join block postpones all incoming messages until one is available from each source.</span></span> <span data-ttu-id="f42c3-115">如果任何推迟的消息由另一个块接受，联接块将重新启动该进程。</span><span class="sxs-lookup"><span data-stu-id="f42c3-115">If any of the postponed messages were accepted by another block, the join block restarts the process.</span></span> <span data-ttu-id="f42c3-116">非贪婪模式使联接块能够共享一个或多个源块，以便在其他块等待数据时能够使进程向前推进。</span><span class="sxs-lookup"><span data-stu-id="f42c3-116">Non-greedy mode enables join blocks that share one or more source blocks to make forward progress as the other blocks wait for data.</span></span> <span data-ttu-id="f42c3-117">在此示例中，如果将 `MemoryResource` 对象添加到 `memoryResources` 池中，那么要接收第二个数据源的第一个联接块可以将进程向前推进。</span><span class="sxs-lookup"><span data-stu-id="f42c3-117">In this example, if a `MemoryResource` object is added to the `memoryResources` pool, the first join block to receive its second data source can make forward progress.</span></span> <span data-ttu-id="f42c3-118">如果此示例使用贪婪模式（默认模式），一个联接块可能会接受 `MemoryResource` 对象，然后等待第二个资源变为可用。</span><span class="sxs-lookup"><span data-stu-id="f42c3-118">If this example were to use greedy mode, which is the default, one join block might take the `MemoryResource` object and wait for the second resource to become available.</span></span> <span data-ttu-id="f42c3-119">但是，如果另一个联接块有自己的第二个可用数据源，则它无法使进程向前推进，因为 `MemoryResource` 对象已被另一联接块占用。</span><span class="sxs-lookup"><span data-stu-id="f42c3-119">However, if the other join block has its second data source available, it cannot make forward progress because the `MemoryResource` object has been taken by the other join block.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f42c3-120">编译代码</span><span class="sxs-lookup"><span data-stu-id="f42c3-120">Compiling the Code</span></span>  
 <span data-ttu-id="f42c3-121">复制示例代码并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为 `DataflowNonGreedyJoin.cs`（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]，则为 `DataflowNonGreedyJoin.vb`）的文件中，然后在 Visual Studio 命令提示符窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="f42c3-121">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowNonGreedyJoin.cs` (`DataflowNonGreedyJoin.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="f42c3-122">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**</span><span class="sxs-lookup"><span data-stu-id="f42c3-122">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="f42c3-123">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**</span><span class="sxs-lookup"><span data-stu-id="f42c3-123">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f42c3-124">可靠编程</span><span class="sxs-lookup"><span data-stu-id="f42c3-124">Robust Programming</span></span>  
 <span data-ttu-id="f42c3-125">使用非贪婪联接还有助于防止应用程序中出现死锁。</span><span class="sxs-lookup"><span data-stu-id="f42c3-125">The use of non-greedy joins can also help you prevent deadlock in your application.</span></span> <span data-ttu-id="f42c3-126">在软件应用程序，*死锁*当两个或多个进程彼此占用一个资源并相互等待另一个进程以释放一些其他资源。</span><span class="sxs-lookup"><span data-stu-id="f42c3-126">In a software application, *deadlock* occurs when two or more processes each hold a resource and mutually wait for another process to release some other resource.</span></span> <span data-ttu-id="f42c3-127">考虑一个定义两个 <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> 对象的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f42c3-127">Consider an application that defines two <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> objects.</span></span> <span data-ttu-id="f42c3-128">两个对象都从两个共享源块读取数据。</span><span class="sxs-lookup"><span data-stu-id="f42c3-128">Both objects each read data from two shared source blocks.</span></span> <span data-ttu-id="f42c3-129">在贪婪模式下，如果一个联接块从第一个源读取，第二个联接块从第二个源读取，则应用程序可能发生死锁，原因是两个联接块相互等待另一个联接块释放其资源。</span><span class="sxs-lookup"><span data-stu-id="f42c3-129">In greedy mode, if one join block reads from the first source and the second join block reads from the second source, the application might deadlock because both join blocks mutually wait for the other to release its resource.</span></span> <span data-ttu-id="f42c3-130">在非贪婪模式下，每个联接块只在所有数据可用时才从其源读取，因此消除了死锁风险。</span><span class="sxs-lookup"><span data-stu-id="f42c3-130">In non-greedy mode, each join block reads from its sources only when all data is available, and therefore, the risk of deadlock is eliminated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f42c3-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f42c3-131">See Also</span></span>  
 [<span data-ttu-id="f42c3-132">数据流</span><span class="sxs-lookup"><span data-stu-id="f42c3-132">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
