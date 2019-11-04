---
title: 值选项
description: 了解F#值选项类型，它是选项类型的结构版本。
ms.date: 02/06/2019
ms.openlocfilehash: 4dc3f7217943345b7aaf1165fd648ab2e01bd727
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424018"
---
# <a name="value-options"></a>值选项

在F#以下两种情况下，使用值选项类型：

1. 方案适用于某个[ F#选项](options.md)。
2. 使用结构可在方案中提供性能优势。

并非所有性能相关的方案都是使用结构 "解决" 的。 使用时，必须考虑复制的额外成本，而不是引用类型。 但是，大型F#程序通常会实例化许多通过热路径的可选类型，在这种情况下，结构通常可以在程序的整个生存期内提供更好的整体性能。

## <a name="definition"></a>定义

值选项定义为类似于引用选项类型的[结构可区分联合](discriminated-unions.md#struct-discriminated-unions)。 它的定义可以通过以下方式来考虑：

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

值选项符合结构相等性和比较。 主要区别在于，已编译的名称、类型名称和大小写名称都表明它是值类型。

## <a name="using-value-options"></a>使用值选项

值选项的使用方式与[选项](options.md)相同。 `ValueSome` 用于指示存在值，并且当值不存在时使用 `ValueNone`：

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

与[选项](options.md)一样，返回 `ValueOption` 的函数的命名约定是使用 `try`作为其前缀。

## <a name="value-option-properties-and-methods"></a>值选项属性和方法

目前存在一个值选项属性： `Value`。 如果调用此属性时没有值，则会引发 <xref:System.InvalidOperationException>。

## <a name="value-option-functions"></a>值选项函数

目前有一个适用于值选项的模块绑定函数，`defaultValueArg`：

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

与 `defaultArg` 函数一样，`defaultValueArg` 返回给定值选项的基础值（如果存在）;否则，它将返回指定的默认值。

目前没有其他用于值选项的模块绑定函数。

## <a name="see-also"></a>请参阅

- [选项](options.md)
