---
title: 结果
description: 了解如何使用F#结果类型可帮助你编写容错的代码。
ms.date: 04/24/2017
ms.openlocfilehash: 36f60df8a2991c1d318e4921af6c9e89a0156918
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645325"
---
# <a name="results"></a><span data-ttu-id="c3717-103">结果</span><span class="sxs-lookup"><span data-stu-id="c3717-103">Results</span></span>

<span data-ttu-id="c3717-104">从F#4.1，没有`Result<'T,'TFailure>`可用于编写容错错误代码的可组合的类型。</span><span class="sxs-lookup"><span data-stu-id="c3717-104">Starting with F# 4.1, there is a `Result<'T,'TFailure>` type which you can use for writing error-tolerant code which can be composed.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3717-105">语法</span><span class="sxs-lookup"><span data-stu-id="c3717-105">Syntax</span></span>

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> = 
    | Ok of ResultValue:'T 
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a><span data-ttu-id="c3717-106">备注</span><span class="sxs-lookup"><span data-stu-id="c3717-106">Remarks</span></span>

<span data-ttu-id="c3717-107">请注意，结果类型是[结构的可区分联合](discriminated-unions.md#struct-discriminated-unions)，这另一项功能在中引入F#4.1。</span><span class="sxs-lookup"><span data-stu-id="c3717-107">Note that the result type is a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions), which is another feature introduced in F# 4.1.</span></span>  <span data-ttu-id="c3717-108">结构相等性语义在此处适用。</span><span class="sxs-lookup"><span data-stu-id="c3717-108">Structural equality semantics apply here.</span></span>

<span data-ttu-id="c3717-109">`Result`类型通常用在一元错误的处理，这通常称为[铁路面向编程](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html)中F#社区。</span><span class="sxs-lookup"><span data-stu-id="c3717-109">The `Result` type is typically used in monadic error-handling, which is often referred to as [Railway-oriented Programming](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) within the F# community.</span></span>  <span data-ttu-id="c3717-110">下面的简单示例演示了这种方法。</span><span class="sxs-lookup"><span data-stu-id="c3717-110">The following trivial example demonstrates this approach.</span></span>

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

<span data-ttu-id="c3717-111">正如您所看到的它是很容易地链接在一起各种验证函数，如果您强制其全部返回`Result`。</span><span class="sxs-lookup"><span data-stu-id="c3717-111">As you can see, it's quite easy to chain together various validation functions if you force them all to return a `Result`.</span></span>  <span data-ttu-id="c3717-112">这样，便分解成小的部分是根据你的需要是可组合此类功能。</span><span class="sxs-lookup"><span data-stu-id="c3717-112">This lets you break up functionality like this into small pieces which are as composable as you need them to be.</span></span>  <span data-ttu-id="c3717-113">这样做还具有的增值*强制实施*利用[模式匹配](pattern-matching.md)在一轮的验证结束时，后者又在强制实施更高程度的程序的正确性。</span><span class="sxs-lookup"><span data-stu-id="c3717-113">This also has the added value of *enforcing* the use of [pattern matching](pattern-matching.md) at the end of a round of validation, which in turns enforces a higher degree of program correctness.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3717-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3717-114">See also</span></span>

- [<span data-ttu-id="c3717-115">可区分联合</span><span class="sxs-lookup"><span data-stu-id="c3717-115">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="c3717-116">模式匹配</span><span class="sxs-lookup"><span data-stu-id="c3717-116">Pattern Matching</span></span>](pattern-matching.md)
