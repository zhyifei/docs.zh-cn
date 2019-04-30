---
title: Null 条件运算符 (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: b83435b8448b53eca63aac0519e9eed2f7dfa9f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62028686"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="2cf02-102">?.</span><span class="sxs-lookup"><span data-stu-id="2cf02-102">?.</span></span> <span data-ttu-id="2cf02-103">和？（） null 条件运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cf02-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="2cf02-104">测试是否为空的左操作数的值 (`Nothing`) 之前执行成员访问 (`?.`) 或索引 (`?()`); 操作返回`Nothing`如果左操作数的计算结果为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="2cf02-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="2cf02-105">请注意，在表达式中通常返回值类型，null 条件运算符返回<xref:System.Nullable%601>。</span><span class="sxs-lookup"><span data-stu-id="2cf02-105">Note that in expressions that ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="2cf02-106">这些运算符可帮助您编写更少代码来处理 null 检查，尤其是当下降到数据结构。</span><span class="sxs-lookup"><span data-stu-id="2cf02-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="2cf02-107">例如：</span><span class="sxs-lookup"><span data-stu-id="2cf02-107">For example:</span></span>

```vb
' Nothing if customers is Nothing  
Dim length As Integer? = customers?.Length  

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()   
```

<span data-ttu-id="2cf02-108">有关比较，这些表达式而无需 null 条件运算符的第一个替代代码是：</span><span class="sxs-lookup"><span data-stu-id="2cf02-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="2cf02-109">NULL 条件运算符采用最小化求值策略。</span><span class="sxs-lookup"><span data-stu-id="2cf02-109">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="2cf02-110">如果条件成员访问和索引操作链中的一个操作返回`Nothing`，链的执行将停止的其余部分。</span><span class="sxs-lookup"><span data-stu-id="2cf02-110">If one operation in a chain of conditional member access and index operations returns `Nothing`, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="2cf02-111">在以下示例中，`C(E)`如果未进行求值`A`， `B`，或`C`计算结果为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="2cf02-111">In the following example, `C(E)` isn't evaluated if `A`, `B`, or `C` evaluates to `Nothing`.</span></span>

```vb
A?.B?.C?(E);
```

<span data-ttu-id="2cf02-112">Null 条件成员访问的另一个用途是在使用非常少的代码以线程安全的方式调用委托。</span><span class="sxs-lookup"><span data-stu-id="2cf02-112">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="2cf02-113">下面的示例定义两种类型，`NewsBroadcaster`和一个`NewsReceiver`。</span><span class="sxs-lookup"><span data-stu-id="2cf02-113">The following example defines two types, a `NewsBroadcaster` and a `NewsReceiver`.</span></span> <span data-ttu-id="2cf02-114">新闻项发送到由接收方`NewsBroadcaster.SendNews`委托。</span><span class="sxs-lookup"><span data-stu-id="2cf02-114">News items are sent to the receiver by the `NewsBroadcaster.SendNews` delegate.</span></span>

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String) 

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

<span data-ttu-id="2cf02-115">如果没有在元素`SendNews`调用列表，列出`SendNews`委托，则会引发<xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="2cf02-115">If there are no elements in the `SendNews` invocation list, the `SendNews` delegate throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="2cf02-116">Null 条件运算符之前代码，类似以下确保委托调用列表不是`Nothing`:</span><span class="sxs-lookup"><span data-stu-id="2cf02-116">Before null conditional operators, code like the following ensured that the delegate invocation list was not `Nothing`:</span></span>

```vb  
SendNews = SendNews.Combine({SendNews, client})  
If SendNews IsNot Nothing Then 
   SendNews("Just in...")
End If
```

<span data-ttu-id="2cf02-117">新的方法是要简单得多：</span><span class="sxs-lookup"><span data-stu-id="2cf02-117">The new way is much simpler:</span></span>  

```vb
SendNews = SendNews.Combine({SendNews, client})  
SendNews?.Invoke("Just in...")
```

<span data-ttu-id="2cf02-118">新方法是线程安全的，因为编译器生成的代码仅评估 `SendNews` 一次，从而使结果保持在临时变量中。</span><span class="sxs-lookup"><span data-stu-id="2cf02-118">The new way is thread-safe because the compiler generates code to evaluate `SendNews` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="2cf02-119">你需要显式调用 `Invoke` 方法，因为不存在 NULL 条件委托调用语法 `SendNews?(String)`。</span><span class="sxs-lookup"><span data-stu-id="2cf02-119">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `SendNews?(String)`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="2cf02-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2cf02-120">See also</span></span>

- [<span data-ttu-id="2cf02-121">运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cf02-121">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="2cf02-122">Visual Basic 编程指南</span><span class="sxs-lookup"><span data-stu-id="2cf02-122">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="2cf02-123">Visual Basic 语言参考</span><span class="sxs-lookup"><span data-stu-id="2cf02-123">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
