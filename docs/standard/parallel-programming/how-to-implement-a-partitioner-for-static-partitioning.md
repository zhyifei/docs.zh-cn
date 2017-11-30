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
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a>如何：实现静态分区的分区程序
下面的示例演示实现简单的自定义分区程序执行静态分区的 PLINQ 的一种方法。 由于分区程序不支持动态分区，不可以从<xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>。 对于为其每个元素需要越来越多的处理时间的数据源，此特定的分区程序可能通过默认范围分区程序提供的加速。  
  
## <a name="example"></a>示例  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 在此示例中分区都基于假设每个元素的处理时间的线性增长。 在现实世界中，它可能很难预测以这种方式的处理时间。 如果您正在使用的特定数据源静态分区程序，你可以优化的源分区的公式、 添加负载平衡的逻辑，或使用分区方法中所示的区块[如何： 实现动态分区](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
## <a name="see-also"></a>另请参阅  
 [PLINQ 和 TPL 的自定义分区程序](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
