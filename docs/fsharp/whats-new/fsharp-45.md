---
title: F# 4.5 - F# 指南中的新增功能
description: 获取 F# 4.5 中提供的新功能的概述。
ms.date: 11/27/2019
ms.openlocfilehash: 560e3dd941f79b76d3b864ba0f6560be154ebc1a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186139"
---
# <a name="whats-new-in-f-45"></a><span data-ttu-id="fc6cf-103">F# 4.5 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="fc6cf-103">What's new in F# 4.5</span></span>

<span data-ttu-id="fc6cf-104">F# 4.5 为 F# 语言添加了多项改进。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-104">F# 4.5 adds multiple improvements to the F# language.</span></span> <span data-ttu-id="fc6cf-105">这些功能中有许多被添加到一起，使您能够在 F# 中编写高效的代码，同时确保此代码是安全的。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-105">Many of these features were added together to enable you to write efficient code in F# while also ensuring this code is safe.</span></span> <span data-ttu-id="fc6cf-106">这样做意味着在使用这些构造时向语言添加一些概念和大量编译器分析。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-106">Doing so means adding a few concepts to the language and a significant amount of compiler analysis when using these constructs.</span></span>

## <a name="get-started"></a><span data-ttu-id="fc6cf-107">入门</span><span class="sxs-lookup"><span data-stu-id="fc6cf-107">Get started</span></span>

<span data-ttu-id="fc6cf-108">F# 4.5 在所有 .NET 核心发行版和可视化工作室工具中均可用。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-108">F# 4.5 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="fc6cf-109">[开始使用 F#](../get-started/index.md)了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-109">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="span-and-byref-like-structs"></a><span data-ttu-id="fc6cf-110">跨度和字节式结构</span><span class="sxs-lookup"><span data-stu-id="fc6cf-110">Span and byref-like structs</span></span>

<span data-ttu-id="fc6cf-111">.NET Core 中引入<xref:System.Span%601>的类型允许您以强类型的方式表示内存中的缓冲区，现在 F# 中允许使用 F# 4.5。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-111">The <xref:System.Span%601> type introduced in .NET Core allows you to represent buffers in memory in a strongly-typed manner, which is now allowed in F# starting with F# 4.5.</span></span> <span data-ttu-id="fc6cf-112">下面的示例演示如何使用具有不同缓冲区表示表示的 对 的<xref:System.Span%601>函数操作：</span><span class="sxs-lookup"><span data-stu-id="fc6cf-112">The following example shows how you can re-use a function operating on a <xref:System.Span%601> with different buffer representations:</span></span>

```fsharp
let safeSum (bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

// managed memory
let arrayMemory = Array.zeroCreate<byte>(100)
let arraySpan = new Span<byte>(arrayMemory)

safeSum(arraySpan) |> printfn "res = %d"

// native memory
let nativeMemory = Marshal.AllocHGlobal(100);
let nativeSpan = new Span<byte>(nativeMemory.ToPointer(), 100)

safeSum(nativeSpan) |> printfn "res = %d"
Marshal.FreeHGlobal(nativeMemory)

// stack memory
let mem = NativePtr.stackalloc<byte>(100)
let mem2 = mem |> NativePtr.toVoidPtr
let stackSpan = Span<byte>(mem2, 100)

safeSum(stackSpan) |> printfn "res = %d"
```

<span data-ttu-id="fc6cf-113">这方面的一个重要方面是，Span 和其他类似[byref 的构造](../language-reference/structures.md#byreflike-structs)具有由编译器执行的非常严格的静态分析，这些分析以您可能会发现意外的方式限制它们的使用。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-113">An important aspect to this is that Span and other [byref-like structs](../language-reference/structures.md#byreflike-structs) have very rigid static analysis performed by the compiler that restrict their usage in ways you might find to be unexpected.</span></span> <span data-ttu-id="fc6cf-114">这是 F# 4.5 中引入的性能、表现力和安全性之间的基本权衡。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-114">This is the fundamental tradeoff between performance, expressiveness, and safety that is introduced in F# 4.5.</span></span>

## <a name="revamped-byrefs"></a><span data-ttu-id="fc6cf-115">已改造的参考</span><span class="sxs-lookup"><span data-stu-id="fc6cf-115">Revamped byrefs</span></span>

<span data-ttu-id="fc6cf-116">在 F# 4.5 之前，F# 中的[Byrefs](../language-reference/byrefs.md)对许多应用程序不安全且不健全。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-116">Prior to F# 4.5, [Byrefs](../language-reference/byrefs.md) in F# were unsafe and unsound for numerous applications.</span></span> <span data-ttu-id="fc6cf-117">在 F# 4.5 中解决了 byrefs 周围的声音问题，并且还应用了对跨度和 byref 类似结构的相同静态分析。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-117">Soundness issues around byrefs have been addressed in F# 4.5 and the same static analysis done for span and byref-like structs was also applied.</span></span>

### <a name="inreft-and-outreft"></a><span data-ttu-id="fc6cf-118">inref<'t't>和出<'t'></span><span class="sxs-lookup"><span data-stu-id="fc6cf-118">inref<'T> and outref<'T></span></span>

<span data-ttu-id="fc6cf-119">为了表示只读、只写和读/写托管指针的概念，F# 4.5 分别引入了`inref<'T>`表示只读`outref<'T>`指针和只写指针的类型。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-119">To represent the notion of a read-only, write-only, and read/write managed pointer, F# 4.5 introduces the `inref<'T>`, `outref<'T>` types to represent read-only and write-only pointers, respectively.</span></span> <span data-ttu-id="fc6cf-120">每个都有不同的语义。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-120">Each have different semantics.</span></span> <span data-ttu-id="fc6cf-121">例如，您不能写入 ： `inref<'T>`</span><span class="sxs-lookup"><span data-stu-id="fc6cf-121">For example, you cannot write to an `inref<'T>`:</span></span>

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

<span data-ttu-id="fc6cf-122">默认情况下，类型推理将推断托管指针`inref<'T>`与 F# 代码的不可变性质一致，除非某些内容已声明为可变指针。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-122">By default, type inference will infer managed pointers as `inref<'T>` to be in line with the immutable nature of F# code, unless something has already been declared as mutable.</span></span> <span data-ttu-id="fc6cf-123">要使某些内容具有可写性，您需要在将类型地址传递给操作`mutable`它的函数或成员之前声明类型。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-123">To make something writable, you'll need to declare a type as `mutable` before passing its address to a function or member that manipulates it.</span></span> <span data-ttu-id="fc6cf-124">要了解更多信息，请参阅[Byrefs](../language-reference/byrefs.md)。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-124">To learn more, see [Byrefs](../language-reference/byrefs.md).</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="fc6cf-125">只读结构</span><span class="sxs-lookup"><span data-stu-id="fc6cf-125">Readonly structs</span></span>

<span data-ttu-id="fc6cf-126">从 F# 4.5 开始，您可以用<xref:System.Runtime.CompilerServices.IsReadOnlyAttribute>这样的来对结构进行加号：</span><span class="sxs-lookup"><span data-stu-id="fc6cf-126">Starting with F# 4.5, you can annotate a struct with <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> as such:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="fc6cf-127">这不允许您在结构中声明可变成员，并发出元数据，允许 F# 和 C# 在从程序集使用时将其视为只读。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-127">This disallows you from declaring a mutable member in the struct and emits metadata that allows F# and C# to treat it as readonly when consumed from an assembly.</span></span> <span data-ttu-id="fc6cf-128">要了解更多信息，请参阅[只读结构](../language-reference/structures.md#readonly-structs)。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-128">To learn more, see [ReadOnly structs](../language-reference/structures.md#readonly-structs).</span></span>

## <a name="void-pointers"></a><span data-ttu-id="fc6cf-129">虚空指针</span><span class="sxs-lookup"><span data-stu-id="fc6cf-129">Void pointers</span></span>

<span data-ttu-id="fc6cf-130">类型`voidptr`将添加到 F# 4.5，以下函数也包括：</span><span class="sxs-lookup"><span data-stu-id="fc6cf-130">The `voidptr` type is added to F# 4.5, as are the following functions:</span></span>

* <span data-ttu-id="fc6cf-131">`NativePtr.ofVoidPtr`将 void 指针转换为本机 int 指针</span><span class="sxs-lookup"><span data-stu-id="fc6cf-131">`NativePtr.ofVoidPtr` to convert a void pointer into a native int pointer</span></span>
* <span data-ttu-id="fc6cf-132">`NativePtr.toVoidPtr`将本机 int 指针转换为空指针</span><span class="sxs-lookup"><span data-stu-id="fc6cf-132">`NativePtr.toVoidPtr` to convert a native int pointer to a void pointer</span></span>

<span data-ttu-id="fc6cf-133">当与使用 void 指针的本机组件进行互操作时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-133">This is helpful when interoperating with a native component that makes use of void pointers.</span></span>

## <a name="the-match-keyword"></a><span data-ttu-id="fc6cf-134">`match!` 关键字</span><span class="sxs-lookup"><span data-stu-id="fc6cf-134">The `match!` keyword</span></span>

<span data-ttu-id="fc6cf-135">关键字`match!`在计算表达式内增强模式匹配：</span><span class="sxs-lookup"><span data-stu-id="fc6cf-135">The `match!` keyword enhances pattern matching when inside a computation expression:</span></span>

```fsharp
// Code that returns an asynchronous option
let checkBananaAsync (s: string) =
    async {
        if s = "banana" then
            return Some s
        else
            return None
    }

// Now you can use 'match!'
let funcWithString (s: string) =
    async {
        match! checkBananaAsync s with
        | Some bananaString -> printfn "It's banana!"
        | None -> printfn "%s" s
}
```

<span data-ttu-id="fc6cf-136">这允许您缩短通常涉及混合选项（或其他类型）的代码与计算表达式（如异步）。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-136">This allows you to shorten code that often involves mixing options (or other types) with computation expressions such as async.</span></span> <span data-ttu-id="fc6cf-137">要了解更多信息，请参阅[匹配！](../language-reference/computation-expressions.md#match)</span><span class="sxs-lookup"><span data-stu-id="fc6cf-137">To learn more, see [match!](../language-reference/computation-expressions.md#match).</span></span>

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a><span data-ttu-id="fc6cf-138">在数组、列表和序列表达式中放宽了向上转换要求</span><span class="sxs-lookup"><span data-stu-id="fc6cf-138">Relaxed upcasting requirements in array, list, and sequence expressions</span></span>

<span data-ttu-id="fc6cf-139">混合类型，其中一个类型可以从数组、列表和序列表达式的另一个内部继承，传统上需要您将任何派生类型用`:>`或`upcast`将其父类型向上转换。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-139">Mixing types where one may inherit from another inside of array, list, and sequence expressions has traditionally required you to upcast any derived type to its parent type with `:>` or `upcast`.</span></span> <span data-ttu-id="fc6cf-140">这是现在放松，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fc6cf-140">This is now relaxed, demonstrated as follows:</span></span>

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a><span data-ttu-id="fc6cf-141">数组和列表表达式的缩进放松</span><span class="sxs-lookup"><span data-stu-id="fc6cf-141">Indentation relaxation for array and list expressions</span></span>

<span data-ttu-id="fc6cf-142">在 F# 4.5 之前，当作为参数传递给方法调用时，需要过度缩进数组和列表表达式。</span><span class="sxs-lookup"><span data-stu-id="fc6cf-142">Prior to F# 4.5, you needed to excessively indent array and list expressions when passed as arguments to method calls.</span></span> <span data-ttu-id="fc6cf-143">不再需要这一点：</span><span class="sxs-lookup"><span data-stu-id="fc6cf-143">This is no longer required:</span></span>

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
