---
title: "如何：使用屏障来使并发操作保持同步"
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
helpviewer_keywords: Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b2e32fe3cec30a4da7467447aee625dfe7e379b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a><span data-ttu-id="93e57-102">如何：使用屏障来使并发操作保持同步</span><span class="sxs-lookup"><span data-stu-id="93e57-102">How to: Synchronize Concurrent Operations with a Barrier</span></span>
<span data-ttu-id="93e57-103">下面的示例演示如何同步使用的并发任务<xref:System.Threading.Barrier>。</span><span class="sxs-lookup"><span data-stu-id="93e57-103">The following example shows how to synchronize concurrent tasks with a <xref:System.Threading.Barrier>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93e57-104">示例</span><span class="sxs-lookup"><span data-stu-id="93e57-104">Example</span></span>  
 <span data-ttu-id="93e57-105">下面的目的是解决方案的程序的以计算多少迭代 （或阶段） 所需的两个线程与每个查找出自己在同一个阶段上通过使用随机化算法的单词。</span><span class="sxs-lookup"><span data-stu-id="93e57-105">The purpose of the following program is to count how many iterations (or phases) are required for two threads to each find their half of the solution on the same phase by using a randomizing algorithm to reshuffle the words.</span></span> <span data-ttu-id="93e57-106">每个线程具有随机排布其单词后，请 barrier 阶段后操作，它以查看完整的句子是否已呈现在正确的单词顺序的两个结果进行比较。</span><span class="sxs-lookup"><span data-stu-id="93e57-106">After each thread has shuffled its words, the barrier post-phase operation compares the two results to see if the complete sentence has been rendered in correct word order.</span></span>  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <span data-ttu-id="93e57-107">A<xref:System.Threading.Barrier>是阻止继续，直到所有任务都到达屏障并行操作中的各个任务的对象。</span><span class="sxs-lookup"><span data-stu-id="93e57-107">A <xref:System.Threading.Barrier> is an object that prevents individual tasks in a parallel operation from continuing until all tasks reach the barrier.</span></span> <span data-ttu-id="93e57-108">当一种并行操作分阶段，并且每个阶段要求任务之间的同步时，它是很有用。</span><span class="sxs-lookup"><span data-stu-id="93e57-108">It is useful when a parallel operation occurs in phases, and each phase requires synchronization between tasks.</span></span> <span data-ttu-id="93e57-109">在此示例中，有两个阶段对操作。</span><span class="sxs-lookup"><span data-stu-id="93e57-109">In this example, there are two phases to the operation.</span></span> <span data-ttu-id="93e57-110">在第一个阶段中，每个任务填充其部分具有数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="93e57-110">In the first phase, each task fills its section of the buffer with data.</span></span> <span data-ttu-id="93e57-111">每个任务完成时填充其部分，任务发出信号屏障已经准备就绪，若要继续，然后等待。</span><span class="sxs-lookup"><span data-stu-id="93e57-111">When each task finishes filling its section, the task signals the barrier that it is ready to continue, and then waits.</span></span> <span data-ttu-id="93e57-112">时所有的任务已收到信号屏障，它们会阻止，然后在第二个阶段开始。</span><span class="sxs-lookup"><span data-stu-id="93e57-112">When all tasks have signaled the barrier, they are unblocked and the second phase starts.</span></span> <span data-ttu-id="93e57-113">屏障是必需的因为第二个阶段需要每个任务具有已生成到目前为止的所有数据的访问。</span><span class="sxs-lookup"><span data-stu-id="93e57-113">The barrier is necessary because the second phase requires that each task have access to all the data that has been generated to this point.</span></span> <span data-ttu-id="93e57-114">而无需屏障，可能会尝试从已不填充尚未由其他任务的缓冲区中读取第一个任务完成。</span><span class="sxs-lookup"><span data-stu-id="93e57-114">Without the barrier, the first tasks to complete might try to read from buffers that have not been filled in yet by other tasks.</span></span> <span data-ttu-id="93e57-115">你可以同步任意数量的这种方式的阶段。</span><span class="sxs-lookup"><span data-stu-id="93e57-115">You can synchronize any number of phases in this manner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e57-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93e57-116">See Also</span></span>  
 [<span data-ttu-id="93e57-117">用于并行编程的数据结构</span><span class="sxs-lookup"><span data-stu-id="93e57-117">Data Structures for Parallel Programming</span></span>](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
