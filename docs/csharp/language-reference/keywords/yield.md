---
title: yield 上下文关键字 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: 3e5bb96357293c42d4bd2161756260fd849cc099
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267788"
---
# <a name="yield-c-reference"></a><span data-ttu-id="7add8-102">yield（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="7add8-102">yield (C# Reference)</span></span>

<span data-ttu-id="7add8-103">如果你在语句中使用 `yield` [上下文关键字](index.md#contextual-keywords)，则意味着它在其中出现的方法、运算符或 `get` 访问器是迭代器。</span><span class="sxs-lookup"><span data-stu-id="7add8-103">When you use the `yield` [contextual keyword](index.md#contextual-keywords) in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="7add8-104">通过使用 `yield` 定义迭代器，可在实现自定义集合类型的 <xref:System.Collections.Generic.IEnumerator%601> 和 <xref:System.Collections.IEnumerable> 模式时无需其他显式类（保留枚举状态的类，有关示例，请参阅 <xref:System.Collections.IEnumerator>）。</span><span class="sxs-lookup"><span data-stu-id="7add8-104">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>

<span data-ttu-id="7add8-105">下面的示例演示了 `yield` 语句的两种形式。</span><span class="sxs-lookup"><span data-stu-id="7add8-105">The following example shows the two forms of the `yield` statement.</span></span>

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a><span data-ttu-id="7add8-106">备注</span><span class="sxs-lookup"><span data-stu-id="7add8-106">Remarks</span></span>

<span data-ttu-id="7add8-107">使用 `yield return` 语句可一次返回一个元素。</span><span class="sxs-lookup"><span data-stu-id="7add8-107">You use a `yield return` statement to return each element one at a time.</span></span>

<span data-ttu-id="7add8-108">可通过使用 [foreach](foreach-in.md) 语句或 LINQ 查询来使用从迭代器方法返回的序列。</span><span class="sxs-lookup"><span data-stu-id="7add8-108">The sequence returned from an iterator method can be consumed by using a [foreach](foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="7add8-109">`foreach` 循环的每次迭代都会调用迭代器方法。</span><span class="sxs-lookup"><span data-stu-id="7add8-109">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="7add8-110">迭代器方法运行到 `yield return` 语句时，会返回一个 `expression`，并保留当前在代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="7add8-110">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="7add8-111">下次调用迭代器函数时，将从该位置重新开始执行。</span><span class="sxs-lookup"><span data-stu-id="7add8-111">Execution is restarted from that location the next time that the iterator function is called.</span></span>

<span data-ttu-id="7add8-112">可以使用 `yield break` 语句来终止迭代。</span><span class="sxs-lookup"><span data-stu-id="7add8-112">You can use a `yield break` statement to end the iteration.</span></span>

<span data-ttu-id="7add8-113">有关迭代器的详细信息，请参阅[迭代器](../../iterators.md)。</span><span class="sxs-lookup"><span data-stu-id="7add8-113">For more information about iterators, see [Iterators](../../iterators.md).</span></span>

## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="7add8-114">迭代器方法和 get 访问器</span><span class="sxs-lookup"><span data-stu-id="7add8-114">Iterator methods and get accessors</span></span>

<span data-ttu-id="7add8-115">迭代器的声明必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="7add8-115">The declaration of an iterator must meet the following requirements:</span></span>

- <span data-ttu-id="7add8-116">返回类型必须为 <xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.IEnumerator> 或 <xref:System.Collections.Generic.IEnumerator%601>。</span><span class="sxs-lookup"><span data-stu-id="7add8-116">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

- <span data-ttu-id="7add8-117">声明不能有任何 [in](in-parameter-modifier.md)、[ref](ref.md) 或 [out](out-parameter-modifier.md) 参数。</span><span class="sxs-lookup"><span data-stu-id="7add8-117">The declaration can't have any [in](in-parameter-modifier.md) [ref](ref.md) or [out](out-parameter-modifier.md) parameters.</span></span>

<span data-ttu-id="7add8-118">返回 `yield` 或 <xref:System.Collections.IEnumerable> 的迭代器的 <xref:System.Collections.IEnumerator> 类型为 `object`。</span><span class="sxs-lookup"><span data-stu-id="7add8-118">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="7add8-119">如果迭代器返回 <xref:System.Collections.Generic.IEnumerable%601> 或 <xref:System.Collections.Generic.IEnumerator%601>，则必须将 `yield return` 语句中的表达式类型隐式转换为泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="7add8-119">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>

<span data-ttu-id="7add8-120">你不能在具有以下特点的方法中包含 `yield return` 或 `yield break` 语句：</span><span class="sxs-lookup"><span data-stu-id="7add8-120">You can't include a `yield return` or `yield break` statement in methods that have the following characteristics:</span></span>

- <span data-ttu-id="7add8-121">匿名方法。</span><span class="sxs-lookup"><span data-stu-id="7add8-121">Anonymous methods.</span></span> <span data-ttu-id="7add8-122">有关详细信息，请参阅[匿名方法](../../programming-guide/statements-expressions-operators/anonymous-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="7add8-122">For more information, see [Anonymous Methods](../../programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>

- <span data-ttu-id="7add8-123">包含不安全的块的方法。</span><span class="sxs-lookup"><span data-stu-id="7add8-123">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="7add8-124">有关详细信息，请参阅 [unsafe](unsafe.md)。</span><span class="sxs-lookup"><span data-stu-id="7add8-124">For more information, see [unsafe](unsafe.md).</span></span>

## <a name="exception-handling"></a><span data-ttu-id="7add8-125">异常处理</span><span class="sxs-lookup"><span data-stu-id="7add8-125">Exception handling</span></span>

<span data-ttu-id="7add8-126">不能将 `yield return` 语句置于 try-catch 块中。</span><span class="sxs-lookup"><span data-stu-id="7add8-126">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="7add8-127">可将 `yield return` 语句置于 try-finally 语句的 try 块中。</span><span class="sxs-lookup"><span data-stu-id="7add8-127">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>

<span data-ttu-id="7add8-128">可将 `yield break` 语句置于 try 块或 catch 块中，但不能将其置于 finally 块中。</span><span class="sxs-lookup"><span data-stu-id="7add8-128">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>

<span data-ttu-id="7add8-129">如果 `foreach` 主体（在迭代器方法之外）引发异常，则将执行迭代器方法中的 `finally` 块。</span><span class="sxs-lookup"><span data-stu-id="7add8-129">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="7add8-130">技术实现</span><span class="sxs-lookup"><span data-stu-id="7add8-130">Technical implementation</span></span>

<span data-ttu-id="7add8-131">以下代码从迭代器方法返回 `IEnumerable<string>`，然后遍历其元素。</span><span class="sxs-lookup"><span data-stu-id="7add8-131">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

<span data-ttu-id="7add8-132">调用 `MyIteratorMethod` 并不执行该方法的主体。</span><span class="sxs-lookup"><span data-stu-id="7add8-132">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="7add8-133">相反，该调用会将 `IEnumerable<string>` 返回到 `elements` 变量中。</span><span class="sxs-lookup"><span data-stu-id="7add8-133">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>

<span data-ttu-id="7add8-134">在 `foreach` 循环迭代时，将为 <xref:System.Collections.IEnumerator.MoveNext%2A> 调用 `elements` 方法。</span><span class="sxs-lookup"><span data-stu-id="7add8-134">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="7add8-135">此调用将执行 `MyIteratorMethod` 的主体，直至到达下一个 `yield return` 语句。</span><span class="sxs-lookup"><span data-stu-id="7add8-135">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="7add8-136">`yield return` 语句返回的表达式不仅决定了循环体使用的 `element` 变量值，还决定了 `elements` 的 <xref:System.Collections.Generic.IEnumerator%601.Current%2A> 属性（它是 `IEnumerable<string>`）。</span><span class="sxs-lookup"><span data-stu-id="7add8-136">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of `elements`, which is an `IEnumerable<string>`.</span></span>

<span data-ttu-id="7add8-137">在 `foreach` 循环的每个后续迭代中，迭代器主体的执行将从它暂停的位置继续，直至到达 `yield return` 语句后才会停止。</span><span class="sxs-lookup"><span data-stu-id="7add8-137">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="7add8-138">在到达迭代器方法的结尾或 `foreach` 语句时，`yield break` 循环便已完成。</span><span class="sxs-lookup"><span data-stu-id="7add8-138">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>

## <a name="example"></a><span data-ttu-id="7add8-139">示例</span><span class="sxs-lookup"><span data-stu-id="7add8-139">Example</span></span>

<span data-ttu-id="7add8-140">下面的示例包含一个位于 `yield return` 循环内的 `for` 语句。</span><span class="sxs-lookup"><span data-stu-id="7add8-140">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="7add8-141">`Main` 方法中的 `foreach` 语句体的每次迭代都会创建对 `Power` 迭代器函数的调用。</span><span class="sxs-lookup"><span data-stu-id="7add8-141">Each iteration of the `foreach` statement body in the `Main` method creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="7add8-142">对迭代器函数的每个调用将继续到 `yield return` 语句的下一次执行（在 `for` 循环的下一次迭代期间发生）。</span><span class="sxs-lookup"><span data-stu-id="7add8-142">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>

<span data-ttu-id="7add8-143">迭代器方法的返回类型是 <xref:System.Collections.IEnumerable>（一种迭代器接口类型）。</span><span class="sxs-lookup"><span data-stu-id="7add8-143">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="7add8-144">当调用迭代器方法时，它将返回一个包含数字幂的可枚举对象。</span><span class="sxs-lookup"><span data-stu-id="7add8-144">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a><span data-ttu-id="7add8-145">示例</span><span class="sxs-lookup"><span data-stu-id="7add8-145">Example</span></span>

<span data-ttu-id="7add8-146">下面的示例演示一个作为迭代器的 `get` 访问器。</span><span class="sxs-lookup"><span data-stu-id="7add8-146">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="7add8-147">在该示例中，每个 `yield return` 语句返回一个用户定义的类的实例。</span><span class="sxs-lookup"><span data-stu-id="7add8-147">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a><span data-ttu-id="7add8-148">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="7add8-148">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7add8-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="7add8-149">See also</span></span>

- [<span data-ttu-id="7add8-150">C# 参考</span><span class="sxs-lookup"><span data-stu-id="7add8-150">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="7add8-151">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7add8-151">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7add8-152">foreach, in</span><span class="sxs-lookup"><span data-stu-id="7add8-152">foreach, in</span></span>](foreach-in.md)
- [<span data-ttu-id="7add8-153">迭代器</span><span class="sxs-lookup"><span data-stu-id="7add8-153">Iterators</span></span>](../../iterators.md)
