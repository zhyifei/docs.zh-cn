---
title: "互锁操作"
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
- cpp
helpviewer_keywords:
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 122058b7e826e27fe6c60c5b07610f7c63e64f78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="interlocked-operations"></a>互锁操作
<xref:System.Threading.Interlocked>类提供同步访问多个线程共享的变量的方法。 如果该变量位于共享内存中，则不同进程的线程都可以使用此机制。 互锁操作是原子的 - 即整个操作是不能由相同变量上的另一个互锁操作中断的单元。 这在抢占式多线程处理操作系统中非常重要，在此类操作系统中，可在从内存地址加载值之后但有机会更改和存储该值之前将线程挂起。  
  
 <xref:System.Threading.Interlocked>类提供了以下操作：  
  
-   在.NET Framework 2.0 版中，<xref:System.Threading.Interlocked.Add%2A>方法将一个整数值添加到一个变量并返回该变量的新值。  
  
-   在.NET Framework 2.0 版中，<xref:System.Threading.Interlocked.Read%2A>方法读取一个 64 位整数值作为原子操作。 这在 32 位操作系统上很有用，在此类操作系统上，读取一个 64 位整数通常不是原子操作。  
  
-   <xref:System.Threading.Interlocked.Increment%2A>和<xref:System.Threading.Interlocked.Decrement%2A>方法递增或递减的变量并返回的结果值。  
  
-   <xref:System.Threading.Interlocked.Exchange%2A>方法在指定变量中，返回该值并将它替换为新值执行原子交换的值。 在 .NET Framework 2.0 版中，可使用此方法的泛型重载在任何引用类型的变量上执行此交换。 请参阅<xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>。  
  
-   <xref:System.Threading.Interlocked.CompareExchange%2A>方法还交换两个值，但取决于比较的结果。 在 .NET Framework 2.0 版中，可使用此方法的泛型重载在任何引用类型的变量上执行此交换。 请参阅<xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>。  
  
 在现代处理器中的方法<xref:System.Threading.Interlocked>类通常可以通过一条指令。 因此，它们提供性能非常高的同步，并且可用于生成更高级的同步机制，例如自旋锁。  
  
 有关示例，使用<xref:System.Threading.Monitor>和<xref:System.Threading.Interlocked>类结合使用，请参阅[监视器](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)。  
  
## <a name="compareexchange-example"></a>CompareExchange示例  
 <xref:System.Threading.Interlocked.CompareExchange%2A>方法可以用于保护比简单递增和递减更复杂的计算。 以下示例演示一个线程安全的方法，该方法向存储为浮点数的累计值执行加运算。 (为整数，<xref:System.Threading.Interlocked.Add%2A>方法是更简单的解决方案。)有关完整的代码示例，请参阅的重载<xref:System.Threading.Interlocked.CompareExchange%2A>它们采用单精度和双精度浮点自变量 (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29>和<xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>)。  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a>Exchange 和 CompareExchange 的非类型化重载  
 <xref:System.Threading.Interlocked.Exchange%2A>和<xref:System.Threading.Interlocked.CompareExchange%2A>方法具有采用的类型自变量的重载<xref:System.Object>。 这些重载的第一个参数是`ref Object`(`ByRef … As Object`在 Visual Basic 中)，和类型安全要求传递给此参数以严格类型化为变量<xref:System.Object>; 只需不能强制转换为类型的第一个参数<xref:System.Object>调用这些方法时。  
  
> [!NOTE]
>  在.NET Framework 2.0 版中，使用的泛型重载<xref:System.Threading.Interlocked.Exchange%2A>和<xref:System.Threading.Interlocked.CompareExchange%2A>方法来交换强类型化变量。  
  
 以下代码示例演示只能设置一次的 `ClassA` 类型的属性，正如它在 .NET Framework 1.0 或 1.1 版中实现的那样。  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.Monitor>  
 [线程处理](../../../docs/standard/threading/index.md)  
 [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)
