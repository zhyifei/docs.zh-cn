---
title: Yield 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: 72a8dafdc5aa834a644e1e70a309cfc0827b5fdf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352724"
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="0673e-102">Yield 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0673e-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="0673e-103">Sends the next element of a collection to a `For Each...Next` statement.</span><span class="sxs-lookup"><span data-stu-id="0673e-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0673e-104">语法</span><span class="sxs-lookup"><span data-stu-id="0673e-104">Syntax</span></span>  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a><span data-ttu-id="0673e-105">参数</span><span class="sxs-lookup"><span data-stu-id="0673e-105">Parameters</span></span>  
  
|<span data-ttu-id="0673e-106">术语</span><span class="sxs-lookup"><span data-stu-id="0673e-106">Term</span></span>|<span data-ttu-id="0673e-107">定义</span><span class="sxs-lookup"><span data-stu-id="0673e-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="0673e-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="0673e-108">Required.</span></span> <span data-ttu-id="0673e-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span><span class="sxs-lookup"><span data-stu-id="0673e-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0673e-110">备注</span><span class="sxs-lookup"><span data-stu-id="0673e-110">Remarks</span></span>  
 <span data-ttu-id="0673e-111">The `Yield` statement returns one element of a collection at a time.</span><span class="sxs-lookup"><span data-stu-id="0673e-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="0673e-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span><span class="sxs-lookup"><span data-stu-id="0673e-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="0673e-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span><span class="sxs-lookup"><span data-stu-id="0673e-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="0673e-114">Each iteration of the `For Each` loop calls the iterator function.</span><span class="sxs-lookup"><span data-stu-id="0673e-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="0673e-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span><span class="sxs-lookup"><span data-stu-id="0673e-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="0673e-116">下次调用迭代器函数时，将从该位置重新开始执行。</span><span class="sxs-lookup"><span data-stu-id="0673e-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="0673e-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span><span class="sxs-lookup"><span data-stu-id="0673e-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="0673e-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span><span class="sxs-lookup"><span data-stu-id="0673e-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="0673e-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span><span class="sxs-lookup"><span data-stu-id="0673e-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="0673e-120">For more information about iterator functions and `Get` accessors, see [Iterators](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="0673e-120">For more information about iterator functions and `Get` accessors, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="0673e-121">Iterator Functions and Get Accessors</span><span class="sxs-lookup"><span data-stu-id="0673e-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="0673e-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span><span class="sxs-lookup"><span data-stu-id="0673e-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
- <span data-ttu-id="0673e-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span><span class="sxs-lookup"><span data-stu-id="0673e-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
- <span data-ttu-id="0673e-124">返回类型必须为 <xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.IEnumerator> 或 <xref:System.Collections.Generic.IEnumerator%601>。</span><span class="sxs-lookup"><span data-stu-id="0673e-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
- <span data-ttu-id="0673e-125">It cannot have any `ByRef` parameters.</span><span class="sxs-lookup"><span data-stu-id="0673e-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="0673e-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span><span class="sxs-lookup"><span data-stu-id="0673e-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="0673e-127">An iterator function can be an anonymous function.</span><span class="sxs-lookup"><span data-stu-id="0673e-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="0673e-128">有关详细信息，请参阅[迭代器](../../programming-guide/concepts/iterators.md)。</span><span class="sxs-lookup"><span data-stu-id="0673e-128">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="0673e-129">异常处理</span><span class="sxs-lookup"><span data-stu-id="0673e-129">Exception Handling</span></span>  
 <span data-ttu-id="0673e-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0673e-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="0673e-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span><span class="sxs-lookup"><span data-stu-id="0673e-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="0673e-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span><span class="sxs-lookup"><span data-stu-id="0673e-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="0673e-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span><span class="sxs-lookup"><span data-stu-id="0673e-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="0673e-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span><span class="sxs-lookup"><span data-stu-id="0673e-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="0673e-135">技术实现</span><span class="sxs-lookup"><span data-stu-id="0673e-135">Technical Implementation</span></span>  
 <span data-ttu-id="0673e-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="0673e-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="0673e-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span><span class="sxs-lookup"><span data-stu-id="0673e-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="0673e-138">相反，该调用会将 `IEnumerable(Of String)` 返回到 `elements` 变量中。</span><span class="sxs-lookup"><span data-stu-id="0673e-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="0673e-139">在 `For Each` 循环迭代时，将为 <xref:System.Collections.IEnumerator.MoveNext%2A> 调用 `elements` 方法。</span><span class="sxs-lookup"><span data-stu-id="0673e-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="0673e-140">此调用将执行 `MyIteratorFunction` 的主体，直至到达下一个 `Yield` 语句。</span><span class="sxs-lookup"><span data-stu-id="0673e-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="0673e-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="0673e-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="0673e-142">在 `For Each` 循环的每个后续迭代中，迭代器主体的执行将从它暂停的位置继续，直至到达 `Yield` 语句后才会停止。</span><span class="sxs-lookup"><span data-stu-id="0673e-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="0673e-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span><span class="sxs-lookup"><span data-stu-id="0673e-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0673e-144">示例</span><span class="sxs-lookup"><span data-stu-id="0673e-144">Example</span></span>  
 <span data-ttu-id="0673e-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span><span class="sxs-lookup"><span data-stu-id="0673e-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="0673e-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span><span class="sxs-lookup"><span data-stu-id="0673e-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="0673e-147">对迭代器函数的每个调用将继续到 `Yield` 语句的下一次执行（在 `For…Next` 循环的下一次迭代期间发生）。</span><span class="sxs-lookup"><span data-stu-id="0673e-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="0673e-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span><span class="sxs-lookup"><span data-stu-id="0673e-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="0673e-149">当调用迭代器方法时，它将返回一个包含数字幂的可枚举对象。</span><span class="sxs-lookup"><span data-stu-id="0673e-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="0673e-150">示例</span><span class="sxs-lookup"><span data-stu-id="0673e-150">Example</span></span>  
 <span data-ttu-id="0673e-151">下面的示例演示一个作为迭代器的 `Get` 访问器。</span><span class="sxs-lookup"><span data-stu-id="0673e-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="0673e-152">The property declaration includes an `Iterator` modifier.</span><span class="sxs-lookup"><span data-stu-id="0673e-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="0673e-153">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="0673e-153">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0673e-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="0673e-154">See also</span></span>

- [<span data-ttu-id="0673e-155">语句</span><span class="sxs-lookup"><span data-stu-id="0673e-155">Statements</span></span>](../../../visual-basic/language-reference/statements/index.md)
