---
title: "如何：实现静态分区的分区程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b28ff0bb8436fefc4956918889435e258ae98b12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a><span data-ttu-id="18a37-102">如何：实现静态分区的分区程序</span><span class="sxs-lookup"><span data-stu-id="18a37-102">How to: Implement a Partitioner for Static Partitioning</span></span>
<span data-ttu-id="18a37-103">下面的示例演示实现简单的自定义分区程序执行静态分区的 PLINQ 的一种方法。</span><span class="sxs-lookup"><span data-stu-id="18a37-103">The following example shows one way to implement a simple custom partitioner for PLINQ that performs static partitioning.</span></span> <span data-ttu-id="18a37-104">由于分区程序不支持动态分区，不可以从<xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="18a37-104">Because the partitioner does not support dynamic partitions, it is not consumable from <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="18a37-105">对于为其每个元素需要越来越多的处理时间的数据源，此特定的分区程序可能通过默认范围分区程序提供的加速。</span><span class="sxs-lookup"><span data-stu-id="18a37-105">This particular partitioner might provide speedup over the default range partitioner for data sources for which each element requires an increasing amount of processing time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18a37-106">示例</span><span class="sxs-lookup"><span data-stu-id="18a37-106">Example</span></span>  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 <span data-ttu-id="18a37-107">在此示例中分区都基于假设每个元素的处理时间的线性增长。</span><span class="sxs-lookup"><span data-stu-id="18a37-107">The partitions in this example are based on the assumption of a linear increase in processing time for each element.</span></span> <span data-ttu-id="18a37-108">在现实世界中，它可能很难预测以这种方式的处理时间。</span><span class="sxs-lookup"><span data-stu-id="18a37-108">In the real world, it might be difficult to predict processing times in this way.</span></span> <span data-ttu-id="18a37-109">如果您正在使用的特定数据源静态分区程序，你可以优化的源分区的公式、 添加负载平衡的逻辑，或使用分区方法中所示的区块[如何： 实现动态分区](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="18a37-109">If you are using a static partitioner with a specific data source, you can optimize the partitioning formula for the source, add load-balancing logic, or use a chunk partitioning approach as demonstrated in [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a37-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18a37-110">See Also</span></span>  
 [<span data-ttu-id="18a37-111">PLINQ 和 TPL 的自定义分区程序</span><span class="sxs-lookup"><span data-stu-id="18a37-111">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
