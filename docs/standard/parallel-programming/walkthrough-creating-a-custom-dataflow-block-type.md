---
title: "演练：创建自定义数据流块类型"
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, creating custom dataflow blocks
- dataflow blocks, creating custom in TPL
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 54882ce5f646e9e790703e0951459a9fceac3bb6
ms.sourcegitcommit: 6a9030eb5bd0f00e1d144f81958adb195cfb1f6f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-creating-a-custom-dataflow-block-type"></a><span data-ttu-id="820a9-102">演练：创建自定义数据流块类型</span><span class="sxs-lookup"><span data-stu-id="820a9-102">Walkthrough: Creating a Custom Dataflow Block Type</span></span>
<span data-ttu-id="820a9-103">尽管 TPL 数据流库提供了多种可启用各种功能的数据流块类型，但也可以创建自定义块类型。</span><span class="sxs-lookup"><span data-stu-id="820a9-103">Although the TPL Dataflow Library provides several dataflow block types that enable a variety of functionality, you can also create custom block types.</span></span> <span data-ttu-id="820a9-104">本文档介绍了如何创建实现自定义行为的数据流块类型。</span><span class="sxs-lookup"><span data-stu-id="820a9-104">This document describes how to create a dataflow block type that implements custom behavior.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="820a9-105">系统必备</span><span class="sxs-lookup"><span data-stu-id="820a9-105">Prerequisites</span></span>  
 <span data-ttu-id="820a9-106">阅读本文档前，请先阅读[数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)。</span><span class="sxs-lookup"><span data-stu-id="820a9-106">Read [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) before you read this document.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="defining-the-sliding-window-dataflow-block"></a><span data-ttu-id="820a9-107">定义滑动窗口数据流块</span><span class="sxs-lookup"><span data-stu-id="820a9-107">Defining the Sliding Window Dataflow Block</span></span>  
 <span data-ttu-id="820a9-108">假设数据流应用要求缓冲输入值，并以滑动窗口方式输出值。</span><span class="sxs-lookup"><span data-stu-id="820a9-108">Consider a dataflow application that requires that input values be buffered and then output in a sliding window manner.</span></span> <span data-ttu-id="820a9-109">例如，如果输入值为 {0, 1, 2, 3, 4, 5}，且窗口大小为 3，那么滑动窗口数据流块生成输出数组 {0, 1, 2}、{1, 2, 3}、{2, 3, 4} 和 {3, 4, 5}。</span><span class="sxs-lookup"><span data-stu-id="820a9-109">For example, for the input values {0, 1, 2, 3, 4, 5} and a window size of three, a sliding window dataflow block produces the output arrays {0, 1, 2}, {1, 2, 3}, {2, 3, 4}, and {3, 4, 5}.</span></span> <span data-ttu-id="820a9-110">下面各部分介绍了两种方式，用于创建实现此自定义行为的数据流块类型。</span><span class="sxs-lookup"><span data-stu-id="820a9-110">The following sections describe two ways to create a dataflow block type that implements this custom behavior.</span></span> <span data-ttu-id="820a9-111">第一种方式是，使用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> 方法将 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 对象和 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 对象的功能合并到一个传播器块中。</span><span class="sxs-lookup"><span data-stu-id="820a9-111">The first technique uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> method to combine the functionality of an <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> object and an <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> object into one propagator block.</span></span> <span data-ttu-id="820a9-112">第二种方式是，定义派生自 <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> 的类，并结合现有功能执行自定义行为。</span><span class="sxs-lookup"><span data-stu-id="820a9-112">The second technique defines a class that derives from <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> and combines existing functionality to perform custom behavior.</span></span>  
  
## <a name="using-the-encapsulate-method-to-define-the-sliding-window-dataflow-block"></a><span data-ttu-id="820a9-113">使用 Encapsulate 方法定义滑动窗口数据流块</span><span class="sxs-lookup"><span data-stu-id="820a9-113">Using the Encapsulate Method to Define the Sliding Window Dataflow Block</span></span>  
 <span data-ttu-id="820a9-114">下面的示例使用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> 方法通过目标和源创建传播器块。</span><span class="sxs-lookup"><span data-stu-id="820a9-114">The following example uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> method to create a propagator block from a target and a source.</span></span> <span data-ttu-id="820a9-115">使用传播器块，可以将源块和目标块用作数据的接收方和发送方。</span><span class="sxs-lookup"><span data-stu-id="820a9-115">A propagator block enables a source block and a target block to act as a receiver and sender of data.</span></span>  
  
 <span data-ttu-id="820a9-116">如果需要自定义数据流功能，但不需要提供其他方法、属性或字段的类型，此方式就很有用。</span><span class="sxs-lookup"><span data-stu-id="820a9-116">This technique is useful when you require custom dataflow functionality, but you do not require a type that provides additional methods, properties, or fields.</span></span>  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## <a name="deriving-from-ipropagatorblock-to-define-the-sliding-window-dataflow-block"></a><span data-ttu-id="820a9-117">派生自 IPropagatorBlock 以定义滑动窗口数据流块</span><span class="sxs-lookup"><span data-stu-id="820a9-117">Deriving from IPropagatorBlock to Define the Sliding Window Dataflow Block</span></span>  
 <span data-ttu-id="820a9-118">下面的示例展示了 `SlidingWindowBlock` 类。</span><span class="sxs-lookup"><span data-stu-id="820a9-118">The following example shows the `SlidingWindowBlock` class.</span></span> <span data-ttu-id="820a9-119">此类派生自 <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602>，可用作数据的源和目标。</span><span class="sxs-lookup"><span data-stu-id="820a9-119">This class derives from <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> so that it can act as both a source and a target of data.</span></span> <span data-ttu-id="820a9-120">与上一示例中所述一样，`SlidingWindowBlock` 类是在现有数据流块类型的基础之上构建而成。</span><span class="sxs-lookup"><span data-stu-id="820a9-120">As in the previous example, the `SlidingWindowBlock` class is built on existing dataflow block types.</span></span> <span data-ttu-id="820a9-121">不同之处在于，`SlidingWindowBlock` 类还实现了 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>、<xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 和 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> 接口所需的方法。</span><span class="sxs-lookup"><span data-stu-id="820a9-121">However, the `SlidingWindowBlock` class also implements the methods that are required by the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, and <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> interfaces.</span></span> <span data-ttu-id="820a9-122">这些方法全都将工作转发给预定义的数据流块类型成员。</span><span class="sxs-lookup"><span data-stu-id="820a9-122">These methods all forward work to the predefined dataflow block type members.</span></span> <span data-ttu-id="820a9-123">例如，`Post` 方法将工作转交给也是 <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> 对象的 `m_target` 数据成员。</span><span class="sxs-lookup"><span data-stu-id="820a9-123">For example, the `Post` method defers work to the `m_target` data member, which is also an <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> object.</span></span>  
  
 <span data-ttu-id="820a9-124">如果需要自定义数据流功能，还需要提供其他方法、属性或字段的类型，此方式就很有用。</span><span class="sxs-lookup"><span data-stu-id="820a9-124">This technique is useful when you require custom dataflow functionality, and also require a type that provides additional methods, properties, or fields.</span></span> <span data-ttu-id="820a9-125">例如，`SlidingWindowBlock` 类也派生自 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601>，这样就可以提供 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> 和 <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> 方法了。</span><span class="sxs-lookup"><span data-stu-id="820a9-125">For example, the `SlidingWindowBlock` class also derives from <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601> so that it can provide the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> and <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> methods.</span></span> <span data-ttu-id="820a9-126">`SlidingWindowBlock` 类还具有扩展性，体现在提供 `WindowSize` 属性，以检索滑动窗口中的元素数量。</span><span class="sxs-lookup"><span data-stu-id="820a9-126">The `SlidingWindowBlock` class also demonstrates extensibility by providing the `WindowSize` property, which retrieves the number of elements in the sliding window.</span></span>  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## <a name="the-complete-example"></a><span data-ttu-id="820a9-127">完整示例</span><span class="sxs-lookup"><span data-stu-id="820a9-127">The Complete Example</span></span>  
 <span data-ttu-id="820a9-128">下面的示例显示此演练的完整代码。</span><span class="sxs-lookup"><span data-stu-id="820a9-128">The following example shows the complete code for this walkthrough.</span></span> <span data-ttu-id="820a9-129">它还展示了如何在对块执行写入和读取操作并将结果打印到控制台的方法中使用两个滑动窗口块。</span><span class="sxs-lookup"><span data-stu-id="820a9-129">It also demonstrates how to use the both sliding window blocks in a method that writes to the block, reads from it, and prints the results to the console.</span></span>  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="820a9-130">编译代码</span><span class="sxs-lookup"><span data-stu-id="820a9-130">Compiling the Code</span></span>  
 <span data-ttu-id="820a9-131">复制示例代码，并将它粘贴到 Visual Studio 项目中，或粘贴到 `SlidingWindowBlock.cs`（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]，则为 `SlidingWindowBlock.vb`）文件中，再在 Visual Studio 命令提示符窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="820a9-131">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `SlidingWindowBlock.cs` (`SlidingWindowBlock.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="820a9-132">**csc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**</span><span class="sxs-lookup"><span data-stu-id="820a9-132">**csc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="820a9-133">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**</span><span class="sxs-lookup"><span data-stu-id="820a9-133">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**</span></span>  

## <a name="see-also"></a><span data-ttu-id="820a9-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="820a9-134">See Also</span></span>  
 [<span data-ttu-id="820a9-135">数据流</span><span class="sxs-lookup"><span data-stu-id="820a9-135">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
