---
title: '什么是 F #'
description: '了解有关 F # 编程语言的含义和新增 F # 编程。 了解丰富的数据类型、 函数和它们如何组合在一起。'
ms.date: 08/03/2018
ms.openlocfilehash: 193747f380c61a387ed79ecca6abbcd90ee74376
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "43863291"
---
# <a name="what-is-f"></a><span data-ttu-id="52320-104">什么是 F #</span><span class="sxs-lookup"><span data-stu-id="52320-104">What is F#</span></span> #

<span data-ttu-id="52320-105">F # 是函数式编程语言，轻松地编写正确、 可维护代码。</span><span class="sxs-lookup"><span data-stu-id="52320-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="52320-106">F # 编程主要包括定义类型和函数的类型推断和自动通用化。</span><span class="sxs-lookup"><span data-stu-id="52320-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="52320-107">这样，你只需重点关注的问题域和操作其数据，而不是编程的详细信息。</span><span class="sxs-lookup"><span data-stu-id="52320-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

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

<span data-ttu-id="52320-108">F # 具有许多功能，包括：</span><span class="sxs-lookup"><span data-stu-id="52320-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="52320-109">轻量语法</span><span class="sxs-lookup"><span data-stu-id="52320-109">Lightweight syntax</span></span>
* <span data-ttu-id="52320-110">默认情况下不可变</span><span class="sxs-lookup"><span data-stu-id="52320-110">Immutable by default</span></span>
* <span data-ttu-id="52320-111">类型推断和自动泛化</span><span class="sxs-lookup"><span data-stu-id="52320-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="52320-112">头等函数。</span><span class="sxs-lookup"><span data-stu-id="52320-112">First-class functions</span></span>
* <span data-ttu-id="52320-113">强大的数据类型</span><span class="sxs-lookup"><span data-stu-id="52320-113">Powerful data types</span></span>
* <span data-ttu-id="52320-114">模式匹配</span><span class="sxs-lookup"><span data-stu-id="52320-114">Pattern matching</span></span>
* <span data-ttu-id="52320-115">异步编程</span><span class="sxs-lookup"><span data-stu-id="52320-115">Async programming</span></span>

<span data-ttu-id="52320-116">中介绍了一套完整的功能[F # 语言参考](language-reference/index.md)。</span><span class="sxs-lookup"><span data-stu-id="52320-116">A full set of features are documented in the [F# language reference](language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="52320-117">丰富的数据类型</span><span class="sxs-lookup"><span data-stu-id="52320-117">Rich data types</span></span>

<span data-ttu-id="52320-118">[记录](language-reference/records.md)和[可区分联合](language-reference/discriminated-unions.md)等数据类型可以表示复杂的数据和域。</span><span class="sxs-lookup"><span data-stu-id="52320-118">Data types such as [Records](language-reference/records.md) and [Discriminated Unions](language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

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

<span data-ttu-id="52320-119">F # 记录和可辨识的联合为非 null、 不可变的和默认情况下，使它们非常易于使用的比较。</span><span class="sxs-lookup"><span data-stu-id="52320-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="52320-120">利用函数和模式匹配强制实现正确性</span><span class="sxs-lookup"><span data-stu-id="52320-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="52320-121">F # 函数是轻松地声明和在实践中功能强大。</span><span class="sxs-lookup"><span data-stu-id="52320-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="52320-122">再加上[模式匹配](language-reference/pattern-matching.md)，它们允许您定义由编译器强制执行其正确性的行为。</span><span class="sxs-lookup"><span data-stu-id="52320-122">When combined with [pattern matching](language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

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

<span data-ttu-id="52320-123">F # 函数也是第一类，这意味着它们可作为参数传递，从其他函数返回的。</span><span class="sxs-lookup"><span data-stu-id="52320-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="52320-124">用于定义对对象执行的操作的函数。</span><span class="sxs-lookup"><span data-stu-id="52320-124">Functions to define operations on objects</span></span>

<span data-ttu-id="52320-125">F # 提供对象，都需要进行混合数据和功能的有用的数据类型的完整的支持。</span><span class="sxs-lookup"><span data-stu-id="52320-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="52320-126">F # 函数用于操作对象。</span><span class="sxs-lookup"><span data-stu-id="52320-126">F# functions are used to manipulate objects.</span></span>

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

<span data-ttu-id="52320-127">而不是编写代码是面向对象，在 F # 中，您将经常编写代码将对象与另一个数据类型的函数来操作。</span><span class="sxs-lookup"><span data-stu-id="52320-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="52320-128">等功能[泛型接口](language-reference/interfaces.md)，[对象表达式](language-reference/object-expressions.md)，和明智地使用[成员](language-reference/members/index.md)在较大的 F # 程序中很常见。</span><span class="sxs-lookup"><span data-stu-id="52320-128">Features such as [generic interfaces](language-reference/interfaces.md), [object expressions](language-reference/object-expressions.md), and judicious use of [members](language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="52320-129">后续步骤</span><span class="sxs-lookup"><span data-stu-id="52320-129">Next steps</span></span>

<span data-ttu-id="52320-130">若要了解有关 F # 功能的一大组的详细信息，请查看[F # 简介](tour.md)。</span><span class="sxs-lookup"><span data-stu-id="52320-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>