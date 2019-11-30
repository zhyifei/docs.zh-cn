---
title: 4\.7 中F#的新增功能- F#指南
description: 获取4.7 中F#提供的新功能的概述。
ms.date: 11/27/2019
ms.openlocfilehash: 203b258466cb9f1f50215ecf8884e92e7e86416b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644120"
---
# <a name="whats-new-in-f-47"></a><span data-ttu-id="2d7e7-103">4\.7 中F#的新增功能</span><span class="sxs-lookup"><span data-stu-id="2d7e7-103">What's new in F# 4.7</span></span>

<span data-ttu-id="2d7e7-104">F#4.7 向F#语言增加了多项改进。</span><span class="sxs-lookup"><span data-stu-id="2d7e7-104">F# 4.7 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="2d7e7-105">入门</span><span class="sxs-lookup"><span data-stu-id="2d7e7-105">Get started</span></span>

<span data-ttu-id="2d7e7-106">F#4.7 适用于所有 .NET Core 分发版和 Visual Studio 工具。</span><span class="sxs-lookup"><span data-stu-id="2d7e7-106">F# 4.7 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="2d7e7-107">[开始F# ](../get-started/index.md)了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="2d7e7-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="language-version"></a><span data-ttu-id="2d7e7-108">语言版本</span><span class="sxs-lookup"><span data-stu-id="2d7e7-108">Language version</span></span>

<span data-ttu-id="2d7e7-109">F# 4.7 编译器引入了通过项目文件中的属性设置有效语言版本的功能：</span><span class="sxs-lookup"><span data-stu-id="2d7e7-109">The F# 4.7 compiler introduces the ability to set your effective language version via a property in your project file:</span></span>

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="2d7e7-110">可以将其设置为值 `4.6`、`4.7`、`latest`和 `preview`。</span><span class="sxs-lookup"><span data-stu-id="2d7e7-110">You can set it to the values `4.6`, `4.7`, `latest`, and `preview`.</span></span> <span data-ttu-id="2d7e7-111">默认值为 `latest`。</span><span class="sxs-lookup"><span data-stu-id="2d7e7-111">The default is `latest`.</span></span>

<span data-ttu-id="2d7e7-112">如果将其设置为 `preview`，编译器会激活在编译器F#中实现的所有预览功能。</span><span class="sxs-lookup"><span data-stu-id="2d7e7-112">If you set it to `preview`, your compiler will activate all F# preview features that are implemented in your compiler.</span></span>

## <a name="implicit-yields"></a><span data-ttu-id="2d7e7-113">隐式生成</span><span class="sxs-lookup"><span data-stu-id="2d7e7-113">Implicit yields</span></span>

<span data-ttu-id="2d7e7-114">不再需要在可推断类型的数组、列表、序列或计算表达式中应用 `yield` 关键字。</span><span class="sxs-lookup"><span data-stu-id="2d7e7-114">You no longer need to apply the `yield` keyword in arrays, lists, sequences, or computation expressions where the type can be inferred.</span></span> <span data-ttu-id="2d7e7-115">在下面的示例中，两个表达式都需要F# 4.7 之前的每个条目的 `yield` 语句：</span><span class="sxs-lookup"><span data-stu-id="2d7e7-115">In the following example, both expressions required the `yield` statement for each entry prior to F# 4.7:</span></span>

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

<span data-ttu-id="2d7e7-116">如果引入了单个 `yield` 关键字，则还必须对每个项应用 `yield`。</span><span class="sxs-lookup"><span data-stu-id="2d7e7-116">If you introduce a single `yield` keyword, every other item must also have `yield` applied to it.</span></span>

<span data-ttu-id="2d7e7-117">如果在表达式中使用隐式生成，而该表达式也使用 `yield!` 来执行诸如平展序列之类的操作，则不会激活。</span><span class="sxs-lookup"><span data-stu-id="2d7e7-117">Implicit yields are not activated when used in an expression that also uses `yield!` to do something like flatten a sequence.</span></span> <span data-ttu-id="2d7e7-118">现在，在这种情况下，你必须继续使用 `yield`。</span><span class="sxs-lookup"><span data-stu-id="2d7e7-118">You must continue to use `yield` today in these cases.</span></span>

## <a name="wildcard-identifiers"></a><span data-ttu-id="2d7e7-119">通配符标识符</span><span class="sxs-lookup"><span data-stu-id="2d7e7-119">Wildcard identifiers</span></span>

<span data-ttu-id="2d7e7-120">在F#涉及类的代码中，自标识符在成员声明中需要始终是显式的。</span><span class="sxs-lookup"><span data-stu-id="2d7e7-120">In F# code involving classes, the self-identifier needs to always be explicit in member declarations.</span></span> <span data-ttu-id="2d7e7-121">但是，在从未使用过自我标识符的情况下，在传统上，使用双下划线来指示不需要的自标识符。</span><span class="sxs-lookup"><span data-stu-id="2d7e7-121">But in cases where the self-identifier is never used, it has traditionally been convention to use a double-underscore to indicate a nameless self-identifiers.</span></span> <span data-ttu-id="2d7e7-122">现在可以使用单个下划线：</span><span class="sxs-lookup"><span data-stu-id="2d7e7-122">You can now use a single underscore:</span></span>

```fsharp
type C() =
    member _.M() = ()
```

<span data-ttu-id="2d7e7-123">这也适用于 `for` 循环：</span><span class="sxs-lookup"><span data-stu-id="2d7e7-123">This also applies for `for` loops:</span></span>

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a><span data-ttu-id="2d7e7-124">缩进松弛法</span><span class="sxs-lookup"><span data-stu-id="2d7e7-124">Indentation relaxations</span></span>

<span data-ttu-id="2d7e7-125">在F# 4.7 之前，主构造函数和静态成员参数的缩进要求需要过度缩进。</span><span class="sxs-lookup"><span data-stu-id="2d7e7-125">Prior to F# 4.7, the indentation requirements for primary constructor and static member arguments required excessive indentation.</span></span> <span data-ttu-id="2d7e7-126">它们现在只需要单个缩进范围：</span><span class="sxs-lookup"><span data-stu-id="2d7e7-126">They now only require a single indentation scope:</span></span>

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
