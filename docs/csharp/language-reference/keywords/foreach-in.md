---
title: C# foreach 语句
ms.date: 05/17/2019
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: af4850b4c33727c818fb5a67d17fb6146627fa06
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267732"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="fae99-102">foreach，in（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="fae99-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="fae99-103">`foreach` 语句为类型实例中实现 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 或 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 接口的每个元素执行语句或语句块。</span><span class="sxs-lookup"><span data-stu-id="fae99-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="fae99-104">`foreach` 语句不局限于这些类型，它可应用于满足以下条件的任何类型的实例：</span><span class="sxs-lookup"><span data-stu-id="fae99-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="fae99-105">具有公共无参数 `GetEnumerator` 方法，其返回类型为类、结构或接口类型。</span><span class="sxs-lookup"><span data-stu-id="fae99-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="fae99-106">`GetEnumerator` 方法的返回类型具有公共 `Current` 属性和公共无参数 `MoveNext` 方法（其返回类型为 <xref:System.Boolean>）。</span><span class="sxs-lookup"><span data-stu-id="fae99-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="fae99-107">从 C# 7.3 开始，如果枚举器的 `Current` 属性返回 [引用返回值](ref.md#reference-return-values)（`ref T`，其中 `T` 为集合元素类型），就可以使用 `ref` 或 `ref readonly` 修饰符来声明迭代变量。</span><span class="sxs-lookup"><span data-stu-id="fae99-107">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="fae99-108">在 `foreach` 语句块中的任何点上，可以使用 [break](break.md) 语句中断循环，或者可以使用 [continue](continue.md) 语句继续执行到循环中的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="fae99-108">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="fae99-109">还可以使用 [goto](goto.md)、[return](return.md) 或 [throw](throw.md) 语句退出 `foreach` 循环。</span><span class="sxs-lookup"><span data-stu-id="fae99-109">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="fae99-110">如果 `foreach` 语句应用为 `null`，则会引发 <xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="fae99-110">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="fae99-111">如果 `foreach` 语句的源集合为空，则 `foreach` 循环的正文不会被执行，而是被跳过。</span><span class="sxs-lookup"><span data-stu-id="fae99-111">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop is not executed and skipped.</span></span>

## <a name="examples"></a><span data-ttu-id="fae99-112">示例</span><span class="sxs-lookup"><span data-stu-id="fae99-112">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="fae99-113">以下示例介绍 `foreach` 语句的使用，其中包含实现 <xref:System.Collections.Generic.IEnumerable%601> 接口的 <xref:System.Collections.Generic.List%601> 类型的实例：</span><span class="sxs-lookup"><span data-stu-id="fae99-113">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="fae99-114">下一个示例使用 `foreach` 语句，其中包含 <xref:System.Span%601?displayProperty=nameWithType> 类型的实例，该实例不实现任何接口：</span><span class="sxs-lookup"><span data-stu-id="fae99-114">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="fae99-115">下面的示例使用 `ref` 迭代变量来设置 stackalloc 数组中每个项的值。</span><span class="sxs-lookup"><span data-stu-id="fae99-115">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="fae99-116">`ref readonly` 版本循环访问该集合以打印所有值。</span><span class="sxs-lookup"><span data-stu-id="fae99-116">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="fae99-117">`readonly` 声明使用隐式局部变量声明。</span><span class="sxs-lookup"><span data-stu-id="fae99-117">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="fae99-118">隐式变量声明可与 `ref` 或 `ref readonly` 声明配合使用，显式类型化变量声明也一样。</span><span class="sxs-lookup"><span data-stu-id="fae99-118">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a><span data-ttu-id="fae99-119">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="fae99-119">C# language specification</span></span>

<span data-ttu-id="fae99-120">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的 [foreach 语句](~/_csharplang/spec/statements.md#the-foreach-statement)部分。</span><span class="sxs-lookup"><span data-stu-id="fae99-120">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fae99-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="fae99-121">See also</span></span>

- [<span data-ttu-id="fae99-122">C# 参考</span><span class="sxs-lookup"><span data-stu-id="fae99-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fae99-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fae99-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fae99-124">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="fae99-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="fae99-125">对数组使用 foreach</span><span class="sxs-lookup"><span data-stu-id="fae99-125">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="fae99-126">for 语句</span><span class="sxs-lookup"><span data-stu-id="fae99-126">for statement</span></span>](for.md)
