---
title: 如何：在查询表达式中使用隐式类型本地变量和数组 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
ms.openlocfilehash: 3cb47f9e80e1fc067a8bac860aa06f3e1860d33d
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419322"
---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a><span data-ttu-id="8d83c-102">如何：在查询表达式中使用隐式类型本地变量和数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="8d83c-102">How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression (C# Programming Guide)</span></span>
<span data-ttu-id="8d83c-103">每当需要编译器确定本地变量类型时，均可使用隐式类型本地变量。</span><span class="sxs-lookup"><span data-stu-id="8d83c-103">You can use implicitly typed local variables whenever you want the compiler to determine the type of a local variable.</span></span> <span data-ttu-id="8d83c-104">必须使用隐式类型本地变量来存储匿名类型，匿名类型通常用于查询表达式中。</span><span class="sxs-lookup"><span data-stu-id="8d83c-104">You must use implicitly typed local variables to store anonymous types, which are often used in query expressions.</span></span> <span data-ttu-id="8d83c-105">以下示例说明了在查询中可以使用和必须使用隐式类型本地变量的情况。</span><span class="sxs-lookup"><span data-stu-id="8d83c-105">The following examples illustrate both optional and required uses of implicitly typed local variables in queries.</span></span>  
  
 <span data-ttu-id="8d83c-106">隐式类型本地变量使用 [var](../../language-reference/keywords/var.md) 上下文关键字进行声明。</span><span class="sxs-lookup"><span data-stu-id="8d83c-106">Implicitly typed local variables are declared by using the [var](../../language-reference/keywords/var.md) contextual keyword.</span></span> <span data-ttu-id="8d83c-107">有关详细信息，请参阅[隐式类型本地变量](./implicitly-typed-local-variables.md)和[隐式类型数组](../arrays/implicitly-typed-arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="8d83c-107">For more information, see [Implicitly Typed Local Variables](./implicitly-typed-local-variables.md) and [Implicitly Typed Arrays](../arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d83c-108">示例</span><span class="sxs-lookup"><span data-stu-id="8d83c-108">Example</span></span>  
 <span data-ttu-id="8d83c-109">以下示例演示必须使用 `var` 关键字的常见情景：用于生成一系列匿名类型的查询表达式。</span><span class="sxs-lookup"><span data-stu-id="8d83c-109">The following example shows a common scenario in which the `var` keyword is required: a query expression that produces a sequence of anonymous types.</span></span> <span data-ttu-id="8d83c-110">在此情景中，必须使用 `var` 隐式类型化 `foreach` 语句中的查询变量和迭代变量，因为你无权访问匿名类型的类型名称。</span><span class="sxs-lookup"><span data-stu-id="8d83c-110">In this scenario, both the query variable and the iteration variable in the `foreach` statement must be implicitly typed by using `var` because you do not have access to a type name for the anonymous type.</span></span> <span data-ttu-id="8d83c-111">有关匿名类型的详细信息，请参阅[匿名类型](./anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="8d83c-111">For more information about anonymous types, see [Anonymous Types](./anonymous-types.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#32)]  
  
## <a name="example"></a><span data-ttu-id="8d83c-112">示例</span><span class="sxs-lookup"><span data-stu-id="8d83c-112">Example</span></span>  
 <span data-ttu-id="8d83c-113">虽然以下示例在类似的情景中使用 `var` 关键字，但使用 `var` 是可选项。</span><span class="sxs-lookup"><span data-stu-id="8d83c-113">The following example uses the `var` keyword in a situation that is similar, but in which the use of `var` is optional.</span></span> <span data-ttu-id="8d83c-114">因为 `student.LastName` 是字符串，所以执行查询将返回一系列字符串。</span><span class="sxs-lookup"><span data-stu-id="8d83c-114">Because `student.LastName` is a string, execution of the query returns a sequence of strings.</span></span> <span data-ttu-id="8d83c-115">因此，`queryID` 的类型可声明为 `System.Collections.Generic.IEnumerable<string>`，而不是 `var`。</span><span class="sxs-lookup"><span data-stu-id="8d83c-115">Therefore, the type of `queryID` could be declared as `System.Collections.Generic.IEnumerable<string>` instead of `var`.</span></span> <span data-ttu-id="8d83c-116">为方便起见，请使用关键字 `var`。</span><span class="sxs-lookup"><span data-stu-id="8d83c-116">Keyword `var` is used for convenience.</span></span> <span data-ttu-id="8d83c-117">在示例中，虽然 `foreach` 语句中的迭代变量被显式类型化为字符串，但可改为使用 `var` 对其进行声明。</span><span class="sxs-lookup"><span data-stu-id="8d83c-117">In the example, the iteration variable in the `foreach` statement is explicitly typed as a string, but it could instead be declared by using `var`.</span></span> <span data-ttu-id="8d83c-118">因为迭代变量的类型不是匿名类型，因此使用 `var` 是可选项，而不是必需项。</span><span class="sxs-lookup"><span data-stu-id="8d83c-118">Because the type of the iteration variable is not an anonymous type, the use of `var` is an option, not a requirement.</span></span> <span data-ttu-id="8d83c-119">请记住，`var` 本身不是类型，而是发送给编译器用于推断和分配类型的指令。</span><span class="sxs-lookup"><span data-stu-id="8d83c-119">Remember, `var` itself is not a type, but an instruction to the compiler to infer and assign the type.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#33)]  
  
## <a name="see-also"></a><span data-ttu-id="8d83c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d83c-120">See also</span></span>

- [<span data-ttu-id="8d83c-121">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8d83c-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8d83c-122">扩展方法</span><span class="sxs-lookup"><span data-stu-id="8d83c-122">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="8d83c-123">LINQ（语言集成查询）</span><span class="sxs-lookup"><span data-stu-id="8d83c-123">LINQ (Language-Integrated Query)</span></span>](../../linq/index.md)
- [<span data-ttu-id="8d83c-124">var</span><span class="sxs-lookup"><span data-stu-id="8d83c-124">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="8d83c-125">C# 中的 LINQ</span><span class="sxs-lookup"><span data-stu-id="8d83c-125">LINQ in C#</span></span>](../../linq/index.md)
