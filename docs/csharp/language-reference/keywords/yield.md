---
title: "yield（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- yield
- yield_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
caps.latest.revision: 46
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eb55fd5b1ade48316516cda83633935abbf8dcf9
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="yield-c-reference"></a><span data-ttu-id="ca531-102">yield（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ca531-102">yield (C# Reference)</span></span>
<span data-ttu-id="ca531-103">如果你在语句中使用 `yield` 关键字，则意味着它在其中出现的方法、运算符或 `get` 访问器是迭代器。</span><span class="sxs-lookup"><span data-stu-id="ca531-103">When you use the `yield` keyword in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="ca531-104">通过使用 `yield` 定义迭代器，可在实现自定义集合类型的 <xref:System.Collections.Generic.IEnumerator%601> 和 <xref:System.Collections.IEnumerable> 模式时无需其他显式类（保留枚举状态的类，有关示例，请参阅 <xref:System.Collections.IEnumerator>）。</span><span class="sxs-lookup"><span data-stu-id="ca531-104">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>  
  
 <span data-ttu-id="ca531-105">下面的示例演示了 `yield` 语句的两种形式。</span><span class="sxs-lookup"><span data-stu-id="ca531-105">The following example shows the two forms of the `yield` statement.</span></span>  
  
```csharp  
yield return <expression>;  
yield break;  
```  
  
## <a name="remarks"></a><span data-ttu-id="ca531-106">备注</span><span class="sxs-lookup"><span data-stu-id="ca531-106">Remarks</span></span>  
 <span data-ttu-id="ca531-107">使用 `yield return` 语句可一次返回一个元素。</span><span class="sxs-lookup"><span data-stu-id="ca531-107">You use a `yield return` statement to return each element one at a time.</span></span>  
  
 <span data-ttu-id="ca531-108">通过 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 语句或 LINQ 查询来使用迭代器方法。</span><span class="sxs-lookup"><span data-stu-id="ca531-108">You consume an iterator method by using a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="ca531-109">`foreach` 循环的每次迭代都会调用迭代器方法。</span><span class="sxs-lookup"><span data-stu-id="ca531-109">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="ca531-110">迭代器方法运行到 `yield return` 语句时，会返回一个 `expression`，并保留当前在代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="ca531-110">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="ca531-111">下次调用迭代器函数时，将从该位置重新开始执行。</span><span class="sxs-lookup"><span data-stu-id="ca531-111">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="ca531-112">可以使用 `yield break` 语句来终止迭代。</span><span class="sxs-lookup"><span data-stu-id="ca531-112">You can use a `yield break` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="ca531-113">有关迭代器的详细信息，请参阅[迭代器](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)。</span><span class="sxs-lookup"><span data-stu-id="ca531-113">For more information about iterators, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="ca531-114">迭代器方法和 get 访问器</span><span class="sxs-lookup"><span data-stu-id="ca531-114">Iterator Methods and get Accessors</span></span>  
 <span data-ttu-id="ca531-115">迭代器的声明必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="ca531-115">The declaration of an iterator must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="ca531-116">返回类型必须为 <xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.IEnumerator> 或 <xref:System.Collections.Generic.IEnumerator%601>。</span><span class="sxs-lookup"><span data-stu-id="ca531-116">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="ca531-117">声明不能有任何 [ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out.md) 参数。</span><span class="sxs-lookup"><span data-stu-id="ca531-117">The declaration can't have any [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameters.</span></span>  
  
 <span data-ttu-id="ca531-118">返回 `yield` 或 <xref:System.Collections.IEnumerable> 的迭代器的 <xref:System.Collections.IEnumerator> 类型为 `object`。</span><span class="sxs-lookup"><span data-stu-id="ca531-118">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="ca531-119">如果迭代器返回 <xref:System.Collections.Generic.IEnumerable%601> 或 <xref:System.Collections.Generic.IEnumerator%601>，则必须将 `yield return` 语句中的表达式类型隐式转换为泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="ca531-119">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>  
  
 <span data-ttu-id="ca531-120">你不能在具有以下特点的方法中包含 `yield return` 或 `yield break` 语句：</span><span class="sxs-lookup"><span data-stu-id="ca531-120">You can't include a `yield return` or `yield break` statement in methods that have the following characteristics:</span></span>  
  
-   <span data-ttu-id="ca531-121">匿名方法。</span><span class="sxs-lookup"><span data-stu-id="ca531-121">Anonymous methods.</span></span> <span data-ttu-id="ca531-122">有关详细信息，请参阅[匿名方法](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="ca531-122">For more information, see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
-   <span data-ttu-id="ca531-123">包含不安全的块的方法。</span><span class="sxs-lookup"><span data-stu-id="ca531-123">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="ca531-124">有关详细信息，请参阅 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)。</span><span class="sxs-lookup"><span data-stu-id="ca531-124">For more information, see [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="ca531-125">异常处理</span><span class="sxs-lookup"><span data-stu-id="ca531-125">Exception Handling</span></span>  
 <span data-ttu-id="ca531-126">不能将 `yield return` 语句置于 try-catch 块中。</span><span class="sxs-lookup"><span data-stu-id="ca531-126">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="ca531-127">可将 `yield return` 语句置于 try-finally 语句的 try 块中。</span><span class="sxs-lookup"><span data-stu-id="ca531-127">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>  
  
 <span data-ttu-id="ca531-128">可将 `yield break` 语句置于 try 块或 catch 块中，但不能将其置于 finally 块中。</span><span class="sxs-lookup"><span data-stu-id="ca531-128">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>  
  
 <span data-ttu-id="ca531-129">如果 `foreach` 主体（在迭代器方法之外）引发异常，则将执行迭代器方法中的 `finally` 块。</span><span class="sxs-lookup"><span data-stu-id="ca531-129">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="ca531-130">技术实现</span><span class="sxs-lookup"><span data-stu-id="ca531-130">Technical Implementation</span></span>  
 <span data-ttu-id="ca531-131">以下代码从迭代器方法返回 `IEnumerable<string>`，然后遍历其元素。</span><span class="sxs-lookup"><span data-stu-id="ca531-131">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>  
  
```csharp  
IEnumerable<string> elements = MyIteratorMethod();  
foreach (string element in elements)  
{  
   ...  
}  
```  
  
 <span data-ttu-id="ca531-132">调用 `MyIteratorMethod` 并不执行该方法的主体。</span><span class="sxs-lookup"><span data-stu-id="ca531-132">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="ca531-133">相反，该调用会将 `IEnumerable<string>` 返回到 `elements` 变量中。</span><span class="sxs-lookup"><span data-stu-id="ca531-133">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="ca531-134">在 `foreach` 循环迭代时，将为 <xref:System.Collections.IEnumerator.MoveNext%2A> 调用 `elements` 方法。</span><span class="sxs-lookup"><span data-stu-id="ca531-134">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="ca531-135">此调用将执行 `MyIteratorMethod` 的主体，直至到达下一个 `yield return` 语句。</span><span class="sxs-lookup"><span data-stu-id="ca531-135">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="ca531-136">`yield return` 语句返回的表达式不仅决定了循环体使用的 `element` 变量值，还决定了元素的 <xref:System.Collections.Generic.IEnumerator%601.Current%2A> 属性（它是 `IEnumerable<string>`）。</span><span class="sxs-lookup"><span data-stu-id="ca531-136">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable<string>`.</span></span>  
  
 <span data-ttu-id="ca531-137">在 `foreach` 循环的每个后续迭代中，迭代器主体的执行将从它暂停的位置继续，直至到达 `yield return` 语句后才会停止。</span><span class="sxs-lookup"><span data-stu-id="ca531-137">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="ca531-138">在到达迭代器方法的结尾或 `foreach` 语句时，`yield break` 循环便已完成。</span><span class="sxs-lookup"><span data-stu-id="ca531-138">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca531-139">示例</span><span class="sxs-lookup"><span data-stu-id="ca531-139">Example</span></span>  
 <span data-ttu-id="ca531-140">下面的示例包含一个位于 `yield return` 循环内的 `for` 语句。</span><span class="sxs-lookup"><span data-stu-id="ca531-140">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="ca531-141">`foreach` 中的 `Process` 语句体的每次迭代都会创建对 `Power` 迭代器函数的调用。</span><span class="sxs-lookup"><span data-stu-id="ca531-141">Each iteration of the `foreach` statement body in `Process` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="ca531-142">对迭代器函数的每个调用将继续到 `yield return` 语句的下一次执行（在 `for` 循环的下一次迭代期间发生）。</span><span class="sxs-lookup"><span data-stu-id="ca531-142">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>  
  
 <span data-ttu-id="ca531-143">迭代器方法的返回类型是 <xref:System.Collections.IEnumerable>（一种迭代器接口类型）。</span><span class="sxs-lookup"><span data-stu-id="ca531-143">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="ca531-144">当调用迭代器方法时，它将返回一个包含数字幂的可枚举对象。</span><span class="sxs-lookup"><span data-stu-id="ca531-144">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 <span data-ttu-id="ca531-145">[!code-cs[csrefKeywordsContextual#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ca531-145">[!code-cs[csrefKeywordsContextual#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca531-146">示例</span><span class="sxs-lookup"><span data-stu-id="ca531-146">Example</span></span>  
 <span data-ttu-id="ca531-147">下面的示例演示一个作为迭代器的 `get` 访问器。</span><span class="sxs-lookup"><span data-stu-id="ca531-147">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="ca531-148">在该示例中，每个 `yield return` 语句返回一个用户定义的类的实例。</span><span class="sxs-lookup"><span data-stu-id="ca531-148">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>  
  
 <span data-ttu-id="ca531-149">[!code-cs[csrefKeywordsContextual#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ca531-149">[!code-cs[csrefKeywordsContextual#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ca531-150">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ca531-150">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ca531-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca531-151">See Also</span></span>  
 <span data-ttu-id="ca531-152">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ca531-152">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ca531-153">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ca531-153">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ca531-154">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span><span class="sxs-lookup"><span data-stu-id="ca531-154">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span></span>  
 [<span data-ttu-id="ca531-155">迭代器</span><span class="sxs-lookup"><span data-stu-id="ca531-155">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)

