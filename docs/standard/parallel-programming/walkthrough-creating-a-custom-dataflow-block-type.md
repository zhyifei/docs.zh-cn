---
title: "演练：创建自定义数据流块类型"
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
- TPL dataflow library, creating custom dataflow blocks
- dataflow blocks, creating custom in TPL
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 809b21fa6e1470890011604792d849998dd03ede
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-creating-a-custom-dataflow-block-type"></a><span data-ttu-id="d739e-102">演练：创建自定义数据流块类型</span><span class="sxs-lookup"><span data-stu-id="d739e-102">Walkthrough: Creating a Custom Dataflow Block Type</span></span>
<span data-ttu-id="d739e-103">尽管 TPL 数据流库提供了启用各种功能的几个数据流块类型，你还可以创建自定义的块类型。</span><span class="sxs-lookup"><span data-stu-id="d739e-103">Although the TPL Dataflow Library provides several dataflow block types that enable a variety of functionality, you can also create custom block types.</span></span> <span data-ttu-id="d739e-104">本文档介绍如何创建实现自定义行为的数据流块类型。</span><span class="sxs-lookup"><span data-stu-id="d739e-104">This document describes how to create a dataflow block type that implements custom behavior.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d739e-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="d739e-105">Prerequisites</span></span>  
 <span data-ttu-id="d739e-106">读取[数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)在阅读本文档之前。</span><span class="sxs-lookup"><span data-stu-id="d739e-106">Read [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) before you read this document.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="d739e-107">TPL 数据流库（<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 命名空间）不是随 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 一起分发的。</span><span class="sxs-lookup"><span data-stu-id="d739e-107">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="d739e-108">若要安装<xref:System.Threading.Tasks.Dataflow>命名空间中，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从项目菜单，然后联机搜索`Microsoft.Tpl.Dataflow`包。</span><span class="sxs-lookup"><span data-stu-id="d739e-108">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="defining-the-sliding-window-dataflow-block"></a><span data-ttu-id="d739e-109">定义滑动窗口数据流块</span><span class="sxs-lookup"><span data-stu-id="d739e-109">Defining the Sliding Window Dataflow Block</span></span>  
 <span data-ttu-id="d739e-110">请考虑需要进行缓冲输入的值，并已将其然后滑动窗口方式输出的数据流应用程序。</span><span class="sxs-lookup"><span data-stu-id="d739e-110">Consider a dataflow application that requires that input values be buffered and then output in a sliding window manner.</span></span> <span data-ttu-id="d739e-111">例如，对于 {0、 1、 2、 3、 4、 5} 的输入的值的三个窗口大小，滑动窗口数据流块都会产生输出数组 {0，1，2}，{1，2，3}，{2，3，4}，和 {3，4，5}。</span><span class="sxs-lookup"><span data-stu-id="d739e-111">For example, for the input values {0, 1, 2, 3, 4, 5} and a window size of three, a sliding window dataflow block produces the output arrays {0, 1, 2}, {1, 2, 3}, {2, 3, 4}, and {3, 4, 5}.</span></span> <span data-ttu-id="d739e-112">以下各节描述了两种方法可以创建实现此自定义行为的数据流块类型。</span><span class="sxs-lookup"><span data-stu-id="d739e-112">The following sections describe two ways to create a dataflow block type that implements this custom behavior.</span></span> <span data-ttu-id="d739e-113">第一种方法使用<xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A>方法，将合并的功能<xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>对象和<xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>构成一个传播器块的对象。</span><span class="sxs-lookup"><span data-stu-id="d739e-113">The first technique uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> method to combine the functionality of an <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> object and an <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> object into one propagator block.</span></span> <span data-ttu-id="d739e-114">第二种方法定义的类派生自<xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602>将合并现有功能，以执行自定义行为。</span><span class="sxs-lookup"><span data-stu-id="d739e-114">The second technique defines a class that derives from <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> and combines existing functionality to perform custom behavior.</span></span>  
  
## <a name="using-the-encapsulate-method-to-define-the-sliding-window-dataflow-block"></a><span data-ttu-id="d739e-115">使用封装方法用来定义滑动窗口数据流块</span><span class="sxs-lookup"><span data-stu-id="d739e-115">Using the Encapsulate Method to Define the Sliding Window Dataflow Block</span></span>  
 <span data-ttu-id="d739e-116">下面的示例使用<xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A>方法来创建从目标和源的传播器块。</span><span class="sxs-lookup"><span data-stu-id="d739e-116">The following example uses the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> method to create a propagator block from a target and a source.</span></span> <span data-ttu-id="d739e-117">传播器块，可以将源块和目标块，使其作为数据的发送者和接收者。</span><span class="sxs-lookup"><span data-stu-id="d739e-117">A propagator block enables a source block and a target block to act as a receiver and sender of data.</span></span>  
  
 <span data-ttu-id="d739e-118">当需要自定义数据流功能，但不是需要提供更多的方法、 属性或字段的类型时，此方法很有用。</span><span class="sxs-lookup"><span data-stu-id="d739e-118">This technique is useful when you require custom dataflow functionality, but you do not require a type that provides additional methods, properties, or fields.</span></span>  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## <a name="deriving-from-ipropagatorblock-to-define-the-sliding-window-dataflow-block"></a><span data-ttu-id="d739e-119">派生自 IPropagatorBlock 定义滑动窗口数据流块</span><span class="sxs-lookup"><span data-stu-id="d739e-119">Deriving from IPropagatorBlock to Define the Sliding Window Dataflow Block</span></span>  
 <span data-ttu-id="d739e-120">下面的示例演示`SlidingWindowBlock`类。</span><span class="sxs-lookup"><span data-stu-id="d739e-120">The following example shows the `SlidingWindowBlock` class.</span></span> <span data-ttu-id="d739e-121">此类派生自<xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602>，以便它可以充当源和数据的目标。</span><span class="sxs-lookup"><span data-stu-id="d739e-121">This class derives from <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> so that it can act as both a source and a target of data.</span></span> <span data-ttu-id="d739e-122">与前面的示例中，`SlidingWindowBlock`类基于现有的数据流块类型。</span><span class="sxs-lookup"><span data-stu-id="d739e-122">As in the previous example, the `SlidingWindowBlock` class is built on existing dataflow block types.</span></span> <span data-ttu-id="d739e-123">但是，`SlidingWindowBlock`类还可实现的方法所需的<xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>， <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>，和<xref:System.Threading.Tasks.Dataflow.IDataflowBlock>接口。</span><span class="sxs-lookup"><span data-stu-id="d739e-123">However, the `SlidingWindowBlock` class also implements the methods that are required by the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, and <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> interfaces.</span></span> <span data-ttu-id="d739e-124">转发所有这些方法的工作原理预定义的数据流块类型的成员。</span><span class="sxs-lookup"><span data-stu-id="d739e-124">These methods all forward work to the predefined dataflow block type members.</span></span> <span data-ttu-id="d739e-125">例如，`Post`方法交由工作`m_target`数据成员，也是<xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>对象。</span><span class="sxs-lookup"><span data-stu-id="d739e-125">For example, the `Post` method defers work to the `m_target` data member, which is also an <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> object.</span></span>  
  
 <span data-ttu-id="d739e-126">当你需要自定义数据流功能，并且还需要提供更多的方法、 属性或字段的类型时，此方法很有用。</span><span class="sxs-lookup"><span data-stu-id="d739e-126">This technique is useful when you require custom dataflow functionality, and also require a type that provides additional methods, properties, or fields.</span></span> <span data-ttu-id="d739e-127">例如，`SlidingWindowBlock`类还派生自<xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601>以便它可以提供<xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A>和<xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="d739e-127">For example, the `SlidingWindowBlock` class also derives from <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601> so that it can provide the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> and <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> methods.</span></span> <span data-ttu-id="d739e-128">`SlidingWindowBlock`类还通过提供演示扩展性`WindowSize`属性，用于检索的滑动窗口中的元素数。</span><span class="sxs-lookup"><span data-stu-id="d739e-128">The `SlidingWindowBlock` class also demonstrates extensibility by providing the `WindowSize` property, which retrieves the number of elements in the sliding window.</span></span>  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## <a name="the-complete-example"></a><span data-ttu-id="d739e-129">完整示例</span><span class="sxs-lookup"><span data-stu-id="d739e-129">The Complete Example</span></span>  
 <span data-ttu-id="d739e-130">下面的示例显示此演练的完整代码。</span><span class="sxs-lookup"><span data-stu-id="d739e-130">The following example shows the complete code for this walkthrough.</span></span> <span data-ttu-id="d739e-131">它还演示了如何使用两个滑动窗口块写入块、 读取它，并将打印到控制台的结果的方法中。</span><span class="sxs-lookup"><span data-stu-id="d739e-131">It also demonstrates how to use the both sliding window blocks in a method that writes to the block, reads from it, and prints the results to the console.</span></span>  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d739e-132">编译代码</span><span class="sxs-lookup"><span data-stu-id="d739e-132">Compiling the Code</span></span>  
 <span data-ttu-id="d739e-133">复制代码示例并将其粘贴到 Visual Studio 项目中，或将其粘贴在文件中名为`SlidingWindowBlock.cs`(`SlidingWindowBlock.vb`为[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)])，然后在 Visual Studio 命令提示符窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="d739e-133">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `SlidingWindowBlock.cs` (`SlidingWindowBlock.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="d739e-134">**csc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**</span><span class="sxs-lookup"><span data-stu-id="d739e-134">**csc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="d739e-135">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**</span><span class="sxs-lookup"><span data-stu-id="d739e-135">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d739e-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d739e-136">Next Steps</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d739e-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d739e-137">See Also</span></span>  
 [<span data-ttu-id="d739e-138">数据流</span><span class="sxs-lookup"><span data-stu-id="d739e-138">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
