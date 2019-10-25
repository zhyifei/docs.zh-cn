---
title: 切片（F#）
description: 了解如何使用现有F#数据类型的切片，以及如何为其他数据类型定义自己的切片。
ms.date: 01/22/2019
ms.openlocfilehash: cbff1b055ea99ef708f9db191be49275e630ee90
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2019
ms.locfileid: "72798905"
---
# <a name="slices"></a><span data-ttu-id="87128-103">切片</span><span class="sxs-lookup"><span data-stu-id="87128-103">Slices</span></span>

<span data-ttu-id="87128-104">在F#中，切片是数据类型的子集。</span><span class="sxs-lookup"><span data-stu-id="87128-104">In F#, a slice is a subset of a data type.</span></span> <span data-ttu-id="87128-105">为了能够从数据类型中获取切片，数据类型必须定义 `GetSlice` 方法或在范围内的[类型扩展](type-extensions.md)中。</span><span class="sxs-lookup"><span data-stu-id="87128-105">To be able to take a slice from a data type, the data type must either define a `GetSlice` method or in a [type extension](type-extensions.md) that is in scope.</span></span> <span data-ttu-id="87128-106">本文介绍如何从现有F#类型获取切片以及如何定义切片。</span><span class="sxs-lookup"><span data-stu-id="87128-106">This article explains how to take slices from existing F# types and how to define your own.</span></span>

<span data-ttu-id="87128-107">切片与[索引器](./members/indexed-properties.md)相似，但它不是从基础数据结构产生单个值，而是生成多个值。</span><span class="sxs-lookup"><span data-stu-id="87128-107">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="87128-108">F#目前对切片字符串、列表、数组和二维数组的内部支持。</span><span class="sxs-lookup"><span data-stu-id="87128-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="87128-109">具有列表和F#数组的基本切片</span><span class="sxs-lookup"><span data-stu-id="87128-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="87128-110">切片最常见的数据类型为F# "列表" 和 "数组"。</span><span class="sxs-lookup"><span data-stu-id="87128-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="87128-111">下面的示例演示如何通过列表执行此操作：</span><span class="sxs-lookup"><span data-stu-id="87128-111">The following example demonstrates how to do this with lists:</span></span>

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

<span data-ttu-id="87128-112">切片数组与切片列表类似：</span><span class="sxs-lookup"><span data-stu-id="87128-112">Slicing arrays is just like slicing lists:</span></span>

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

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="87128-113">切片多维数组</span><span class="sxs-lookup"><span data-stu-id="87128-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="87128-114">F#支持F#核心库中的多维数组。</span><span class="sxs-lookup"><span data-stu-id="87128-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="87128-115">与一维数组一样，多维数组的切片也很有用。</span><span class="sxs-lookup"><span data-stu-id="87128-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="87128-116">但是，附加维度的引入要求使用略微不同的语法，以便能够获取特定行和列的切片。</span><span class="sxs-lookup"><span data-stu-id="87128-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="87128-117">下面的示例演示如何切分二维数组：</span><span class="sxs-lookup"><span data-stu-id="87128-117">The following examples demonstrate how to slice a 2D array:</span></span>

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

<span data-ttu-id="87128-118">F#核心库未定义三维数组`GetSlice`。</span><span class="sxs-lookup"><span data-stu-id="87128-118">The F# core library does not define `GetSlice`for 3D arrays.</span></span> <span data-ttu-id="87128-119">如果要对其他维度的数组或其他数组进行切片，则必须自行定义 `GetSlice` 成员。</span><span class="sxs-lookup"><span data-stu-id="87128-119">If you wish to slice those or other arrays of more dimensions, you must define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="87128-120">为其他数据结构定义切片</span><span class="sxs-lookup"><span data-stu-id="87128-120">Defining slices for other data structures</span></span>

<span data-ttu-id="87128-121">F#核心库定义了有限类型集的切片。</span><span class="sxs-lookup"><span data-stu-id="87128-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="87128-122">如果要定义更多数据类型的切片，可以在类型定义本身或类型扩展中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="87128-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="87128-123">例如，下面介绍了如何为 <xref:System.ArraySegment%601> 类定义切片，以便方便地进行数据操作：</span><span class="sxs-lookup"><span data-stu-id="87128-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

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

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a><span data-ttu-id="87128-124">如果需要，请使用内联来避免装箱</span><span class="sxs-lookup"><span data-stu-id="87128-124">Use inlining to avoid boxing if it is necessary</span></span>

<span data-ttu-id="87128-125">如果要为实际为结构的类型定义切片，我们建议您 `inline` `GetSlice` 成员。</span><span class="sxs-lookup"><span data-stu-id="87128-125">If you are defining slices for a type that is actually a struct, we recommend that you `inline` the `GetSlice` member.</span></span> <span data-ttu-id="87128-126">F#编译器消除了可选参数，避免了切片的任何分配。</span><span class="sxs-lookup"><span data-stu-id="87128-126">The F# compiler optimizes away the optional arguments, avoiding any heap allocations as a result of slicing.</span></span> <span data-ttu-id="87128-127">对于无法在堆上分配的切片构造（如 <xref:System.Span%601>），这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="87128-127">This is critically important for slicing constructs such as <xref:System.Span%601> that cannot be allocated on the heap.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="87128-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="87128-128">See also</span></span>

- [<span data-ttu-id="87128-129">索引属性</span><span class="sxs-lookup"><span data-stu-id="87128-129">Indexed properties</span></span>](./members/indexed-properties.md)
