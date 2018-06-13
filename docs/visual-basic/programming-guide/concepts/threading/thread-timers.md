---
title: 线程计时器 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 809cba93-cc93-4e21-afda-f299f9a39818
ms.openlocfilehash: 019b8372be63b9a9fdbcee134834a34f6bef2b74
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646886"
---
# <a name="thread-timers-visual-basic"></a>线程计时器 (Visual Basic)
<xref:System.Threading.Timer?displayProperty=nameWithType> 类对于定期在单独的线程上运行任务很有用。 例如，可以使用线程计时器来检查数据库的状态和完整性，或备份关键文件。  
  
## <a name="thread-timer-example"></a>线程计时器示例  
 以下示例每两秒启动一个任务，并使用标志启动用于停止计时器的 <xref:System.IDisposable.Dispose%2A> 方法。 此示例将状态发送到输出窗口。  
  
```vb  
Private Class StateObjClass  
    ' Used to hold parameters for calls to TimerTask.  
    Public SomeValue As Integer  
    Public TimerReference As System.Threading.Timer  
    Public TimerCanceled As Boolean  
End Class  
  
Public Sub RunTimer()  
    Dim StateObj As New StateObjClass  
    StateObj.TimerCanceled = False  
    StateObj.SomeValue = 1  
    Dim TimerDelegate As New System.Threading.TimerCallback(AddressOf TimerTask)  
    ' Create a timer that calls a procedure every 2 seconds.  
    ' Note: There is no Start method; the timer starts running as soon as   
    ' the instance is created.  
    Dim TimerItem As New System.Threading.Timer(TimerDelegate, StateObj,  
                                                2000, 2000)  
    ' Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem  
  
    ' Run for ten loops.  
    While StateObj.SomeValue < 10  
        ' Wait one second.  
        System.Threading.Thread.Sleep(1000)  
    End While  
  
    ' Request Dispose of the timer object.  
    StateObj.TimerCanceled = True  
End Sub  
  
Private Sub TimerTask(ByVal StateObj As Object)  
    Dim State As StateObjClass = CType(StateObj, StateObjClass)  
    ' Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(State.SomeValue)  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " & Now.ToString)  
    If State.TimerCanceled Then  
        ' Dispose Requested.  
        State.TimerReference.Dispose()  
        System.Diagnostics.Debug.WriteLine("Done  " & Now)  
    End If  
End Sub  
```  
  
 当 <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> 对象不可用时（例如开发控制台应用程序时），线程计时器特别有用。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Threading>  
 [多线程应用 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)
