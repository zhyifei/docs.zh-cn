---
title: "如何：实现动态分区"
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
helpviewer_keywords: tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1e5dc93997918e0f7da29fa1f94c434a556f19f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="f1a07-102">如何：实现动态分区</span><span class="sxs-lookup"><span data-stu-id="f1a07-102">How to: Implement Dynamic Partitions</span></span>
<span data-ttu-id="f1a07-103">下面的示例演示如何实现一个自定义<xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType>，实现动态分区，并可以从特定重载使用<xref:System.Threading.Tasks.Parallel.ForEach%2A>和从 PLINQ。</span><span class="sxs-lookup"><span data-stu-id="f1a07-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1a07-104">示例</span><span class="sxs-lookup"><span data-stu-id="f1a07-104">Example</span></span>  
 <span data-ttu-id="f1a07-105">每次分区调用<xref:System.Collections.IEnumerator.MoveNext%2A>对枚举器，枚举数为分区提供一个列表元素。</span><span class="sxs-lookup"><span data-stu-id="f1a07-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="f1a07-106">在 PLINQ 和<xref:System.Threading.Tasks.Parallel.ForEach%2A>，分区是<xref:System.Threading.Tasks.Task>实例。</span><span class="sxs-lookup"><span data-stu-id="f1a07-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="f1a07-107">请求的多个线程同时发生，因为对当前索引的访问被同步。</span><span class="sxs-lookup"><span data-stu-id="f1a07-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 <span data-ttu-id="f1a07-108">这是一个示例的分区，其中包含一个元素的每个区块的块区。</span><span class="sxs-lookup"><span data-stu-id="f1a07-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="f1a07-109">通过一次提供多个元素，你可以通过锁减少争用并理论上实现更快的性能。</span><span class="sxs-lookup"><span data-stu-id="f1a07-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="f1a07-110">但是，在某些时候，更大的区块可能需要其他负载平衡的逻辑才能使所有线程处于繁忙状态，直到完成所有工作。</span><span class="sxs-lookup"><span data-stu-id="f1a07-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a07-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1a07-111">See Also</span></span>  
 [<span data-ttu-id="f1a07-112">PLINQ 和 TPL 的自定义分区程序</span><span class="sxs-lookup"><span data-stu-id="f1a07-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [<span data-ttu-id="f1a07-113">如何：实现静态分区程序</span><span class="sxs-lookup"><span data-stu-id="f1a07-113">How to: Implement a Partitioner for Static Partitioning</span></span>](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
