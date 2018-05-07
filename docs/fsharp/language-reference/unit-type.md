---
title: unit 类型 (F#)
description: '了解如何的 F # 单位类型通常用来保存其中一个值时所需的语言语法需要或所需的任何值的位置。'
ms.date: 05/16/2016
ms.openlocfilehash: fdd6b62f9d5c6d73407d5326c7d1f66d55780682
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="unit-type"></a>unit 类型

`unit`类型是类型，该值指示一个特定值; 如果没有`unit`类型具有只能是单个值，当没有其他值存在，或者需要时充当占位符。


## <a name="syntax"></a>语法

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>备注
每个 F # 表达式的计算结果必须为一个值。 不会生成有意义，类型的值的表达式`unit`使用。 `unit`类型类似于`void`C# 和 c + + 等语言的类型。

`unit`类型具有单个值，该值指定标记`()`。

值`unit`类型通常使用 F # 编程来保留位置，而值所需的语言语法，但需要或所需的任何值中。 一个示例可能是的返回值`printf`函数。 因为的重要操作`printf`操作发生在函数中，该函数不需要返回实际值。 因此，返回值的类型是`unit`。

某些构造应`unit`值。 例如，`do`绑定或所有代码模块的顶层是计算结果应为`unit`值。 编译器将报告警告时`do`绑定或模块的顶层的代码生成的结果以外`unit`未使用，如下面的示例中所示的值。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

此警告是函数编程; 的特征它不会显示在其他.NET 编程语言。 在纯粹的函数的程序中，函数不具有任何方面的副作用，最终的返回值是函数调用的唯一结果。 因此，当结果将被忽略，它是可能的编程错误。 虽然 F # 不是纯粹的函数编程语言，所以最好遵循函数编程的方式，只要有可能。

## <a name="see-also"></a>请参阅
[基元](primitive-types.md)

[F# 语言参考](index.md)
