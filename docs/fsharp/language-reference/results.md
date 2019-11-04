---
title: 结果
description: 了解如何使用F# "结果" 类型来帮助你编写容错代码。
ms.date: 04/24/2017
ms.openlocfilehash: 187aa26ccbaac7e0ec998756377bb7b0489eb1ab
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424855"
---
# <a name="results"></a>结果

从F# 4.1 开始，可以使用 `Result<'T,'TFailure>` 类型来编写可以撰写的错误容错代码。

## <a name="syntax"></a>语法

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> =
    | Ok of ResultValue:'T
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a>备注

请注意，结果类型是[结构可区分联合](discriminated-unions.md#struct-discriminated-unions)，这是4.1 中F#引入的另一项功能。  在此处应用结构相等性语义。

`Result` 类型通常用于一元错误处理，这在F#社区中通常称为[面向铁路的编程](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html)。  以下简单示例演示了这种方法。

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

正如您所看到的，如果强制所有验证函数都返回 `Result`，则可以很容易地将各种验证函数链接在一起。  这使你可以将此类功能分解为小部分，它们可根据你的需要进行组合。  这也增加了在一轮验证的末尾*强制*使用[模式匹配](pattern-matching.md)的值，进而强制实施更高程度的程序正确性。

## <a name="see-also"></a>请参阅

- [可区分联合](discriminated-unions.md)
- [模式匹配](pattern-matching.md)
