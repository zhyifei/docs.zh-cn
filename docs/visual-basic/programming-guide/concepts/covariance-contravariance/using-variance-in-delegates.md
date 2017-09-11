---
title: "在委托 (Visual Basic 中) 中使用变体 |Microsoft 文档"
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
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 620fd61000e42d68f566e441d023d73a036000ae
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="5d1be-102">在委托 (Visual Basic 中) 中使用变体</span><span class="sxs-lookup"><span data-stu-id="5d1be-102">Using Variance in Delegates (Visual Basic)</span></span>
<span data-ttu-id="5d1be-103">当将一种方法分配给一个委托，委托*协方差*和*逆变*为匹配方法签名与委托类型提供的灵活性。</span><span class="sxs-lookup"><span data-stu-id="5d1be-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="5d1be-104">协变允许方法具有返回类型为于在委托中定义的派生程度更大。</span><span class="sxs-lookup"><span data-stu-id="5d1be-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="5d1be-105">逆变允许具有比委托类型中派生程度更小的参数类型的方法。</span><span class="sxs-lookup"><span data-stu-id="5d1be-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="5d1be-106">示例 1︰ 协方差</span><span class="sxs-lookup"><span data-stu-id="5d1be-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="5d1be-107">描述</span><span class="sxs-lookup"><span data-stu-id="5d1be-107">Description</span></span>  
 <span data-ttu-id="5d1be-108">此示例演示如何使用具有返回类型的派生自委托签名中的返回类型的方法使用委托。</span><span class="sxs-lookup"><span data-stu-id="5d1be-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="5d1be-109">返回的数据类型`DogsHandler`属于类型`Dogs`，它派生自`Mammals`委托中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="5d1be-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5d1be-110">代码</span><span class="sxs-lookup"><span data-stu-id="5d1be-110">Code</span></span>  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="5d1be-111">示例 2︰ 逆变</span><span class="sxs-lookup"><span data-stu-id="5d1be-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="5d1be-112">描述</span><span class="sxs-lookup"><span data-stu-id="5d1be-112">Description</span></span>  
 <span data-ttu-id="5d1be-113">此示例演示如何使用具有一种类型的基类型的委托签名参数类型的参数的方法使用委托。</span><span class="sxs-lookup"><span data-stu-id="5d1be-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="5d1be-114">逆变，您可以使用一个事件处理程序而不是单独的处理程序。</span><span class="sxs-lookup"><span data-stu-id="5d1be-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="5d1be-115">例如，您可以创建的事件处理程序接受`EventArgs`输入参数并将其用于`Button.MouseClick`发送的事件`MouseEventArgs`类型作为参数，以及与`TextBox.KeyDown`发送的事件`KeyEventArgs`参数。</span><span class="sxs-lookup"><span data-stu-id="5d1be-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5d1be-116">代码</span><span class="sxs-lookup"><span data-stu-id="5d1be-116">Code</span></span>  
  
```vb  
' Event hander that accepts a parameter of the EventArgs type.  
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
  
## <a name="see-also"></a><span data-ttu-id="5d1be-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d1be-117">See Also</span></span>  
 <span data-ttu-id="5d1be-118">[委托 (Visual Basic 中) 中的变体](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span><span class="sxs-lookup"><span data-stu-id="5d1be-118">[Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span></span>  
<span data-ttu-id="5d1be-119"> [对 Func 和 Action 泛型委托 (Visual Basic 中) 中使用变体](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="5d1be-119"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
