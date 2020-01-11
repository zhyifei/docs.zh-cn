---
title: Byref
description: 了解用于低级别编程的中F#的 byref 和 byref 类型（如）。
ms.date: 11/04/2019
ms.openlocfilehash: 5aaee1e4eac9ce0d7e9ba89a2ab5f745d31367a0
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901314"
---
# <a name="byrefs"></a>Byref

F#具有两个主要功能区域，用于处理低级别编程的空间：

* `byref`/`inref`/`outref` 类型，这些类型是托管指针。 它们对使用情况有限制，因此无法编译在运行时无效的程序。
* 类似于 `byref`的结构，它是具有类似语义和 `byref<'T>`编译时限制的[结构](structures.md)。 <xref:System.Span%601>一个示例。

## <a name="syntax"></a>语法

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

## <a name="byref-inref-and-outref"></a>Byref、inref 和 outref

有三种形式的 `byref`：

* `inref<'T>`，用于读取基础值的托管指针。
* `outref<'T>`，用于写入基础值的托管指针。
* `byref<'T>`，用于读取和写入基础值的托管指针。

可以将 `byref<'T>` 传递到需要 `inref<'T>` 的位置。 同样，可以将 `byref<'T>` 传递到需要 `outref<'T>` 的位置。

## <a name="using-byrefs"></a>使用 byref

若要使用 `inref<'T>`，需要使用 `&`获取指针值：

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

若要通过使用 `outref<'T>` 或 `byref<'T>`来写入指针，还必须使你获取指向 `mutable`的指针的值。

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

如果只是编写指针而不是读取它，请考虑使用 `outref<'T>` 而不是 `byref<'T>`。

### <a name="inref-semantics"></a>Inref 语义

考虑下列代码：

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

从语义上说，这意味着：

* `x` 指针的刀柄只能用它来读取值。
* 获取到嵌套在 `SomeStruct` 中的 `struct` 字段的任何指针都给定类型 `inref<_>`。

以下情况也成立：

* 不意味着其他线程或别名不具有对 `x`的写访问权限。
* 由于 `x` 成为 `inref`，因此没有任何隐含 `SomeStruct`。

但是，对于F#不可变的值类型 **，会将**`this` 指针推断为 `inref`。

所有这些规则一起意味着 `inref` 指针的持有者可能不会修改所指向的内存的即时内容。

### <a name="outref-semantics"></a>Outref 语义

`outref<'T>` 的目的是指示只应将指针写入。 意外，`outref<'T>` 允许读取基础值，而不考虑其名称。 这是为了实现兼容性。 在语义上，`outref<'T>` 与 `byref<'T>`没有区别。

### <a name="interop-with-c"></a>与 C\# 互操作

C#除 `ref` 返回外，还支持 `in ref` 和 `out ref` 关键字。 下表显示了如何F#解释发出C#的内容：

|C#构造|F#推断|
|------------|---------|
|`ref` 返回值|`outref<'T>`|
|`ref readonly` 返回值|`inref<'T>`|
|`in ref` 参数|`inref<'T>`|
|`out ref` 参数|`outref<'T>`|

下表显示了发出F#的内容：

|F#构造|发出的构造|
|------------|-----------------|
|`inref<'T>` 参数|参数 `[In]` 特性|
|`inref<'T>` 返回|值 `modreq` 属性|
|在抽象槽或实现中 `inref<'T>`|参数或返回 `modreq`|
|`outref<'T>` 参数|参数 `[Out]` 特性|

### <a name="type-inference-and-overloading-rules"></a>类型推理和重载规则

在以下情况下， F#编译器将推断 `inref<'T>` 类型：

1. 具有 `IsReadOnly` 特性的 .NET 参数或返回类型。
2. 结构类型上没有可变字段的 `this` 指针。
3. 派生自另一个 `inref<_>` 指针的内存位置的地址。

当执行 `inref` 的隐式地址时，具有类型 `SomeType` 的参数的重载优先于具有类型 `inref<SomeType>`的参数的重载。 例如：

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

在这两种情况下，将解析采用 `System.DateTime` 的重载，而不是采用 `inref<System.DateTime>`的重载。

## <a name="byref-like-structs"></a>类似 Byref 的结构

除了 `byref`/`inref`/`outref` 三个，还可以定义自己的结构，该结构可以遵循与 `byref`类似的语义。 此操作通过 <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> 属性实现：

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` 并不意味着 `Struct`。 这两者都必须存在于类型上。

中F#的 "类似于`byref`的" 结构是堆栈绑定值类型。 永远不会在托管堆上分配。 与 `byref`类似的结构可用于实现高性能编程，因为它是通过针对生存期和非捕获的一组强检查来强制实施的。 规则如下：

* 它们可用作函数参数、方法参数、局部变量、方法返回。
* 它们不能是类或普通结构的静态成员或实例成员。
* 它们不能由任何闭包构造（`async` 方法或 lambda 表达式）捕获。
* 它们不能用作泛型参数。

最后一点对于F#管道样式编程至关重要，因为 `|>` 是参数化其输入类型的泛型函数。 此限制可能会在将来的 `|>` 中宽松，因为它是内联的，不会对其主体中的非内联泛型函数进行任何调用。

尽管这些规则对使用进行了严格的限制，但这样做可确保以安全的方式满足高性能计算的承诺。

## <a name="byref-returns"></a>Byref 返回

可以生成和F#使用来自函数或成员的 Byref 返回。 使用返回 `byref`方法时，会隐式取消引用该值。 例如：

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

若要避免隐式取消引用（如通过多个链式调用传递引用），请使用 `&x` （其中 `x` 是值）。

还可以直接分配给返回 `byref`。 请考虑以下（高度命令式）程序：

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

以下是输出：

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a>Byref 的作用域

`let`绑定值不能将其引用超出定义它的范围。 例如，不允许以下操作：

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

这会阻止你获取不同的结果，具体取决于你在编译时是启用还是禁用优化。
