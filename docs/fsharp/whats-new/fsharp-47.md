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
# <a name="whats-new-in-f-47"></a>4\.7 中F#的新增功能

F#4.7 向F#语言增加了多项改进。

## <a name="get-started"></a>入门

F#4.7 适用于所有 .NET Core 分发版和 Visual Studio 工具。 [开始F# ](../get-started/index.md)了解更多详细信息。

## <a name="language-version"></a>语言版本

F# 4.7 编译器引入了通过项目文件中的属性设置有效语言版本的功能：

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

可以将其设置为值 `4.6`、`4.7`、`latest`和 `preview`。 默认值为 `latest`。

如果将其设置为 `preview`，编译器会激活在编译器F#中实现的所有预览功能。

## <a name="implicit-yields"></a>隐式生成

不再需要在可推断类型的数组、列表、序列或计算表达式中应用 `yield` 关键字。 在下面的示例中，两个表达式都需要F# 4.7 之前的每个条目的 `yield` 语句：

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

如果引入了单个 `yield` 关键字，则还必须对每个项应用 `yield`。

如果在表达式中使用隐式生成，而该表达式也使用 `yield!` 来执行诸如平展序列之类的操作，则不会激活。 现在，在这种情况下，你必须继续使用 `yield`。

## <a name="wildcard-identifiers"></a>通配符标识符

在F#涉及类的代码中，自标识符在成员声明中需要始终是显式的。 但是，在从未使用过自我标识符的情况下，在传统上，使用双下划线来指示不需要的自标识符。 现在可以使用单个下划线：

```fsharp
type C() =
    member _.M() = ()
```

这也适用于 `for` 循环：

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a>缩进松弛法

在F# 4.7 之前，主构造函数和静态成员参数的缩进要求需要过度缩进。 它们现在只需要单个缩进范围：

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
