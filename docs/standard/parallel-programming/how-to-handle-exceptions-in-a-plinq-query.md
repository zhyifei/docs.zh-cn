---
title: "如何：处理 PLINQ 查询中的异常"
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
helpviewer_keywords: PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 209e0c1bf89f231d03647ae4351279bfdb172e68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a>如何：处理 PLINQ 查询中的异常
本主题中的第一个示例演示如何处理<xref:System.AggregateException?displayProperty=nameWithType>，可能引发从 PLINQ 查询执行时。 第二个示例显示如何将 try-catch 块中的代理，而到会引发该异常尽可能地接近。 在这种方式，你可以捕获它们就会立即发生，并且可能继续执行查询。 如果允许异常向上冒泡回到联接线程，则查询也许可以在引发异常后继续处理一些项。  
  
 在某些情况下 PLINQ 回退到顺序执行，并发生异常时，异常可能比较传播直接，因此不包装在<xref:System.AggregateException>。 此外， <xref:System.Threading.ThreadAbortException>s 会始终直接传播。  
  
> [!NOTE]
>  Visual Studio 启用"仅我的代码"后，将引发异常的行中断并显示一条显示"未处理异常由用户代码。"的错误消息 此错误是良性的。 可以按 F5 继续运行，并请参阅下面示例中所示的异常处理行为。 若要阻止 Visual Studio 的第一个错误时中断，只需取消选中下的"仅我的代码"复选框**工具、 选项、 调试、 常规**。  
>   
>  本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。 有关加速的详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。  
  
## <a name="example"></a>示例  
 此示例演示如何将在执行查询以捕获所有的代码周围 try catch 块<xref:System.AggregateException?displayProperty=nameWithType>引发的 s。  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 在此示例中，查询无法继续后，将引发异常。 应用程序代码捕获异常时，PLINQ 已查询已停止所有线程上。  
  
## <a name="example"></a>示例  
 下面的示例演示如何将 try catch 块放在一个委托，以使其可以捕获异常并继续执行查询。  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## <a name="compiling-the-code"></a>编译代码  
  
-   若要编译并运行这些示例，将它们复制到的 PLINQ 数据示例示例中，并从 Main 调用方法。  
  
## <a name="robust-programming"></a>可靠编程  
 除非你知道如何处理它，以便不会损坏你的程序的状态，则不要捕捉异常。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Linq.ParallelEnumerable>  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
