---
title: "结果 （F #）"
description: "了解如何使用 F # Result 类型可帮助你编写容错的代码。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a15b5cf1-9055-4481-918c-4c8a051b5829
ms.openlocfilehash: e6535b11464f5de0515c05e6678f6328f48a676a
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="results"></a><span data-ttu-id="842bb-104">结果</span><span class="sxs-lookup"><span data-stu-id="842bb-104">Results</span></span>

<span data-ttu-id="842bb-105">F # 4.1 开始，没有`Result<'T,'TFailure>`可用于编写可由容错错误代码的类型。</span><span class="sxs-lookup"><span data-stu-id="842bb-105">Starting with F# 4.1, there is a `Result<'T,'TFailure>` type which you can use for writing error-tolerant code which can be composed.</span></span>

## <a name="syntax"></a><span data-ttu-id="842bb-106">语法</span><span class="sxs-lookup"><span data-stu-id="842bb-106">Syntax</span></span>

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> = 
    | Ok of ResultValue:'T 
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a><span data-ttu-id="842bb-107">备注</span><span class="sxs-lookup"><span data-stu-id="842bb-107">Remarks</span></span>

<span data-ttu-id="842bb-108">请注意，结果类型是[结构可区分的联合](discriminated-unions.md#struct-discriminated-unions)，即在 F # 4.1 中引入的另一个功能。</span><span class="sxs-lookup"><span data-stu-id="842bb-108">Note that the result type is a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions), which is another feature introduced in F# 4.1.</span></span>  <span data-ttu-id="842bb-109">结构上相等语义在此处适用。</span><span class="sxs-lookup"><span data-stu-id="842bb-109">Structural equality semantics apply here.</span></span>

<span data-ttu-id="842bb-110">`Result`类型通常用于一元错误处理，这通常称为[铁路面向编程](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html)F # 社区内。</span><span class="sxs-lookup"><span data-stu-id="842bb-110">The `Result` type is typically used in monadic error-handling, which is often referred to as [Railway-oriented Programming](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) within the F# community.</span></span>  <span data-ttu-id="842bb-111">下面的简单示例演示这种方法。</span><span class="sxs-lookup"><span data-stu-id="842bb-111">The following trivial example demonstrates this approach.</span></span>

```fsharp
// Define a simple type which has fields that can be validated
type Request = 
    { Name: string
      Email: string }

// Define some logic for what defines a valid name.
//
// Generates a Result which is an Ok if the name validates;
// otherwise, it generates a Result which is an Error.
let validateName req =
    match req.Name with
    | null -> Error "No name found."
    | "" -> Error "Name is empty."
    | "bananas" -> Error "Bananas is not a name."
    | _ -> Ok req

// Similarly, define some email validation logic.
let validateEmail req =
    match req.Email with
    | null -> Error "No email found."
    | "" -> Error "Email is empty."
    | s when s.EndsWith("bananas.com") -> Error "No email from bananas.com is allowed."
    | _ -> Ok req

let validateRequest reqResult =
    reqResult 
    |> Result.bind validateName
    |> Result.bind validateEmail

let test() = 
    // Now, create a Request and pattern match on the result.
    let req1 = { Name = "Phillip"; Email = "phillip@contoso.biz" }
    let res1 = validateRequest (Ok req1)
    match res1 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (Ok req2)
    match res2 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

<span data-ttu-id="842bb-112">如你所见，它是很容易地链接在一起验证的各种函数，如果强制其全部返回`Result`。</span><span class="sxs-lookup"><span data-stu-id="842bb-112">As you can see, it's quite easy to chain together various validation functions if you force them all to return a `Result`.</span></span>  <span data-ttu-id="842bb-113">这样，分解如下分为小的部分是根据你的需要是可组合的功能。</span><span class="sxs-lookup"><span data-stu-id="842bb-113">This lets you break up functionality like this into small pieces which are as composable as you need them to be.</span></span>  <span data-ttu-id="842bb-114">此模式还具有增加的价值在于*强制实施*使用[模式匹配](pattern-matching.md)在一轮验证结束时，后者又在强制实施更高的程序正确性。</span><span class="sxs-lookup"><span data-stu-id="842bb-114">This also has the added value of *enforcing* the use of [pattern matching](pattern-matching.md) at the end of a round of validation, which in turns enforces a higher degree of program correctness.</span></span>

## <a name="see-also"></a><span data-ttu-id="842bb-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="842bb-115">See Also</span></span>

[<span data-ttu-id="842bb-116">可区分联合</span><span class="sxs-lookup"><span data-stu-id="842bb-116">Discriminated Unions</span></span>](discriminated-unions.md)

[<span data-ttu-id="842bb-117">模式匹配</span><span class="sxs-lookup"><span data-stu-id="842bb-117">Pattern Matching</span></span>](pattern-matching.md)
