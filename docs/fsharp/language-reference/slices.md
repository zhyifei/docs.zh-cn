---
title: 切片 (F#)
description: 了解如何使用现有的切片F#数据类型以及如何定义其他数据类型的切片。
ms.date: 01/22/2019
ms.openlocfilehash: 1d8bb029ad18c8853ab58888959967ed279fb368
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675272"
---
# <a name="slices"></a><span data-ttu-id="d51af-103">切片</span><span class="sxs-lookup"><span data-stu-id="d51af-103">Slices</span></span>

<span data-ttu-id="d51af-104">在F#，切片是一种数据类型的子集。</span><span class="sxs-lookup"><span data-stu-id="d51af-104">In F#, a slice is a subset of a data type.</span></span> <span data-ttu-id="d51af-105">若要将能够从数据类型执行切片，数据类型必须要么定义`GetSlice`方法中或在[键入扩展名](type-extensions.md)，它是在作用域。</span><span class="sxs-lookup"><span data-stu-id="d51af-105">To be able to take a slice from a data type, the data type must either define a `GetSlice` method or in a [type extension](type-extensions.md) that is in scope.</span></span> <span data-ttu-id="d51af-106">本文介绍了如何获取切片从现有F#类型以及如何定义你自己。</span><span class="sxs-lookup"><span data-stu-id="d51af-106">This article explains how to take slices from existing F# types and how to define your own.</span></span>

<span data-ttu-id="d51af-107">切片是类似于[索引器](members/indexed-properties.md)，但而不是从基础数据结构生成单个值，它们会产生多个数据库。</span><span class="sxs-lookup"><span data-stu-id="d51af-107">Slices are similar to [indexers](members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="d51af-108">F#当前具有对字符串、 列表、 数组和 2D 数组进行切片的内部函数支持。</span><span class="sxs-lookup"><span data-stu-id="d51af-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="d51af-109">使用基本切片F#列表和数组</span><span class="sxs-lookup"><span data-stu-id="d51af-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="d51af-110">生成切片的最常见的数据类型F#列表和数组。</span><span class="sxs-lookup"><span data-stu-id="d51af-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="d51af-111">下面的示例演示如何执行此操作的列表：</span><span class="sxs-lookup"><span data-stu-id="d51af-111">The following example demonstrates how to do this with lists:</span></span>

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

<span data-ttu-id="d51af-112">对数组进行切片就像对列表进行切片：</span><span class="sxs-lookup"><span data-stu-id="d51af-112">Slicing arrays is just like slicing lists:</span></span>

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

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="d51af-113">切片的多维数组</span><span class="sxs-lookup"><span data-stu-id="d51af-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="d51af-114">F#支持多维数组中的F#核心库。</span><span class="sxs-lookup"><span data-stu-id="d51af-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="d51af-115">与一维数组相同的多维数组的切片也很有用。</span><span class="sxs-lookup"><span data-stu-id="d51af-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="d51af-116">但是，引入了额外的维度要求略有不同的语法，以便您可以采取的特定行和列切片。</span><span class="sxs-lookup"><span data-stu-id="d51af-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="d51af-117">以下示例演示如何进行切片的二维数组：</span><span class="sxs-lookup"><span data-stu-id="d51af-117">The following examples demonstrate how to slice a 2D array:</span></span>

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

<span data-ttu-id="d51af-118">F#核心库不会定义`GetSlice`三维数组。</span><span class="sxs-lookup"><span data-stu-id="d51af-118">The F# core library does not define `GetSlice`for 3D arrays.</span></span> <span data-ttu-id="d51af-119">如果你想要对那些或其他数组或多个维度进行切片，则必须定义`GetSlice`成员自己。</span><span class="sxs-lookup"><span data-stu-id="d51af-119">If you wish to slice those or other arrays of more dimensions, you must define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="d51af-120">定义其他数据结构的切片</span><span class="sxs-lookup"><span data-stu-id="d51af-120">Defining slices for other data structures</span></span>

<span data-ttu-id="d51af-121">F#核心库定义了针对一组有限的类型段。</span><span class="sxs-lookup"><span data-stu-id="d51af-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="d51af-122">如果你想要定义更多的数据类型的切片，就可以做到本身在类型定义中或在类型扩展中。</span><span class="sxs-lookup"><span data-stu-id="d51af-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="d51af-123">例如，下面是可以如何定义切片<xref:System.ArraySegment%601>类，以允许用于方便数据处理：</span><span class="sxs-lookup"><span data-stu-id="d51af-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(?start, ?finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a><span data-ttu-id="d51af-124">使用内联，从而避免装箱，如有必要</span><span class="sxs-lookup"><span data-stu-id="d51af-124">Use inlining to avoid boxing if it is necessary</span></span>

<span data-ttu-id="d51af-125">如果你正在定义的实际结构类型的切片，我们建议您`inline``GetSlice`成员。</span><span class="sxs-lookup"><span data-stu-id="d51af-125">If you are defining slices for a type that is actually a struct, we recommend that you `inline` the `GetSlice` member.</span></span> <span data-ttu-id="d51af-126">F#编译器会优化的可选参数，避免由于切片任何堆分配。</span><span class="sxs-lookup"><span data-stu-id="d51af-126">The F# compiler optimizes away the optional arguments, avoiding any heap allocations as a result of slicing.</span></span> <span data-ttu-id="d51af-127">这是非常重要的如切片构造<xref:System.Span%601>，不能在堆上分配。</span><span class="sxs-lookup"><span data-stu-id="d51af-127">This is critically important for slicing constructs such as <xref:System.Span%601> that cannot be allocated on the heap.</span></span>

```fsharp
open System

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..2] // |2; 3|]
```

## <a name="see-also"></a><span data-ttu-id="d51af-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d51af-128">See also</span></span>

- [<span data-ttu-id="d51af-129">索引的属性</span><span class="sxs-lookup"><span data-stu-id="d51af-129">Indexed properties</span></span>](members/indexed-properties.md)
