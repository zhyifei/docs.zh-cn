---
title: 使用委托 (Visual Basic 中) 中的方差
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: 19eb3070c1b8359a4eb050e7cf2f16622f66ebe9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787252"
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="71205-102">使用委托 (Visual Basic 中) 中的方差</span><span class="sxs-lookup"><span data-stu-id="71205-102">Using Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="71205-103">向委托分配方法时，协变和逆变为匹配委托类型和方法签名提供了灵活性。</span><span class="sxs-lookup"><span data-stu-id="71205-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="71205-104">协变允许方法具有的派生返回类型多于委托中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="71205-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="71205-105">逆变允许方法具有的派生参数类型少于委托类型中的类型。</span><span class="sxs-lookup"><span data-stu-id="71205-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>

## <a name="example-1-covariance"></a><span data-ttu-id="71205-106">示例 1：协变</span><span class="sxs-lookup"><span data-stu-id="71205-106">Example 1: Covariance</span></span>

### <a name="description"></a><span data-ttu-id="71205-107">描述</span><span class="sxs-lookup"><span data-stu-id="71205-107">Description</span></span>

<span data-ttu-id="71205-108">本示例演示如何将委托与具有返回类型的方法一起使用，这些返回类型派生自委托签名中的返回类型。</span><span class="sxs-lookup"><span data-stu-id="71205-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="71205-109">`DogsHandler` 返回的数据类型属于 `Dogs` 类型，它派生自委托中定义的 `Mammals` 类型。</span><span class="sxs-lookup"><span data-stu-id="71205-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>

### <a name="code"></a><span data-ttu-id="71205-110">代码</span><span class="sxs-lookup"><span data-stu-id="71205-110">Code</span></span>

```vb
Class Mammals
End Class

Class Dogs
    Inherits Mammals
End Class
Class Test
    Public Delegate Function HandlerMethod() As Mammals
    Public Shared Function MammalsHandler() As Mammals
        Return Nothing
    End Function
    Public Shared Function DogsHandler() As Dogs
        Return Nothing
    End Function
    Sub Test()
        Dim handlerMammals As HandlerMethod = AddressOf MammalsHandler
        ' Covariance enables this assignment.
        Dim handlerDogs As HandlerMethod = AddressOf DogsHandler
    End Sub
End Class
```

## <a name="example-2-contravariance"></a><span data-ttu-id="71205-111">示例 2：逆变</span><span class="sxs-lookup"><span data-stu-id="71205-111">Example 2: Contravariance</span></span>

### <a name="description"></a><span data-ttu-id="71205-112">描述</span><span class="sxs-lookup"><span data-stu-id="71205-112">Description</span></span>

<span data-ttu-id="71205-113">本示例演示如何将委托与具有某个类型的参数的方法一起使用，这些返回类型是委托签名参数类型的基类型。</span><span class="sxs-lookup"><span data-stu-id="71205-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="71205-114">通过逆变可以使用一个事件处理程序而不是多个单独的处理程序。</span><span class="sxs-lookup"><span data-stu-id="71205-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="71205-115">例如，可以创建接受 `EventArgs` 输入参数的事件处理程序，并将其与将 `MouseEventArgs` 类型作为参数发送的 `Button.MouseClick` 事件一起使用，也可以将其与发送 `KeyEventArgs` 参数的 `TextBox.KeyDown` 事件一起使用。</span><span class="sxs-lookup"><span data-stu-id="71205-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>

### <a name="code"></a><span data-ttu-id="71205-116">代码</span><span class="sxs-lookup"><span data-stu-id="71205-116">Code</span></span>

```vb
' Event handler that accepts a parameter of the EventArgs type.
Private Sub MultiHandler(ByVal sender As Object,
                         ByVal e As System.EventArgs)
    Label1.Text = DateTime.Now
End Sub

Private Sub Form1_Load(ByVal sender As System.Object,
    ByVal e As System.EventArgs) Handles MyBase.Load

    ' You can use a method that has an EventArgs parameter,
    ' although the event expects the KeyEventArgs parameter.
    AddHandler Button1.KeyDown, AddressOf MultiHandler

    ' You can use the same method
    ' for the event that expects the MouseEventArgs parameter.
    AddHandler Button1.MouseClick, AddressOf MultiHandler
End Sub
```

## <a name="see-also"></a><span data-ttu-id="71205-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="71205-117">See also</span></span>

- [<span data-ttu-id="71205-118">委托中的变体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71205-118">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
- [<span data-ttu-id="71205-119">对 Func 和 Action 泛型委托使用变体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71205-119">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
