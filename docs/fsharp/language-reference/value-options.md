---
title: '值选项 （F #）'
description: '了解有关 F # 值选项类型，即选项类型的结构版本。'
ms.date: 06/16/2018
ms.openlocfilehash: 4c255cbbcfd9cb480230de09cd370a401c87343a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43527578"
---
# <a name="value-options"></a><span data-ttu-id="96af7-103">值选项</span><span class="sxs-lookup"><span data-stu-id="96af7-103">Value Options</span></span>

<span data-ttu-id="96af7-104">以下两种情况下保存时使用 F # 中的值选项类型：</span><span class="sxs-lookup"><span data-stu-id="96af7-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="96af7-105">一种方案是适用于[F # 选项](options.md)。</span><span class="sxs-lookup"><span data-stu-id="96af7-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="96af7-106">使用结构提供了在你的方案中可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="96af7-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="96af7-107">并非所有性能敏感方案"都解决"通过使用结构。</span><span class="sxs-lookup"><span data-stu-id="96af7-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="96af7-108">您必须考虑复制而不引用类型中使用它们时的额外成本。</span><span class="sxs-lookup"><span data-stu-id="96af7-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="96af7-109">但是，大型 F # 程序通常通过热路径中，流的许多可选类型，因此实例化结构有时可以产生更好地整体性能的程序的整个生命周期。</span><span class="sxs-lookup"><span data-stu-id="96af7-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, because structs can sometimes yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="96af7-110">定义</span><span class="sxs-lookup"><span data-stu-id="96af7-110">Definition</span></span>

<span data-ttu-id="96af7-111">值选项指[结构的可区分联合](discriminated-unions.md#struct-discriminated-unions)类似于引用选项类型：</span><span class="sxs-lookup"><span data-stu-id="96af7-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpValueOption`1")>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone: 'T voption
    | ValueSome: 'T -> 'T voption

    member Value : 'T

and 'T voption = ValueOption<'T>
```

<span data-ttu-id="96af7-112">值选项符合结构相等和比较。</span><span class="sxs-lookup"><span data-stu-id="96af7-112">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="96af7-113">主要区别是已编译的名称、 类型名称和大小写的名称所有指示它是值类型。</span><span class="sxs-lookup"><span data-stu-id="96af7-113">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="96af7-114">使用值选项</span><span class="sxs-lookup"><span data-stu-id="96af7-114">Using Value Options</span></span>

<span data-ttu-id="96af7-115">就像使用值选项[选项](options.md)。</span><span class="sxs-lookup"><span data-stu-id="96af7-115">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="96af7-116">`ValueSome` 用于指示一个值是否存在，并且`ValueNone`值不存在时使用：</span><span class="sxs-lookup"><span data-stu-id="96af7-116">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

<span data-ttu-id="96af7-117">如同[选项](options.md)，返回的函数的命名约定`ValueOption`是它前面加`try`。</span><span class="sxs-lookup"><span data-stu-id="96af7-117">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="96af7-118">值选项属性和方法</span><span class="sxs-lookup"><span data-stu-id="96af7-118">Value Option properties and methods</span></span>

<span data-ttu-id="96af7-119">这次还有另一个属性的值选项： `Value`。</span><span class="sxs-lookup"><span data-stu-id="96af7-119">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="96af7-120"><xref:System.InvalidOperationException>如果没有值，则的存在调用此属性时引发。</span><span class="sxs-lookup"><span data-stu-id="96af7-120">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="96af7-121">值选项函数</span><span class="sxs-lookup"><span data-stu-id="96af7-121">Value Option functions</span></span>

<span data-ttu-id="96af7-122">目前有一个模块绑定函数的值选项`defaultValueArg`:</span><span class="sxs-lookup"><span data-stu-id="96af7-122">There is currently one module-bound function for Value Options, `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

<span data-ttu-id="96af7-123">如同`defaultArg`函数，`defaultValueArg`返回给定值选项的基础值，如果它存在; 否则，返回指定的默认值。</span><span class="sxs-lookup"><span data-stu-id="96af7-123">As with the `defaultArg` function, `defaultValueArg` returns the underlying value of the given Value Option if it exists; otherwise, it returns the specified default value.</span></span>

<span data-ttu-id="96af7-124">在此期间，没有其他模块绑定函数的值选项。</span><span class="sxs-lookup"><span data-stu-id="96af7-124">At this time, there are no other module-bound functions for Value Options.</span></span>

## <a name="see-also"></a><span data-ttu-id="96af7-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="96af7-125">See also</span></span>

[<span data-ttu-id="96af7-126">选项</span><span class="sxs-lookup"><span data-stu-id="96af7-126">Options</span></span>](options.md)