---
title: 参数和返回值的多线程过程 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
ms.openlocfilehash: 545da3e89d44c29c67784b5f01812d87350030c6
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874606"
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a>参数和返回值的多线程过程 (Visual Basic)
在多线程应用程序中提供和返回值是很复杂的，因为必须将对某个过程的引用传递给线程类的构造函数，该过程不带参数也不返回值。 下面几节介绍一些提供参数和从不同线程上的过程返回值的简单方法。  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a>为多线程过程提供参数  
 为多线程方法调用提供参数的最好办法是将目标方法包装在类中，并为该类定义字段，这些字段将用作新线程的参数。 这种方法的优点是，任何时候想要启动新线程，都可以创建类的新实例，该实例带有自身的参数。 例如，假设有一个计算三角形面积的函数，如以下代码所示：  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 可以编写一个包装 `CalcArea` 函数的类，并创建一些字段来存储输入参数，如以下所示：  
  
```vb  
Class AreaClass  
    Public Base As Double  
    Public Height As Double  
    Public Area As Double  
    Sub CalcArea()  
        Area = 0.5 * Base * Height  
        MessageBox.Show("The area is: " & Area.ToString)  
    End Sub  
End Class  
```  
  
 若要使用 `AreaClass`，可以创建一个 `AreaClass` 对象并设置 `Base` 和 `Height` 属性，如以下代码所示：  
  
```vb  
Protected Sub TestArea()  
    Dim AreaObject As New AreaClass  
    Dim Thread As New System.Threading.Thread(  
                        AddressOf AreaObject.CalcArea)  
    AreaObject.Base = 30  
    AreaObject.Height = 40  
    Thread.Start()  
End Sub  
```  
  
 请注意，调用 `CalcArea` 方法后，`TestArea` 过程并不检查 `Area` 字段的值。 `CalcArea` 运行于单独的线程，因此，如果在调用 `Thread.Start` 后立即检查，则无法确定 `Area` 字段已被设置。 下一节讨论从多线程过程返回值的更好方法。  
  
## <a name="returning-values-from-multithreaded-procedures"></a>从多线程过程返回值  
 由于这些过程不能为函数也不能使用 `ByRef` 参数，因而从运行于不同线程的过程返回值是很复杂的。 返回值最简单的方法是：使用 <xref:System.ComponentModel.BackgroundWorker> 组件来管理线程，在任务完成时引发事件，然后用事件处理程序处理结果。  
  
 下面的示例通过从运行于单独线程的某过程引发一个事件来返回值：  
  
```vb  
Private Class AreaClass2  
    Public Base As Double  
    Public Height As Double  
    Function CalcArea() As Double  
        ' Calculate the area of a triangle.  
        Return 0.5 * Base * Height  
    End Function  
End Class  
  
Private WithEvents BackgroundWorker1 As New System.ComponentModel.BackgroundWorker  
  
Private Sub TestArea2()  
    Dim AreaObject2 As New AreaClass2  
    AreaObject2.Base = 30  
    AreaObject2.Height = 40  
  
    ' Start the asynchronous operation.  
    BackgroundWorker1.RunWorkerAsync(AreaObject2)  
End Sub  
  
' This method runs on the background thread when it starts.  
Private Sub BackgroundWorker1_DoWork(  
    ByVal sender As Object,   
    ByVal e As System.ComponentModel.DoWorkEventArgs  
    ) Handles BackgroundWorker1.DoWork  
  
    Dim AreaObject2 As AreaClass2 = CType(e.Argument, AreaClass2)  
    ' Return the value through the Result property.  
    e.Result = AreaObject2.CalcArea()  
End Sub  
  
' This method runs on the main thread when the background thread finishes.  
Private Sub BackgroundWorker1_RunWorkerCompleted(  
    ByVal sender As Object,  
    ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs  
    ) Handles BackgroundWorker1.RunWorkerCompleted  
  
    ' Access the result through the Result property.  
    Dim Area As Double = CDbl(e.Result)  
    MessageBox.Show("The area is: " & Area.ToString)  
End Sub  
```  
  
 可以通过使用 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 方法的可选 `ByVal` 状态对象变量来向线程池线程提供参数并返回值。 线程计时器线程也支持将状态对象用于此目的。 有关线程池和线程计时器的信息，请参阅[线程池 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[线程池](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701)并[计时器](../../../../standard/threading/timers.md)。  
  
## <a name="see-also"></a>请参阅  
 [演练：利用 BackgroundWorker 组件进行多线程处理 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [线程池 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [线程同步 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [多线程应用 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [委托](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [组件中的多线程处理](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
