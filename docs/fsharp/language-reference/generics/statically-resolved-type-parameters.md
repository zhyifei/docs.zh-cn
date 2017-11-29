---
title: "静态解析的类型参数 (F#)"
description: "了解如何使用 F # 静态解析的类型参数，它将被替换为实际类型在编译时而不是在运行时。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b3797415-3e49-4f8a-a8ee-fa614c5721aa
ms.openlocfilehash: 88b4590a4323e75949c1915503b51793283792de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="8088b-104">静态解析的类型参数</span><span class="sxs-lookup"><span data-stu-id="8088b-104">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="8088b-105">A*静态解析的类型参数*是将被替换为实际类型在编译时而不是在运行时的类型参数。</span><span class="sxs-lookup"><span data-stu-id="8088b-105">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="8088b-106">它们的前面有脱字号 (^) 符号。</span><span class="sxs-lookup"><span data-stu-id="8088b-106">They are preceded by a caret (^) symbol.</span></span>


## <a name="syntax"></a><span data-ttu-id="8088b-107">语法</span><span class="sxs-lookup"><span data-stu-id="8088b-107">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="8088b-108">备注</span><span class="sxs-lookup"><span data-stu-id="8088b-108">Remarks</span></span>
<span data-ttu-id="8088b-109">在 F # 语言中，有两种不同的类型参数。</span><span class="sxs-lookup"><span data-stu-id="8088b-109">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="8088b-110">第一种是标准的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="8088b-110">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="8088b-111">这些类型由撇号 （'），作为 in 参数指示`'T`和`'U`。</span><span class="sxs-lookup"><span data-stu-id="8088b-111">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="8088b-112">它们是等效于其他.NET Framework 语言中的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="8088b-112">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="8088b-113">另外一种类型是静态解析并由一个插入符号，如指示`^T`和`^U`。</span><span class="sxs-lookup"><span data-stu-id="8088b-113">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="8088b-114">静态解析的类型参数是主要适用于与成员限制，这是允许你指定的类型自变量必须才可以使用具有特定的成员的约束一起使用。</span><span class="sxs-lookup"><span data-stu-id="8088b-114">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="8088b-115">没有方法来通过使用正则泛型类型参数创建这种类型的约束。</span><span class="sxs-lookup"><span data-stu-id="8088b-115">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="8088b-116">下表总结了两种类型的类型参数之间的异同。</span><span class="sxs-lookup"><span data-stu-id="8088b-116">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="8088b-117">功能</span><span class="sxs-lookup"><span data-stu-id="8088b-117">Feature</span></span>|<span data-ttu-id="8088b-118">泛型</span><span class="sxs-lookup"><span data-stu-id="8088b-118">Generic</span></span>|<span data-ttu-id="8088b-119">静态解析的</span><span class="sxs-lookup"><span data-stu-id="8088b-119">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="8088b-120">语法</span><span class="sxs-lookup"><span data-stu-id="8088b-120">Syntax</span></span>|<span data-ttu-id="8088b-121">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="8088b-121">`'T`, `'U`</span></span>|<span data-ttu-id="8088b-122">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="8088b-122">`^T`, `^U`</span></span>|
|<span data-ttu-id="8088b-123">解决时间</span><span class="sxs-lookup"><span data-stu-id="8088b-123">Resolution time</span></span>|<span data-ttu-id="8088b-124">运行时</span><span class="sxs-lookup"><span data-stu-id="8088b-124">Run time</span></span>|<span data-ttu-id="8088b-125">编译时间</span><span class="sxs-lookup"><span data-stu-id="8088b-125">Compile time</span></span>|
|<span data-ttu-id="8088b-126">成员约束</span><span class="sxs-lookup"><span data-stu-id="8088b-126">Member constraints</span></span>|<span data-ttu-id="8088b-127">不能与成员约束使用。</span><span class="sxs-lookup"><span data-stu-id="8088b-127">Cannot be used with member constraints.</span></span>|<span data-ttu-id="8088b-128">可以与成员约束一起使用。</span><span class="sxs-lookup"><span data-stu-id="8088b-128">Can be used with member constraints.</span></span>|
|<span data-ttu-id="8088b-129">代码生成</span><span class="sxs-lookup"><span data-stu-id="8088b-129">Code generation</span></span>|<span data-ttu-id="8088b-130">使用标准的泛型类型参数的类型 （或方法） 产生的单个泛型类型或方法的生成结果。</span><span class="sxs-lookup"><span data-stu-id="8088b-130">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="8088b-131">生成的类型和方法的多个实例化，每个类型的需要。</span><span class="sxs-lookup"><span data-stu-id="8088b-131">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="8088b-132">与类型一起使用</span><span class="sxs-lookup"><span data-stu-id="8088b-132">Use with types</span></span>|<span data-ttu-id="8088b-133">可以在类型上使用。</span><span class="sxs-lookup"><span data-stu-id="8088b-133">Can be used on types.</span></span>|<span data-ttu-id="8088b-134">不能在类型上使用。</span><span class="sxs-lookup"><span data-stu-id="8088b-134">Cannot be used on types.</span></span>|
|<span data-ttu-id="8088b-135">使用内联函数</span><span class="sxs-lookup"><span data-stu-id="8088b-135">Use with inline functions</span></span>|<span data-ttu-id="8088b-136">不可以。</span><span class="sxs-lookup"><span data-stu-id="8088b-136">No.</span></span> <span data-ttu-id="8088b-137">内联函数不能使用标准的泛型类型参数参数化。</span><span class="sxs-lookup"><span data-stu-id="8088b-137">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="8088b-138">可以。</span><span class="sxs-lookup"><span data-stu-id="8088b-138">Yes.</span></span> <span data-ttu-id="8088b-139">静态解析的类型参数不能用于函数或不是内联的方法。</span><span class="sxs-lookup"><span data-stu-id="8088b-139">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="8088b-140">许多 F # 核心库函数，尤其是运算符，具有静态解析的类型参数。</span><span class="sxs-lookup"><span data-stu-id="8088b-140">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="8088b-141">这些函数和运算符将以内联方式，并且导致数值计算的高效的代码生成。</span><span class="sxs-lookup"><span data-stu-id="8088b-141">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="8088b-142">内联方法和函数，使用运算符，或使用其他具有静态解析的类型参数的函数还可以使用自己的静态解析的类型参数。</span><span class="sxs-lookup"><span data-stu-id="8088b-142">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="8088b-143">通常情况下，类型推断功能来推断此类为具有静态解析类型参数的内联函数。</span><span class="sxs-lookup"><span data-stu-id="8088b-143">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="8088b-144">下面的示例演示推断为具有静态解析的类型参数的运算符定义。</span><span class="sxs-lookup"><span data-stu-id="8088b-144">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="8088b-145">解析的类型的`(+@)`取决于如何使用`(+)`和`(*)`，这两个的这导致类型推理来推断成员的静态解析的类型参数约束。</span><span class="sxs-lookup"><span data-stu-id="8088b-145">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="8088b-146">解析的类型，F # 解释器中, 所示是，如下所示。</span><span class="sxs-lookup"><span data-stu-id="8088b-146">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member (+) : ^a * ^b -> ^d) and
(^a or ^c) : (static member (+) : ^a * ^c -> ^b)
```

<span data-ttu-id="8088b-147">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="8088b-147">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="8088b-148">F # 4.1 开始，你还可以指定具体的类型名称静态解析的类型的参数签名中。</span><span class="sxs-lookup"><span data-stu-id="8088b-148">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="8088b-149">在以前版本的语言，类型名称实际上无法由编译器推断，但无法实际指定的签名中。</span><span class="sxs-lookup"><span data-stu-id="8088b-149">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="8088b-150">截至 F # 4.1，还可以在静态解析的类型的参数签名中指定具体的类型名称。</span><span class="sxs-lookup"><span data-stu-id="8088b-150">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="8088b-151">以下是一个示例：</span><span class="sxs-lookup"><span data-stu-id="8088b-151">Here's an example:</span></span>

```fsharp
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

## <a name="see-also"></a><span data-ttu-id="8088b-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8088b-152">See Also</span></span>
[<span data-ttu-id="8088b-153">泛型</span><span class="sxs-lookup"><span data-stu-id="8088b-153">Generics</span></span>](index.md)

[<span data-ttu-id="8088b-154">类型推断</span><span class="sxs-lookup"><span data-stu-id="8088b-154">Type Inference</span></span>](../type-inference.md)

[<span data-ttu-id="8088b-155">自动泛化</span><span class="sxs-lookup"><span data-stu-id="8088b-155">Automatic Generalization</span></span>](automatic-generalization.md)

[<span data-ttu-id="8088b-156">约束</span><span class="sxs-lookup"><span data-stu-id="8088b-156">Constraints</span></span>](constraints.md)

[<span data-ttu-id="8088b-157">内联函数</span><span class="sxs-lookup"><span data-stu-id="8088b-157">Inline Functions</span></span>](../functions/inline-functions.md)
