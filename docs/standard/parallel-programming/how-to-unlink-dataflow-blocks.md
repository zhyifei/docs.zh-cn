---
title: "如何：取消链接数据流块"
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
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41f1b83fab6ff44e69ac2f010f70e6e254341f5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-unlink-dataflow-blocks"></a><span data-ttu-id="6a5d3-102">如何：取消链接数据流块</span><span class="sxs-lookup"><span data-stu-id="6a5d3-102">How to: Unlink Dataflow Blocks</span></span>
<span data-ttu-id="6a5d3-103">本文档介绍如何取消目标数据流块与其源的链接。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-103">This document describes how to unlink a target dataflow block from its source.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="6a5d3-104">TPL 数据流库（<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 命名空间）不是随 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 一起分发的。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-104">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="6a5d3-105">若要安装<xref:System.Threading.Tasks.Dataflow>命名空间中，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从项目菜单，然后联机搜索`Microsoft.Tpl.Dataflow`包。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-105">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a5d3-106">示例</span><span class="sxs-lookup"><span data-stu-id="6a5d3-106">Example</span></span>  
 <span data-ttu-id="6a5d3-107">下面的示例创建了三个 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 对象，每个对象调用 `TrySolution` 方法来计算值。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-107">The following example creates three <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objects, each of which calls the `TrySolution` method to compute a value.</span></span> <span data-ttu-id="6a5d3-108">此示例只需使用第一次调用 `TrySolution` 的结果即可完成。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-108">This example requires only the result from the first call to `TrySolution` to finish.</span></span>  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 <span data-ttu-id="6a5d3-109">为了接收完成的第一个 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 对象的值，该示例定义了 `ReceiveFromAny(T)` 方法。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-109">To receive the value from the first <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> object that finishes, this example defines the `ReceiveFromAny(T)` method.</span></span> <span data-ttu-id="6a5d3-110">`ReceiveFromAny(T)` 方法接受一个 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 对象的数组，并将其中每个对象链接到 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-110">The `ReceiveFromAny(T)` method accepts an array of <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> objects and links each of these objects to a <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="6a5d3-111">当使用 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 方法将源数据流块链接到目标块时，源会在数据可用时将消息传播到目标。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-111">When you use the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method to link a source dataflow block to a target block, the source propagates messages to the target as data becomes available.</span></span> <span data-ttu-id="6a5d3-112">因为 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 类只接受为其提供的第一条消息，`ReceiveFromAny(T)` 方法通过调用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> 方法来生成其结果。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-112">Because the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> class accepts only the first message that it is offered, the `ReceiveFromAny(T)` method produces its result by calling the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> method.</span></span> <span data-ttu-id="6a5d3-113">这将生成提供给 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象的第一条消息。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-113">This produces the first message that is offered to the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="6a5d3-114"><xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 方法有一个采用 <xref:System.Boolean> 参数的重载版本 `unlinkAfterOne`，当其设置为 `True` 时，则指示源块在目标收到来自源的一条消息后取消与目标的链接。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-114">The <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method has an overloaded version that takes a <xref:System.Boolean> parameter, `unlinkAfterOne` that, when it is set to `True`, instructs the source block to unlink from the target after the target receives one message from the source.</span></span> <span data-ttu-id="6a5d3-115">取消 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象与其源的链接非常重要，因为当 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象收到一条消息后，便不再需要源数组与 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象之间的关系。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-115">It is important for the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object to unlink from its sources because the relationship between the array of sources and the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object is no longer required after the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object receives a message.</span></span>  
  
 <span data-ttu-id="6a5d3-116">为了使 `TrySolution` 的剩余调用能够在其中一个调用计算了一个值后结束，`TrySolution` 方法采用一个 <xref:System.Threading.CancellationToken> 对象，该对象在对 `ReceiveFromAny(T)` 的调用返回后将被取消。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-116">To enable the remaining calls to `TrySolution` to end after one of them computes a value, the `TrySolution` method takes a <xref:System.Threading.CancellationToken> object that is canceled after the call to `ReceiveFromAny(T)` returns.</span></span> <span data-ttu-id="6a5d3-117">当此 <xref:System.Threading.SpinWait.SpinUntil%2A> 对象取消时，<xref:System.Threading.CancellationToken> 方法将返回。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-117">The <xref:System.Threading.SpinWait.SpinUntil%2A> method returns when this <xref:System.Threading.CancellationToken> object is canceled.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6a5d3-118">编译代码</span><span class="sxs-lookup"><span data-stu-id="6a5d3-118">Compiling the Code</span></span>  
 <span data-ttu-id="6a5d3-119">复制示例代码并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为 `DataflowReceiveAny.cs`（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]，则为 `DataflowReceiveAny.vb`）的文件中，然后在 Visual Studio 命令提示符窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="6a5d3-119">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="6a5d3-120">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span><span class="sxs-lookup"><span data-stu-id="6a5d3-120">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="6a5d3-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span><span class="sxs-lookup"><span data-stu-id="6a5d3-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6a5d3-122">可靠编程</span><span class="sxs-lookup"><span data-stu-id="6a5d3-122">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a5d3-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a5d3-123">See Also</span></span>  
 [<span data-ttu-id="6a5d3-124">数据流</span><span class="sxs-lookup"><span data-stu-id="6a5d3-124">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
