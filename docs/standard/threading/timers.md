---
title: 计时器
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 478484651bf839f842148f0b4164c9387db3b98a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="timers"></a>计时器
计时器是一种轻型对象，可便于指定要在指定时间调用的委托。 线程池中的线程执行等待操作。  
  
 <xref:System.Threading.Timer?displayProperty=nameWithType> 类使用起来非常简单。 创建 Timer 的同时，向回调方法传递 <xref:System.Threading.TimerCallback> 委托、表示传递给回调的状态的对象、初始抛出时间和表示回调调用时间间隔的时间。 若要取消挂起的计时器，请调用 Timer.Dispose 函数。  
  
> [!NOTE]
>  还有其他两个计时器类。 <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> 类是与可视化设计器结合使用的控件，适用于用户界面上下文，在用户界面线程上抛出事件。 由于 <xref:System.Timers.Timer?displayProperty=nameWithType> 类派生自 <xref:System.ComponentModel.Component>，因此可以与可视化设计器结合使用；它还会抛出事件，但是在 <xref:System.Threading.ThreadPool> 线程上抛出这些事件。 <xref:System.Threading.Timer?displayProperty=nameWithType> 类在 <xref:System.Threading.ThreadPool> 线程上执行回调，完全不使用事件模型。 它还向回调方法提供状态对象，而其他计时器则不会。 它是极度轻型类。  
  
 下面的代码示例启动计时器，此计时器在一秒（1000 毫秒）后启动，且每秒都会计时，直到按下 Enter 键。 为了确保计时器在运行的同时不受垃圾回收影响，包含对计时器的引用的变量是类级别字段。 若要详细了解积极垃圾回收，请参阅 <xref:System.GC.KeepAlive%2A>。  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Threading.Timer>  
 [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)
