---
title: 枚举 (F#)
description: '了解如何使用 F # 枚举代替文本以使代码更具可读性且更容易维护。'
ms.date: 05/16/2016
ms.openlocfilehash: 00faf6e2ad08a7b232a8ae35aa0f7deb1ba3e76a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562987"
---
# <a name="enumerations"></a>枚举

*枚举*，也称为*枚举*、 都是整型其中将标签分配给值的子集。 可以使用它们来代替文本，使代码更具可读性且更易维护。


## <a name="syntax"></a>语法

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>备注
枚举看起来非常类似于具有简单值的可区分联合只不过可以指定的值。 这些值通常是从 0 或 1，开始的整数或整数，用于表示位位置。 如果枚举用于表示位位置，你还应使用[标志](xref:System.FlagsAttribute)属性。

枚举的基础类型由使用时，该文本，以便，例如，你可以使用文本替换为后缀，例如`1u`， `2u`，依此类推，对于无符号整数 (`uint32`) 类型。

当引用已命名的值时，你必须使用枚举类型本身的名称用作限定符，即`enum-name.value1`，而不是`value1`。 此行为不同于可区分联合。 这是因为枚举始终具有[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)属性。

下面的代码演示的声明和用法的枚举。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

你可以轻松地将转换枚举的基础类型通过使用适当的运算符，如下面的代码中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

枚举的类型可以具有以下基础类型之一： `sbyte`， `byte`， `int16`， `uint16`， `int32`， `uint32`， `int64`， `uint16`， `uint64`，和`char`。 枚举类型.NET Framework 中表示为从继承的类型`System.Enum`，其反过来继承自`System.ValueType`。 因此，它们就是位于堆栈或在包含的对象中，内联的值类型和基础类型的任何值是有效的值的枚举。 这很重要时模式匹配枚举值，因为你必须提供一种模式，捕获未命名的值。

`enum` F # 库中的函数可用来生成一个枚举值，即使其中一个的预定义以外的值命名值。 你使用`enum`函数，如下所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

默认值`enum`函数配合类型`int32`。 因此，它不用于具有其他基础类型的枚举类型。 相反，使用以下命令。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]
    
## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

[强制转换和转换](casting-and-conversions.md)
