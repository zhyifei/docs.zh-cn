---
title: 内联函数
description: 了解如何使用F#直接集成到调用代码的内联函数。
ms.date: 05/16/2016
ms.openlocfilehash: 12c175e3e46e12d978fe02d3e1fe83142e71a25d
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610562"
---
# <a name="inline-functions"></a><span data-ttu-id="f0baf-103">内联函数</span><span class="sxs-lookup"><span data-stu-id="f0baf-103">Inline Functions</span></span>

<span data-ttu-id="f0baf-104">*内联函数*是直接集成到调用代码的函数。</span><span class="sxs-lookup"><span data-stu-id="f0baf-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>

## <a name="using-inline-functions"></a><span data-ttu-id="f0baf-105">使用内联函数</span><span class="sxs-lookup"><span data-stu-id="f0baf-105">Using Inline Functions</span></span>

<span data-ttu-id="f0baf-106">当使用静态类型参数时，任何类型参数的参数化的函数必须是内联。</span><span class="sxs-lookup"><span data-stu-id="f0baf-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="f0baf-107">这可确保编译器可以解决这些类型参数。</span><span class="sxs-lookup"><span data-stu-id="f0baf-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="f0baf-108">当您使用普通的泛型类型参数时，没有任何此类限制。</span><span class="sxs-lookup"><span data-stu-id="f0baf-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="f0baf-109">不允许使用成员约束，内联函数可以帮助优化代码。</span><span class="sxs-lookup"><span data-stu-id="f0baf-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="f0baf-110">但是，过度使用的内联函数会导致编译器优化和库函数的实现变化不太本身也可以在代码。</span><span class="sxs-lookup"><span data-stu-id="f0baf-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="f0baf-111">出于此原因，应避免进行优化使用内联函数，除非您已尝试了所有其他优化技术。</span><span class="sxs-lookup"><span data-stu-id="f0baf-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="f0baf-112">使函数或方法的内联有时可以提高性能，但它并不总是这种情况。</span><span class="sxs-lookup"><span data-stu-id="f0baf-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="f0baf-113">因此，您应使用性能度量值以验证使任何给定的函数内联实际上产生积极的影响。</span><span class="sxs-lookup"><span data-stu-id="f0baf-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="f0baf-114">`inline`修饰符可以应用于函数的顶层，在模块级别，或在方法级别在类中。</span><span class="sxs-lookup"><span data-stu-id="f0baf-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="f0baf-115">下面的代码示例说明了在最高级别、 内联实例方法和内联静态方法的内联函数。</span><span class="sxs-lookup"><span data-stu-id="f0baf-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="f0baf-116">内联函数和类型推理</span><span class="sxs-lookup"><span data-stu-id="f0baf-116">Inline Functions and Type Inference</span></span>

<span data-ttu-id="f0baf-117">是否存在`inline`影响类型推理。</span><span class="sxs-lookup"><span data-stu-id="f0baf-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="f0baf-118">这是因为内联函数可以具有静态解析的类型参数，而非内联函数不能。</span><span class="sxs-lookup"><span data-stu-id="f0baf-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="f0baf-119">下面的代码示例显示了一种情况其中`inline`十分有用，因为正在使用具有一个静态解析的类型参数的函数`float`转换运算符。</span><span class="sxs-lookup"><span data-stu-id="f0baf-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="f0baf-120">无需`inline`修饰符，类型推理强制函数以这种情况下采用特定的类型， `int`。</span><span class="sxs-lookup"><span data-stu-id="f0baf-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="f0baf-121">但与`inline`修饰符，该函数同样被推断为具有静态解析的类型参数。</span><span class="sxs-lookup"><span data-stu-id="f0baf-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="f0baf-122">使用`inline`修饰符，类型推断为以下：</span><span class="sxs-lookup"><span data-stu-id="f0baf-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="f0baf-123">这意味着该函数接受任何类型的支持将转换为**float**。</span><span class="sxs-lookup"><span data-stu-id="f0baf-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0baf-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0baf-124">See also</span></span>

- [<span data-ttu-id="f0baf-125">函数</span><span class="sxs-lookup"><span data-stu-id="f0baf-125">Functions</span></span>](index.md)
- [<span data-ttu-id="f0baf-126">约束</span><span class="sxs-lookup"><span data-stu-id="f0baf-126">Constraints</span></span>](../generics/constraints.md)
- [<span data-ttu-id="f0baf-127">静态解析的类型参数</span><span class="sxs-lookup"><span data-stu-id="f0baf-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)