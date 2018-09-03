---
title: 互锁操作
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 361e618578e836e10cf8655f027bed42eac7affd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393134"
---
# <a name="interlocked-operations"></a>互锁操作
<xref:System.Threading.Interlocked> 类中的方法可用于同步对多个线程共享的变量的访问。 如果该变量位于共享内存中，则不同进程的线程都可以使用此机制。 互锁操作是原子的 - 即整个操作是不能由相同变量上的另一个互锁操作中断的单元。 这在抢占式多线程处理操作系统中非常重要，在此类操作系统中，可在从内存地址加载值之后但有机会更改和存储该值之前将线程挂起。  
  
 <xref:System.Threading.Interlocked> 类提供以下操作：  
  
-   在 .NET Framework 版本 2.0 中，<xref:System.Threading.Interlocked.Add%2A> 方法向变量添加整数值，并返回此变量的新值。  
  
-   在 .NET Framework 版本 2.0 中，<xref:System.Threading.Interlocked.Read%2A> 方法以原子操作的形式读取 64 位整数值。 这在 32 位操作系统上很有用，在此类操作系统上，读取一个 64 位整数通常不是原子操作。  
  
-   <xref:System.Threading.Interlocked.Increment%2A> 和 <xref:System.Threading.Interlocked.Decrement%2A> 方法递增或递减变量，并返回生成值。  
  
-   <xref:System.Threading.Interlocked.Exchange%2A> 方法在指定变量中以原子操作的形式交换值，同时返回此值并将它替换为新值。 在 .NET Framework 2.0 版中，可使用此方法的泛型重载在任何引用类型的变量上执行此交换。 请参阅 <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>。  
  
-   <xref:System.Threading.Interlocked.CompareExchange%2A> 方法也交换两个值，但具体视比较结果而定。 在 .NET Framework 2.0 版中，可使用此方法的泛型重载在任何引用类型的变量上执行此交换。 请参阅 <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>。  
  
 在新式处理器中，通常使用一个指令即可实现 <xref:System.Threading.Interlocked> 类的方法。 因此，它们提供性能非常高的同步，并且可用于生成更高级的同步机制，例如自旋锁。  
  
 有关组合使用 <xref:System.Threading.Monitor> 和 <xref:System.Threading.Interlocked> 类的示例，请参阅[监视器](https://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)。  
  
## <a name="compareexchange-example"></a>CompareExchange示例  
 <xref:System.Threading.Interlocked.CompareExchange%2A> 方法可用于保护比简单的递增和递减更为复杂的计算。 以下示例演示一个线程安全的方法，该方法向存储为浮点数的累计值执行加运算。 （对于整数，<xref:System.Threading.Interlocked.Add%2A> 方法是更简单的解决方案。）有关完整的代码示例，请参阅需要使用单精度和双精度浮点参数的 <xref:System.Threading.Interlocked.CompareExchange%2A> 重载（<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> 和 <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>）。  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a>Exchange 和 CompareExchange 的非类型化重载  
 <xref:System.Threading.Interlocked.Exchange%2A> 和 <xref:System.Threading.Interlocked.CompareExchange%2A> 方法包含需要使用 <xref:System.Object> 类型参数的重载。 其中每个重载的第一个参数都是 `ref Object`（Visual Basic 中的 `ByRef … As Object`），根据类型安全性要求，必须将传递给此参数的变量严格类型化为 <xref:System.Object>；不能在调用这些方法时，直接将第一个参数强制转换为 <xref:System.Object> 类型。  
  
> [!NOTE]
>  在 .NET Framework 版本 2.0 中，使用 <xref:System.Threading.Interlocked.Exchange%2A> 和 <xref:System.Threading.Interlocked.CompareExchange%2A> 方法的泛型重载来交换强类型变量。  
  
 以下代码示例演示只能设置一次的 `ClassA` 类型的属性，正如它在 .NET Framework 1.0 或 1.1 版中实现的那样。  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.Monitor>  
 [线程处理](../../../docs/standard/threading/index.md)  
 [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)
