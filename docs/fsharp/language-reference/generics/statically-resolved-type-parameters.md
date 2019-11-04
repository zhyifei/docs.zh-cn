---
title: 静态解析的类型参数
description: 了解如何使用在编译F#时（而不是在运行时）替换为实际类型的静态解析的类型参数。
ms.date: 05/16/2016
ms.openlocfilehash: 017c18dd3caaa484ddc653557573f548e3224ca0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425000"
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="8ada9-103">静态解析的类型参数</span><span class="sxs-lookup"><span data-stu-id="8ada9-103">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="8ada9-104">*静态解析的类型参数*是一个类型参数，它在编译时（而不是在运行时）替换为实际类型。</span><span class="sxs-lookup"><span data-stu-id="8ada9-104">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="8ada9-105">它们前面有一个插入符号（^）符号。</span><span class="sxs-lookup"><span data-stu-id="8ada9-105">They are preceded by a caret (^) symbol.</span></span>

## <a name="syntax"></a><span data-ttu-id="8ada9-106">语法</span><span class="sxs-lookup"><span data-stu-id="8ada9-106">Syntax</span></span>

```fsharp
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="8ada9-107">备注</span><span class="sxs-lookup"><span data-stu-id="8ada9-107">Remarks</span></span>

<span data-ttu-id="8ada9-108">在F#语言中，有两种不同类型的类型参数。</span><span class="sxs-lookup"><span data-stu-id="8ada9-108">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="8ada9-109">第一种类型是标准泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="8ada9-109">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="8ada9-110">它们由撇号（'）表示，如 `'T` 和 `'U`中。</span><span class="sxs-lookup"><span data-stu-id="8ada9-110">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="8ada9-111">它们等效于其他 .NET Framework 语言的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="8ada9-111">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="8ada9-112">另一种类型是静态解析的，它由一个插入符号表示，如 `^T` 和 `^U`中所示。</span><span class="sxs-lookup"><span data-stu-id="8ada9-112">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="8ada9-113">静态解析的类型参数主要用于与成员约束结合使用，后者是允许您指定类型参数必须具有特定成员才能使用的约束。</span><span class="sxs-lookup"><span data-stu-id="8ada9-113">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="8ada9-114">无法使用常规泛型类型参数创建这种约束。</span><span class="sxs-lookup"><span data-stu-id="8ada9-114">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="8ada9-115">下表总结了两种类型参数之间的相似性和差异。</span><span class="sxs-lookup"><span data-stu-id="8ada9-115">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="8ada9-116">功能</span><span class="sxs-lookup"><span data-stu-id="8ada9-116">Feature</span></span>|<span data-ttu-id="8ada9-117">泛型</span><span class="sxs-lookup"><span data-stu-id="8ada9-117">Generic</span></span>|<span data-ttu-id="8ada9-118">静态解析</span><span class="sxs-lookup"><span data-stu-id="8ada9-118">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="8ada9-119">语法</span><span class="sxs-lookup"><span data-stu-id="8ada9-119">Syntax</span></span>|<span data-ttu-id="8ada9-120">`'T`，`'U`</span><span class="sxs-lookup"><span data-stu-id="8ada9-120">`'T`, `'U`</span></span>|<span data-ttu-id="8ada9-121">`^T`，`^U`</span><span class="sxs-lookup"><span data-stu-id="8ada9-121">`^T`, `^U`</span></span>|
|<span data-ttu-id="8ada9-122">解决时间</span><span class="sxs-lookup"><span data-stu-id="8ada9-122">Resolution time</span></span>|<span data-ttu-id="8ada9-123">运行时</span><span class="sxs-lookup"><span data-stu-id="8ada9-123">Run time</span></span>|<span data-ttu-id="8ada9-124">编译时间</span><span class="sxs-lookup"><span data-stu-id="8ada9-124">Compile time</span></span>|
|<span data-ttu-id="8ada9-125">成员约束</span><span class="sxs-lookup"><span data-stu-id="8ada9-125">Member constraints</span></span>|<span data-ttu-id="8ada9-126">不能与成员约束一起使用。</span><span class="sxs-lookup"><span data-stu-id="8ada9-126">Cannot be used with member constraints.</span></span>|<span data-ttu-id="8ada9-127">可以与成员约束一起使用。</span><span class="sxs-lookup"><span data-stu-id="8ada9-127">Can be used with member constraints.</span></span>|
|<span data-ttu-id="8ada9-128">代码生成</span><span class="sxs-lookup"><span data-stu-id="8ada9-128">Code generation</span></span>|<span data-ttu-id="8ada9-129">具有标准泛型类型参数的类型（或方法）导致生成单个泛型类型或方法。</span><span class="sxs-lookup"><span data-stu-id="8ada9-129">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="8ada9-130">生成类型和方法的多个实例化，每个实例对应于所需的类型。</span><span class="sxs-lookup"><span data-stu-id="8ada9-130">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="8ada9-131">与类型一起使用</span><span class="sxs-lookup"><span data-stu-id="8ada9-131">Use with types</span></span>|<span data-ttu-id="8ada9-132">可用于类型。</span><span class="sxs-lookup"><span data-stu-id="8ada9-132">Can be used on types.</span></span>|<span data-ttu-id="8ada9-133">不能用于类型。</span><span class="sxs-lookup"><span data-stu-id="8ada9-133">Cannot be used on types.</span></span>|
|<span data-ttu-id="8ada9-134">与内联函数一起使用</span><span class="sxs-lookup"><span data-stu-id="8ada9-134">Use with inline functions</span></span>|<span data-ttu-id="8ada9-135">否。</span><span class="sxs-lookup"><span data-stu-id="8ada9-135">No.</span></span> <span data-ttu-id="8ada9-136">不能使用标准泛型类型参数参数化内联函数。</span><span class="sxs-lookup"><span data-stu-id="8ada9-136">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="8ada9-137">可以。</span><span class="sxs-lookup"><span data-stu-id="8ada9-137">Yes.</span></span> <span data-ttu-id="8ada9-138">静态解析的类型参数不能用于非内联的函数或方法。</span><span class="sxs-lookup"><span data-stu-id="8ada9-138">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="8ada9-139">许多F#核心库函数（特别是运算符）都有静态解析的类型参数。</span><span class="sxs-lookup"><span data-stu-id="8ada9-139">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="8ada9-140">这些函数和运算符是内联的，为数值计算生成了高效的代码生成。</span><span class="sxs-lookup"><span data-stu-id="8ada9-140">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="8ada9-141">使用运算符或使用具有静态解析的类型参数的其他函数的内联方法和函数也可以使用静态解析的类型参数。</span><span class="sxs-lookup"><span data-stu-id="8ada9-141">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="8ada9-142">通常，类型推理会将此类内联函数推断为具有静态解析的类型参数。</span><span class="sxs-lookup"><span data-stu-id="8ada9-142">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="8ada9-143">下面的示例演示了一个运算符定义，该运算符定义被推断为具有静态解析的类型参数。</span><span class="sxs-lookup"><span data-stu-id="8ada9-143">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="8ada9-144">`(+@)` 的解析类型基于 `(+)` 和 `(*)`的使用，这两种方法都会导致类型推理推断静态解析的类型参数上的成员约束。</span><span class="sxs-lookup"><span data-stu-id="8ada9-144">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="8ada9-145">解析后的类型（如F#解释器中所示）如下所示。</span><span class="sxs-lookup"><span data-stu-id="8ada9-145">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="8ada9-146">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="8ada9-146">The output is as follows.</span></span>

```console
2
1.500000
```

<span data-ttu-id="8ada9-147">从F# 4.1 开始，还可以在静态解析的类型参数签名中指定具体的类型名称。</span><span class="sxs-lookup"><span data-stu-id="8ada9-147">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="8ada9-148">在以前版本的语言中，类型名称实际上可能由编译器推断，但实际上无法在签名中指定。</span><span class="sxs-lookup"><span data-stu-id="8ada9-148">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="8ada9-149">从F# 4.1，你还可以在静态解析的类型参数签名中指定具体的类型名称。</span><span class="sxs-lookup"><span data-stu-id="8ada9-149">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="8ada9-150">以下是一个示例：</span><span class="sxs-lookup"><span data-stu-id="8ada9-150">Here's an example:</span></span>

```fsharp
let inline konst x _ = x

type CFunctor() =
    static member inline fmap (f: ^a -> ^b, a: ^a list) = List.map f a
    static member inline fmap (f: ^a -> ^b, a: ^a option) =
        match a with
        | None -> None
        | Some x -> Some (f x)

    // default implementation of replace
    static member inline replace< ^a, ^b, ^c, ^d, ^e when ^a :> CFunctor and (^a or ^d): (static member fmap: (^b -> ^c) * ^d -> ^e) > (a, f) =
        ((^a or ^d) : (static member fmap : (^b -> ^c) * ^d -> ^e) (konst a, f))

    // call overridden replace if present
    static member inline replace< ^a, ^b, ^c when ^b: (static member replace: ^a * ^b -> ^c)>(a: ^a, f: ^b) =
        (^b : (static member replace: ^a * ^b -> ^c) (a, f))

let inline replace_instance< ^a, ^b, ^c, ^d when (^a or ^c): (static member replace: ^b * ^c -> ^d)> (a: ^b, f: ^c) =
        ((^a or ^c): (static member replace: ^b * ^c -> ^d) (a, f))

// Note the concrete type 'CFunctor' specified in the signature
let inline replace (a: ^a) (f: ^b): ^a0 when (CFunctor or  ^b): (static member replace: ^a *  ^b ->  ^a0) =
    replace_instance<CFunctor, _, _, _> (a, f)
```

## <a name="see-also"></a><span data-ttu-id="8ada9-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ada9-151">See also</span></span>

- [<span data-ttu-id="8ada9-152">泛型</span><span class="sxs-lookup"><span data-stu-id="8ada9-152">Generics</span></span>](index.md)
- [<span data-ttu-id="8ada9-153">类型推断</span><span class="sxs-lookup"><span data-stu-id="8ada9-153">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="8ada9-154">自动泛化</span><span class="sxs-lookup"><span data-stu-id="8ada9-154">Automatic Generalization</span></span>](automatic-generalization.md)
- [<span data-ttu-id="8ada9-155">约束</span><span class="sxs-lookup"><span data-stu-id="8ada9-155">Constraints</span></span>](constraints.md)
- [<span data-ttu-id="8ada9-156">内联函数</span><span class="sxs-lookup"><span data-stu-id="8ada9-156">Inline Functions</span></span>](../functions/inline-functions.md)
