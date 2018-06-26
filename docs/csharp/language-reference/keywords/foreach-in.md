---
title: foreach，in（C# 参考）
ms.date: 05/24/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 7613590686f7f7ec6439da4a2bb672e524ab01e8
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34565701"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="c1a1c-102">foreach，in（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c1a1c-102">foreach, in (C# Reference)</span></span>

<span data-ttu-id="c1a1c-103">`foreach` 语句为类型实例中实现 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 或 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 接口的每个元素执行语句或语句块。</span><span class="sxs-lookup"><span data-stu-id="c1a1c-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="c1a1c-104">`foreach` 语句不局限于这些类型，它可应用于满足以下条件的任何类型的实例：</span><span class="sxs-lookup"><span data-stu-id="c1a1c-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="c1a1c-105">具有公共无参数 `GetEnumerator` 方法，其返回类型为类、结构或接口类型。</span><span class="sxs-lookup"><span data-stu-id="c1a1c-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="c1a1c-106">`GetEnumerator` 方法的返回类型具有公共 `Current` 属性和公共无参数 `MoveNext` 方法（其返回类型为 <xref:System.Boolean>）。</span><span class="sxs-lookup"><span data-stu-id="c1a1c-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="c1a1c-107">在 `foreach` 语句块中的任何点上，可以使用 [break](break.md) 语句中断循环，或者可以使用 [continue](continue.md) 语句继续执行到循环中的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="c1a1c-107">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="c1a1c-108">还可以使用 [goto](goto.md)、[return](return.md) 或 [throw](throw.md) 语句退出 `foreach` 循环。</span><span class="sxs-lookup"><span data-stu-id="c1a1c-108">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="examples"></a><span data-ttu-id="c1a1c-109">示例</span><span class="sxs-lookup"><span data-stu-id="c1a1c-109">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="c1a1c-110">以下示例介绍 `foreach` 语句的使用，其中包含实现 <xref:System.Collections.Generic.IEnumerable%601> 接口的 <xref:System.Collections.Generic.List%601> 类型的实例：</span><span class="sxs-lookup"><span data-stu-id="c1a1c-110">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="c1a1c-111">下一个示例使用 `foreach` 语句，其中包含 <xref:System.Span%601?displayProperty=nameWithType> 类型的实例，该实例不实现任何接口：</span><span class="sxs-lookup"><span data-stu-id="c1a1c-111">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="c1a1c-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="c1a1c-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c1a1c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1a1c-113">See also</span></span>

[<span data-ttu-id="c1a1c-114">foreach 语句（C# 语言规范）</span><span class="sxs-lookup"><span data-stu-id="c1a1c-114">The foreach statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)  
[<span data-ttu-id="c1a1c-115">对数组使用 foreach</span><span class="sxs-lookup"><span data-stu-id="c1a1c-115">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  
[<span data-ttu-id="c1a1c-116">for</span><span class="sxs-lookup"><span data-stu-id="c1a1c-116">for</span></span>](for.md)  
[<span data-ttu-id="c1a1c-117">迭代语句</span><span class="sxs-lookup"><span data-stu-id="c1a1c-117">Iteration Statements</span></span>](iteration-statements.md)  
[<span data-ttu-id="c1a1c-118">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="c1a1c-118">C# Keywords</span></span>](index.md)  
[<span data-ttu-id="c1a1c-119">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c1a1c-119">C# Reference</span></span>](../index.md)  
[<span data-ttu-id="c1a1c-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c1a1c-120">C# Programming Guide</span></span>](../../programming-guide/index.md)  