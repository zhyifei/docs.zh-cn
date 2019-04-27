---
title: 迭代器 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 499949d1f4c20e1f465355bd076ba39f1496779b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920713"
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="517b1-102">迭代器 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="517b1-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="517b1-103">指定的函数或`Get`访问器是一个迭代器。</span><span class="sxs-lookup"><span data-stu-id="517b1-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="517b1-104">备注</span><span class="sxs-lookup"><span data-stu-id="517b1-104">Remarks</span></span>  
 <span data-ttu-id="517b1-105">*迭代器*对集合执行自定义迭代。</span><span class="sxs-lookup"><span data-stu-id="517b1-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="517b1-106">迭代器使用[产生](../../../visual-basic/language-reference/statements/yield-statement.md)语句每次在集合中返回每个元素。</span><span class="sxs-lookup"><span data-stu-id="517b1-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="517b1-107">当`Yield`达到语句时，保留当前代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="517b1-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="517b1-108">下次调用迭代器函数时，将从该位置重新开始执行。</span><span class="sxs-lookup"><span data-stu-id="517b1-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="517b1-109">一个迭代器，可以为函数或作为实现`Get`的属性定义访问器。</span><span class="sxs-lookup"><span data-stu-id="517b1-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="517b1-110">`Iterator`修饰符将出现在迭代器函数的声明或`Get`访问器。</span><span class="sxs-lookup"><span data-stu-id="517b1-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="517b1-111">通过使用从客户端代码调用迭代器[为每个...下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="517b1-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="517b1-112">迭代器函数的返回类型或`Get`访问器均可<xref:System.Collections.IEnumerable>， <xref:System.Collections.Generic.IEnumerable%601>， <xref:System.Collections.IEnumerator>，或<xref:System.Collections.Generic.IEnumerator%601>。</span><span class="sxs-lookup"><span data-stu-id="517b1-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="517b1-113">一个迭代器不能有任何`ByRef`参数。</span><span class="sxs-lookup"><span data-stu-id="517b1-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="517b1-114">不能在事件、实例构造函数、静态构造函数或静态析构函数中使用迭代器。</span><span class="sxs-lookup"><span data-stu-id="517b1-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="517b1-115">一个迭代器，可以是匿名函数。</span><span class="sxs-lookup"><span data-stu-id="517b1-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="517b1-116">有关更多信息，请参见 [迭代器](../../programming-guide/concepts/iterators.md)。</span><span class="sxs-lookup"><span data-stu-id="517b1-116">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="517b1-117">用法</span><span class="sxs-lookup"><span data-stu-id="517b1-117">Usage</span></span>  
 <span data-ttu-id="517b1-118">`Iterator` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="517b1-118">The `Iterator` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="517b1-119">Function 语句</span><span class="sxs-lookup"><span data-stu-id="517b1-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="517b1-120">Property 语句</span><span class="sxs-lookup"><span data-stu-id="517b1-120">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="517b1-121">示例</span><span class="sxs-lookup"><span data-stu-id="517b1-121">Example</span></span>  
 <span data-ttu-id="517b1-122">下面的示例演示一个迭代器函数。</span><span class="sxs-lookup"><span data-stu-id="517b1-122">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="517b1-123">迭代器函数具有`Yield`内的语句[为...下一步](../../../visual-basic/language-reference/statements/for-next-statement.md)循环。</span><span class="sxs-lookup"><span data-stu-id="517b1-123">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="517b1-124">每次迭代[为每个](../../../visual-basic/language-reference/statements/for-each-next-statement.md)在语句体`Main`会调用`Power`迭代器函数。</span><span class="sxs-lookup"><span data-stu-id="517b1-124">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="517b1-125">对迭代器函数的每个调用将继续到 `Yield` 语句的下一次执行（在 `For…Next` 循环的下一次迭代期间发生）。</span><span class="sxs-lookup"><span data-stu-id="517b1-125">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="517b1-126">示例</span><span class="sxs-lookup"><span data-stu-id="517b1-126">Example</span></span>  
 <span data-ttu-id="517b1-127">下面的示例演示一个作为迭代器的 `Get` 访问器。</span><span class="sxs-lookup"><span data-stu-id="517b1-127">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="517b1-128">`Iterator`修饰符是属性声明中。</span><span class="sxs-lookup"><span data-stu-id="517b1-128">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="517b1-129">有关其他示例，请参阅[迭代器](../../programming-guide/concepts/iterators.md)。</span><span class="sxs-lookup"><span data-stu-id="517b1-129">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="517b1-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="517b1-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [<span data-ttu-id="517b1-131">迭代器</span><span class="sxs-lookup"><span data-stu-id="517b1-131">Iterators</span></span>](../../programming-guide/concepts/iterators.md)
- [<span data-ttu-id="517b1-132">Yield 语句</span><span class="sxs-lookup"><span data-stu-id="517b1-132">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
