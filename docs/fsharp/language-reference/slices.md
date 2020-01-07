---
title: 切片
description: 了解如何使用现有F#数据类型的切片，以及如何为其他数据类型定义自己的切片。
ms.date: 12/23/2019
ms.openlocfilehash: 3911139c7ce656043817eb23d30f3686555b6efe
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/29/2019
ms.locfileid: "75545103"
---
# <a name="slices"></a>切片

在F#中，切片是在其定义或范围内[类型扩展](type-extensions.md)中具有 `GetSlice` 方法的任何数据类型的子集。 它最常用于F#数组和列表。 本文介绍如何从现有F#类型获取切片，以及如何定义自己的切片。

切片与[索引器](./members/indexed-properties.md)相似，但它不是从基础数据结构产生单个值，而是生成多个值。

F#目前对切片字符串、列表、数组和二维数组的内部支持。

## <a name="basic-slicing-with-f-lists-and-arrays"></a>具有列表和F#数组的基本切片

切片最常见的数据类型为F# "列表" 和 "数组"。 下面的示例演示如何通过列表执行此操作：

```fsharp
// Generate a list of 100 integers
let fullList = [ 1 .. 100 ]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullList.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullList.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullList.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

切片数组与切片列表类似：

```fsharp
// Generate an array of 100 integers
let fullArray = [| 1 .. 100 |]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullArray.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullArray.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullArray.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

## <a name="slicing-multidimensional-arrays"></a>切片多维数组

F#支持F#核心库中的多维数组。 与一维数组一样，多维数组的切片也很有用。 但是，附加维度的引入要求使用略微不同的语法，以便能够获取特定行和列的切片。

下面的示例演示如何切分二维数组：

```fsharp
// Generate a 3x3 2D matrix
let A = array2D [[1;2;3];[4;5;6];[7;8;9]]
printfn "Full matrix:\n %A" A

// Take the first row
let row0 = A.[0,*]
printfn "Row 0: %A" row0

// Take the first column
let col0 = A.[*,0]
printfn "Column 0: %A" col0

// Take all rows but only two columns
let subA = A.[*,0..1]
printfn "%A" subA

// Take two rows and all columns
let subA' = A.[0..1,*]
printfn "%A" subA'

// Slice a 2x2 matrix out of the full 3x3 matrix
let twoByTwo = A.[0..1,0..1]
printfn "%A" twoByTwo
```

F#核心库当前没有为三维数组定义 `GetSlice`。 如果要对三维数组或其他维度的其他数组进行切片，请自行定义 `GetSlice` 成员。

## <a name="defining-slices-for-other-data-structures"></a>为其他数据结构定义切片

F#核心库定义了有限类型集的切片。 如果要定义更多数据类型的切片，可以在类型定义本身或类型扩展中执行此操作。

例如，下面介绍了如何为 <xref:System.ArraySegment%601> 类定义切片，以便方便地进行数据操作：

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(start, finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a>如果需要，请使用内联来避免装箱

如果要为实际为结构的类型定义切片，我们建议您 `inline` `GetSlice` 成员。 F#编译器消除了可选参数，避免了切片的任何分配。 对于无法在堆上分配的切片构造（如 <xref:System.Span%601>），这一点非常重要。

```fsharp
open System

type ReadOnlySpan<'T> with
    // Note the 'inline' in the member definition
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..2] // |2; 3|]
```

## <a name="built-in-f-slices-are-end-inclusive"></a>内置F#切片包含结尾

中F#的所有内部切片都是结尾的;也就是说，切片中包括上限。 对于具有起始索引 `x` 和结束索引 `y`的给定切片，生成的切片将包含*yth*值。

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="see-also"></a>另请参阅

- [索引属性](./members/indexed-properties.md)
