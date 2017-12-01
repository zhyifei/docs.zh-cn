---
title: "如何：取消 PLINQ 查询"
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
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8031758462df45c030b8b75a3507f1bfb44bfd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-plinq-query"></a>如何：取消 PLINQ 查询
下面的示例演示两种方法取消 PLINQ 查询。 第一个示例演示如何取消查询主要组成数据遍历。 第二个示例演示如何取消查询包含一个用户函数，则计算开销很大。  
  
> [!NOTE]
>  Visual Studio 启用"仅我的代码"后，将引发异常的行中断并显示一条显示"未处理异常由用户代码。"的错误消息 此错误是良性的。 可以按 F5 继续运行，并请参阅下面示例中所示的异常处理行为。 若要阻止 Visual Studio 的第一个错误时中断，只需取消选中下的"仅我的代码"复选框**工具、 选项、 调试、 常规**。  
>   
>  本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。 有关加速的详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 PLINQ framework 不会回滚单个<xref:System.OperationCanceledException>到<xref:System.AggregateException?displayProperty=nameWithType>;<xref:System.OperationCanceledException>必须在单独的 catch 块中处理。 如果一个或多个用户委托引发 OperationCanceledException(externalCT) (通过使用外部<xref:System.Threading.CancellationToken?displayProperty=nameWithType>) 但没有其他异常，并且查询被定义为`AsParallel().WithCancellation(externalCT)`，然后 PLINQ 将发出单个<xref:System.OperationCanceledException>(externalCT) 而非<xref:System.AggregateException?displayProperty=nameWithType>. 但是，如果一个用户委托引发<xref:System.OperationCanceledException>，并且另一个委托引发其他异常类型，则这两种异常的事务将回滚到<xref:System.AggregateException>。  
  
 有关取消的一般性指导原则是，如下所示：  
  
1.  如果你执行用户委托取消您应通知外部 PLINQ<xref:System.Threading.CancellationToken>并引发<xref:System.OperationCanceledException>(externalCT)。  
  
2.  如果取消，并且没有其他引发异常，则您应处理<xref:System.OperationCanceledException>而非<xref:System.AggregateException>。  
  
## <a name="example"></a>示例  
 下面的示例演示如何处理取消时在用户代码中有计算开销很大的函数。  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 在处理用户代码中的取消操作时，则不需要使用<xref:System.Linq.ParallelEnumerable.WithCancellation%2A>查询定义中。 但是，我们建议你这样做，因为<xref:System.Linq.ParallelEnumerable.WithCancellation%2A>有对查询性能影响，并且它使由查询运算符和你的用户代码处理取消操作。  
  
 为了确保系统的响应能力，我们建议你检查解决每毫秒; 一次取消但是，最多 10 毫秒任意一段被视为可接受。 此频率不应在代码的性能产生负面影响。  
  
 当释放枚举器时，例如代码中断的 （对于 Visual Basic 中的每个） 的 foreach 循环中循环访问查询结果外，则查询被取消时，但不会引发异常。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Linq.ParallelEnumerable>  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [托管线程中的取消](../../../docs/standard/threading/cancellation-in-managed-threads.md)
