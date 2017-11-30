---
title: "内联函数 (F#)"
description: "了解如何使用直接集成到调用代码的 F # 内联函数。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3fa31178-08f8-463d-9d41-d29220a90027
ms.openlocfilehash: 0489d411e2754eaab6a10ff0feb4405491b3b511
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2017
---
# <a name="inline-functions"></a><span data-ttu-id="41236-104">内联函数</span><span class="sxs-lookup"><span data-stu-id="41236-104">Inline Functions</span></span>

<span data-ttu-id="41236-105">*内联函数*是直接集成到调用代码的函数。</span><span class="sxs-lookup"><span data-stu-id="41236-105">*Inline functions* are functions that are integrated directly into the calling code.</span></span>


## <a name="using-inline-functions"></a><span data-ttu-id="41236-106">使用内联函数</span><span class="sxs-lookup"><span data-stu-id="41236-106">Using Inline Functions</span></span>
<span data-ttu-id="41236-107">当使用静态类型参数时，由类型参数化任何函数必须进行内联。</span><span class="sxs-lookup"><span data-stu-id="41236-107">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="41236-108">这可保证编译器可以解决这些类型参数。</span><span class="sxs-lookup"><span data-stu-id="41236-108">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="41236-109">当使用普通的泛型类型参数时，没有这样的限制。</span><span class="sxs-lookup"><span data-stu-id="41236-109">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="41236-110">以外启用将成员约束，内联函数可以帮助优化代码。</span><span class="sxs-lookup"><span data-stu-id="41236-110">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="41236-111">但是，内联函数的过度使用可能导致代码不太抵抗编译器优化和库函数的实现中的更改。</span><span class="sxs-lookup"><span data-stu-id="41236-111">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="41236-112">为此，应避免使用内联函数进行优化，除非你已尝试所有其他优化技术。</span><span class="sxs-lookup"><span data-stu-id="41236-112">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="41236-113">使函数或方法内联有时可以提高性能，但是，并非总是这种情况。</span><span class="sxs-lookup"><span data-stu-id="41236-113">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="41236-114">因此，你还应使用性能度量值以确定进行任何给定的函数内联实际上具有积极的影响。</span><span class="sxs-lookup"><span data-stu-id="41236-114">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="41236-115">`inline`修饰符可以应用于函数最高级别，在模块级别，或在类中的方法级别。</span><span class="sxs-lookup"><span data-stu-id="41236-115">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="41236-116">下面的代码示例说明了内联函数在顶级、 内联实例方法和内联静态方法。</span><span class="sxs-lookup"><span data-stu-id="41236-116">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="41236-117">内联函数和类型推理</span><span class="sxs-lookup"><span data-stu-id="41236-117">Inline Functions and Type Inference</span></span>
<span data-ttu-id="41236-118">是否存在`inline`影响类型推理。</span><span class="sxs-lookup"><span data-stu-id="41236-118">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="41236-119">这是因为内联函数可以具有静态解析的类型参数，而非内联函数不能。</span><span class="sxs-lookup"><span data-stu-id="41236-119">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="41236-120">下面的代码示例演示一种情况其中`inline`非常有用，因为正在使用具有一个静态解析的类型参数的函数`float`转换运算符。</span><span class="sxs-lookup"><span data-stu-id="41236-120">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="41236-121">而无需`inline`修饰符，类型推理将强制使用特定的类型，在这种情况下函数`int`。</span><span class="sxs-lookup"><span data-stu-id="41236-121">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="41236-122">但与`inline`修饰符，该函数同样被推断为具有静态解析的类型参数。</span><span class="sxs-lookup"><span data-stu-id="41236-122">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="41236-123">与`inline`修饰符，类型推断为以下：</span><span class="sxs-lookup"><span data-stu-id="41236-123">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="41236-124">这意味着，该函数接受支持将转换为任何类型**float**。</span><span class="sxs-lookup"><span data-stu-id="41236-124">This means that the function accepts any type that supports a conversion to **float**.</span></span>


## <a name="see-also"></a><span data-ttu-id="41236-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41236-125">See Also</span></span>
[<span data-ttu-id="41236-126">函数</span><span class="sxs-lookup"><span data-stu-id="41236-126">Functions</span></span>](index.md)

[<span data-ttu-id="41236-127">约束</span><span class="sxs-lookup"><span data-stu-id="41236-127">Constraints</span></span>](../generics/constraints.md)

[<span data-ttu-id="41236-128">静态解析的类型参数</span><span class="sxs-lookup"><span data-stu-id="41236-128">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
