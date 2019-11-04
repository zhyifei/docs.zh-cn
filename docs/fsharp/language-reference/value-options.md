---
title: 值选项
description: 了解F#值选项类型，它是选项类型的结构版本。
ms.date: 02/06/2019
ms.openlocfilehash: 4dc3f7217943345b7aaf1165fd648ab2e01bd727
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424018"
---
# <a name="value-options"></a><span data-ttu-id="04e67-103">值选项</span><span class="sxs-lookup"><span data-stu-id="04e67-103">Value Options</span></span>

<span data-ttu-id="04e67-104">在F#以下两种情况下，使用值选项类型：</span><span class="sxs-lookup"><span data-stu-id="04e67-104">The Value Option type in F# is used when the following two circumstances hold:</span></span>

1. <span data-ttu-id="04e67-105">方案适用于某个[ F#选项](options.md)。</span><span class="sxs-lookup"><span data-stu-id="04e67-105">A scenario is appropriate for an [F# Option](options.md).</span></span>
2. <span data-ttu-id="04e67-106">使用结构可在方案中提供性能优势。</span><span class="sxs-lookup"><span data-stu-id="04e67-106">Using a struct provides a performance benefit in your scenario.</span></span>

<span data-ttu-id="04e67-107">并非所有性能相关的方案都是使用结构 "解决" 的。</span><span class="sxs-lookup"><span data-stu-id="04e67-107">Not all performance-sensitive scenarios are "solved" by using structs.</span></span> <span data-ttu-id="04e67-108">使用时，必须考虑复制的额外成本，而不是引用类型。</span><span class="sxs-lookup"><span data-stu-id="04e67-108">You must consider the additional cost of copying when using them instead of reference types.</span></span> <span data-ttu-id="04e67-109">但是，大型F#程序通常会实例化许多通过热路径的可选类型，在这种情况下，结构通常可以在程序的整个生存期内提供更好的整体性能。</span><span class="sxs-lookup"><span data-stu-id="04e67-109">However, large F# programs commonly instantiate many optional types that flow through hot paths, and in such cases, structs can often yield better overall performance over the lifetime of a program.</span></span>

## <a name="definition"></a><span data-ttu-id="04e67-110">定义</span><span class="sxs-lookup"><span data-stu-id="04e67-110">Definition</span></span>

<span data-ttu-id="04e67-111">值选项定义为类似于引用选项类型的[结构可区分联合](discriminated-unions.md#struct-discriminated-unions)。</span><span class="sxs-lookup"><span data-stu-id="04e67-111">Value Option is defined as a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions) that is similar to the reference option type.</span></span> <span data-ttu-id="04e67-112">它的定义可以通过以下方式来考虑：</span><span class="sxs-lookup"><span data-stu-id="04e67-112">Its definition can be thought of this way:</span></span>

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

<span data-ttu-id="04e67-113">值选项符合结构相等性和比较。</span><span class="sxs-lookup"><span data-stu-id="04e67-113">Value Option conforms to structural equality and comparison.</span></span> <span data-ttu-id="04e67-114">主要区别在于，已编译的名称、类型名称和大小写名称都表明它是值类型。</span><span class="sxs-lookup"><span data-stu-id="04e67-114">The main difference is that the compiled name, type name, and case names all indicate that it is a value type.</span></span>

## <a name="using-value-options"></a><span data-ttu-id="04e67-115">使用值选项</span><span class="sxs-lookup"><span data-stu-id="04e67-115">Using Value Options</span></span>

<span data-ttu-id="04e67-116">值选项的使用方式与[选项](options.md)相同。</span><span class="sxs-lookup"><span data-stu-id="04e67-116">Value Options are used just like [Options](options.md).</span></span> <span data-ttu-id="04e67-117">`ValueSome` 用于指示存在值，并且当值不存在时使用 `ValueNone`：</span><span class="sxs-lookup"><span data-stu-id="04e67-117">`ValueSome` is used to indicate that a value is present, and `ValueNone` is used when a value is not present:</span></span>

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

<span data-ttu-id="04e67-118">与[选项](options.md)一样，返回 `ValueOption` 的函数的命名约定是使用 `try`作为其前缀。</span><span class="sxs-lookup"><span data-stu-id="04e67-118">As with [Options](options.md), the naming convention for a function that returns `ValueOption` is to prefix it with `try`.</span></span>

## <a name="value-option-properties-and-methods"></a><span data-ttu-id="04e67-119">值选项属性和方法</span><span class="sxs-lookup"><span data-stu-id="04e67-119">Value Option properties and methods</span></span>

<span data-ttu-id="04e67-120">目前存在一个值选项属性： `Value`。</span><span class="sxs-lookup"><span data-stu-id="04e67-120">There is one property for Value Options at this time: `Value`.</span></span> <span data-ttu-id="04e67-121">如果调用此属性时没有值，则会引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="04e67-121">An <xref:System.InvalidOperationException> is raised if no value is present when this property is invoked.</span></span>

## <a name="value-option-functions"></a><span data-ttu-id="04e67-122">值选项函数</span><span class="sxs-lookup"><span data-stu-id="04e67-122">Value Option functions</span></span>

<span data-ttu-id="04e67-123">目前有一个适用于值选项的模块绑定函数，`defaultValueArg`：</span><span class="sxs-lookup"><span data-stu-id="04e67-123">There is currently one module-bound function for Value Options, `defaultValueArg`:</span></span>

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

<span data-ttu-id="04e67-124">与 `defaultArg` 函数一样，`defaultValueArg` 返回给定值选项的基础值（如果存在）;否则，它将返回指定的默认值。</span><span class="sxs-lookup"><span data-stu-id="04e67-124">As with the `defaultArg` function, `defaultValueArg` returns the underlying value of the given Value Option if it exists; otherwise, it returns the specified default value.</span></span>

<span data-ttu-id="04e67-125">目前没有其他用于值选项的模块绑定函数。</span><span class="sxs-lookup"><span data-stu-id="04e67-125">At this time, there are no other module-bound functions for Value Options.</span></span>

## <a name="see-also"></a><span data-ttu-id="04e67-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="04e67-126">See also</span></span>

- [<span data-ttu-id="04e67-127">选项</span><span class="sxs-lookup"><span data-stu-id="04e67-127">Options</span></span>](options.md)
