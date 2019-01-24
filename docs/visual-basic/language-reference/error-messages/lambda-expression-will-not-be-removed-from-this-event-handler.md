---
title: 将不会从此事件处理程序中移除 Lambda 表达式
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 2f8b10082bb39c76ba1393daf8327df2ed631caf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568096"
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a><span data-ttu-id="2fc88-102">将不会从此事件处理程序中移除 Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="2fc88-102">Lambda expression will not be removed from this event handler</span></span>
<span data-ttu-id="2fc88-103">从此事件处理程序不会移除 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="2fc88-103">Lambda expression will not be removed from this event handler.</span></span> <span data-ttu-id="2fc88-104">将 lambda 表达式分配给一个变量并将该变量来添加和删除该事件。</span><span class="sxs-lookup"><span data-stu-id="2fc88-104">Assign the lambda expression to a variable and use the variable to add and remove the event.</span></span>  
  
 <span data-ttu-id="2fc88-105">当事件处理程序中使用 lambda 表达式时，可能无法看到所需的行为。</span><span class="sxs-lookup"><span data-stu-id="2fc88-105">When lambda expressions are used with event handlers, you may not see the behavior you expect.</span></span> <span data-ttu-id="2fc88-106">编译器将生成新的方法对于每个 lambda 表达式定义，即使它们是完全相同。</span><span class="sxs-lookup"><span data-stu-id="2fc88-106">The compiler generates a new method for each lambda expression definition, even if they are identical.</span></span> <span data-ttu-id="2fc88-107">因此，下面的代码显示`False`。</span><span class="sxs-lookup"><span data-stu-id="2fc88-107">Therefore, the following code displays `False`.</span></span>  
  
```vb  
Module Module1  
  
    Sub Main()  
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1  
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1  
        Console.WriteLine(fun1 = fun2)  
    End Sub  
  
    Delegate Function ChangeInteger(ByVal x As Integer) As Integer  
  
End Module  
```  
  
 <span data-ttu-id="2fc88-108">当事件处理程序中使用 lambda 表达式时，这可能会导致意外的结果。</span><span class="sxs-lookup"><span data-stu-id="2fc88-108">When lambda expressions are used with event handlers, this may cause unexpected results.</span></span> <span data-ttu-id="2fc88-109">在以下示例中，lambda 表达式添加`AddHandler`情况下不删除`RemoveHandler`语句。</span><span class="sxs-lookup"><span data-stu-id="2fc88-109">In the following example, the lambda expression added by `AddHandler` is not removed by the `RemoveHandler` statement.</span></span>  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Sub Main()  
  
        ' The following line adds one listener to the event.  
        AddHandler ProcessInteger, Function(m As Integer) m  
  
        ' The following statement searches the current listeners   
        ' for a match to remove. However, this lambda is not the same  
        ' as the previous one, so nothing is removed.  
        RemoveHandler ProcessInteger, Function(m As Integer) m  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="2fc88-110">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="2fc88-110">By default, this message is a warning.</span></span> <span data-ttu-id="2fc88-111">有关如何隐藏警告或将警告视为错误的详细信息，请参阅 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="2fc88-111">For more information about how to hide warnings or treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="2fc88-112">**错误 ID:** BC42326</span><span class="sxs-lookup"><span data-stu-id="2fc88-112">**Error ID:** BC42326</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2fc88-113">更正此错误</span><span class="sxs-lookup"><span data-stu-id="2fc88-113">To correct this error</span></span>  
  
-   <span data-ttu-id="2fc88-114">若要避免出现警告，并删除 lambda 表达式，lambda 表达式分配给一个变量，并在这种使用该变量`AddHandler`和`RemoveHandler`语句，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="2fc88-114">To avoid the warning and remove the lambda expression, assign the lambda expression to a variable and use the variable in both the `AddHandler` and `RemoveHandler` statements, as shown in the following example.</span></span>  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Dim PrintHandler As ProcessIntegerEventHandler  
  
    Sub Main()  
  
        ' Assign the lambda expression to a variable.  
        PrintHandler = Function(m As Integer) m  
  
        ' Use the variable to add the listener.  
        AddHandler ProcessInteger, PrintHandler  
  
        ' Use the variable again when you want to remove the listener.  
        RemoveHandler ProcessInteger, PrintHandler  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fc88-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fc88-115">See also</span></span>
- [<span data-ttu-id="2fc88-116">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="2fc88-116">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="2fc88-117">宽松委托转换</span><span class="sxs-lookup"><span data-stu-id="2fc88-117">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="2fc88-118">事件</span><span class="sxs-lookup"><span data-stu-id="2fc88-118">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
