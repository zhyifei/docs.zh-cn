---
title: unit 类型
description: 了解如何F#单位类型通常用来保存其中一个值所需的语言语法需要或所需的任何值时的位置。
ms.date: 05/16/2016
ms.openlocfilehash: d515e19489bfa7de6f17194fd74176cfa0bcd7c9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645124"
---
# <a name="unit-type"></a>unit 类型

`unit`类型是一种类型，表示一个特定值; 如果不存在`unit`类型具有只能是单个值，它将作为一个占位符，存在或需要任何其他值时。

## <a name="syntax"></a>语法

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>备注

每个F#表达式的计算结果必须为一个值。 不会生成所需类型的值的表达式`unit`使用。 `unit`类与类似`void`语言中键入类似于C#和C++。

`unit`类型具有一个值，并由该令牌指示该值`()`。

值`unit`类型，经常在F#编程来保留位置： 一个值所必需的语言语法，但在需要或所需的任何值。 一个示例可能是返回值的`printf`函数。 因为的重要操作`printf`操作发生在函数中，该函数没有返回实际值。 因此，返回值属于类型`unit`。

某些构造应`unit`值。 例如，`do`绑定或任何代码模块的顶层是计算结果应为`unit`值。 编译器将报告警告时`do`绑定或代码模块的顶层生成的结果，而不`unit`未使用，如下面的示例中所示的值。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

此警告是函数式编程; 的特征它不会出现在其他.NET 编程语言。 在纯粹的函数的程序中，函数不具有任何方面的副作用，最终的返回值是唯一的函数调用的结果。 因此，当结果将被忽略，它是可能的编程错误。 尽管F#不是纯粹的函数编程语言，它是遵循函数编程的方式应尽可能的好办法。

## <a name="see-also"></a>请参阅

- [Primitive](primitive-types.md)
- [F# 语言参考](index.md)
