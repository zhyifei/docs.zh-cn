---
title: "如何：编写简单的 Parallel.ForEach 循环"
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
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16d8cd3c3c01c2f9d83786e78f0eb1c45a38a49b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>如何：编写简单的 Parallel.ForEach 循环
此示例演示如何使用<xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>循环，以启用对任何数据并行<xref:System.Collections.IEnumerable?displayProperty=nameWithType>或<xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>数据源。  
  
> [!NOTE]
>  本文档使用 lambda 表达式在 PLINQ 中定义委托。 如果不熟悉 C# 或 Visual Basic 中的 lambda 表达式，请参阅 [PLINQ 和 TPL 中的 Lambda 表达式](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 A<xref:System.Threading.Tasks.Parallel.ForEach%2A>循环的工作原理类似<xref:System.Threading.Tasks.Parallel.For%2A>循环。 对源集合进行分区，并基于系统环境的多个线程上计划工作。 在系统上的处理器越多，越快，并行方法运行。 对于某些源集合，一个顺序循环可能更快，具体取决于源和正在执行的工作类型的大小。 有关性能的详细信息，请参阅[数据并行和任务并行中的潜在缺陷](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)  
  
 有关并行循环的详细信息，请参阅[如何： 编写简单的 Parallel.For 循环](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)。  
  
 若要使用<xref:System.Threading.Tasks.Parallel.ForEach%2A>对于非泛型集合，你可以使用<xref:System.Linq.Enumerable.Cast%2A>扩展方法将集合转换为泛型集合，如下面的示例中所示：  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 此外可以使用并行 LINQ (PLINQ) 来并行执行的处理<xref:System.Collections.Generic.IEnumerable%601>数据源。 PLINQ，可使用声明性查询语法表示的循环行为。 有关详细信息，请参阅[并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)。  
  
## <a name="compiling-the-code"></a>编译代码  
  
-   复制并粘贴到此代码[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]2010年控制台应用程序项目。  
  
-   添加对 System.Drawing.dll 的引用  
  
-   按 F5  
  
## <a name="see-also"></a>另请参阅  
 [数据并行](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [并行编程](../../../docs/standard/parallel-programming/index.md)  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
