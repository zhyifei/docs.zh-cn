---
title: F# 4.7 - F# 指南中的新增功能
description: 获取 F# 4.7 中提供的新功能的概述。
ms.date: 11/27/2019
ms.openlocfilehash: 7a6e744a398719bcb55d168dd700459e0b122dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185876"
---
# <a name="whats-new-in-f-47"></a><span data-ttu-id="27a9e-103">F# 4.7 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="27a9e-103">What's new in F# 4.7</span></span>

<span data-ttu-id="27a9e-104">F# 4.7 为 F# 语言添加了多项改进。</span><span class="sxs-lookup"><span data-stu-id="27a9e-104">F# 4.7 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="27a9e-105">入门</span><span class="sxs-lookup"><span data-stu-id="27a9e-105">Get started</span></span>

<span data-ttu-id="27a9e-106">F# 4.7 在所有 .NET 核心发行版和可视化工作室工具中均可用。</span><span class="sxs-lookup"><span data-stu-id="27a9e-106">F# 4.7 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="27a9e-107">[开始使用 F#](../get-started/index.md)了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="27a9e-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="language-version"></a><span data-ttu-id="27a9e-108">语言版本</span><span class="sxs-lookup"><span data-stu-id="27a9e-108">Language version</span></span>

<span data-ttu-id="27a9e-109">F# 4.7 编译器引入了通过项目文件中的属性设置有效语言版本的能力：</span><span class="sxs-lookup"><span data-stu-id="27a9e-109">The F# 4.7 compiler introduces the ability to set your effective language version via a property in your project file:</span></span>

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="27a9e-110">可以将其`4.6`设置为 值 、`4.7``latest`和`preview`。</span><span class="sxs-lookup"><span data-stu-id="27a9e-110">You can set it to the values `4.6`, `4.7`, `latest`, and `preview`.</span></span> <span data-ttu-id="27a9e-111">默认为 `latest`。</span><span class="sxs-lookup"><span data-stu-id="27a9e-111">The default is `latest`.</span></span>

<span data-ttu-id="27a9e-112">如果将其设置为`preview`，编译器将激活编译器中实现的所有 F# 预览功能。</span><span class="sxs-lookup"><span data-stu-id="27a9e-112">If you set it to `preview`, your compiler will activate all F# preview features that are implemented in your compiler.</span></span>

## <a name="implicit-yields"></a><span data-ttu-id="27a9e-113">隐式收益</span><span class="sxs-lookup"><span data-stu-id="27a9e-113">Implicit yields</span></span>

<span data-ttu-id="27a9e-114">不再需要在`yield`可以推断类型的数组、列表、序列或计算表达式中应用关键字。</span><span class="sxs-lookup"><span data-stu-id="27a9e-114">You no longer need to apply the `yield` keyword in arrays, lists, sequences, or computation expressions where the type can be inferred.</span></span> <span data-ttu-id="27a9e-115">在下面的示例中，两个表达式都需要 F# 4.7 之前每个条目的`yield`语句：</span><span class="sxs-lookup"><span data-stu-id="27a9e-115">In the following example, both expressions required the `yield` statement for each entry prior to F# 4.7:</span></span>

```fsharp
let s = seq { 1; 2; 3; 4; 5 }

let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]
```

<span data-ttu-id="27a9e-116">如果引入单个`yield`关键字，则所有其他项也必须已`yield`应用于该关键字。</span><span class="sxs-lookup"><span data-stu-id="27a9e-116">If you introduce a single `yield` keyword, every other item must also have `yield` applied to it.</span></span>

<span data-ttu-id="27a9e-117">在表达式中使用时，隐式收益不会激活，该表达式`yield!`还用于执行诸如拼平序列之类的操作。</span><span class="sxs-lookup"><span data-stu-id="27a9e-117">Implicit yields are not activated when used in an expression that also uses `yield!` to do something like flatten a sequence.</span></span> <span data-ttu-id="27a9e-118">在这些情况下，今天必须继续`yield`使用。</span><span class="sxs-lookup"><span data-stu-id="27a9e-118">You must continue to use `yield` today in these cases.</span></span>

## <a name="wildcard-identifiers"></a><span data-ttu-id="27a9e-119">通配符标识符</span><span class="sxs-lookup"><span data-stu-id="27a9e-119">Wildcard identifiers</span></span>

<span data-ttu-id="27a9e-120">在涉及类的 F# 代码中，自标识符必须始终在成员声明中显式。</span><span class="sxs-lookup"><span data-stu-id="27a9e-120">In F# code involving classes, the self-identifier needs to always be explicit in member declarations.</span></span> <span data-ttu-id="27a9e-121">但是，在从未使用自标识符的情况下，传统上使用双下划线来指示无名的自标识符是惯例。</span><span class="sxs-lookup"><span data-stu-id="27a9e-121">But in cases where the self-identifier is never used, it has traditionally been convention to use a double-underscore to indicate a nameless self-identifiers.</span></span> <span data-ttu-id="27a9e-122">现在可以使用单个下划线：</span><span class="sxs-lookup"><span data-stu-id="27a9e-122">You can now use a single underscore:</span></span>

```fsharp
type C() =
    member _.M() = ()
```

<span data-ttu-id="27a9e-123">这也适用于`for`循环：</span><span class="sxs-lookup"><span data-stu-id="27a9e-123">This also applies for `for` loops:</span></span>

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a><span data-ttu-id="27a9e-124">缩进松弛</span><span class="sxs-lookup"><span data-stu-id="27a9e-124">Indentation relaxations</span></span>

<span data-ttu-id="27a9e-125">在 F# 4.7 之前，主构造函数和静态成员参数的缩进要求要求过高的缩进。</span><span class="sxs-lookup"><span data-stu-id="27a9e-125">Prior to F# 4.7, the indentation requirements for primary constructor and static member arguments required excessive indentation.</span></span> <span data-ttu-id="27a9e-126">它们现在只需要一个缩进范围：</span><span class="sxs-lookup"><span data-stu-id="27a9e-126">They now only require a single indentation scope:</span></span>

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
