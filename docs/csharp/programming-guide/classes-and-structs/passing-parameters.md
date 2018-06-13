---
title: 传递参数（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: a1ccfff8081d101eee46360009653b0591dfb3ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33323100"
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="9858d-102">传递参数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="9858d-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="9858d-103">在 C# 中，实参可以按值或按引用传递给形参。</span><span class="sxs-lookup"><span data-stu-id="9858d-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="9858d-104">按引用传递使函数成员、方法、属性、索引器、运算符和构造函数可以更改参数的值，并让该更改在调用环境中保持。</span><span class="sxs-lookup"><span data-stu-id="9858d-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="9858d-105">若要按引用传递参数，且具有更改值的意向，请使用 `ref` 或 `out` 关键字。</span><span class="sxs-lookup"><span data-stu-id="9858d-105">To pass a parameter by reference with the intent of changing the value, use the `ref`, or `out` keyword.</span></span> <span data-ttu-id="9858d-106">若要按引用传递，且只有避免复制而不更改值的意向，请使用 `in` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="9858d-106">To pass by reference with the intent of avoiding copying but not changing the value, use the `in` modifier.</span></span> <span data-ttu-id="9858d-107">为简单起见，本主题的示例中只使用 `ref` 关键字。</span><span class="sxs-lookup"><span data-stu-id="9858d-107">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="9858d-108">有关 `in`、`ref` 和 `out` 之间的差异的详细信息，请参阅 [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md)、[ref](../../../csharp/language-reference/keywords/ref.md)、[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 和[使用 ref 和 out 传递数组](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)。</span><span class="sxs-lookup"><span data-stu-id="9858d-108">For more information about the difference between `in`, `ref`, and `out`, see [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), and [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="9858d-109">以下示例演示值与引用参数之间的差异。</span><span class="sxs-lookup"><span data-stu-id="9858d-109">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 <span data-ttu-id="9858d-110">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="9858d-110">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="9858d-111">传递值类型参数</span><span class="sxs-lookup"><span data-stu-id="9858d-111">Passing Value-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [<span data-ttu-id="9858d-112">传递引用类型参数</span><span class="sxs-lookup"><span data-stu-id="9858d-112">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="9858d-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="9858d-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9858d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9858d-114">See Also</span></span>  
 [<span data-ttu-id="9858d-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="9858d-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9858d-116">方法</span><span class="sxs-lookup"><span data-stu-id="9858d-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
