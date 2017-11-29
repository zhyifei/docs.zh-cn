---
title: "传递参数（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d9e0e06d67f9da39c6b55f91e35d4a75b43353f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="b2fcb-102">传递参数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="b2fcb-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="b2fcb-103">在 C# 中，实参可以按值或按引用传递给形参。</span><span class="sxs-lookup"><span data-stu-id="b2fcb-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="b2fcb-104">按引用传递使函数成员、方法、属性、索引器、运算符和构造函数可以更改参数的值，并让该更改在调用环境中保持。</span><span class="sxs-lookup"><span data-stu-id="b2fcb-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="b2fcb-105">若要按引用传递参数，请使用 `ref` 或 `out` 关键字。</span><span class="sxs-lookup"><span data-stu-id="b2fcb-105">To pass a parameter by reference, use the `ref` or `out` keyword.</span></span> <span data-ttu-id="b2fcb-106">为简单起见，本主题的示例中只使用 `ref` 关键字。</span><span class="sxs-lookup"><span data-stu-id="b2fcb-106">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="b2fcb-107">有关 `ref` 与 `out` 之间的差异的详细信息，请参阅 [ref](../../../csharp/language-reference/keywords/ref.md)、[out](../../../csharp/language-reference/keywords/out.md) 和 [使用 ref 和 out 传递数组](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)。</span><span class="sxs-lookup"><span data-stu-id="b2fcb-107">For more information about the difference between `ref` and `out`, see [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md), and [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="b2fcb-108">以下示例演示值与引用参数之间的差异。</span><span class="sxs-lookup"><span data-stu-id="b2fcb-108">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 <span data-ttu-id="b2fcb-109">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="b2fcb-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="b2fcb-110">传递值类型参数</span><span class="sxs-lookup"><span data-stu-id="b2fcb-110">Passing Value-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [<span data-ttu-id="b2fcb-111">传递引用类型参数</span><span class="sxs-lookup"><span data-stu-id="b2fcb-111">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="b2fcb-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b2fcb-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b2fcb-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2fcb-113">See Also</span></span>  
 [<span data-ttu-id="b2fcb-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b2fcb-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b2fcb-115">方法</span><span class="sxs-lookup"><span data-stu-id="b2fcb-115">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
