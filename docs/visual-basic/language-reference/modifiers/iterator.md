---
title: "迭代器 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Iterator
helpviewer_keywords: Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 503d586c0515b4cb53f8ec5656e5fe765cc094a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iterator-visual-basic"></a><span data-ttu-id="52de0-102">迭代器 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52de0-102">Iterator (Visual Basic)</span></span>
<span data-ttu-id="52de0-103">指定函数或`Get`访问器是迭代器。</span><span class="sxs-lookup"><span data-stu-id="52de0-103">Specifies that a function or `Get` accessor is an iterator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52de0-104">备注</span><span class="sxs-lookup"><span data-stu-id="52de0-104">Remarks</span></span>  
 <span data-ttu-id="52de0-105">*迭代器*对集合执行自定义迭代。</span><span class="sxs-lookup"><span data-stu-id="52de0-105">An *iterator* performs a custom iteration over a collection.</span></span> <span data-ttu-id="52de0-106">迭代器使用[产生](../../../visual-basic/language-reference/statements/yield-statement.md)语句以返回一次的一个集合中的每个元素。</span><span class="sxs-lookup"><span data-stu-id="52de0-106">An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time.</span></span> <span data-ttu-id="52de0-107">当`Yield`达到语句，保留当前代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="52de0-107">When a `Yield` statement is reached, the current location in code is retained.</span></span> <span data-ttu-id="52de0-108">下次调用迭代器函数时，将从该位置重新开始执行。</span><span class="sxs-lookup"><span data-stu-id="52de0-108">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="52de0-109">迭代器可以为函数或作为实现`Get`的属性定义访问器。</span><span class="sxs-lookup"><span data-stu-id="52de0-109">An iterator can be implemented as a function or as a `Get` accessor of a property definition.</span></span> <span data-ttu-id="52de0-110">`Iterator`修饰符出现在声明中的迭代器函数或`Get`访问器。</span><span class="sxs-lookup"><span data-stu-id="52de0-110">The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="52de0-111">通过使用，从客户端代码调用迭代器[每个...下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="52de0-111">You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 <span data-ttu-id="52de0-112">迭代器函数的返回类型或`Get`访问器可以是<xref:System.Collections.IEnumerable>， <xref:System.Collections.Generic.IEnumerable%601>， <xref:System.Collections.IEnumerator>，或<xref:System.Collections.Generic.IEnumerator%601>。</span><span class="sxs-lookup"><span data-stu-id="52de0-112">The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="52de0-113">迭代器不能含有任何`ByRef`参数。</span><span class="sxs-lookup"><span data-stu-id="52de0-113">An iterator cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="52de0-114">不能在事件、实例构造函数、静态构造函数或静态析构函数中使用迭代器。</span><span class="sxs-lookup"><span data-stu-id="52de0-114">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="52de0-115">迭代器可以是一个匿名函数。</span><span class="sxs-lookup"><span data-stu-id="52de0-115">An iterator can be an anonymous function.</span></span> <span data-ttu-id="52de0-116">有关详细信息，请参阅[迭代器](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)。</span><span class="sxs-lookup"><span data-stu-id="52de0-116">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
 <span data-ttu-id="52de0-117">有关迭代器的详细信息，请参阅[迭代器](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)。</span><span class="sxs-lookup"><span data-stu-id="52de0-117">For more information about iterators, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="52de0-118">用法</span><span class="sxs-lookup"><span data-stu-id="52de0-118">Usage</span></span>  
 <span data-ttu-id="52de0-119">`Iterator` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="52de0-119">The `Iterator` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="52de0-120">Function 语句</span><span class="sxs-lookup"><span data-stu-id="52de0-120">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="52de0-121">Property 语句</span><span class="sxs-lookup"><span data-stu-id="52de0-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a><span data-ttu-id="52de0-122">示例</span><span class="sxs-lookup"><span data-stu-id="52de0-122">Example</span></span>  
 <span data-ttu-id="52de0-123">下面的示例演示一个迭代器函数。</span><span class="sxs-lookup"><span data-stu-id="52de0-123">The following example demonstrates an iterator function.</span></span> <span data-ttu-id="52de0-124">迭代器函数具有`Yield`语句内[为...下一步](../../../visual-basic/language-reference/statements/for-next-statement.md)循环。</span><span class="sxs-lookup"><span data-stu-id="52de0-124">The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="52de0-125">每次迭代[每个](../../../visual-basic/language-reference/statements/for-each-next-statement.md)语句体中的`Main`创建调用`Power`迭代器函数。</span><span class="sxs-lookup"><span data-stu-id="52de0-125">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="52de0-126">对迭代器函数的每个调用将继续到 `Yield` 语句的下一次执行（在 `For…Next` 循环的下一次迭代期间发生）。</span><span class="sxs-lookup"><span data-stu-id="52de0-126">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="52de0-127">示例</span><span class="sxs-lookup"><span data-stu-id="52de0-127">Example</span></span>  
 <span data-ttu-id="52de0-128">下面的示例演示一个作为迭代器的 `Get` 访问器。</span><span class="sxs-lookup"><span data-stu-id="52de0-128">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="52de0-129">`Iterator`修饰符为属性声明中。</span><span class="sxs-lookup"><span data-stu-id="52de0-129">The `Iterator` modifier is in the property declaration.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 <span data-ttu-id="52de0-130">有关其他示例，请参阅[迭代器](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)。</span><span class="sxs-lookup"><span data-stu-id="52de0-130">For additional examples, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52de0-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52de0-131">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>  
 [<span data-ttu-id="52de0-132">迭代器</span><span class="sxs-lookup"><span data-stu-id="52de0-132">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [<span data-ttu-id="52de0-133">Yield 语句</span><span class="sxs-lookup"><span data-stu-id="52de0-133">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
