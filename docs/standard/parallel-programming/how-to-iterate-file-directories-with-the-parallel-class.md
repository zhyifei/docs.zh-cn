---
title: "如何：使用并行类循环访问文件目录"
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
helpviewer_keywords: parallel loops, how to iterate directories
ms.assetid: 555e9f48-f53d-4774-9bcf-3e965c732ec5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c21aadf70eaccafc8c8ec9c4efefff1c66abc6b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-iterate-file-directories-with-the-parallel-class"></a>如何：使用并行类循环访问文件目录
在许多情况下，文件迭代是可以轻松地并行化操作。 主题[如何： 使用 PLINQ 循环文件目录](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md)演示很多情况下执行此任务的最简单方法。 但是，当你的代码具有许多类型的访问的文件系统时可能会出现的异常处理，则可能会出现复杂性。 下面的示例演示问题的一种方法。 它使用基于堆栈的迭代来遍历所有文件和文件夹下指定的目录，使你的代码以捕获和处理各种异常。 当然，处理异常的方法是由您决定。  
  
## <a name="example"></a>示例  
 下面的示例按顺序循环访问目录，但会并行处理文件。 当你具有大型文件目录比率时，这可能是最好的方法。 还有可能并行化目录迭代中，并按顺序访问每个文件。 它可能不是高效以并行化这两个循环，除非特别面向具有大量的处理器的计算机。 但是，如下所示所有情况下，你应测试你的应用程序进行全面以确定最佳的方法。  
  
 [!code-csharp[TPL_Parallel#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_file.cs#08)]
 [!code-vb[TPL_Parallel#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/fileiteration08.vb#08)]  
  
 在此示例中，以同步方式执行文件 I/O。 在处理大型文件或慢速网络连接，它可能更可取的方法以异步方式访问的文件。 你可以使用并行迭代组合异步 I/O 技术。 有关详细信息，请参阅 [TPL 和传统 .NET Framework 异步编程](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)。  
  
 此示例使用局部 `fileCount` 变量维护已处理的总文件数的计数。 由于多个任务可能并发访问此变量，可以调用 <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType> 方法来同步对它的访问。  
  
 请注意，如果主引发异常的线程，通过启动的线程<xref:System.Threading.Tasks.Parallel.ForEach%2A>方法可能会继续运行。 若要停止这些线程，你可以在异常处理程序，设置布尔变量，并检查它并行循环的每个迭代上的值。 如果值指示已引发异常，则使用<xref:System.Threading.Tasks.ParallelLoopState>变量以停止或中断循环。 有关详细信息，请参阅[如何： 停止或中断 Parallel.For 循环](http://msdn.microsoft.com/en-us/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e)。  
  
## <a name="see-also"></a>另请参阅  
 [数据并行](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
