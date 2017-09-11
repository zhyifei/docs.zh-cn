---
title: "参数和返回值为多线程过程 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6d1eb53454b6e0d964be15df2e320ce189e7d875
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a><span data-ttu-id="24f03-102">参数和多线程过程 (Visual Basic 中) 的返回值</span><span class="sxs-lookup"><span data-stu-id="24f03-102">Parameters and Return Values for Multithreaded Procedures (Visual Basic)</span></span>
<span data-ttu-id="24f03-103">提供和多线程应用程序中返回值是很复杂，因为线程类的构造函数必须传递一个过程，不采用任何参数并不返回值的引用。</span><span class="sxs-lookup"><span data-stu-id="24f03-103">Supplying and returning values in a multithreaded application is complicated because the constructor for the thread class must be passed a reference to a procedure that takes no arguments and returns no value.</span></span> <span data-ttu-id="24f03-104">以下部分说明一些简单的方法来提供参数，以在单独的线程从过程返回的值。</span><span class="sxs-lookup"><span data-stu-id="24f03-104">The following sections show some simple ways to supply parameters and return values from procedures on separate threads.</span></span>  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a><span data-ttu-id="24f03-105">提供多线程过程的参数</span><span class="sxs-lookup"><span data-stu-id="24f03-105">Supplying Parameters for Multithreaded Procedures</span></span>  
 <span data-ttu-id="24f03-106">提供多线程的方法调用的参数的最好办法是将目标方法包装在一个类并为该类类型的值将用作新线程的参数定义的字段。</span><span class="sxs-lookup"><span data-stu-id="24f03-106">The best way to supply parameters for a multithreaded method call is to wrap the target method in a class and define fields for that class that will serve as parameters for the new thread.</span></span> <span data-ttu-id="24f03-107">这种方法的优点是可以具有其自己的参数，都创建新类的实例，每次想要启动新线程。</span><span class="sxs-lookup"><span data-stu-id="24f03-107">The advantage of this approach is that you can create a new instance of the class, with its own parameters, every time you want to start a new thread.</span></span> <span data-ttu-id="24f03-108">例如，假设您有一个计算一个三角形，如以下代码所示的区域的函数︰</span><span class="sxs-lookup"><span data-stu-id="24f03-108">For example, suppose you have a function that calculates the area of a triangle, as in the following code:</span></span>  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 <span data-ttu-id="24f03-109">您可以编写一个类用于包装`CalcArea`函数，并且创建字段来存储输入的参数，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="24f03-109">You can write a class that wraps the `CalcArea` function and creates fields to store input parameters, as follows:</span></span>  
  
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
  
 <span data-ttu-id="24f03-110">若要使用`AreaClass`，您可以创建`AreaClass`对象，并设置`Base`和`Height`属性，如下面的代码中所示︰</span><span class="sxs-lookup"><span data-stu-id="24f03-110">To use the `AreaClass`, you can create an `AreaClass` object, and set the `Base` and `Height` properties as shown in the following code:</span></span>  
  
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
  
 <span data-ttu-id="24f03-111">请注意，`TestArea`过程不检查的值`Area`字段之后调用`CalcArea`方法。</span><span class="sxs-lookup"><span data-stu-id="24f03-111">Notice that the `TestArea` procedure does not check the value of the `Area` field after calling the `CalcArea` method.</span></span> <span data-ttu-id="24f03-112">因为`CalcArea`的单独线程上运行`Area`字段不能保证如果您在调用后立即检查设置`Thread.Start`。</span><span class="sxs-lookup"><span data-stu-id="24f03-112">Because `CalcArea` runs on a separate thread, the `Area` field is not guaranteed to be set if you check it immediately after calling `Thread.Start`.</span></span> <span data-ttu-id="24f03-113">下一节讨论了更好的方法可从多线程过程返回值。</span><span class="sxs-lookup"><span data-stu-id="24f03-113">The next section discusses a better way to return values from multithreaded procedures.</span></span>  
  
## <a name="returning-values-from-multithreaded-procedures"></a><span data-ttu-id="24f03-114">从多线程过程返回值</span><span class="sxs-lookup"><span data-stu-id="24f03-114">Returning Values from Multithreaded Procedures</span></span>  
 <span data-ttu-id="24f03-115">从在单独的线程运行的过程返回值很复杂的过程不能是函数，也不能使用的事实`ByRef`参数。</span><span class="sxs-lookup"><span data-stu-id="24f03-115">Returning values from procedures that run on separate threads is complicated by the fact that the procedures cannot be functions and cannot use `ByRef` arguments.</span></span> <span data-ttu-id="24f03-116">返回值的最简单方法是使用<xref:System.ComponentModel.BackgroundWorker>组件可管理您的线程，并引发一个事件完成任务后，和过程与一个事件处理程序的结果。</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="24f03-116">The easiest way to return values is to use the <xref:System.ComponentModel.BackgroundWorker> component to manage your threads and raise an event when the task is done, and process the results with an event handler.</span></span>  
  
 <span data-ttu-id="24f03-117">下面的示例通过从在单独的线程上运行的过程引发一个事件来返回一个值︰</span><span class="sxs-lookup"><span data-stu-id="24f03-117">The following example returns a value by raising an event from a procedure running on a separate thread:</span></span>  
  
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
  
 <span data-ttu-id="24f03-118">您可以提供参数，并通过使用可选值返回到线程池线程`ByVal`的状态对象变量<xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>方法。</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="24f03-118">You can provide parameters and return values to thread-pool threads by using the optional `ByVal` state-object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="24f03-119">线程计时器线程还支持用于此目的的状态对象。</span><span class="sxs-lookup"><span data-stu-id="24f03-119">Thread-timer threads also support a state object for this purpose.</span></span> <span data-ttu-id="24f03-120">有关线程池和线程计时器的信息，请参阅[线程池 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[线程池](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701)和[线程计时器 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md)。</span><span class="sxs-lookup"><span data-stu-id="24f03-120">For information on thread pooling and thread timers, see [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[Thread Pooling](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) and [Thread Timers (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24f03-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24f03-121">See Also</span></span>  
 <span data-ttu-id="24f03-122">[演练︰ 利用 BackgroundWorker 组件 (Visual Basic 中) 的多线程处理](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md) </span><span class="sxs-lookup"><span data-stu-id="24f03-122">[Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md) </span></span>  
<span data-ttu-id="24f03-123"> [线程池 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md) </span><span class="sxs-lookup"><span data-stu-id="24f03-123"> [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md) </span></span>  
<span data-ttu-id="24f03-124"> [线程同步 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="24f03-124"> [Thread Synchronization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md) </span></span>  
<span data-ttu-id="24f03-125"> [事件](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="24f03-125"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="24f03-126"> [多线程应用程序 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span><span class="sxs-lookup"><span data-stu-id="24f03-126"> [Multithreaded Applications (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span></span>  
<span data-ttu-id="24f03-127"> [委托](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="24f03-127"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="24f03-128"> [在组件多线程处理](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)</span><span class="sxs-lookup"><span data-stu-id="24f03-128"> [Multithreading in Components](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)</span></span>
