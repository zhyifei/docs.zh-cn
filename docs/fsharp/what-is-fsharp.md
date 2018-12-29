---
title: 什么是 F#
description: 了解有关 F# 编程语言的含义和新增 F# 编程。 了解丰富的数据类型、 函数和它们如何组合在一起。
ms.date: 08/03/2018
ms.openlocfilehash: 193747f380c61a387ed79ecca6abbcd90ee74376
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "43863291"
---
# <a name="what-is-f"></a>什么是 F# #

F# 是一个函数式编程语言，能够让您轻松地编写正确、维护方便的代码。

设计 F# 语言目的是使得类型和函数的定义能够轻松地被推断与泛化。 这样，你只需关注问题本身和对数据的操作，而不是编程的细节问题。

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

F# 具有许多特性，比如：

* 轻量语法
* 默认情况下集合不可变
* 类型推断和自动泛化
* 头等函数。
* 强大多样的数据类型
* 模式匹配
* 异步编程

这里有F#语言完整的文档[F# 语言参考](language-reference/index.md)。

## <a name="rich-data-types"></a>丰富的数据类型

像[Records](language-reference/records.md)和[Discriminated Unions](language-reference/discriminated-unions.md)这样的数据类型可以表示复杂的数据和域。

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

F# Records和可Discriminated Unions默认情况下是不能为null，不可变且能够比较的。这使它们非常易于使用。

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>对函数正确性的保证与模式的匹配

F# 函数非常容易声明，也非常强大。有了[模式匹配](language-reference/pattern-matching.md)加持，它使得您定义由编译器强制保证正确的行为的函数。

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

F# 函数也是头等函数。也就是说，函数能像参数那样被传递到另一个函数、从另一个函数那像值一样被返回出来、函数可以赋值给变量或者存在数据结构中。

## <a name="functions-to-define-operations-on-objects"></a>用于定义【对 对象 的操作】的函数

F# 完全支持objects的概念。在您需要混合使用函数与数据时这是一个非常好用的数据类型。 F# 函数是用于操作对象的。

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

与面向对象编程不同的是，在 F# 中，您编写出的代码经常会将对象看作另一种数据类型，以便让函数去处理它们。[泛型接口](language-reference/interfaces.md)，[对象表达式](language-reference/object-expressions.md)，[成员](language-reference/members/index.md)的使用在大型的F#程序中很常见。

## <a name="next-steps"></a>后续步骤

若要了解有关 F# 功能的一大组的详细信息，请查看[F# 简介](tour.md)。
