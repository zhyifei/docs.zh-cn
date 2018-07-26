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
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a><span data-ttu-id="200f1-102">参数和返回值的多线程过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="200f1-102">Parameters and Return Values for Multithreaded Procedures (Visual Basic)</span></span>
<span data-ttu-id="200f1-103">在多线程应用程序中提供和返回值是很复杂的，因为必须将对某个过程的引用传递给线程类的构造函数，该过程不带参数也不返回值。</span><span class="sxs-lookup"><span data-stu-id="200f1-103">Supplying and returning values in a multithreaded application is complicated because the constructor for the thread class must be passed a reference to a procedure that takes no arguments and returns no value.</span></span> <span data-ttu-id="200f1-104">下面几节介绍一些提供参数和从不同线程上的过程返回值的简单方法。</span><span class="sxs-lookup"><span data-stu-id="200f1-104">The following sections show some simple ways to supply parameters and return values from procedures on separate threads.</span></span>  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a><span data-ttu-id="200f1-105">为多线程过程提供参数</span><span class="sxs-lookup"><span data-stu-id="200f1-105">Supplying Parameters for Multithreaded Procedures</span></span>  
 <span data-ttu-id="200f1-106">为多线程方法调用提供参数的最好办法是将目标方法包装在类中，并为该类定义字段，这些字段将用作新线程的参数。</span><span class="sxs-lookup"><span data-stu-id="200f1-106">The best way to supply parameters for a multithreaded method call is to wrap the target method in a class and define fields for that class that will serve as parameters for the new thread.</span></span> <span data-ttu-id="200f1-107">这种方法的优点是，任何时候想要启动新线程，都可以创建类的新实例，该实例带有自身的参数。</span><span class="sxs-lookup"><span data-stu-id="200f1-107">The advantage of this approach is that you can create a new instance of the class, with its own parameters, every time you want to start a new thread.</span></span> <span data-ttu-id="200f1-108">例如，假设有一个计算三角形面积的函数，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="200f1-108">For example, suppose you have a function that calculates the area of a triangle, as in the following code:</span></span>  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 <span data-ttu-id="200f1-109">可以编写一个包装 `CalcArea` 函数的类，并创建一些字段来存储输入参数，如以下所示：</span><span class="sxs-lookup"><span data-stu-id="200f1-109">You can write a class that wraps the `CalcArea` function and creates fields to store input parameters, as follows:</span></span>  
  
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
  
 <span data-ttu-id="200f1-110">若要使用 `AreaClass`，可以创建一个 `AreaClass` 对象并设置 `Base` 和 `Height` 属性，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="200f1-110">To use the `AreaClass`, you can create an `AreaClass` object, and set the `Base` and `Height` properties as shown in the following code:</span></span>  
  
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
  
 <span data-ttu-id="200f1-111">请注意，调用 `CalcArea` 方法后，`TestArea` 过程并不检查 `Area` 字段的值。</span><span class="sxs-lookup"><span data-stu-id="200f1-111">Notice that the `TestArea` procedure does not check the value of the `Area` field after calling the `CalcArea` method.</span></span> <span data-ttu-id="200f1-112">`CalcArea` 运行于单独的线程，因此，如果在调用 `Thread.Start` 后立即检查，则无法确定 `Area` 字段已被设置。</span><span class="sxs-lookup"><span data-stu-id="200f1-112">Because `CalcArea` runs on a separate thread, the `Area` field is not guaranteed to be set if you check it immediately after calling `Thread.Start`.</span></span> <span data-ttu-id="200f1-113">下一节讨论从多线程过程返回值的更好方法。</span><span class="sxs-lookup"><span data-stu-id="200f1-113">The next section discusses a better way to return values from multithreaded procedures.</span></span>  
  
## <a name="returning-values-from-multithreaded-procedures"></a><span data-ttu-id="200f1-114">从多线程过程返回值</span><span class="sxs-lookup"><span data-stu-id="200f1-114">Returning Values from Multithreaded Procedures</span></span>  
 <span data-ttu-id="200f1-115">由于这些过程不能为函数也不能使用 `ByRef` 参数，因而从运行于不同线程的过程返回值是很复杂的。</span><span class="sxs-lookup"><span data-stu-id="200f1-115">Returning values from procedures that run on separate threads is complicated by the fact that the procedures cannot be functions and cannot use `ByRef` arguments.</span></span> <span data-ttu-id="200f1-116">返回值最简单的方法是：使用 <xref:System.ComponentModel.BackgroundWorker> 组件来管理线程，在任务完成时引发事件，然后用事件处理程序处理结果。</span><span class="sxs-lookup"><span data-stu-id="200f1-116">The easiest way to return values is to use the <xref:System.ComponentModel.BackgroundWorker> component to manage your threads and raise an event when the task is done, and process the results with an event handler.</span></span>  
  
 <span data-ttu-id="200f1-117">下面的示例通过从运行于单独线程的某过程引发一个事件来返回值：</span><span class="sxs-lookup"><span data-stu-id="200f1-117">The following example returns a value by raising an event from a procedure running on a separate thread:</span></span>  
  
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
  
 <span data-ttu-id="200f1-118">可以通过使用 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 方法的可选 `ByVal` 状态对象变量来向线程池线程提供参数并返回值。</span><span class="sxs-lookup"><span data-stu-id="200f1-118">You can provide parameters and return values to thread-pool threads by using the optional `ByVal` state-object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="200f1-119">线程计时器线程也支持将状态对象用于此目的。</span><span class="sxs-lookup"><span data-stu-id="200f1-119">Thread-timer threads also support a state object for this purpose.</span></span> <span data-ttu-id="200f1-120">有关线程池和线程计时器的信息，请参阅[线程池 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[线程池](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701)并[计时器](../../../../standard/threading/timers.md)。</span><span class="sxs-lookup"><span data-stu-id="200f1-120">For information on thread pooling and thread timers, see [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[Thread Pooling](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) and [Timers](../../../../standard/threading/timers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="200f1-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="200f1-121">See Also</span></span>  
 [<span data-ttu-id="200f1-122">演练：利用 BackgroundWorker 组件进行多线程处理 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="200f1-122">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [<span data-ttu-id="200f1-123">线程池 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="200f1-123">Thread Pooling (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [<span data-ttu-id="200f1-124">线程同步 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="200f1-124">Thread Synchronization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="200f1-125">事件</span><span class="sxs-lookup"><span data-stu-id="200f1-125">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="200f1-126">多线程应用 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="200f1-126">Multithreaded Applications (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="200f1-127">委托</span><span class="sxs-lookup"><span data-stu-id="200f1-127">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="200f1-128">组件中的多线程处理</span><span class="sxs-lookup"><span data-stu-id="200f1-128">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
