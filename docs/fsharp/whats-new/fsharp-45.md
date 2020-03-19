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
# <a name="whats-new-in-f-45"></a>F# 4.5 中的新增功能

F# 4.5 为 F# 语言添加了多项改进。 这些功能中有许多被添加到一起，使您能够在 F# 中编写高效的代码，同时确保此代码是安全的。 这样做意味着在使用这些构造时向语言添加一些概念和大量编译器分析。

## <a name="get-started"></a>入门

F# 4.5 在所有 .NET 核心发行版和可视化工作室工具中均可用。 [开始使用 F#](../get-started/index.md)了解更多信息。

## <a name="span-and-byref-like-structs"></a>跨度和字节式结构

.NET Core 中引入<xref:System.Span%601>的类型允许您以强类型的方式表示内存中的缓冲区，现在 F# 中允许使用 F# 4.5。 下面的示例演示如何使用具有不同缓冲区表示表示的 对 的<xref:System.Span%601>函数操作：

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

这方面的一个重要方面是，Span 和其他类似[byref 的构造](../language-reference/structures.md#byreflike-structs)具有由编译器执行的非常严格的静态分析，这些分析以您可能会发现意外的方式限制它们的使用。 这是 F# 4.5 中引入的性能、表现力和安全性之间的基本权衡。

## <a name="revamped-byrefs"></a>已改造的参考

在 F# 4.5 之前，F# 中的[Byrefs](../language-reference/byrefs.md)对许多应用程序不安全且不健全。 在 F# 4.5 中解决了 byrefs 周围的声音问题，并且还应用了对跨度和 byref 类似结构的相同静态分析。

### <a name="inreft-and-outreft"></a>inref<'t't>和出<'t'>

为了表示只读、只写和读/写托管指针的概念，F# 4.5 分别引入了`inref<'T>`表示只读`outref<'T>`指针和只写指针的类型。 每个都有不同的语义。 例如，您不能写入 ： `inref<'T>`

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

默认情况下，类型推理将推断托管指针`inref<'T>`与 F# 代码的不可变性质一致，除非某些内容已声明为可变指针。 要使某些内容具有可写性，您需要在将类型地址传递给操作`mutable`它的函数或成员之前声明类型。 要了解更多信息，请参阅[Byrefs](../language-reference/byrefs.md)。

## <a name="readonly-structs"></a>只读结构

从 F# 4.5 开始，您可以用<xref:System.Runtime.CompilerServices.IsReadOnlyAttribute>这样的来对结构进行加号：

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

这不允许您在结构中声明可变成员，并发出元数据，允许 F# 和 C# 在从程序集使用时将其视为只读。 要了解更多信息，请参阅[只读结构](../language-reference/structures.md#readonly-structs)。

## <a name="void-pointers"></a>虚空指针

类型`voidptr`将添加到 F# 4.5，以下函数也包括：

* `NativePtr.ofVoidPtr`将 void 指针转换为本机 int 指针
* `NativePtr.toVoidPtr`将本机 int 指针转换为空指针

当与使用 void 指针的本机组件进行互操作时，这非常有用。

## <a name="the-match-keyword"></a>`match!` 关键字

关键字`match!`在计算表达式内增强模式匹配：

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

这允许您缩短通常涉及混合选项（或其他类型）的代码与计算表达式（如异步）。 要了解更多信息，请参阅[匹配！](../language-reference/computation-expressions.md#match)

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a>在数组、列表和序列表达式中放宽了向上转换要求

混合类型，其中一个类型可以从数组、列表和序列表达式的另一个内部继承，传统上需要您将任何派生类型用`:>`或`upcast`将其父类型向上转换。 这是现在放松，如下所示：

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a>数组和列表表达式的缩进放松

在 F# 4.5 之前，当作为参数传递给方法调用时，需要过度缩进数组和列表表达式。 不再需要这一点：

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
