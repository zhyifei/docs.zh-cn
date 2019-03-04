---
title: 如何：在查询表达式中使用隐式类型本地变量和数组 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
ms.openlocfilehash: 8e3534abf961ba7b8a41eed592455962e5b551e7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979029"
---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a><span data-ttu-id="01539-102">如何：在查询表达式中使用隐式类型本地变量和数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="01539-102">How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression (C# Programming Guide)</span></span>
<span data-ttu-id="01539-103">每当需要编译器确定本地变量类型时，均可使用隐式类型本地变量。</span><span class="sxs-lookup"><span data-stu-id="01539-103">You can use implicitly typed local variables whenever you want the compiler to determine the type of a local variable.</span></span> <span data-ttu-id="01539-104">必须使用隐式类型本地变量来存储匿名类型，匿名类型通常用于查询表达式中。</span><span class="sxs-lookup"><span data-stu-id="01539-104">You must use implicitly typed local variables to store anonymous types, which are often used in query expressions.</span></span> <span data-ttu-id="01539-105">以下示例说明了在查询中可以使用和必须使用隐式类型本地变量的情况。</span><span class="sxs-lookup"><span data-stu-id="01539-105">The following examples illustrate both optional and required uses of implicitly typed local variables in queries.</span></span>  
  
 <span data-ttu-id="01539-106">隐式类型本地变量使用 [var](../../../csharp/language-reference/keywords/var.md) 上下文关键字进行声明。</span><span class="sxs-lookup"><span data-stu-id="01539-106">Implicitly typed local variables are declared by using the [var](../../../csharp/language-reference/keywords/var.md) contextual keyword.</span></span> <span data-ttu-id="01539-107">有关详细信息，请参阅[隐式类型本地变量](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)和[隐式类型数组](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="01539-107">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01539-108">示例</span><span class="sxs-lookup"><span data-stu-id="01539-108">Example</span></span>  
 <span data-ttu-id="01539-109">以下示例演示必须使用 `var` 关键字的常见情景：用于生成一系列匿名类型的查询表达式。</span><span class="sxs-lookup"><span data-stu-id="01539-109">The following example shows a common scenario in which the `var` keyword is required: a query expression that produces a sequence of anonymous types.</span></span> <span data-ttu-id="01539-110">在此情景中，必须使用 `var` 隐式类型化 `foreach` 语句中的查询变量和迭代变量，因为你无权访问匿名类型的类型名称。</span><span class="sxs-lookup"><span data-stu-id="01539-110">In this scenario, both the query variable and the iteration variable in the `foreach` statement must be implicitly typed by using `var` because you do not have access to a type name for the anonymous type.</span></span> <span data-ttu-id="01539-111">有关匿名类型的详细信息，请参阅[匿名类型](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="01539-111">For more information about anonymous types, see [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#32)]  
  
## <a name="example"></a><span data-ttu-id="01539-112">示例</span><span class="sxs-lookup"><span data-stu-id="01539-112">Example</span></span>  
 <span data-ttu-id="01539-113">虽然以下示例在类似的情景中使用 `var` 关键字，但使用 `var` 是可选项。</span><span class="sxs-lookup"><span data-stu-id="01539-113">The following example uses the `var` keyword in a situation that is similar, but in which the use of `var` is optional.</span></span> <span data-ttu-id="01539-114">因为 `student.LastName` 是字符串，所以执行查询将返回一系列字符串。</span><span class="sxs-lookup"><span data-stu-id="01539-114">Because `student.LastName` is a string, execution of the query returns a sequence of strings.</span></span> <span data-ttu-id="01539-115">因此，`queryID` 的类型可声明为 `System.Collections.Generic.IEnumerable<string>`，而不是 `var`。</span><span class="sxs-lookup"><span data-stu-id="01539-115">Therefore, the type of `queryID` could be declared as `System.Collections.Generic.IEnumerable<string>` instead of `var`.</span></span> <span data-ttu-id="01539-116">为方便起见，请使用关键字 `var`。</span><span class="sxs-lookup"><span data-stu-id="01539-116">Keyword `var` is used for convenience.</span></span> <span data-ttu-id="01539-117">在示例中，虽然 `foreach` 语句中的迭代变量被显式类型化为字符串，但可改为使用 `var` 对其进行声明。</span><span class="sxs-lookup"><span data-stu-id="01539-117">In the example, the iteration variable in the `foreach` statement is explicitly typed as a string, but it could instead be declared by using `var`.</span></span> <span data-ttu-id="01539-118">因为迭代变量的类型不是匿名类型，因此使用 `var` 是可选项，而不是必需项。</span><span class="sxs-lookup"><span data-stu-id="01539-118">Because the type of the iteration variable is not an anonymous type, the use of `var` is an option, not a requirement.</span></span> <span data-ttu-id="01539-119">请记住，`var` 本身不是类型，而是发送给编译器用于推断和分配类型的指令。</span><span class="sxs-lookup"><span data-stu-id="01539-119">Remember, `var` itself is not a type, but an instruction to the compiler to infer and assign the type.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#33)]  
  
## <a name="see-also"></a><span data-ttu-id="01539-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="01539-120">See also</span></span>

- [<span data-ttu-id="01539-121">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="01539-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="01539-122">扩展方法</span><span class="sxs-lookup"><span data-stu-id="01539-122">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [<span data-ttu-id="01539-123">LINQ（语言集成查询）</span><span class="sxs-lookup"><span data-stu-id="01539-123">LINQ (Language-Integrated Query)</span></span>](../../../csharp/linq/index.md)
- [<span data-ttu-id="01539-124">var</span><span class="sxs-lookup"><span data-stu-id="01539-124">var</span></span>](../../../csharp/language-reference/keywords/var.md)
- [<span data-ttu-id="01539-125">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="01539-125">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
