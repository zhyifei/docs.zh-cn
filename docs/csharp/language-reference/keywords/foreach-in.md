---
title: foreach，in（C# 参考）
ms.date: 06/29/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: d3ce1122c54c14b1baf35641f28d062a2855d335
ms.sourcegitcommit: 736ec4d3e2c74895b47a0d36126657b95da383c9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2018
ms.locfileid: "37140263"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="9e488-102">foreach，in（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="9e488-102">foreach, in (C# Reference)</span></span>

<span data-ttu-id="9e488-103">`foreach` 语句为类型实例中实现 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 或 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 接口的每个元素执行语句或语句块。</span><span class="sxs-lookup"><span data-stu-id="9e488-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="9e488-104">`foreach` 语句不局限于这些类型，它可应用于满足以下条件的任何类型的实例：</span><span class="sxs-lookup"><span data-stu-id="9e488-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="9e488-105">具有公共无参数 `GetEnumerator` 方法，其返回类型为类、结构或接口类型。</span><span class="sxs-lookup"><span data-stu-id="9e488-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="9e488-106">`GetEnumerator` 方法的返回类型具有公共 `Current` 属性和公共无参数 `MoveNext` 方法（其返回类型为 <xref:System.Boolean>）。</span><span class="sxs-lookup"><span data-stu-id="9e488-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="9e488-107">在 `foreach` 语句块中的任何点上，可以使用 [break](break.md) 语句中断循环，或者可以使用 [continue](continue.md) 语句继续执行到循环中的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="9e488-107">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="9e488-108">还可以使用 [goto](goto.md)、[return](return.md) 或 [throw](throw.md) 语句退出 `foreach` 循环。</span><span class="sxs-lookup"><span data-stu-id="9e488-108">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="examples"></a><span data-ttu-id="9e488-109">示例</span><span class="sxs-lookup"><span data-stu-id="9e488-109">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="9e488-110">以下示例介绍 `foreach` 语句的使用，其中包含实现 <xref:System.Collections.Generic.IEnumerable%601> 接口的 <xref:System.Collections.Generic.List%601> 类型的实例：</span><span class="sxs-lookup"><span data-stu-id="9e488-110">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="9e488-111">下一个示例使用 `foreach` 语句，其中包含 <xref:System.Span%601?displayProperty=nameWithType> 类型的实例，该实例不实现任何接口：</span><span class="sxs-lookup"><span data-stu-id="9e488-111">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="9e488-112">从 C# 7.3 开始，如果枚举器的 `Current` 属性返回 [引用返回值](../../programming-guide/classes-and-structs/ref-returns.md)（`ref T`，其中 `T` 为集合元素类型），就可以使用 `ref` 或 `ref readonly` 修饰符来声明迭代变量。</span><span class="sxs-lookup"><span data-stu-id="9e488-112">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](../../programming-guide/classes-and-structs/ref-returns.md) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span> <span data-ttu-id="9e488-113">下面的示例使用 `ref` 迭代变量来设置 stackalloc 数组中每个项的值。</span><span class="sxs-lookup"><span data-stu-id="9e488-113">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="9e488-114">`ref readonly` 版本循环访问该集合以打印所有值。</span><span class="sxs-lookup"><span data-stu-id="9e488-114">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="9e488-115">`readonly` 声明使用隐式局部变量声明。</span><span class="sxs-lookup"><span data-stu-id="9e488-115">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="9e488-116">隐式变量声明可与 `ref` 或 `ref readonly` 声明配合使用，显式类型化变量声明也一样。</span><span class="sxs-lookup"><span data-stu-id="9e488-116">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a><span data-ttu-id="9e488-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="9e488-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9e488-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e488-118">See also</span></span>

[<span data-ttu-id="9e488-119">foreach 语句（C# 语言规范）</span><span class="sxs-lookup"><span data-stu-id="9e488-119">The foreach statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)  
[<span data-ttu-id="9e488-120">对数组使用 foreach</span><span class="sxs-lookup"><span data-stu-id="9e488-120">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  
[<span data-ttu-id="9e488-121">for</span><span class="sxs-lookup"><span data-stu-id="9e488-121">for</span></span>](for.md)  
[<span data-ttu-id="9e488-122">迭代语句</span><span class="sxs-lookup"><span data-stu-id="9e488-122">Iteration Statements</span></span>](iteration-statements.md)  
[<span data-ttu-id="9e488-123">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="9e488-123">C# Keywords</span></span>](index.md)  
[<span data-ttu-id="9e488-124">C# 参考</span><span class="sxs-lookup"><span data-stu-id="9e488-124">C# Reference</span></span>](../index.md)  
[<span data-ttu-id="9e488-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="9e488-125">C# Programming Guide</span></span>](../../programming-guide/index.md)  
