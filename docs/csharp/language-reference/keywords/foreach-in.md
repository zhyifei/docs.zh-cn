---
title: "foreach，in（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: 29
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
ms.openlocfilehash: aed1d4f086f0b1334df750fd912d20d66326a043
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="3a0b5-102">foreach，in（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3a0b5-102">foreach, in (C# Reference)</span></span>
<span data-ttu-id="3a0b5-103">`foreach` 语句针对实现 <xref:System.Collections.IEnumerable?displayProperty=fullName> 或 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 接口的数组或集合中的每个元素重复一组嵌入语句。</span><span class="sxs-lookup"><span data-stu-id="3a0b5-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=fullName> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> interface.</span></span> <span data-ttu-id="3a0b5-104">`foreach` 语句用于循环访问集合以获取所需信息，但不用于添加或删除源集合中的项，以避免不可预知的副作用。</span><span class="sxs-lookup"><span data-stu-id="3a0b5-104">The `foreach` statement is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="3a0b5-105">如果需要添加或删除源集合中的项，请使用 [for](../../../csharp/language-reference/keywords/for.md) 循环。</span><span class="sxs-lookup"><span data-stu-id="3a0b5-105">If you need to add or remove items from the source collection, use a [for](../../../csharp/language-reference/keywords/for.md) loop.</span></span>  
  
 <span data-ttu-id="3a0b5-106">为数组或集合中的每个元素继续执行嵌入的语句。</span><span class="sxs-lookup"><span data-stu-id="3a0b5-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="3a0b5-107">为集合中的所有元素完成迭代后，控制将传递给 `foreach` 块之后的下一语句。</span><span class="sxs-lookup"><span data-stu-id="3a0b5-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>  
  
 <span data-ttu-id="3a0b5-108">在 `foreach` 块中的任何点上，可以使用[中断](../../../csharp/language-reference/keywords/break.md)关键字中断该循环，或者可以使用[继续](../../../csharp/language-reference/keywords/continue.md)关键字单步执行到循环中的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="3a0b5-108">At any point within the `foreach` block, you can break out of the loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or step to the next iteration in the loop by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span>  
  
 <span data-ttu-id="3a0b5-109">`foreach` 循环还可以通过 [goto](../../../csharp/language-reference/keywords/goto.md)、[return](../../../csharp/language-reference/keywords/return.md) 或 [throw](../../../csharp/language-reference/keywords/throw.md) 语句退出。</span><span class="sxs-lookup"><span data-stu-id="3a0b5-109">A `foreach` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
 <span data-ttu-id="3a0b5-110">有关 `foreach` 关键字和代码示例的详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="3a0b5-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  
  
 [<span data-ttu-id="3a0b5-111">对数组使用 foreach</span><span class="sxs-lookup"><span data-stu-id="3a0b5-111">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
 [<span data-ttu-id="3a0b5-112">如何：使用 foreach 访问集合类</span><span class="sxs-lookup"><span data-stu-id="3a0b5-112">How to: Access a Collection Class with foreach</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  
  
## <a name="example"></a><span data-ttu-id="3a0b5-113">示例</span><span class="sxs-lookup"><span data-stu-id="3a0b5-113">Example</span></span>  
 <span data-ttu-id="3a0b5-114">下面的代码演示了三个示例：</span><span class="sxs-lookup"><span data-stu-id="3a0b5-114">The following code shows three examples:</span></span>  
  
-   <span data-ttu-id="3a0b5-115">显示整数数组内容的典型 `foreach` 循环</span><span class="sxs-lookup"><span data-stu-id="3a0b5-115">a typical `foreach` loop that displays the contents of an array of integers</span></span>  
  
-   <span data-ttu-id="3a0b5-116">执行相同操作的 [for](../../../csharp/language-reference/keywords/for.md) 循环</span><span class="sxs-lookup"><span data-stu-id="3a0b5-116">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>  
  
-   <span data-ttu-id="3a0b5-117">维护数组中元素数计数的 `foreach` 循环</span><span class="sxs-lookup"><span data-stu-id="3a0b5-117">a `foreach` loop that maintains a count of the number of elements in the array</span></span>  
  
 <span data-ttu-id="3a0b5-118">[!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3a0b5-118">[!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3a0b5-119">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3a0b5-119">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3a0b5-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a0b5-120">See Also</span></span>  
 <span data-ttu-id="3a0b5-121">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3a0b5-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3a0b5-122">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3a0b5-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3a0b5-123">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="3a0b5-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="3a0b5-124">[迭代语句](../../../csharp/language-reference/keywords/iteration-statements.md) </span><span class="sxs-lookup"><span data-stu-id="3a0b5-124">[Iteration Statements](../../../csharp/language-reference/keywords/iteration-statements.md) </span></span>  
 [<span data-ttu-id="3a0b5-125">for</span><span class="sxs-lookup"><span data-stu-id="3a0b5-125">for</span></span>](../../../csharp/language-reference/keywords/for.md)

