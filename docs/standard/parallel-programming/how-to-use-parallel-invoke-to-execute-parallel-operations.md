---
title: 如何：使用 Parallel.Invoke 来执行并行操作
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ad4b5e005ddd7bbd598a9da3032574eb2ba7dd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>如何：使用 Parallel.Invoke 来执行并行操作
此示例演示如何通过使用任务并行库中的 <xref:System.Threading.Tasks.Parallel.Invoke%2A> 并行操作。 共享的数据源上执行三个操作。 因为操作均不修改源，所以可以直接的方式并行执行。  
  
> [!NOTE]
>  本文档使用 lambda 表达式在 TPL 中定义委托。 如果不熟悉 C# 或 Visual Basic 中的 lambda 表达式，请参阅 [PLINQ 和 TPL 中的 Lambda 表达式](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
 [!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]  
  
 请注意，借助 <xref:System.Threading.Tasks.Parallel.Invoke%2A>，你只需表达想同时运行的操作，运行时会处理所有线程计划详细信息（包括自动缩放至主计算机上的内核数）。  
  
 此示例并行操作，而非数据。 此外，可使用 PLINQ 并行 LINQ 查询，并按顺序运行查询。 或者，可使用 PLINQ 并行数据。 另一个选项是并行查询和任务。 尽管生成的开销在处理器相对较少的主机计算机上可能会降低性能，但在处理器较多的计算机上可进行更好的缩放。  
  
## <a name="compiling-the-code"></a>编译代码  
  
-   将完整示例复制和粘贴到 Microsoft Visual Studio 2010 项目，并按 F5 键。  
  
## <a name="see-also"></a>请参阅  
 [并行编程](../../../docs/standard/parallel-programming/index.md)  
 [如何：取消任务及其子级](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
