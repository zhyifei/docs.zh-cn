---
title: "在委托 (Visual Basic 中) 中使用变体"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 435591d69e67c4fc4be8e781c5f63e025c71a8cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="395d1-102">在委托 (Visual Basic 中) 中使用变体</span><span class="sxs-lookup"><span data-stu-id="395d1-102">Using Variance in Delegates (Visual Basic)</span></span>
<span data-ttu-id="395d1-103">向委托分配方法时，协变和逆变为匹配委托类型和方法签名提供了灵活性。</span><span class="sxs-lookup"><span data-stu-id="395d1-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="395d1-104">协变允许方法具有的派生返回类型多于委托中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="395d1-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="395d1-105">逆变允许方法具有的派生参数类型少于委托类型中的类型。</span><span class="sxs-lookup"><span data-stu-id="395d1-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="395d1-106">示例 1：协变</span><span class="sxs-lookup"><span data-stu-id="395d1-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="395d1-107">描述</span><span class="sxs-lookup"><span data-stu-id="395d1-107">Description</span></span>  
 <span data-ttu-id="395d1-108">本示例演示如何将委托与具有返回类型的方法一起使用，这些返回类型派生自委托签名中的返回类型。</span><span class="sxs-lookup"><span data-stu-id="395d1-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="395d1-109">`DogsHandler` 返回的数据类型属于 `Dogs` 类型，它派生自委托中定义的 `Mammals` 类型。</span><span class="sxs-lookup"><span data-stu-id="395d1-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="395d1-110">代码</span><span class="sxs-lookup"><span data-stu-id="395d1-110">Code</span></span>  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="395d1-111">示例 2：逆变</span><span class="sxs-lookup"><span data-stu-id="395d1-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="395d1-112">描述</span><span class="sxs-lookup"><span data-stu-id="395d1-112">Description</span></span>  
 <span data-ttu-id="395d1-113">本示例演示如何将委托与具有某个类型的参数的方法一起使用，这些返回类型是委托签名参数类型的基类型。</span><span class="sxs-lookup"><span data-stu-id="395d1-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="395d1-114">通过逆变可以使用一个事件处理程序而不是多个单独的处理程序。</span><span class="sxs-lookup"><span data-stu-id="395d1-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="395d1-115">例如，可以创建接受 `EventArgs` 输入参数的事件处理程序，并将其与将 `MouseEventArgs` 类型作为参数发送的 `Button.MouseClick` 事件一起使用，也可以将其与发送 `KeyEventArgs` 参数的 `TextBox.KeyDown` 事件一起使用。</span><span class="sxs-lookup"><span data-stu-id="395d1-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="395d1-116">代码</span><span class="sxs-lookup"><span data-stu-id="395d1-116">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="395d1-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="395d1-117">See Also</span></span>  
 [<span data-ttu-id="395d1-118">委托中的变体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="395d1-118">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)  
 [<span data-ttu-id="395d1-119">对 Func 和 Action 泛型委托使用变体 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="395d1-119">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
