---
title: 枚举
description: 了解如何使用F#枚举替代文本, 使代码更具可读性和更易维护性。
ms.date: 05/16/2016
ms.openlocfilehash: 784cd9612b199e4648bb64432d3b4422ad35f649
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630339"
---
# <a name="enumerations"></a>枚举

*枚举*(也称为*枚举*) 是整型类型, 其中标签分配给值的子集。 可以使用它们来代替文本，使代码更具可读性且更易维护。

## <a name="syntax"></a>语法

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>备注

枚举非常类似于具有简单值的可区分联合, 只不过可以指定这些值。 值通常是从0或1开始的整数, 或者是表示位位置的整数。 如果枚举旨在表示位位置, 还应使用[Flags](xref:System.FlagsAttribute)特性。

枚举的基础类型是根据使用的文本确定的, 因此, 例如, 可以对无符号整数 ( `1u` `uint32`) 类型使用带有后缀的文本 (例如、 `2u`等)。

引用命名值时, 必须使用枚举类型本身的名称作为限定符, `enum-name.value1`即, 而不只`value1`是。 此行为不同于可区分联合的行为。 这是因为枚举始终具有[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)属性。

下面的代码演示了枚举的声明和使用。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

使用适当的运算符可以轻松地将枚举转换为基础类型, 如下面的代码所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

枚举类型可以`sbyte`具有以下基础类型之一:、 `int32` `uint16` `uint32` `int16` `byte` 、、`uint64`、、 `uint16`、、、和`char`。 `int64` 枚举类型在 .NET Framework 中表示为从`System.Enum`继承的类型, 而后者又继承自。 `System.ValueType` 因此, 它们是位于堆栈上或内联在包含对象中的值类型, 并且基础类型的任何值都是枚举的有效值。 这在对枚举值进行模式匹配时很重要, 因为您必须提供一个模式来捕获未命名的值。

库中的`enum`函数可用于生成枚举值, 甚至是预定义的命名值之一之外的值。 F# `enum`函数如下所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

默认`enum`函数适用于类型`int32`。 因此, 它不能与具有其他基础类型的枚举类型一起使用。 请改用以下各项。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

此外, 枚举事例始终作为`public`发出。 这是为了使它们与C# .net 平台的其余部分保持一致。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [强制转换和转换](casting-and-conversions.md)
