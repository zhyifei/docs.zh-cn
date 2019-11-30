---
title: 4\.6 中F#的新增功能- F#指南
description: 获取4.6 中F#提供的新功能的概述。
ms.date: 11/27/2019
ms.openlocfilehash: 81d3e988d044cb16f8ec079118fd0ede2dabc587
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644132"
---
# <a name="whats-new-in-f-46"></a><span data-ttu-id="827bf-103">4\.6 中F#的新增功能</span><span class="sxs-lookup"><span data-stu-id="827bf-103">What's new in F# 4.6</span></span>

<span data-ttu-id="827bf-104">F#4.6 向F#语言增加了多项改进。</span><span class="sxs-lookup"><span data-stu-id="827bf-104">F# 4.6 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="827bf-105">入门</span><span class="sxs-lookup"><span data-stu-id="827bf-105">Get started</span></span>

<span data-ttu-id="827bf-106">F#4.6 适用于所有 .NET Core 分发版和 Visual Studio 工具。</span><span class="sxs-lookup"><span data-stu-id="827bf-106">F# 4.6 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="827bf-107">[开始F# ](../get-started/index.md)了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="827bf-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="anonymous-records"></a><span data-ttu-id="827bf-108">匿名记录</span><span class="sxs-lookup"><span data-stu-id="827bf-108">Anonymous records</span></span>

<span data-ttu-id="827bf-109">[匿名记录](../language-reference/anonymous-records.md)是4.6 中F#引入的F#一种新类型。</span><span class="sxs-lookup"><span data-stu-id="827bf-109">[Anonymous records](../language-reference/anonymous-records.md) are a new kind of F# type introduced in F# 4.6.</span></span> <span data-ttu-id="827bf-110">它们是命名值的简单聚合，在使用之前无需声明。</span><span class="sxs-lookup"><span data-stu-id="827bf-110">They are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="827bf-111">可以将它们声明为结构或引用类型。</span><span class="sxs-lookup"><span data-stu-id="827bf-111">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="827bf-112">默认情况下，它们是引用类型。</span><span class="sxs-lookup"><span data-stu-id="827bf-112">They're reference types by default.</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

<span data-ttu-id="827bf-113">如果要对值类型进行分组并在性能相关的方案中运行，还可以将它们声明为结构：</span><span class="sxs-lookup"><span data-stu-id="827bf-113">They can also be declared as structs for when you want to group value types and are operating in performance-sensitive scenarios:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    struct {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

<span data-ttu-id="827bf-114">它们的功能非常强大，可以在许多方案中使用。</span><span class="sxs-lookup"><span data-stu-id="827bf-114">They're quite powerful and can be used in numerous scenarios.</span></span> <span data-ttu-id="827bf-115">了解有关[匿名记录](../language-reference/anonymous-records.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="827bf-115">Learn more at [Anonymous records](../language-reference/anonymous-records.md).</span></span>

## <a name="valueoption-functions"></a><span data-ttu-id="827bf-116">ValueOption 函数</span><span class="sxs-lookup"><span data-stu-id="827bf-116">ValueOption functions</span></span>

<span data-ttu-id="827bf-117">4\.5 中F#添加的 ValueOption 类型现在具有选项类型的 "模块绑定函数奇偶校验"。</span><span class="sxs-lookup"><span data-stu-id="827bf-117">The ValueOption type added in F# 4.5 now has "module-bound function parity" with the Option type.</span></span> <span data-ttu-id="827bf-118">一些更常用的示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="827bf-118">Some of the more commonly-used examples are as follows:</span></span>

```fsharp
// Multiply a value option by 2 if it has  value
let xOpt = ValueSome 99
let result = xOpt |> ValueOption.map (fun v -> v * 2)

// Reverse a string if it exists
let strOpt = ValueSome "Mirror image"
let reverse (str: string) =
    match str with
    | null
    | "" -> None
    | s ->
        str.ToCharArray()
        |> Array.rev
        |> string
        |> Some

let reversedString = strOpt |> Option.bind reverse
```

<span data-ttu-id="827bf-119">这允许在值类型提高性能的情况下，使用类似于 ValueOption 的选项。</span><span class="sxs-lookup"><span data-stu-id="827bf-119">This allows for ValueOption to be used just like Option in scenarios where having a value type improves performance.</span></span>
