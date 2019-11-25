---
title: 使用委托中的变体
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: 9c2aad0e4b9408939600938412fe5c3e73b5bf15
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349034"
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="a95ee-102">Using Variance in Delegates (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a95ee-102">Using Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="a95ee-103">向委托分配方法时，协变和逆变为匹配委托类型和方法签名提供了灵活性。</span><span class="sxs-lookup"><span data-stu-id="a95ee-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="a95ee-104">协变允许方法具有的派生返回类型多于委托中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="a95ee-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="a95ee-105">逆变允许方法具有的派生参数类型少于委托类型中的类型。</span><span class="sxs-lookup"><span data-stu-id="a95ee-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>

## <a name="example-1-covariance"></a><span data-ttu-id="a95ee-106">示例 1：协变</span><span class="sxs-lookup"><span data-stu-id="a95ee-106">Example 1: Covariance</span></span>

### <a name="description"></a><span data-ttu-id="a95ee-107">描述</span><span class="sxs-lookup"><span data-stu-id="a95ee-107">Description</span></span>

<span data-ttu-id="a95ee-108">本示例演示如何将委托与具有返回类型的方法一起使用，这些返回类型派生自委托签名中的返回类型。</span><span class="sxs-lookup"><span data-stu-id="a95ee-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="a95ee-109">`DogsHandler` 返回的数据类型属于 `Dogs` 类型，它派生自委托中定义的 `Mammals` 类型。</span><span class="sxs-lookup"><span data-stu-id="a95ee-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>

### <a name="code"></a><span data-ttu-id="a95ee-110">代码</span><span class="sxs-lookup"><span data-stu-id="a95ee-110">Code</span></span>

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

## <a name="example-2-contravariance"></a><span data-ttu-id="a95ee-111">示例 2：逆变</span><span class="sxs-lookup"><span data-stu-id="a95ee-111">Example 2: Contravariance</span></span>

### <a name="description"></a><span data-ttu-id="a95ee-112">描述</span><span class="sxs-lookup"><span data-stu-id="a95ee-112">Description</span></span>

<span data-ttu-id="a95ee-113">本示例演示如何将委托与具有参数的方法一起使用，这些参数的类型是委托签名参数类型的基类型。</span><span class="sxs-lookup"><span data-stu-id="a95ee-113">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="a95ee-114">通过逆变可以使用一个事件处理程序而不是多个单独的处理程序。</span><span class="sxs-lookup"><span data-stu-id="a95ee-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="a95ee-115">下面的示例使用两个委托：</span><span class="sxs-lookup"><span data-stu-id="a95ee-115">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="a95ee-116">定义 [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) 事件签名的 <xref:System.Windows.Forms.KeyEventHandler> 委托。</span><span class="sxs-lookup"><span data-stu-id="a95ee-116">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="a95ee-117">其签名为：</span><span class="sxs-lookup"><span data-stu-id="a95ee-117">Its signature is:</span></span>

   ```vb
   Public Delegate Sub KeyEventHandler(sender As Object, e As KeyEventArgs)
   ```

- <span data-ttu-id="a95ee-118">定义 [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) 事件签名的 <xref:System.Windows.Forms.MouseEventHandler> 委托。</span><span class="sxs-lookup"><span data-stu-id="a95ee-118">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="a95ee-119">其签名为：</span><span class="sxs-lookup"><span data-stu-id="a95ee-119">Its signature is:</span></span>

   ```vb
   Public Delegate Sub MouseEventHandler(sender As Object, e As MouseEventArgs)
   ```

<span data-ttu-id="a95ee-120">该示例定义了一个具有 <xref:System.EventArgs> 参数的事件处理程序，并使用它来处理 `Button.KeyDown` 和 `Button.MouseClick` 事件。</span><span class="sxs-lookup"><span data-stu-id="a95ee-120">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="a95ee-121">它可以这样做是因为 <xref:System.EventArgs> 是 <xref:System.Windows.Forms.KeyEventArgs> 和 <xref:System.Windows.Forms.MouseEventArgs> 的基类型。</span><span class="sxs-lookup"><span data-stu-id="a95ee-121">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>

### <a name="code"></a><span data-ttu-id="a95ee-122">代码</span><span class="sxs-lookup"><span data-stu-id="a95ee-122">Code</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a95ee-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="a95ee-123">See also</span></span>

- [<span data-ttu-id="a95ee-124">委托中的变体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a95ee-124">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
- [<span data-ttu-id="a95ee-125">对 Func 和 Action 泛型委托使用变体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a95ee-125">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
