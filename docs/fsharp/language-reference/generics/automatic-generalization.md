---
title: "自动泛化 (F#)"
description: "了解如何 F # 自动泛化的自变量和类型的函数，使它们工作的多个类型在可能的情况。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 14a3554c-3fad-4eba-a93d-8ba07d1245b4
ms.openlocfilehash: d60831084cef76ce29f64322362b4920520f71d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="automatic-generalization"></a>自动泛化

F # 使用类型推理来评估现有的函数和表达式的类型。 本主题介绍如何 F # 自动泛化的自变量和类型的函数，使它们可以将其工作的多个类型时这是可行的。


## <a name="automatic-generalization"></a>自动泛化
F # 编译器上一个函数，, 执行类型推理时确定的给定的参数是否可以为泛型。 编译器将检查每个参数，并确定该函数是否具有该参数的特定类型的依赖关系。 如果不存在，推断的类型为泛型。

下面的代码示例阐释了编译器推断出是通用的函数。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

类型将被推断`'a -> 'a -> 'a`。

该类型指示这是一个函数，它采用相同的未知类型的两个参数并返回该同一类型的值。 以前的函数可以是原因之一而泛型是： 大于-运算符 (`>`) 本身是泛型。 较大的-不是运算符具有签名`'a -> 'a -> bool`。 并非所有运算符都是泛型，并且如果在函数中的代码使用与非泛型函数或运算符的参数类型，该参数类型不能通用。

因为`max`是泛型，它可与类型如`int`， `float`，依此类推，如下面的示例中所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

但是，两个自变量必须是类型的相同。 该签名是`'a -> 'a -> 'a`，而不`'a -> 'b -> 'a`。 因此，下面的代码产生一个错误，因为类型不匹配。

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

`max`函数也适用于支持大于任何类型的运算符。 因此，你可能还上使用它一个字符串，如下面的代码中所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]
    
## <a name="value-restriction"></a>值限制
编译器执行自动泛化，只能在具有显式参数的完整函数定义上和简单不可变的值。

这意味着，编译器将发出错误，如果您尝试编译未充分约束为特定类型，但也不可泛化的代码。 此问题的错误消息是指此限制的值作为自动泛化*值限制*。

通常，当你想构造来为泛型，但编译器没有足够的信息来通用化，或者当你无意中忽略足够非泛型构造中的类型信息时，会发生值限制错误。 值限制错误的解决方案是提供更明确的信息，以便更全面地约束类型推理问题，通过以下方式之一：


- 限制要通过将显式类型批注添加到的值或参数非泛型的类型。

- 如果问题使用不可泛化构造来定义泛型功能，例如函数组合或未完整应用的扩充的函数自变量，请尝试重写为普通函数定义的函数。

- 如果问题是太复杂，无法泛化，使它成为函数通过添加额外的未使用参数的表达式。

- 添加显式的泛型类型参数。 很少使用此选项。

- 下面的代码示例说明了每种方案。

案例 1： 太复杂的表达式。 在此示例中，列表`counter`旨在`int option ref`，但它未定义为一个简单的不可变值。

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

案例 2： 使用不可泛化构造来定义的泛型函数。 在此示例中，则构造是不可泛化，因为它涉及部分应用函数自变量。

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

情况 3： 添加额外的未使用参数。 此表达式不是简单的泛化，因为编译器会发出值限制错误。

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

案例 4： 添加的类型参数。

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

在最后一种情况中的值将成为类型函数，可用于创建例如在如下所示的许多不同类型，值：

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a>另请参阅
[类型推断](../type-inference.md)

[泛型](index.md)

[静态解析的类型参数](statically-resolved-type-parameters.md)

[约束](constraints.md)

