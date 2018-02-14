---
title: "如何：取消链接数据流块"
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: db3c0d3a6d94e2e9eb65046267f14feff0c056cb
ms.sourcegitcommit: 6a9030eb5bd0f00e1d144f81958adb195cfb1f6f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-unlink-dataflow-blocks"></a><span data-ttu-id="ae111-102">如何：取消链接数据流块</span><span class="sxs-lookup"><span data-stu-id="ae111-102">How to: Unlink Dataflow Blocks</span></span>
<span data-ttu-id="ae111-103">本文档介绍如何取消目标数据流块与其源的链接。</span><span class="sxs-lookup"><span data-stu-id="ae111-103">This document describes how to unlink a target dataflow block from its source.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a><span data-ttu-id="ae111-104">示例</span><span class="sxs-lookup"><span data-stu-id="ae111-104">Example</span></span>  
 <span data-ttu-id="ae111-105">下面的示例创建了三个 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 对象，每个对象调用 `TrySolution` 方法来计算值。</span><span class="sxs-lookup"><span data-stu-id="ae111-105">The following example creates three <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objects, each of which calls the `TrySolution` method to compute a value.</span></span> <span data-ttu-id="ae111-106">此示例只需使用第一次调用 `TrySolution` 的结果即可完成。</span><span class="sxs-lookup"><span data-stu-id="ae111-106">This example requires only the result from the first call to `TrySolution` to finish.</span></span>  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 <span data-ttu-id="ae111-107">为了接收完成的第一个 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 对象的值，该示例定义了 `ReceiveFromAny(T)` 方法。</span><span class="sxs-lookup"><span data-stu-id="ae111-107">To receive the value from the first <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> object that finishes, this example defines the `ReceiveFromAny(T)` method.</span></span> <span data-ttu-id="ae111-108">`ReceiveFromAny(T)` 方法接受一个 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 对象的数组，并将其中每个对象链接到 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象。</span><span class="sxs-lookup"><span data-stu-id="ae111-108">The `ReceiveFromAny(T)` method accepts an array of <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> objects and links each of these objects to a <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="ae111-109">当使用 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 方法将源数据流块链接到目标块时，源会在数据可用时将消息传播到目标。</span><span class="sxs-lookup"><span data-stu-id="ae111-109">When you use the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method to link a source dataflow block to a target block, the source propagates messages to the target as data becomes available.</span></span> <span data-ttu-id="ae111-110">因为 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 类只接受为其提供的第一条消息，`ReceiveFromAny(T)` 方法通过调用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> 方法来生成其结果。</span><span class="sxs-lookup"><span data-stu-id="ae111-110">Because the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> class accepts only the first message that it is offered, the `ReceiveFromAny(T)` method produces its result by calling the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> method.</span></span> <span data-ttu-id="ae111-111">这将生成提供给 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象的第一条消息。</span><span class="sxs-lookup"><span data-stu-id="ae111-111">This produces the first message that is offered to the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="ae111-112"><xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 方法有一个采用 <xref:System.Boolean> 参数的重载版本 `unlinkAfterOne`，当其设置为 `True` 时，则指示源块在目标收到来自源的一条消息后取消与目标的链接。</span><span class="sxs-lookup"><span data-stu-id="ae111-112">The <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method has an overloaded version that takes a <xref:System.Boolean> parameter, `unlinkAfterOne` that, when it is set to `True`, instructs the source block to unlink from the target after the target receives one message from the source.</span></span> <span data-ttu-id="ae111-113">取消 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象与其源的链接非常重要，因为当 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象收到一条消息后，便不再需要源数组与 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象之间的关系。</span><span class="sxs-lookup"><span data-stu-id="ae111-113">It is important for the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object to unlink from its sources because the relationship between the array of sources and the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object is no longer required after the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object receives a message.</span></span>  
  
 <span data-ttu-id="ae111-114">为了使 `TrySolution` 的剩余调用能够在其中一个调用计算了一个值后结束，`TrySolution` 方法采用一个 <xref:System.Threading.CancellationToken> 对象，该对象在对 `ReceiveFromAny(T)` 的调用返回后将被取消。</span><span class="sxs-lookup"><span data-stu-id="ae111-114">To enable the remaining calls to `TrySolution` to end after one of them computes a value, the `TrySolution` method takes a <xref:System.Threading.CancellationToken> object that is canceled after the call to `ReceiveFromAny(T)` returns.</span></span> <span data-ttu-id="ae111-115">当此 <xref:System.Threading.SpinWait.SpinUntil%2A> 对象取消时，<xref:System.Threading.CancellationToken> 方法将返回。</span><span class="sxs-lookup"><span data-stu-id="ae111-115">The <xref:System.Threading.SpinWait.SpinUntil%2A> method returns when this <xref:System.Threading.CancellationToken> object is canceled.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ae111-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="ae111-116">Compiling the Code</span></span>  
 <span data-ttu-id="ae111-117">复制示例代码并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为 `DataflowReceiveAny.cs`（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]，则为 `DataflowReceiveAny.vb`）的文件中，然后在 Visual Studio 命令提示符窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="ae111-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="ae111-118">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span><span class="sxs-lookup"><span data-stu-id="ae111-118">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="ae111-119">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span><span class="sxs-lookup"><span data-stu-id="ae111-119">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span></span>  

## <a name="see-also"></a><span data-ttu-id="ae111-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae111-120">See Also</span></span>  
 [<span data-ttu-id="ae111-121">数据流</span><span class="sxs-lookup"><span data-stu-id="ae111-121">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
