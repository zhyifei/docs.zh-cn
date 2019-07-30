---
title: Null 值
description: 了解如何在F#编程语言中使用 null 值。
ms.date: 03/22/2019
ms.openlocfilehash: 2038c0a461fec9884c51edd50c3c9f336104e30e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630814"
---
# <a name="null-values"></a>Null 值

本主题介绍如何在中F#使用 null 值。

## <a name="null-value"></a>Null 值

F#对于值或变量, 通常不使用 null 值。 但是, 在某些情况下, null 显示为异常值。 如果在中F#定义了类型, 则不允许将 null 作为常规值, 除非将[AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f)属性应用于该类型。 如果类型是使用其他某种 .NET 语言定义的, 则 null 是可能的值, 当您与此类类型进行互操作F#时, 您的代码可能会遇到 null 值。

对于在F#中定义并严格使用的类型F#, F#使用库直接创建 null 值的唯一方法是使用[unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977)或[array.zerocreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)。 但是, 对于从F#其他 .net 语言中使用的类型, 或者如果使用的是不是用编写F#的 API (如 .NET Framework), 则可能会出现 null 值。

当你可能在`option`其他 .net F#语言中使用具有可能为 null 值的引用变量时, 可以使用中的类型。 如果没有对象, 则可以F# `option`使用选项值`None` (而不是 null)。 当有对象时, `Some(obj)`可将选项`obj`值用于对象。 有关详细信息，请参阅[选项](../options.md)。 `null`请注意, 如果`Some x` `x`的为`null`, 则仍可将值打包到选项中。 因此, 在值为`None` `null`时使用非常重要。

关键字是F#语言中的有效关键字, 当你使用以其他 .net 语言编写的 .NET Framework api 或其他 api 时, 你必须使用它。 `null` 在以下两种情况下, 您可能需要 null 值: 调用 .NET API 并将 null 值作为参数传递, 以及从 .NET 方法调用解释返回值或输出参数。

若要将 null 值传递到 .net 方法, 只需在`null`调用代码中使用关键字。 下面的代码示例阐释了这一点。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

若要解释从 .NET 方法获取的 null 值, 请在可以时使用模式匹配。 下面的代码示例演示如何使用模式匹配来解释在其尝试读取超出输入流末尾`ReadLine`时返回的 null 值。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

还可以通过F#其他方式生成类型为 Null 的值, 例如在使用时, `Array.zeroCreate`将调用。 `Unchecked.defaultof` 必须谨慎处理此类代码, 使封装的值保持为空值。 在仅用于的F#库中, 无需在每个函数中检查 null 值。 如果要编写与其他 .net 语言的互操作性的库, 则可能必须添加对 null 输入参数的检查并引发`ArgumentNullException`, 就像在或 Visual Basic C#代码中一样。

可以使用以下代码检查任意值是否为 null。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>请参阅

- [值](index.md)
- [match 表达式](../match-expressions.md)
