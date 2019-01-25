---
title: Null 条件运算符 (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: d30d452a7c140a0c56529386b14ef3a3512df490
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722148"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="62a69-102">?.</span><span class="sxs-lookup"><span data-stu-id="62a69-102">?.</span></span> <span data-ttu-id="62a69-103">和？（） null 条件运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62a69-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="62a69-104">测试是否为空的左操作数的值 (`Nothing`) 之前执行成员访问 (`?.`) 或索引 (`?()`); 操作返回`Nothing`如果左操作数的计算结果为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="62a69-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="62a69-105">请注意，在表达式中通常会返回值类型，null 条件运算符返回<xref:System.Nullable%601>。</span><span class="sxs-lookup"><span data-stu-id="62a69-105">Note that, in the expressions that would ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="62a69-106">这些运算符可帮助您编写更少代码来处理 null 检查，尤其是当下降到数据结构。</span><span class="sxs-lookup"><span data-stu-id="62a69-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="62a69-107">例如：</span><span class="sxs-lookup"><span data-stu-id="62a69-107">For example:</span></span>

```vb
Dim length As Integer? = customers?.Length  ' Nothing if customers is Nothing  
Dim first As Customer = customers?(0)  ' Nothing if customers is Nothing  
Dim count As Integer? = customers?(0)?.Orders?.Count()  ' Nothing if customers, the first customer, or Orders is Nothing  
```

<span data-ttu-id="62a69-108">有关比较，这些表达式而无需 null 条件运算符的第一个替代代码是：</span><span class="sxs-lookup"><span data-stu-id="62a69-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="62a69-109">NULL 条件运算符采用最小化求值策略。</span><span class="sxs-lookup"><span data-stu-id="62a69-109">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="62a69-110">如果条件成员访问和索引操作链中的一个操作不返回任何内容，将停止的链的执行其余部分。</span><span class="sxs-lookup"><span data-stu-id="62a69-110">If one operation in a chain of conditional member access and index operations returns Nothing, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="62a69-111">在以下示例中，如果 c （e） 不评估`A`， `B`，或`C`计算结果为 Nothing。</span><span class="sxs-lookup"><span data-stu-id="62a69-111">In the following example, C(E) isn't evaluated if `A`, `B`, or `C` evaluates to Nothing.</span></span>

```vb
A?.B?.C?(E);
```

<span data-ttu-id="62a69-112">Null 条件成员访问的另一个用途是在使用非常少的代码以线程安全的方式调用委托。</span><span class="sxs-lookup"><span data-stu-id="62a69-112">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="62a69-113">旧方法需要如下所示的代码：</span><span class="sxs-lookup"><span data-stu-id="62a69-113">The old way requires code like the following:</span></span>  

```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```

<span data-ttu-id="62a69-114">新的方法是要简单得多：</span><span class="sxs-lookup"><span data-stu-id="62a69-114">The new way is much simpler:</span></span>  

```vb
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="62a69-115">新方法是线程安全的，因为编译器生成的代码仅评估 `PropertyChanged` 一次，从而使结果保持在临时变量中。</span><span class="sxs-lookup"><span data-stu-id="62a69-115">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="62a69-116">你需要显式调用 `Invoke` 方法，因为不存在 NULL 条件委托调用语法 `PropertyChanged?(e)`。</span><span class="sxs-lookup"><span data-stu-id="62a69-116">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="62a69-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="62a69-117">See also</span></span>

- [<span data-ttu-id="62a69-118">运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62a69-118">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="62a69-119">Visual Basic 编程指南</span><span class="sxs-lookup"><span data-stu-id="62a69-119">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="62a69-120">Visual Basic 语言参考</span><span class="sxs-lookup"><span data-stu-id="62a69-120">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
