---
title: "foreach，in（C# 参考）"
ms.date: 10/11/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: "29"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d5601682d53a01ff07aba7e416aa81ded4c03e4e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="ae6d3-102">foreach，in（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ae6d3-102">foreach, in (C# Reference)</span></span>
<span data-ttu-id="ae6d3-103">`foreach` 语句针对实现 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 或 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 接口的数组或集合中的每个元素重复一组嵌入语句。</span><span class="sxs-lookup"><span data-stu-id="ae6d3-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="ae6d3-104">`foreach` 语句用于循环访问集合以获取所需信息，但不用于添加或删除源集合中的项，以避免不可预知的副作用。</span><span class="sxs-lookup"><span data-stu-id="ae6d3-104">The `foreach` statement is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="ae6d3-105">如果需要添加或删除源集合中的项，请使用 [for](for.md) 循环。</span><span class="sxs-lookup"><span data-stu-id="ae6d3-105">If you need to add or remove items from the source collection, use a [for](for.md) loop.</span></span>
  
 <span data-ttu-id="ae6d3-106">为数组或集合中的每个元素继续执行嵌入的语句。</span><span class="sxs-lookup"><span data-stu-id="ae6d3-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="ae6d3-107">为集合中的所有元素完成迭代后，控制将传递给 `foreach` 块之后的下一语句。</span><span class="sxs-lookup"><span data-stu-id="ae6d3-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>
  
 <span data-ttu-id="ae6d3-108">在 `foreach` 块中的任何点上，可以使用[中断](break.md)关键字中断该循环，或者可以使用[继续](continue.md)关键字单步执行到循环中的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="ae6d3-108">At any point within the `foreach` block, you can break out of the loop by using the [break](break.md) keyword, or step to the next iteration in the loop by using the [continue](continue.md) keyword.</span></span>

 <span data-ttu-id="ae6d3-109">`foreach` 循环还可以通过 [goto](goto.md)、[return](return.md) 或 [throw](throw.md) 语句退出。</span><span class="sxs-lookup"><span data-stu-id="ae6d3-109">A `foreach` loop can also be exited by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

 <span data-ttu-id="ae6d3-110">有关 `foreach` 关键字和代码示例的详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="ae6d3-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  

 [<span data-ttu-id="ae6d3-111">对数组使用 foreach</span><span class="sxs-lookup"><span data-stu-id="ae6d3-111">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [<span data-ttu-id="ae6d3-112">如何：使用 foreach 访问集合类</span><span class="sxs-lookup"><span data-stu-id="ae6d3-112">How to: Access a Collection Class with foreach</span></span>](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a><span data-ttu-id="ae6d3-113">示例</span><span class="sxs-lookup"><span data-stu-id="ae6d3-113">Example</span></span>
 <span data-ttu-id="ae6d3-114">下面的代码演示三个示例。</span><span class="sxs-lookup"><span data-stu-id="ae6d3-114">The following code shows three examples.</span></span>

> [!TIP]
> <span data-ttu-id="ae6d3-115">你可以修改这些示例试验的语法，然后重更类似于使用情况的不同用法。</span><span class="sxs-lookup"><span data-stu-id="ae6d3-115">You can modify the examples to experiment with the syntax and try different usages that are more similar to your use case.</span></span> <span data-ttu-id="ae6d3-116">按"运行"以运行该代码，然后编辑并再次按"运行"。</span><span class="sxs-lookup"><span data-stu-id="ae6d3-116">Press "Run" to run the code, then edit and press "Run" again.</span></span>

-   <span data-ttu-id="ae6d3-117">显示整数数组内容的典型 `foreach` 循环</span><span class="sxs-lookup"><span data-stu-id="ae6d3-117">a typical `foreach` loop that displays the contents of an array of integers</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   <span data-ttu-id="ae6d3-118">执行相同操作的 [for](../../../csharp/language-reference/keywords/for.md) 循环</span><span class="sxs-lookup"><span data-stu-id="ae6d3-118">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   <span data-ttu-id="ae6d3-119">维护数组中元素数计数的 `foreach` 循环</span><span class="sxs-lookup"><span data-stu-id="ae6d3-119">a `foreach` loop that maintains a count of the number of elements in the array</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a><span data-ttu-id="ae6d3-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ae6d3-120">C# Language Specification</span></span>
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ae6d3-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae6d3-121">See Also</span></span>  

[<span data-ttu-id="ae6d3-122">C# 参考</span><span class="sxs-lookup"><span data-stu-id="ae6d3-122">C# Reference</span></span>](../index.md)

[<span data-ttu-id="ae6d3-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ae6d3-123">C# Programming Guide</span></span>](../../programming-guide/index.md)

[<span data-ttu-id="ae6d3-124">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="ae6d3-124">C# Keywords</span></span>](index.md)

[<span data-ttu-id="ae6d3-125">迭代语句</span><span class="sxs-lookup"><span data-stu-id="ae6d3-125">Iteration Statements</span></span>](iteration-statements.md)

[<span data-ttu-id="ae6d3-126">for</span><span class="sxs-lookup"><span data-stu-id="ae6d3-126">for</span></span>](for.md)
