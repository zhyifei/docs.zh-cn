---
title: 在委托中使用变体 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: ebba7e862e1b4677d9438aa301ef2b713fba3712
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "70169072"
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="26e2e-102">在委托中使用变体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26e2e-102">Using Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="26e2e-103">向委托分配方法时，协变和逆变为匹配委托类型和方法签名提供了灵活性。</span><span class="sxs-lookup"><span data-stu-id="26e2e-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="26e2e-104">协变允许方法具有的派生返回类型多于委托中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="26e2e-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="26e2e-105">逆变允许方法具有的派生参数类型少于委托类型中的类型。</span><span class="sxs-lookup"><span data-stu-id="26e2e-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>

## <a name="example-1-covariance"></a><span data-ttu-id="26e2e-106">示例 1：协变</span><span class="sxs-lookup"><span data-stu-id="26e2e-106">Example 1: Covariance</span></span>

### <a name="description"></a><span data-ttu-id="26e2e-107">描述</span><span class="sxs-lookup"><span data-stu-id="26e2e-107">Description</span></span>

<span data-ttu-id="26e2e-108">本示例演示如何将委托与具有返回类型的方法一起使用，这些返回类型派生自委托签名中的返回类型。</span><span class="sxs-lookup"><span data-stu-id="26e2e-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="26e2e-109">`DogsHandler` 返回的数据类型属于 `Dogs` 类型，它派生自委托中定义的 `Mammals` 类型。</span><span class="sxs-lookup"><span data-stu-id="26e2e-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>

### <a name="code"></a><span data-ttu-id="26e2e-110">代码</span><span class="sxs-lookup"><span data-stu-id="26e2e-110">Code</span></span>

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

## <a name="example-2-contravariance"></a><span data-ttu-id="26e2e-111">示例 2：逆变</span><span class="sxs-lookup"><span data-stu-id="26e2e-111">Example 2: Contravariance</span></span>

### <a name="description"></a><span data-ttu-id="26e2e-112">描述</span><span class="sxs-lookup"><span data-stu-id="26e2e-112">Description</span></span>

<span data-ttu-id="26e2e-113">此示例演示如何将委托与具有参数类型为委托签名参数类型的基类型的方法一起使用。</span><span class="sxs-lookup"><span data-stu-id="26e2e-113">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="26e2e-114">通过逆变可以使用一个事件处理程序而不是多个单独的处理程序。</span><span class="sxs-lookup"><span data-stu-id="26e2e-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="26e2e-115">下面的示例使用两个委托:</span><span class="sxs-lookup"><span data-stu-id="26e2e-115">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="26e2e-116">定义[按钮 KeyDown](xref:System.Windows.Forms.Control.KeyDown)事件签名的委托。<xref:System.Windows.Forms.KeyEventHandler></span><span class="sxs-lookup"><span data-stu-id="26e2e-116">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="26e2e-117">其签名为:</span><span class="sxs-lookup"><span data-stu-id="26e2e-117">Its signature is:</span></span>

   ```vb
   Public Delegate Sub KeyEventHandler(sender As Object, e As KeyEventArgs)
   ```

- <span data-ttu-id="26e2e-118">用于定义[MouseClick](xref:System.Windows.Forms.Control.MouseDown)事件的签名的委托。<xref:System.Windows.Forms.MouseEventHandler></span><span class="sxs-lookup"><span data-stu-id="26e2e-118">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="26e2e-119">其签名为:</span><span class="sxs-lookup"><span data-stu-id="26e2e-119">Its signature is:</span></span>

   ```vb
   Public Delegate Sub MouseEventHandler(sender As Object, e As MouseEventArgs)
   ```

<span data-ttu-id="26e2e-120">该示例使用一个<xref:System.EventArgs>参数定义一个事件处理程序, 并使用它来处理`Button.KeyDown`和`Button.MouseClick`事件。</span><span class="sxs-lookup"><span data-stu-id="26e2e-120">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="26e2e-121">这是因为<xref:System.EventArgs> , 是<xref:System.Windows.Forms.KeyEventArgs>和<xref:System.Windows.Forms.MouseEventArgs>的基类型。</span><span class="sxs-lookup"><span data-stu-id="26e2e-121">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>

### <a name="code"></a><span data-ttu-id="26e2e-122">代码</span><span class="sxs-lookup"><span data-stu-id="26e2e-122">Code</span></span>

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

## <a name="see-also"></a><span data-ttu-id="26e2e-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="26e2e-123">See also</span></span>

- [<span data-ttu-id="26e2e-124">委托中的变体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26e2e-124">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
- [<span data-ttu-id="26e2e-125">对 Func 和 Action 泛型委托使用变体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26e2e-125">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
