---
title: '值选项 （F #）'
description: '了解有关 F # 值选项类型，即选项类型的结构版本。'
ms.date: 06/16/2018
ms.openlocfilehash: 978bd1713c16f7c050ccb097cb134973d10ef6f5
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "50185831"
---
# <a name="value-options"></a>值选项

以下两种情况下保存时使用 F # 中的值选项类型：

1. 一种方案是适用于[F # 选项](options.md)。
2. 使用结构提供了在你的方案中可以提高性能。

并非所有性能敏感方案"都解决"通过使用结构。 您必须考虑复制而不引用类型中使用它们时的额外成本。 但是，大型 F # 程序通常通过热路径中，流的许多可选类型，因此实例化结构有时可以产生更好地整体性能的程序的整个生命周期。

## <a name="definition"></a>定义

值选项指[结构的可区分联合](discriminated-unions.md#struct-discriminated-unions)类似于引用选项类型。 这种方式可被视为其定义：

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

值选项符合结构相等和比较。 主要区别是已编译的名称、 类型名称和大小写的名称所有指示它是值类型。

## <a name="using-value-options"></a>使用值选项

就像使用值选项[选项](options.md)。 `ValueSome` 用于指示一个值是否存在，并且`ValueNone`值不存在时使用：

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

如同[选项](options.md)，返回的函数的命名约定`ValueOption`是它前面加`try`。

## <a name="value-option-properties-and-methods"></a>值选项属性和方法

这次还有另一个属性的值选项： `Value`。 <xref:System.InvalidOperationException>如果没有值，则的存在调用此属性时引发。

## <a name="value-option-functions"></a>值选项函数

目前有一个模块绑定函数的值选项`defaultValueArg`:

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

如同`defaultArg`函数，`defaultValueArg`返回给定值选项的基础值，如果它存在; 否则，返回指定的默认值。

在此期间，没有其他模块绑定函数的值选项。

## <a name="see-also"></a>请参阅

- [选项](options.md)
