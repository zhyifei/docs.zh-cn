---
title: F# 是什么
description: 了解F#编程语言是以及F#就像编程。 了解丰富的数据类型、 函数和它们如何组合在一起。
ms.date: 08/03/2018
ms.openlocfilehash: ea82147e4e6d3c980fb224eeafd805c7ed53f8f2
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966952"
---
# <a name="what-is-f"></a><span data-ttu-id="55a67-104">F\# 是什么</span><span class="sxs-lookup"><span data-stu-id="55a67-104">What is F\#</span></span>

<span data-ttu-id="55a67-105">F# 是一种函数式编程语言，可用于轻松地编写正确和可维护的代码。</span><span class="sxs-lookup"><span data-stu-id="55a67-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="55a67-106">F# 编程主要包括定义类型以及自动通过类型进行推断和通用化的函数。</span><span class="sxs-lookup"><span data-stu-id="55a67-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="55a67-107">这样，你只需重点关注问题域并操作其数据，而不需关注编程细节。</span><span class="sxs-lookup"><span data-stu-id="55a67-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

[<EntryPoint>]
let main args =
    // Defines a list of names
    let names = [ "Don"; "Julia"; "Xi" ]

    // Prints a greeting for each name!
    names
    |> List.map getGreeting
    |> List.iter (fun greeting -> printfn "%s" greeting)

    0
```

<span data-ttu-id="55a67-108">F# 具有许多特性，包括：</span><span class="sxs-lookup"><span data-stu-id="55a67-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="55a67-109">轻量语法</span><span class="sxs-lookup"><span data-stu-id="55a67-109">Lightweight syntax</span></span>
* <span data-ttu-id="55a67-110">默认情况下不可变</span><span class="sxs-lookup"><span data-stu-id="55a67-110">Immutable by default</span></span>
* <span data-ttu-id="55a67-111">类型推断和自动泛化</span><span class="sxs-lookup"><span data-stu-id="55a67-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="55a67-112">头等函数</span><span class="sxs-lookup"><span data-stu-id="55a67-112">First-class functions</span></span>
* <span data-ttu-id="55a67-113">强大的数据类型</span><span class="sxs-lookup"><span data-stu-id="55a67-113">Powerful data types</span></span>
* <span data-ttu-id="55a67-114">模式匹配</span><span class="sxs-lookup"><span data-stu-id="55a67-114">Pattern matching</span></span>
* <span data-ttu-id="55a67-115">异步编程</span><span class="sxs-lookup"><span data-stu-id="55a67-115">Async programming</span></span>

<span data-ttu-id="55a67-116">[F# 语言参考](language-reference/index.md)中介绍了完整的特性。</span><span class="sxs-lookup"><span data-stu-id="55a67-116">A full set of features are documented in the [F# language reference](language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="55a67-117">丰富的数据类型</span><span class="sxs-lookup"><span data-stu-id="55a67-117">Rich data types</span></span>

<span data-ttu-id="55a67-118">[记录](language-reference/records.md)和[可区分联合](language-reference/discriminated-unions.md)等数据类型可以表示复杂的数据和域。</span><span class="sxs-lookup"><span data-stu-id="55a67-118">Data types such as [Records](language-reference/records.md) and [Discriminated Unions](language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

```fsharp
// Group data with Records
type SuccessfulWithdrawal = {
    Amount: decimal
    Balance: decimal
}

type FailedWithdrawal = {
    Amount: decimal
    Balance: decimal
    IsOverdraft: bool
}

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

<span data-ttu-id="55a67-119">F# 的记录和可区分联合默认情况下非 null、不可变且可比较，因此非常易于使用。</span><span class="sxs-lookup"><span data-stu-id="55a67-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="55a67-120">利用函数和模式匹配强制实现正确性</span><span class="sxs-lookup"><span data-stu-id="55a67-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="55a67-121">F# 函数易于声明且实用性强。</span><span class="sxs-lookup"><span data-stu-id="55a67-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="55a67-122">与[模式匹配](language-reference/pattern-matching.md)结合使用时，可以定义其正确性获得编译器保障的行为。</span><span class="sxs-lookup"><span data-stu-id="55a67-122">When combined with [pattern matching](language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f" s.Amount
    | InsufficientFunds f -> printfn "Failed: balance is %f" f.Balance
    | CardExpired d -> printfn "Failed: card expired on %O" d
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

<span data-ttu-id="55a67-123">F# 函数也是头等函数，也就是说，它们可以作为参数传递，还可以从其他函数返回。</span><span class="sxs-lookup"><span data-stu-id="55a67-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="55a67-124">用于定义对对象执行的操作的函数。</span><span class="sxs-lookup"><span data-stu-id="55a67-124">Functions to define operations on objects</span></span>

<span data-ttu-id="55a67-125">F# 具有对对象的完整支持，即在需要混合数据和功能时非常有用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="55a67-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="55a67-126">F#函数用于操作对象。</span><span class="sxs-lookup"><span data-stu-id="55a67-126">F# functions are used to manipulate objects.</span></span>

```fsharp
type Set<[<EqualityConditionOn>] ‘T when ‘T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

[<RequireQualifiedAccess>]
module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

<span data-ttu-id="55a67-127">在 F# 中，你会经常编写一类代码，这些代码将对象视为供函数操作的另一种数据类型，而不是编写面向对象的代码。</span><span class="sxs-lookup"><span data-stu-id="55a67-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="55a67-128">在较大型的 F# 程序中，通常需要使用[泛型接口](language-reference/interfaces.md)、[对象表达式](language-reference/object-expressions.md)等功能，此文还需正确使用[成员](language-reference/members/index.md)。</span><span class="sxs-lookup"><span data-stu-id="55a67-128">Features such as [generic interfaces](language-reference/interfaces.md), [object expressions](language-reference/object-expressions.md), and judicious use of [members](language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="55a67-129">后续步骤</span><span class="sxs-lookup"><span data-stu-id="55a67-129">Next steps</span></span>

<span data-ttu-id="55a67-130">若要详细了解更多 F# 功能，请查看 [F# 教程](tour.md)。</span><span class="sxs-lookup"><span data-stu-id="55a67-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>