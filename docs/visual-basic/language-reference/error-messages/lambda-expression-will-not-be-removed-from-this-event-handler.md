---
title: 将不会从此事件处理程序中移除 Lambda 表达式
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 69228bbb5f659a8e500e85dea1ef87cb43b0356e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590162"
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a><span data-ttu-id="3af86-102">将不会从此事件处理程序中移除 Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="3af86-102">Lambda expression will not be removed from this event handler</span></span>
<span data-ttu-id="3af86-103">Lambda 表达式不会从此事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="3af86-103">Lambda expression will not be removed from this event handler.</span></span> <span data-ttu-id="3af86-104">将 lambda 表达式分配给变量并将该变量添加和删除事件。</span><span class="sxs-lookup"><span data-stu-id="3af86-104">Assign the lambda expression to a variable and use the variable to add and remove the event.</span></span>  
  
 <span data-ttu-id="3af86-105">当与事件处理程序使用 lambda 表达式时，你可能无法看到你预期的行为。</span><span class="sxs-lookup"><span data-stu-id="3af86-105">When lambda expressions are used with event handlers, you may not see the behavior you expect.</span></span> <span data-ttu-id="3af86-106">即使它们是相同，编译器将生成每个 lambda 表达式定义中，一个新方法。</span><span class="sxs-lookup"><span data-stu-id="3af86-106">The compiler generates a new method for each lambda expression definition, even if they are identical.</span></span> <span data-ttu-id="3af86-107">因此，下面的代码显示`False`。</span><span class="sxs-lookup"><span data-stu-id="3af86-107">Therefore, the following code displays `False`.</span></span>  
  
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
  
 <span data-ttu-id="3af86-108">当与事件处理程序使用 lambda 表达式时，这可能导致意外的结果。</span><span class="sxs-lookup"><span data-stu-id="3af86-108">When lambda expressions are used with event handlers, this may cause unexpected results.</span></span> <span data-ttu-id="3af86-109">在下面的示例中，lambda 表达式添加`AddHandler`并不能消除`RemoveHandler`语句。</span><span class="sxs-lookup"><span data-stu-id="3af86-109">In the following example, the lambda expression added by `AddHandler` is not removed by the `RemoveHandler` statement.</span></span>  
  
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
  
 <span data-ttu-id="3af86-110">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="3af86-110">By default, this message is a warning.</span></span> <span data-ttu-id="3af86-111">有关如何隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="3af86-111">For more information about how to hide warnings or treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="3af86-112">**错误 ID:** BC42326</span><span class="sxs-lookup"><span data-stu-id="3af86-112">**Error ID:** BC42326</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3af86-113">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3af86-113">To correct this error</span></span>  
  
-   <span data-ttu-id="3af86-114">若要避免此警告，并删除该 lambda 表达式，分配给一个变量的 lambda 表达式，并在将该变量`AddHandler`和`RemoveHandler`语句，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="3af86-114">To avoid the warning and remove the lambda expression, assign the lambda expression to a variable and use the variable in both the `AddHandler` and `RemoveHandler` statements, as shown in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3af86-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3af86-115">See Also</span></span>  
 [<span data-ttu-id="3af86-116">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="3af86-116">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="3af86-117">宽松委托转换</span><span class="sxs-lookup"><span data-stu-id="3af86-117">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [<span data-ttu-id="3af86-118">事件</span><span class="sxs-lookup"><span data-stu-id="3af86-118">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
