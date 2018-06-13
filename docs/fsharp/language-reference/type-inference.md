---
title: 类型推理 (F#)
description: '了解如何 F # 编译器推断出的值、 变量、 参数和返回值的类型。'
ms.date: 05/16/2016
ms.openlocfilehash: 93e1568ebe71436ad8f7119ac9d9628cdf58012a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563690"
---
# <a name="type-inference"></a>类型推断

本主题介绍如何 F # 编译器推断出的值、 变量、 参数和返回值的类型。

## <a name="type-inference-in-general"></a>一般情况下类型推理
类型推理思路是不需要指定除当编译器无法最终推断类型的 F # 构造的类型。 省略显式类型信息并不意味着 F # 是一种动态类型化的语言或 F # 中的值为弱类型化。 F # 是一种静态类型化的语言，这意味着编译器会在编译期间推导为每个构造的确切类型。 如果没有足够的信息供编译器推导出的每个构造类型，则必须在代码中某个位置添加显式类型批注通常提供附加类型信息。


## <a name="inference-of-parameter-and-return-types"></a>参数和返回类型推理
在参数列表中，无需指定每个参数的类型。 和尚未，F # 是一种静态类型化的语言，并因此每个值和表达式具有明确的类型在编译时。 对于不显式指定这些类型，编译器推断出基于上下文的类型。 如果类型不是否则指定，它将被推断为泛型。 如果代码不一致使用一个值，在这种方式中是否有没有一推断出的类型满足所有的用法的一个值，则编译器会报告错误。

函数返回类型由在函数中的最后一个表达式的类型确定。

例如，在下面的代码中，参数类型`a`和`b`和返回类型所有推断`int`因为文本`100`属于类型`int`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

你可以通过更改文本影响类型推理。 如果你进行`100``uint32`通过追加后缀`u`，类型的`a`， `b`，并返回的值会被推断为`uint32`。

也会影响使用的其他隐含限制的类型，例如函数和工作通过仅将特定类型的方法的构造类型推理。

此外，你可以将应用显式类型批注到函数或方法参数或变量在表达式中，如下面的示例中所示。 如果在不同的约束之间发生冲突，将发生错误。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

你还可显式指定函数的返回值通过提供类型批注，别忘了参数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

参数的对象类型，并且你想要使用的成员时常见的情况，其中类型批注是有用的参数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]
    
## <a name="automatic-generalization"></a>自动泛化
如果函数代码不依赖于参数的类型，编译器将认为是通用的参数。 这称为*自动泛化*，这可以在不增加复杂性的情况下编写泛型代码大有帮助。

例如，下面的函数将合并的元组的任何类型的两个参数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

类型推断为

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a>其他信息
F # 语言规范中的更详细地描述了类型推理。


## <a name="see-also"></a>请参阅
[自动泛化](generics/automatic-generalization.md)
