---
title: 内联函数
description: 了解如何使用F#直接集成到调用代码中的内联函数。
ms.date: 05/16/2016
ms.openlocfilehash: 2830d1ada5b3005c3fcae975a44e85a7c84554f7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630678"
---
# <a name="inline-functions"></a><span data-ttu-id="9766b-103">内联函数</span><span class="sxs-lookup"><span data-stu-id="9766b-103">Inline Functions</span></span>

<span data-ttu-id="9766b-104">*内联函数*是直接集成到调用代码中的函数。</span><span class="sxs-lookup"><span data-stu-id="9766b-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>

## <a name="using-inline-functions"></a><span data-ttu-id="9766b-105">使用内联函数</span><span class="sxs-lookup"><span data-stu-id="9766b-105">Using Inline Functions</span></span>

<span data-ttu-id="9766b-106">使用静态类型参数时, 必须以内联方式为类型参数参数化的任何函数。</span><span class="sxs-lookup"><span data-stu-id="9766b-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="9766b-107">这可确保编译器可以解析这些类型参数。</span><span class="sxs-lookup"><span data-stu-id="9766b-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="9766b-108">当使用普通泛型类型参数时, 没有此类限制。</span><span class="sxs-lookup"><span data-stu-id="9766b-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="9766b-109">除了允许使用成员约束外, 内联函数对于优化代码非常有用。</span><span class="sxs-lookup"><span data-stu-id="9766b-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="9766b-110">但是, 如果过度利用内联函数, 则可能会导致您的代码不受编译器优化和库函数实现中的更改。</span><span class="sxs-lookup"><span data-stu-id="9766b-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="9766b-111">出于此原因, 应避免使用内联函数进行优化, 除非已尝试所有其他优化方法。</span><span class="sxs-lookup"><span data-stu-id="9766b-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="9766b-112">使函数或方法为内联可能会提高性能, 但并非总是如此。</span><span class="sxs-lookup"><span data-stu-id="9766b-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="9766b-113">因此, 您还应该使用性能度量来验证使任何给定函数的内联确实会产生积极影响。</span><span class="sxs-lookup"><span data-stu-id="9766b-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="9766b-114">`inline`修饰符可应用于顶层的函数、模块级别或类中的方法级别。</span><span class="sxs-lookup"><span data-stu-id="9766b-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="9766b-115">下面的代码示例演示顶级的内联函数、内联实例方法和内联静态方法。</span><span class="sxs-lookup"><span data-stu-id="9766b-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="9766b-116">内联函数和类型推理</span><span class="sxs-lookup"><span data-stu-id="9766b-116">Inline Functions and Type Inference</span></span>

<span data-ttu-id="9766b-117">存在影响类型`inline`推理的情况。</span><span class="sxs-lookup"><span data-stu-id="9766b-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="9766b-118">这是因为内联函数可以具有静态解析的类型参数, 而非内联函数不能。</span><span class="sxs-lookup"><span data-stu-id="9766b-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="9766b-119">下面的代码示例演示了一个很`inline`有用的情况, 因为你使用的是具有静态解析的类型参数的`float`函数 (即转换运算符)。</span><span class="sxs-lookup"><span data-stu-id="9766b-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="9766b-120">`inline` 如果`int`不使用修饰符, 则类型推理强制函数采用特定类型 (在本例中为)。</span><span class="sxs-lookup"><span data-stu-id="9766b-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="9766b-121">但对于`inline`修饰符, 还会将函数推断为具有静态解析的类型参数。</span><span class="sxs-lookup"><span data-stu-id="9766b-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="9766b-122">`inline`通过修饰符, 将类型推断为以下内容:</span><span class="sxs-lookup"><span data-stu-id="9766b-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="9766b-123">这意味着函数接受支持转换为**float**类型的任何类型。</span><span class="sxs-lookup"><span data-stu-id="9766b-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>

## <a name="see-also"></a><span data-ttu-id="9766b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="9766b-124">See also</span></span>

- [<span data-ttu-id="9766b-125">函数</span><span class="sxs-lookup"><span data-stu-id="9766b-125">Functions</span></span>](index.md)
- [<span data-ttu-id="9766b-126">约束</span><span class="sxs-lookup"><span data-stu-id="9766b-126">Constraints</span></span>](../generics/constraints.md)
- [<span data-ttu-id="9766b-127">静态解析的类型参数</span><span class="sxs-lookup"><span data-stu-id="9766b-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
