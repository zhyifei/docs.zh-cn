---
title: 线程计时器 (C#)
ms.date: 07/20/2015
ms.assetid: 52ed71e8-4fd9-43a4-ae40-04cce7cff23f
ms.openlocfilehash: c2be9fef0b3f6f3db7ae8c9a519ece0cb64b6f49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33323438"
---
# <a name="thread-timers-c"></a>线程计时器 (C#)
<xref:System.Threading.Timer?displayProperty=nameWithType> 类对于定期在单独的线程上运行任务很有用。 例如，可以使用线程计时器来检查数据库的状态和完整性，或备份关键文件。  
  
## <a name="thread-timer-example"></a>线程计时器示例  
 以下示例每两秒启动一个任务，并使用标志启动用于停止计时器的 <xref:System.IDisposable.Dispose%2A> 方法。 此示例将状态发送到输出窗口。  
  
```csharp  
private class StateObjClass  
{  
    // Used to hold parameters for calls to TimerTask.  
    public int SomeValue;  
    public System.Threading.Timer TimerReference;  
    public bool TimerCanceled;  
}  
  
public void RunTimer()  
{  
    StateObjClass StateObj = new StateObjClass();  
    StateObj.TimerCanceled = false;  
    StateObj.SomeValue = 1;  
    System.Threading.TimerCallback TimerDelegate =  
        new System.Threading.TimerCallback(TimerTask);  
  
    // Create a timer that calls a procedure every 2 seconds.  
    // Note: There is no Start method; the timer starts running as soon as   
    // the instance is created.  
    System.Threading.Timer TimerItem =  
        new System.Threading.Timer(TimerDelegate, StateObj, 2000, 2000);  
  
    // Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem;    
  
    // Run for ten loops.  
    while (StateObj.SomeValue < 10)   
    {  
        // Wait one second.  
        System.Threading.Thread.Sleep(1000);    
    }  
  
    // Request Dispose of the timer object.  
    StateObj.TimerCanceled = true;    
}  
  
private void TimerTask(object StateObj)  
{  
    StateObjClass State = (StateObjClass)StateObj;  
    // Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(ref State.SomeValue);  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " + DateTime.Now.ToString());  
    if (State.TimerCanceled)      
    // Dispose Requested.  
    {  
        State.TimerReference.Dispose();  
        System.Diagnostics.Debug.WriteLine("Done  " + DateTime.Now.ToString());  
    }  
}  
```  
  
 当 <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> 对象不可用时（例如开发控制台应用程序时），线程计时器特别有用。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Threading>  
 [多线程应用程序 (C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)
