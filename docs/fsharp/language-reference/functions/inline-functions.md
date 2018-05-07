---
title: 内联函数 (F#)
description: '了解如何使用直接集成到调用代码的 F # 内联函数。'
ms.date: 05/16/2016
ms.openlocfilehash: d265f9b4e828946c510bd8e84b14d5236ab511fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="inline-functions"></a>内联函数

*内联函数*是直接集成到调用代码的函数。


## <a name="using-inline-functions"></a>使用内联函数
当使用静态类型参数时，由类型参数化任何函数必须进行内联。 这可保证编译器可以解决这些类型参数。 当使用普通的泛型类型参数时，没有这样的限制。

以外启用将成员约束，内联函数可以帮助优化代码。 但是，内联函数的过度使用可能导致代码不太抵抗编译器优化和库函数的实现中的更改。 为此，应避免使用内联函数进行优化，除非你已尝试所有其他优化技术。 使函数或方法内联有时可以提高性能，但是，并非总是这种情况。 因此，你还应使用性能度量值以确定进行任何给定的函数内联实际上具有积极的影响。

`inline`修饰符可以应用于函数最高级别，在模块级别，或在类中的方法级别。

下面的代码示例说明了内联函数在顶级、 内联实例方法和内联静态方法。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a>内联函数和类型推理
是否存在`inline`影响类型推理。 这是因为内联函数可以具有静态解析的类型参数，而非内联函数不能。 下面的代码示例演示一种情况其中`inline`非常有用，因为正在使用具有一个静态解析的类型参数的函数`float`转换运算符。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

而无需`inline`修饰符，类型推理将强制使用特定的类型，在这种情况下函数`int`。 但与`inline`修饰符，该函数同样被推断为具有静态解析的类型参数。 与`inline`修饰符，类型推断为以下：

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

这意味着，该函数接受支持将转换为任何类型**float**。


## <a name="see-also"></a>请参阅
[函数](index.md)

[约束](../generics/constraints.md)

[静态解析的类型参数](../generics/statically-resolved-type-parameters.md)
