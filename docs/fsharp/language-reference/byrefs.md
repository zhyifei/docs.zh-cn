---
title: 'Byref （F #）'
description: '了解有关 byref 和类似 byref 类型在 F # 中，用于低级编程。'
ms.date: 09/02/2018
ms.openlocfilehash: 6131104e4325f77da84368c337f998c6b2b5309b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47082872"
---
# <a name="byrefs"></a><span data-ttu-id="4c333-103">Byref</span><span class="sxs-lookup"><span data-stu-id="4c333-103">Byrefs</span></span>

<span data-ttu-id="4c333-104">F # 有处理低级别编程的空间中的两个主要功能区域：</span><span class="sxs-lookup"><span data-stu-id="4c333-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="4c333-105">`byref` / `inref` / `outref`类型，它们是托管的指针。</span><span class="sxs-lookup"><span data-stu-id="4c333-105">The `byref`/`inref`/`outref` types, which are a managed pointers.</span></span> <span data-ttu-id="4c333-106">必须对使用情况的限制，以便不能编译的程序在运行时无效。</span><span class="sxs-lookup"><span data-stu-id="4c333-106">They have restrictions on usage so that you cannot compile a program that is invalid at runtime.</span></span>
* <span data-ttu-id="4c333-107">一个`byref`-如结构，即[结构](structures.md)具有类似语义和相同的编译时限制`byref<'T>`。</span><span class="sxs-lookup"><span data-stu-id="4c333-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="4c333-108">一个示例是<xref:System.Span%601>。</span><span class="sxs-lookup"><span data-stu-id="4c333-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="4c333-109">语法</span><span class="sxs-lookup"><span data-stu-id="4c333-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="4c333-110">Byref、 inref 和 outref</span><span class="sxs-lookup"><span data-stu-id="4c333-110">Byref, inref, and outref</span></span>

<span data-ttu-id="4c333-111">有三种形式的`byref`:</span><span class="sxs-lookup"><span data-stu-id="4c333-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="4c333-112">`inref<'T>`用于读取的基础值的托管的指针。</span><span class="sxs-lookup"><span data-stu-id="4c333-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="4c333-113">`outref<'T>`用于将写入的基础值的托管的指针。</span><span class="sxs-lookup"><span data-stu-id="4c333-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="4c333-114">`byref<'T>`用于读取和写入的基础值的托管的指针。</span><span class="sxs-lookup"><span data-stu-id="4c333-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="4c333-115">一个`byref<'T>`可以在其中传递`inref<'T>`预期。</span><span class="sxs-lookup"><span data-stu-id="4c333-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="4c333-116">同样，`byref<'T>`可以在其中传递`outref<'T>`预期。</span><span class="sxs-lookup"><span data-stu-id="4c333-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="4c333-117">使用 byref</span><span class="sxs-lookup"><span data-stu-id="4c333-117">Using byrefs</span></span>

<span data-ttu-id="4c333-118">若要使用`inref<'T>`，您需要先获取一个指针值与`&`:</span><span class="sxs-lookup"><span data-stu-id="4c333-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let dt = DateTime.Now
f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="4c333-119">若要使用写入指针`outref<'T>`或`byref<'T>`，你还必须对获取指向指针的值`mutable`。</span><span class="sxs-lookup"><span data-stu-id="4c333-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="4c333-120">如果你仅编写读取它，而是指针，请考虑使用`outref<'T>`而不是`byref<'T>`。</span><span class="sxs-lookup"><span data-stu-id="4c333-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="4c333-121">Inref 语义</span><span class="sxs-lookup"><span data-stu-id="4c333-121">Inref semantics</span></span>

<span data-ttu-id="4c333-122">考虑下列代码：</span><span class="sxs-lookup"><span data-stu-id="4c333-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = s.SomeField
```

<span data-ttu-id="4c333-123">在语义上，这意味着以下内容：</span><span class="sxs-lookup"><span data-stu-id="4c333-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="4c333-124">持有者`x`指针只能使用它来读取值。</span><span class="sxs-lookup"><span data-stu-id="4c333-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="4c333-125">获取到的任何指针`struct`字段中嵌套`SomeStruct`给定类型`inref<_>`。</span><span class="sxs-lookup"><span data-stu-id="4c333-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="4c333-126">以下也是如此：</span><span class="sxs-lookup"><span data-stu-id="4c333-126">The following is also true:</span></span>

* <span data-ttu-id="4c333-127">没有任何含义的其他线程或别名不具有写访问权限`x`。</span><span class="sxs-lookup"><span data-stu-id="4c333-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="4c333-128">没有任何含义，`SomeStruct`是固定不变，凭借`x`正在`inref`。</span><span class="sxs-lookup"><span data-stu-id="4c333-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="4c333-129">但是，对于 F # 的值类型**都**不可变的`this`指针被推断为`inref`。</span><span class="sxs-lookup"><span data-stu-id="4c333-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="4c333-130">所有这些规则组合在一起表示的持有者`inref`指针不能修改所指向的内存的直接内容。</span><span class="sxs-lookup"><span data-stu-id="4c333-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="4c333-131">Outref 语义</span><span class="sxs-lookup"><span data-stu-id="4c333-131">Outref semantics</span></span>

<span data-ttu-id="4c333-132">用途`outref<'T>`是指示指针应仅在从读取。</span><span class="sxs-lookup"><span data-stu-id="4c333-132">The purpose of `outref<'T>` is to indicate that the pointer should only be read from.</span></span> <span data-ttu-id="4c333-133">意外，`outref<'T>`允许读取基础值，尽管其名称。</span><span class="sxs-lookup"><span data-stu-id="4c333-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="4c333-134">这是为了实现兼容性。</span><span class="sxs-lookup"><span data-stu-id="4c333-134">This is for compatibility purposes.</span></span> <span data-ttu-id="4c333-135">在语义上，`outref<'T>`没有什么不同`byref<'T>`。</span><span class="sxs-lookup"><span data-stu-id="4c333-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="4c333-136">使用 C# 的互操作</span><span class="sxs-lookup"><span data-stu-id="4c333-136">Interop with C#</span></span> #

<span data-ttu-id="4c333-137">C# 支持`in ref`并`out ref`关键字，除了`ref`返回。</span><span class="sxs-lookup"><span data-stu-id="4c333-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="4c333-138">下表显示了如何 F # 解释什么 C# 发出：</span><span class="sxs-lookup"><span data-stu-id="4c333-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="4c333-139">C# 构造</span><span class="sxs-lookup"><span data-stu-id="4c333-139">C# construct</span></span>|<span data-ttu-id="4c333-140">F # 推断</span><span class="sxs-lookup"><span data-stu-id="4c333-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="4c333-141">`ref` 返回值</span><span class="sxs-lookup"><span data-stu-id="4c333-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="4c333-142">`ref readonly` 返回值</span><span class="sxs-lookup"><span data-stu-id="4c333-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="4c333-143">`in ref` 参数</span><span class="sxs-lookup"><span data-stu-id="4c333-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="4c333-144">`out ref` 参数</span><span class="sxs-lookup"><span data-stu-id="4c333-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="4c333-145">下表显示了什么 F # 发出：</span><span class="sxs-lookup"><span data-stu-id="4c333-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="4c333-146">F # 构造</span><span class="sxs-lookup"><span data-stu-id="4c333-146">F# construct</span></span>|<span data-ttu-id="4c333-147">发出的构造</span><span class="sxs-lookup"><span data-stu-id="4c333-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="4c333-148">`inref<'T>` 自变量</span><span class="sxs-lookup"><span data-stu-id="4c333-148">`inref<'T>` argument</span></span>|<span data-ttu-id="4c333-149">`[In]` 在参数上的属性</span><span class="sxs-lookup"><span data-stu-id="4c333-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="4c333-150">`inref<'T>` 返回</span><span class="sxs-lookup"><span data-stu-id="4c333-150">`inref<'T>` return</span></span>|<span data-ttu-id="4c333-151">`modreq` 属性值</span><span class="sxs-lookup"><span data-stu-id="4c333-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="4c333-152">`inref<'T>` 在抽象槽或实现</span><span class="sxs-lookup"><span data-stu-id="4c333-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="4c333-153">`modreq` 在自变量或返回</span><span class="sxs-lookup"><span data-stu-id="4c333-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="4c333-154">`outref<'T>` 自变量</span><span class="sxs-lookup"><span data-stu-id="4c333-154">`outref<'T>` argument</span></span>|<span data-ttu-id="4c333-155">`[Out]` 在参数上的属性</span><span class="sxs-lookup"><span data-stu-id="4c333-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="4c333-156">类型推理和重载规则</span><span class="sxs-lookup"><span data-stu-id="4c333-156">Type inference and overloading rules</span></span>

<span data-ttu-id="4c333-157">`inref<'T>`在以下情况下 F # 编译器推断类型：</span><span class="sxs-lookup"><span data-stu-id="4c333-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="4c333-158">.NET 参数或返回类型具有`IsReadOnly`属性。</span><span class="sxs-lookup"><span data-stu-id="4c333-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="4c333-159">`this`没有可变字段的结构类型的指针。</span><span class="sxs-lookup"><span data-stu-id="4c333-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="4c333-160">内存位置的地址派生自另一个`inref<_>`指针。</span><span class="sxs-lookup"><span data-stu-id="4c333-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="4c333-161">时隐式的地址`inref`被采用，用类型自变量的重载`SomeType`优于使用类型的自变量的重载`inref<SomeType>`。</span><span class="sxs-lookup"><span data-stu-id="4c333-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="4c333-162">例如：</span><span class="sxs-lookup"><span data-stu-id="4c333-162">For example:</span></span>

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

<span data-ttu-id="4c333-163">在这两种情况下，重载采用`System.DateTime`而不是重载采用解决`inref<System.DateTime>`。</span><span class="sxs-lookup"><span data-stu-id="4c333-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="4c333-164">Byref 类似结构</span><span class="sxs-lookup"><span data-stu-id="4c333-164">Byref-like structs</span></span>

<span data-ttu-id="4c333-165">除了`byref` / `inref` / `outref`三个，你可以定义自己的结构，可以遵循`byref`-等语义。</span><span class="sxs-lookup"><span data-stu-id="4c333-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="4c333-166">这通过<xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>属性：</span><span class="sxs-lookup"><span data-stu-id="4c333-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="4c333-167">`IsByRefLike` 并不意味着`Struct`。</span><span class="sxs-lookup"><span data-stu-id="4c333-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="4c333-168">必须同时出现在类型上。</span><span class="sxs-lookup"><span data-stu-id="4c333-168">Both must be present on the type.</span></span>

<span data-ttu-id="4c333-169">一个"`byref`-例如"F # 中的结构是绑定堆栈的值类型。</span><span class="sxs-lookup"><span data-stu-id="4c333-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="4c333-170">它永远不会分配托管堆上。</span><span class="sxs-lookup"><span data-stu-id="4c333-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="4c333-171">一个`byref`-像结构可用于高效的编程中，因为它强制实施强检查有关生存期和非捕获组。</span><span class="sxs-lookup"><span data-stu-id="4c333-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="4c333-172">中的规则：</span><span class="sxs-lookup"><span data-stu-id="4c333-172">The rules are:</span></span>

* <span data-ttu-id="4c333-173">它们可用作函数参数、 方法参数、 局部变量、 方法返回。</span><span class="sxs-lookup"><span data-stu-id="4c333-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="4c333-174">它们不能是静态或实例的类或常规结构的成员。</span><span class="sxs-lookup"><span data-stu-id="4c333-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="4c333-175">不能通过任何闭包构造捕获它们 (`async`方法或 lambda 表达式)。</span><span class="sxs-lookup"><span data-stu-id="4c333-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="4c333-176">它们不能用作泛型参数。</span><span class="sxs-lookup"><span data-stu-id="4c333-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="4c333-177">最后这一点非常重要的 F # 管道样式编程中，作为`|>`是参数化其输入的类型的泛型函数。</span><span class="sxs-lookup"><span data-stu-id="4c333-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="4c333-178">可能的放宽此限制`|>`将来，因为它是内联的不会不调用任何非内联泛型函数在其主体中。</span><span class="sxs-lookup"><span data-stu-id="4c333-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="4c333-179">尽管这些规则非常强限制使用，但它们这样做是为了满足这一承诺的高性能计算以安全方式。</span><span class="sxs-lookup"><span data-stu-id="4c333-179">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="4c333-180">Byref 返回</span><span class="sxs-lookup"><span data-stu-id="4c333-180">Byref returns</span></span>

<span data-ttu-id="4c333-181">Byref 返回从 F # 函数或成员可以产生和使用。</span><span class="sxs-lookup"><span data-stu-id="4c333-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="4c333-182">使用时`byref`-返回方法，则这是隐式取消引用。</span><span class="sxs-lookup"><span data-stu-id="4c333-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="4c333-183">例如：</span><span class="sxs-lookup"><span data-stu-id="4c333-183">For example:</span></span>

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

<span data-ttu-id="4c333-184">若要避免隐式取消引用，例如传递一个引用多个链接的调用，通过使用`&x`(其中`x`是值)。</span><span class="sxs-lookup"><span data-stu-id="4c333-184">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="4c333-185">您可以直接将分配给返回`byref`。</span><span class="sxs-lookup"><span data-stu-id="4c333-185">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="4c333-186">请考虑以下 （高度命令性） 程序：</span><span class="sxs-lookup"><span data-stu-id="4c333-186">Consider the following (highly imperative) program:</span></span>

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override __.ToString() = String.Join(' ', nums)

    member __.FindLargestSmallerThan(target: int) =
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

<span data-ttu-id="4c333-187">以下是输出：</span><span class="sxs-lookup"><span data-stu-id="4c333-187">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="4c333-188">范围，将 byref</span><span class="sxs-lookup"><span data-stu-id="4c333-188">Scoping for byrefs</span></span>

<span data-ttu-id="4c333-189">一个`let`-绑定的值不能具有超过在其中定义的作用域的引用。</span><span class="sxs-lookup"><span data-stu-id="4c333-189">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="4c333-190">例如，以下是不允许：</span><span class="sxs-lookup"><span data-stu-id="4c333-190">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="4c333-191">这会阻止您获取具体取决于不同的结果，如果使用打开或关闭优化进行编译。</span><span class="sxs-lookup"><span data-stu-id="4c333-191">This prevents you from getting different results depending on if you compile with optimizations on or off.</span></span>
