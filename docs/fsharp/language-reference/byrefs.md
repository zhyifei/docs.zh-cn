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
# <a name="byrefs"></a>Byref

F# 具有在低级编程领域处理的两个主要功能领域：

* `byref`/类型`inref`，/托管`outref`指针。 它们对使用有限制，因此您不能编译在运行时无效的程序。
* 类似`byref`结构的结构，它是具有与 相似的语义和相同的编译时间限制[的结构](structures.md)`byref<'T>`。 一个例子是<xref:System.Span%601>。

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

有三种形式： `byref`

* `inref<'T>`，用于读取基础值的托管指针。
* `outref<'T>`，用于写入基础值的托管指针。
* `byref<'T>`，用于读取和写入基础值的托管指针。

`byref<'T>`可以传递预期 为`inref<'T>`的 。 同样，`byref<'T>`可以传递预期 为`outref<'T>`的 。

## <a name="using-byrefs"></a>使用参考

要使用`inref<'T>`， 需要获取具有 的`&`指针值：

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

要使用`outref<'T>`或`byref<'T>`写入指针，还必须使获取指向`mutable`的指针的值。

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

如果只编写指针而不是读取指针，请考虑使用`outref<'T>`而不是`byref<'T>`。

### <a name="inref-semantics"></a>Inref 语义

考虑下列代码：

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

从语义上讲，这意味着以下内容：

* 指针的`x`持有者只能使用它读取该值。
* 任何获取到`struct`嵌套在其中`SomeStruct`的字段的指针都是`inref<_>`给定的类型。

以下内容也是如此：

* 其他线程或别名对 没有写入访问权限，这没有任何含义`x`。
* 没有任何暗示是`SomeStruct`不变的`x`，因为是一个。 `inref`

但是，**对于不可变**的 F# 值类型，`this`将指针推断为`inref`。

所有这些规则加在一`inref`起意味着指针的持有者不能修改指向的内存的即时内容。

### <a name="outref-semantics"></a>外部参照语义

的目的是`outref<'T>`指示指针应只写入。 出乎意料的是`outref<'T>`，允许读取基础值，尽管它的名称。 这是出于兼容性目的。 从语义上讲`outref<'T>`，与 没有什么`byref<'T>`不同。

### <a name="interop-with-c"></a>与 C 的互通\#

除了`in ref``ref`返回之外，C# 还支持 和`out ref`关键字。 下表显示了 F# 如何解释 C# 发出的内容：

|C# 构造|F# 推断|
|------------|---------|
|`ref`返回值|`outref<'T>`|
|`ref readonly`返回值|`inref<'T>`|
|`in ref` 参数|`inref<'T>`|
|`out ref` 参数|`outref<'T>`|

下表显示了 F# 发出的内容：

|F# 构造|已发出构造|
|------------|-----------------|
|`inref<'T>` 参数|`[In]`参数上的属性|
|`inref<'T>`返回|`modreq`值的属性|
|`inref<'T>`抽象插槽或实现|`modreq`在参数或返回|
|`outref<'T>` 参数|`[Out]`参数上的属性|

### <a name="type-inference-and-overloading-rules"></a>类型推理和重载规则

在`inref<'T>`以下情况下，F# 编译器会推断类型：

1. 具有`IsReadOnly`属性的 .NET 参数或返回类型。
2. 没有`this`可变字段的结构类型的指针。
3. 从其他`inref<_>`指针派生的内存位置的地址。

当采用 隐式地址`inref`时，具有类型`SomeType`参数的重载优先于具有类型`inref<SomeType>`类型的重载。 例如：

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

在这两种情况下，重`System.DateTime`载将得到解决，而不是重载。 `inref<System.DateTime>`

## <a name="byref-like-structs"></a>类似 Byref 的结构

`byref`/除了`outref``byref`三者组之外，您还可以定义自己的结构，这些结构可以遵循类似语义。 `inref` / 这与属性一<xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>起完成：

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike`并不意味着`Struct`. 两者都必须存在于类型上。

F#`byref`中的"类似"结构是一种堆栈绑定值类型。 它永远不会在托管堆上分配。 `byref`类似结构对于高性能编程非常有用，因为它通过一组有关生存期和非捕获的强检查强制执行。 规则包括：

* 它们可用作函数参数、方法参数、局部变量、方法返回。
* 它们不能是类的静态或实例成员或正常结构。
* 它们不能被任何闭包构造（`async`方法或 lambda 表达式）捕获。
* 它们不能用作泛型参数。

最后一点对于 F# 管道样式编程至关重要，用于`|>`参数化其输入类型的泛型函数也是如此。 将来可能会放宽`|>`此限制，因为它是内联的，并且不会对其正文中的非内联泛型函数进行任何调用。

尽管这些规则严格限制使用，但它们这样做是为了以安全的方式实现高性能计算的承诺。

## <a name="byref-returns"></a>Byref 返回

可以生成和使用 F# 函数或成员的 Byref 返回。 使用`byref`-返回方法时，将隐式取消引用该值。 例如：

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

要返回值 byref，包含该值的变量必须比当前作用域长。
此外，要返回 byref，`&value`请使用 （其中值是比当前作用域长的变量）。

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

为了避免隐式取消引用（例如通过多个链接调用传递引用），请使用`&x`（值在哪里）。 `x`

您也可以直接分配给返回`byref`。 请考虑以下（高度必要）计划：

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

## <a name="scoping-for-byrefs"></a>字节范围

`let`绑定值不能使其引用超过定义该值的范围。 例如，不允许使用以下内容：

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

这可以防止您获得不同的结果，具体取决于是否使用优化进行编译。
