---
title: Byref
description: 了解 F# 中的 byref 和类似 byref 的类型，这些类型用于低级编程。
ms.date: 11/04/2019
ms.openlocfilehash: 527f465ee87fe153a2deae1306b6730531dc4123
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187050"
---
# <a name="byrefs"></a><span data-ttu-id="87c04-103">Byref</span><span class="sxs-lookup"><span data-stu-id="87c04-103">Byrefs</span></span>

<span data-ttu-id="87c04-104">F# 具有在低级编程领域处理的两个主要功能领域：</span><span class="sxs-lookup"><span data-stu-id="87c04-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="87c04-105">`byref`/类型`inref`，/托管`outref`指针。</span><span class="sxs-lookup"><span data-stu-id="87c04-105">The `byref`/`inref`/`outref` types, which are managed pointers.</span></span> <span data-ttu-id="87c04-106">它们对使用有限制，因此您不能编译在运行时无效的程序。</span><span class="sxs-lookup"><span data-stu-id="87c04-106">They have restrictions on usage so that you cannot compile a program that is invalid at run time.</span></span>
* <span data-ttu-id="87c04-107">类似`byref`结构的结构，它是具有与 相似的语义和相同的编译时间限制[的结构](structures.md)`byref<'T>`。</span><span class="sxs-lookup"><span data-stu-id="87c04-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="87c04-108">一个例子是<xref:System.Span%601>。</span><span class="sxs-lookup"><span data-stu-id="87c04-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="87c04-109">语法</span><span class="sxs-lookup"><span data-stu-id="87c04-109">Syntax</span></span>

```fsharp
// Byref types as parameters
let f (x: byref<'T>) = ()
let g (x: inref<'T>) = ()
let h (x: outref<'T>) = ()

// Calling a function with a byref parameter
let mutable x = 3
f &x

// Declaring a byref-like struct
open System.Runtime.CompilerServices

[<Struct; IsByRefLike>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

## <a name="byref-inref-and-outref"></a><span data-ttu-id="87c04-110">Byref、inref 和 outref</span><span class="sxs-lookup"><span data-stu-id="87c04-110">Byref, inref, and outref</span></span>

<span data-ttu-id="87c04-111">有三种形式： `byref`</span><span class="sxs-lookup"><span data-stu-id="87c04-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="87c04-112">`inref<'T>`，用于读取基础值的托管指针。</span><span class="sxs-lookup"><span data-stu-id="87c04-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="87c04-113">`outref<'T>`，用于写入基础值的托管指针。</span><span class="sxs-lookup"><span data-stu-id="87c04-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="87c04-114">`byref<'T>`，用于读取和写入基础值的托管指针。</span><span class="sxs-lookup"><span data-stu-id="87c04-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="87c04-115">`byref<'T>`可以传递预期 为`inref<'T>`的 。</span><span class="sxs-lookup"><span data-stu-id="87c04-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="87c04-116">同样，`byref<'T>`可以传递预期 为`outref<'T>`的 。</span><span class="sxs-lookup"><span data-stu-id="87c04-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="87c04-117">使用参考</span><span class="sxs-lookup"><span data-stu-id="87c04-117">Using byrefs</span></span>

<span data-ttu-id="87c04-118">要使用`inref<'T>`， 需要获取具有 的`&`指针值：</span><span class="sxs-lookup"><span data-stu-id="87c04-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="87c04-119">要使用`outref<'T>`或`byref<'T>`写入指针，还必须使获取指向`mutable`的指针的值。</span><span class="sxs-lookup"><span data-stu-id="87c04-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn "Now: %s" (dt.ToString())
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

<span data-ttu-id="87c04-120">如果只编写指针而不是读取指针，请考虑使用`outref<'T>`而不是`byref<'T>`。</span><span class="sxs-lookup"><span data-stu-id="87c04-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="87c04-121">Inref 语义</span><span class="sxs-lookup"><span data-stu-id="87c04-121">Inref semantics</span></span>

<span data-ttu-id="87c04-122">考虑下列代码：</span><span class="sxs-lookup"><span data-stu-id="87c04-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="87c04-123">从语义上讲，这意味着以下内容：</span><span class="sxs-lookup"><span data-stu-id="87c04-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="87c04-124">指针的`x`持有者只能使用它读取该值。</span><span class="sxs-lookup"><span data-stu-id="87c04-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="87c04-125">任何获取到`struct`嵌套在其中`SomeStruct`的字段的指针都是`inref<_>`给定的类型。</span><span class="sxs-lookup"><span data-stu-id="87c04-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="87c04-126">以下内容也是如此：</span><span class="sxs-lookup"><span data-stu-id="87c04-126">The following is also true:</span></span>

* <span data-ttu-id="87c04-127">其他线程或别名对 没有写入访问权限，这没有任何含义`x`。</span><span class="sxs-lookup"><span data-stu-id="87c04-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="87c04-128">没有任何暗示是`SomeStruct`不变的`x`，因为是一个。 `inref`</span><span class="sxs-lookup"><span data-stu-id="87c04-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="87c04-129">但是，**对于不可变**的 F# 值类型，`this`将指针推断为`inref`。</span><span class="sxs-lookup"><span data-stu-id="87c04-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="87c04-130">所有这些规则加在一`inref`起意味着指针的持有者不能修改指向的内存的即时内容。</span><span class="sxs-lookup"><span data-stu-id="87c04-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="87c04-131">外部参照语义</span><span class="sxs-lookup"><span data-stu-id="87c04-131">Outref semantics</span></span>

<span data-ttu-id="87c04-132">的目的是`outref<'T>`指示指针应只写入。</span><span class="sxs-lookup"><span data-stu-id="87c04-132">The purpose of `outref<'T>` is to indicate that the pointer should only be written to.</span></span> <span data-ttu-id="87c04-133">出乎意料的是`outref<'T>`，允许读取基础值，尽管它的名称。</span><span class="sxs-lookup"><span data-stu-id="87c04-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="87c04-134">这是出于兼容性目的。</span><span class="sxs-lookup"><span data-stu-id="87c04-134">This is for compatibility purposes.</span></span> <span data-ttu-id="87c04-135">从语义上讲`outref<'T>`，与 没有什么`byref<'T>`不同。</span><span class="sxs-lookup"><span data-stu-id="87c04-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="87c04-136">与 C 的互通\#</span><span class="sxs-lookup"><span data-stu-id="87c04-136">Interop with C\#</span></span>

<span data-ttu-id="87c04-137">除了`in ref``ref`返回之外，C# 还支持 和`out ref`关键字。</span><span class="sxs-lookup"><span data-stu-id="87c04-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="87c04-138">下表显示了 F# 如何解释 C# 发出的内容：</span><span class="sxs-lookup"><span data-stu-id="87c04-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="87c04-139">C# 构造</span><span class="sxs-lookup"><span data-stu-id="87c04-139">C# construct</span></span>|<span data-ttu-id="87c04-140">F# 推断</span><span class="sxs-lookup"><span data-stu-id="87c04-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="87c04-141">`ref`返回值</span><span class="sxs-lookup"><span data-stu-id="87c04-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="87c04-142">`ref readonly`返回值</span><span class="sxs-lookup"><span data-stu-id="87c04-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="87c04-143">`in ref` 参数</span><span class="sxs-lookup"><span data-stu-id="87c04-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="87c04-144">`out ref` 参数</span><span class="sxs-lookup"><span data-stu-id="87c04-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="87c04-145">下表显示了 F# 发出的内容：</span><span class="sxs-lookup"><span data-stu-id="87c04-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="87c04-146">F# 构造</span><span class="sxs-lookup"><span data-stu-id="87c04-146">F# construct</span></span>|<span data-ttu-id="87c04-147">已发出构造</span><span class="sxs-lookup"><span data-stu-id="87c04-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="87c04-148">`inref<'T>` 参数</span><span class="sxs-lookup"><span data-stu-id="87c04-148">`inref<'T>` argument</span></span>|<span data-ttu-id="87c04-149">`[In]`参数上的属性</span><span class="sxs-lookup"><span data-stu-id="87c04-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="87c04-150">`inref<'T>`返回</span><span class="sxs-lookup"><span data-stu-id="87c04-150">`inref<'T>` return</span></span>|<span data-ttu-id="87c04-151">`modreq`值的属性</span><span class="sxs-lookup"><span data-stu-id="87c04-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="87c04-152">`inref<'T>`抽象插槽或实现</span><span class="sxs-lookup"><span data-stu-id="87c04-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="87c04-153">`modreq`在参数或返回</span><span class="sxs-lookup"><span data-stu-id="87c04-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="87c04-154">`outref<'T>` 参数</span><span class="sxs-lookup"><span data-stu-id="87c04-154">`outref<'T>` argument</span></span>|<span data-ttu-id="87c04-155">`[Out]`参数上的属性</span><span class="sxs-lookup"><span data-stu-id="87c04-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="87c04-156">类型推理和重载规则</span><span class="sxs-lookup"><span data-stu-id="87c04-156">Type inference and overloading rules</span></span>

<span data-ttu-id="87c04-157">在`inref<'T>`以下情况下，F# 编译器会推断类型：</span><span class="sxs-lookup"><span data-stu-id="87c04-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="87c04-158">具有`IsReadOnly`属性的 .NET 参数或返回类型。</span><span class="sxs-lookup"><span data-stu-id="87c04-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="87c04-159">没有`this`可变字段的结构类型的指针。</span><span class="sxs-lookup"><span data-stu-id="87c04-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="87c04-160">从其他`inref<_>`指针派生的内存位置的地址。</span><span class="sxs-lookup"><span data-stu-id="87c04-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="87c04-161">当采用 隐式地址`inref`时，具有类型`SomeType`参数的重载优先于具有类型`inref<SomeType>`类型的重载。</span><span class="sxs-lookup"><span data-stu-id="87c04-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="87c04-162">例如：</span><span class="sxs-lookup"><span data-stu-id="87c04-162">For example:</span></span>

```fsharp
type C() =
    static member M(x: System.DateTime) = x.AddDays(1.0)
    static member M(x: inref<System.DateTime>) = x.AddDays(2.0)
    static member M2(x: System.DateTime, y: int) = x.AddDays(1.0)
    static member M2(x: inref<System.DateTime>, y: int) = x.AddDays(2.0)

let res = System.DateTime.Now
let v =  C.M(res)
let v2 =  C.M2(res, 4)
```

<span data-ttu-id="87c04-163">在这两种情况下，重`System.DateTime`载将得到解决，而不是重载。 `inref<System.DateTime>`</span><span class="sxs-lookup"><span data-stu-id="87c04-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="87c04-164">类似 Byref 的结构</span><span class="sxs-lookup"><span data-stu-id="87c04-164">Byref-like structs</span></span>

<span data-ttu-id="87c04-165">`byref`/除了`outref``byref`三者组之外，您还可以定义自己的结构，这些结构可以遵循类似语义。 `inref` /</span><span class="sxs-lookup"><span data-stu-id="87c04-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="87c04-166">这与属性一<xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>起完成：</span><span class="sxs-lookup"><span data-stu-id="87c04-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="87c04-167">`IsByRefLike`并不意味着`Struct`.</span><span class="sxs-lookup"><span data-stu-id="87c04-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="87c04-168">两者都必须存在于类型上。</span><span class="sxs-lookup"><span data-stu-id="87c04-168">Both must be present on the type.</span></span>

<span data-ttu-id="87c04-169">F#`byref`中的"类似"结构是一种堆栈绑定值类型。</span><span class="sxs-lookup"><span data-stu-id="87c04-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="87c04-170">它永远不会在托管堆上分配。</span><span class="sxs-lookup"><span data-stu-id="87c04-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="87c04-171">`byref`类似结构对于高性能编程非常有用，因为它通过一组有关生存期和非捕获的强检查强制执行。</span><span class="sxs-lookup"><span data-stu-id="87c04-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="87c04-172">规则包括：</span><span class="sxs-lookup"><span data-stu-id="87c04-172">The rules are:</span></span>

* <span data-ttu-id="87c04-173">它们可用作函数参数、方法参数、局部变量、方法返回。</span><span class="sxs-lookup"><span data-stu-id="87c04-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="87c04-174">它们不能是类的静态或实例成员或正常结构。</span><span class="sxs-lookup"><span data-stu-id="87c04-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="87c04-175">它们不能被任何闭包构造（`async`方法或 lambda 表达式）捕获。</span><span class="sxs-lookup"><span data-stu-id="87c04-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="87c04-176">它们不能用作泛型参数。</span><span class="sxs-lookup"><span data-stu-id="87c04-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="87c04-177">最后一点对于 F# 管道样式编程至关重要，用于`|>`参数化其输入类型的泛型函数也是如此。</span><span class="sxs-lookup"><span data-stu-id="87c04-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="87c04-178">将来可能会放宽`|>`此限制，因为它是内联的，并且不会对其正文中的非内联泛型函数进行任何调用。</span><span class="sxs-lookup"><span data-stu-id="87c04-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="87c04-179">尽管这些规则严格限制使用，但它们这样做是为了以安全的方式实现高性能计算的承诺。</span><span class="sxs-lookup"><span data-stu-id="87c04-179">Although these rules strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="87c04-180">Byref 返回</span><span class="sxs-lookup"><span data-stu-id="87c04-180">Byref returns</span></span>

<span data-ttu-id="87c04-181">可以生成和使用 F# 函数或成员的 Byref 返回。</span><span class="sxs-lookup"><span data-stu-id="87c04-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="87c04-182">使用`byref`-返回方法时，将隐式取消引用该值。</span><span class="sxs-lookup"><span data-stu-id="87c04-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="87c04-183">例如：</span><span class="sxs-lookup"><span data-stu-id="87c04-183">For example:</span></span>

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

<span data-ttu-id="87c04-184">要返回值 byref，包含该值的变量必须比当前作用域长。</span><span class="sxs-lookup"><span data-stu-id="87c04-184">To return a value byref, the variable that contains the value must live longer than the current scope.</span></span>
<span data-ttu-id="87c04-185">此外，要返回 byref，`&value`请使用 （其中值是比当前作用域长的变量）。</span><span class="sxs-lookup"><span data-stu-id="87c04-185">Also, to return byref, use `&value` (where value is a variable that lives longer than the current scope).</span></span>

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

<span data-ttu-id="87c04-186">为了避免隐式取消引用（例如通过多个链接调用传递引用），请使用`&x`（值在哪里）。 `x`</span><span class="sxs-lookup"><span data-stu-id="87c04-186">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="87c04-187">您也可以直接分配给返回`byref`。</span><span class="sxs-lookup"><span data-stu-id="87c04-187">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="87c04-188">请考虑以下（高度必要）计划：</span><span class="sxs-lookup"><span data-stu-id="87c04-188">Consider the following (highly imperative) program:</span></span>

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override _.ToString() = String.Join(' ', nums)

    member _.FindLargestSmallerThan(target: int) =
        let mutable ctr = nums.Length - 1

        while ctr > 0 && nums.[ctr] >= target do ctr <- ctr - 1

        if ctr > 0 then &nums.[ctr] else &nums.[0]

[<EntryPoint>]
let main argv =
    let c = C()
    printfn "Original sequence: %s" (c.ToString())

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn "New sequence:      %s" (c.ToString())

    0 // return an integer exit code
```

<span data-ttu-id="87c04-189">以下是输出：</span><span class="sxs-lookup"><span data-stu-id="87c04-189">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="87c04-190">字节范围</span><span class="sxs-lookup"><span data-stu-id="87c04-190">Scoping for byrefs</span></span>

<span data-ttu-id="87c04-191">`let`绑定值不能使其引用超过定义该值的范围。</span><span class="sxs-lookup"><span data-stu-id="87c04-191">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="87c04-192">例如，不允许使用以下内容：</span><span class="sxs-lookup"><span data-stu-id="87c04-192">For example, the following is disallowed:</span></span>

```fsharp
let test2 () =
    let x = 12
    &x // Error: 'x' exceeds its defined scope!

let test () =
    let x =
        let y = 1
        &y // Error: `y` exceeds its defined scope!
    ()
```

<span data-ttu-id="87c04-193">这可以防止您获得不同的结果，具体取决于是否使用优化进行编译。</span><span class="sxs-lookup"><span data-stu-id="87c04-193">This prevents you from getting different results depending on if you compile with optimizations or not.</span></span>
