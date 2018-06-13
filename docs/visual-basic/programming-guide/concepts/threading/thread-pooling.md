---
title: 线程池 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
ms.openlocfilehash: 445c1c70cc1371ef918f32046e0c30ae2a473da2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647828"
---
# <a name="thread-pooling-visual-basic"></a>线程池 (Visual Basic)
线程池是可用于在后台执行多种任务的线程集合。 (请参阅[线程处理 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/threading/index.md)有关背景信息。)这使主线程可以自由地异步执行其他任务。  
  
 线程池通常用于服务器应用程序。 每个传入请求都将分配给线程池中的一个线程，因此可以异步处理请求，而不会占用主线程，也不会延迟后续请求的处理。  
  
 一旦池中的线程完成任务，它将返回到等待线程队列中，等待被重复使用。 通过这种重复使用，应用程序可以避免产生为每个任务创建新线程的开销。  
  
 线程池通常具有最大线程数限制。 如果所有线程处于忙碌状态，则额外的任务将放入队列中，直到有线程可用时才能够得到处理。  
  
 你可以实现自己的线程池，但是通过 <xref:System.Threading.ThreadPool> 类使用 .NET Framework 提供的线程池更容易。  
  
 对于线程池，你调用<xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType>想要运行，有关该过程的委托的方法和 Visual Basic 创建线程并运行你的过程。  
  
## <a name="thread-pooling-example"></a>线程池示例  
 下面的示例演示如何使用线程池来启动若干任务。  
  
```vb  
Public Sub DoWork()  
    ' Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf SomeLongTask))  
    ' Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf AnotherLongTask))  
End Sub  
Private Sub SomeLongTask(ByVal state As Object)  
    ' Insert code to perform a long task.  
End Sub  
Private Sub AnotherLongTask(ByVal state As Object)  
    ' Insert code to perform another long task.  
End Sub  
```  
  
 线程池的一个优点是可以将状态对象中的自变量传递到任务过程。 如果要调用的过程需要多个自变量，可将结构或类的实例强制转换为 `Object` 数据类型。  
  
## <a name="thread-pool-parameters-and-return-values"></a>线程池参数和返回值  
 不能直接从线程池线程返回值。 不允许使用通过函数调用来返回值的标准方法，因为 `Sub` 过程是唯一一种可以排队到线程池的过程。 一种方法你可以提供参数和返回值是通过换行的参数，返回值和方法在包装类中所述[参数和多线程过程 (Visual Basic 中) 的返回值](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)。  
  
 一种提供参数和返回值的更简单方法是使用 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 方法的可选 `ByVal` 状态对象变量。 如果使用此变量来传递对类实例的引用，则该实例的成员可以由线程池线程修改，并用作返回值。  
  
 最初，可以修改由值传递的变量所引用的对象可能并不明显。 由于只有对象引用由值传递，因此可以执行此操作。 当对由对象引用所引用的对象的成员进行更改时，这些更改将应用于实际的类实例。  
  
 不能使用结构在状态对象内部返回值。 由于结构属于值类型，异步进程所做的更改不会更改原始结构的成员。 如果不需要返回值，可以使用结构来提供参数。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [如何：使用线程池 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 [线程 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [多线程应用 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [线程同步 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)
