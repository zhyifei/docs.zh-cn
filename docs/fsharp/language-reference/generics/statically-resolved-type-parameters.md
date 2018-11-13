---
title: 静态解析的类型参数 (F#)
description: 了解如何使用 F# 静态解析的类型参数，它将被替换为实际类型在编译时而不是在运行时。
ms.date: 05/16/2016
ms.openlocfilehash: 747917fef2746dcbf363ef4b717ace5e47229800
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "48032772"
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="e30df-103">静态解析的类型参数</span><span class="sxs-lookup"><span data-stu-id="e30df-103">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="e30df-104">一个*静态解析的类型参数*是在编译时而不是在运行时替换为实际类型的类型参数。</span><span class="sxs-lookup"><span data-stu-id="e30df-104">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="e30df-105">它们的前面有一个插入符号 (^) 符号。</span><span class="sxs-lookup"><span data-stu-id="e30df-105">They are preceded by a caret (^) symbol.</span></span>

## <a name="syntax"></a><span data-ttu-id="e30df-106">语法</span><span class="sxs-lookup"><span data-stu-id="e30df-106">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="e30df-107">备注</span><span class="sxs-lookup"><span data-stu-id="e30df-107">Remarks</span></span>

<span data-ttu-id="e30df-108">在 F# 语言中，有两种不同的类型参数。</span><span class="sxs-lookup"><span data-stu-id="e30df-108">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="e30df-109">第一个类型为标准的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="e30df-109">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="e30df-110">这些类型由撇号 （'），作为 in 参数指示`'T`和`'U`。</span><span class="sxs-lookup"><span data-stu-id="e30df-110">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="e30df-111">它们等效于其他.NET Framework 语言中的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="e30df-111">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="e30df-112">另外一种类型是静态解析并由一个插入符号，如`^T`和`^U`。</span><span class="sxs-lookup"><span data-stu-id="e30df-112">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="e30df-113">静态解析的类型参数是主要适用于与约束，可用于指定类型参数必须为可具有的特定成员的成员约束一起使用。</span><span class="sxs-lookup"><span data-stu-id="e30df-113">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="e30df-114">没有办法使用常规的泛型类型参数创建这种类型的约束。</span><span class="sxs-lookup"><span data-stu-id="e30df-114">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="e30df-115">下表总结了两种类型的类型参数之间的异同。</span><span class="sxs-lookup"><span data-stu-id="e30df-115">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="e30df-116">功能</span><span class="sxs-lookup"><span data-stu-id="e30df-116">Feature</span></span>|<span data-ttu-id="e30df-117">泛型</span><span class="sxs-lookup"><span data-stu-id="e30df-117">Generic</span></span>|<span data-ttu-id="e30df-118">静态解析的</span><span class="sxs-lookup"><span data-stu-id="e30df-118">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="e30df-119">语法</span><span class="sxs-lookup"><span data-stu-id="e30df-119">Syntax</span></span>|<span data-ttu-id="e30df-120">`'T`， `'U`</span><span class="sxs-lookup"><span data-stu-id="e30df-120">`'T`, `'U`</span></span>|<span data-ttu-id="e30df-121">`^T`， `^U`</span><span class="sxs-lookup"><span data-stu-id="e30df-121">`^T`, `^U`</span></span>|
|<span data-ttu-id="e30df-122">解决时间</span><span class="sxs-lookup"><span data-stu-id="e30df-122">Resolution time</span></span>|<span data-ttu-id="e30df-123">运行时</span><span class="sxs-lookup"><span data-stu-id="e30df-123">Run time</span></span>|<span data-ttu-id="e30df-124">编译时间</span><span class="sxs-lookup"><span data-stu-id="e30df-124">Compile time</span></span>|
|<span data-ttu-id="e30df-125">成员约束</span><span class="sxs-lookup"><span data-stu-id="e30df-125">Member constraints</span></span>|<span data-ttu-id="e30df-126">不能与成员约束一起使用。</span><span class="sxs-lookup"><span data-stu-id="e30df-126">Cannot be used with member constraints.</span></span>|<span data-ttu-id="e30df-127">可以与成员约束一起使用。</span><span class="sxs-lookup"><span data-stu-id="e30df-127">Can be used with member constraints.</span></span>|
|<span data-ttu-id="e30df-128">代码生成</span><span class="sxs-lookup"><span data-stu-id="e30df-128">Code generation</span></span>|<span data-ttu-id="e30df-129">使用标准的泛型类型参数的类型 （或方法） 会导致单个泛型类型或方法的生成。</span><span class="sxs-lookup"><span data-stu-id="e30df-129">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="e30df-130">生成多个实例化的类型和方法，每个类型的需要。</span><span class="sxs-lookup"><span data-stu-id="e30df-130">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="e30df-131">与类型一起使用</span><span class="sxs-lookup"><span data-stu-id="e30df-131">Use with types</span></span>|<span data-ttu-id="e30df-132">可以在类型上使用。</span><span class="sxs-lookup"><span data-stu-id="e30df-132">Can be used on types.</span></span>|<span data-ttu-id="e30df-133">不能在类型上使用。</span><span class="sxs-lookup"><span data-stu-id="e30df-133">Cannot be used on types.</span></span>|
|<span data-ttu-id="e30df-134">使用内联函数</span><span class="sxs-lookup"><span data-stu-id="e30df-134">Use with inline functions</span></span>|<span data-ttu-id="e30df-135">不是。</span><span class="sxs-lookup"><span data-stu-id="e30df-135">No.</span></span> <span data-ttu-id="e30df-136">内联函数不能使用标准的泛型类型参数进行参数化。</span><span class="sxs-lookup"><span data-stu-id="e30df-136">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="e30df-137">可以。</span><span class="sxs-lookup"><span data-stu-id="e30df-137">Yes.</span></span> <span data-ttu-id="e30df-138">静态解析的类型参数不能用于函数或不是内联的方法。</span><span class="sxs-lookup"><span data-stu-id="e30df-138">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="e30df-139">许多 F# 核心库函数，尤其是运算符，具有静态解析的类型参数。</span><span class="sxs-lookup"><span data-stu-id="e30df-139">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="e30df-140">这些函数和运算符将以内联方式，并导致数值计算的高效的代码生成。</span><span class="sxs-lookup"><span data-stu-id="e30df-140">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="e30df-141">内联方法和函数，使用运算符，或使用其他具有静态解析的类型参数的函数还可以使用静态解析的类型参数本身。</span><span class="sxs-lookup"><span data-stu-id="e30df-141">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="e30df-142">通常情况下，类型推理来推断这类内联函数具有静态解析的类型参数。</span><span class="sxs-lookup"><span data-stu-id="e30df-142">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="e30df-143">下面的示例演示为具有静态解析的类型参数推断出的运算符定义。</span><span class="sxs-lookup"><span data-stu-id="e30df-143">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="e30df-144">解析的类型的`(+@)`的同时使用基于`(+)`和`(*)`，这两个的这会导致类型推理来推断成员的静态解析的类型参数的约束。</span><span class="sxs-lookup"><span data-stu-id="e30df-144">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="e30df-145">解析的类型，如所示的 F# 解释器，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e30df-145">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="e30df-146">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="e30df-146">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="e30df-147">从 F# 4.1 开始，你还可以指定具体的类型名称中静态解析的类型的参数签名。</span><span class="sxs-lookup"><span data-stu-id="e30df-147">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="e30df-148">在以前版本的语言，类型名称实际上无法由编译器推断出，但无法实际指定的签名中。</span><span class="sxs-lookup"><span data-stu-id="e30df-148">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="e30df-149">截至 F# 4.1，还可以在静态解析的类型的参数签名中指定具体的类型名称。</span><span class="sxs-lookup"><span data-stu-id="e30df-149">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="e30df-150">以下是一个示例：</span><span class="sxs-lookup"><span data-stu-id="e30df-150">Here's an example:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e30df-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="e30df-151">See also</span></span>

- [<span data-ttu-id="e30df-152">泛型</span><span class="sxs-lookup"><span data-stu-id="e30df-152">Generics</span></span>](index.md)
- [<span data-ttu-id="e30df-153">类型推断</span><span class="sxs-lookup"><span data-stu-id="e30df-153">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="e30df-154">自动泛化</span><span class="sxs-lookup"><span data-stu-id="e30df-154">Automatic Generalization</span></span>](automatic-generalization.md)
- [<span data-ttu-id="e30df-155">约束</span><span class="sxs-lookup"><span data-stu-id="e30df-155">Constraints</span></span>](constraints.md)
- [<span data-ttu-id="e30df-156">内联函数</span><span class="sxs-lookup"><span data-stu-id="e30df-156">Inline Functions</span></span>](../functions/inline-functions.md)
