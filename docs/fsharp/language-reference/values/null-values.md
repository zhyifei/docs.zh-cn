---
title: Null 值 (F#)
description: '了解如何在 F # 编程语言中使用 null 值。'
ms.date: 05/16/2016
ms.openlocfilehash: 8751ac402c43ddb07fb62e08b6c6d5403cbe9acc
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43787891"
---
# <a name="null-values"></a>Null 值

本主题介绍如何在 F # 中使用 null 值。

## <a name="null-value"></a>Null 值

Null 值不正常情况下用于在 F # 中的值或变量。 但是，null 将显示异常值在某些情况下。 如果 F # 中定义了一个类型，null 不允许作为常规值除非[AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f)特性应用于类型。 如果某些其他.NET 语言中定义一个类型，则为 null，则是一个可能的值，并在 F # 代码进行互操作与此类类型时, 可能会遇到 null 值。

对于 F # 中定义的从 F # 使用严格的类型，创建一个 null 值，直接使用 F # 库的唯一方法是使用[Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977)或[Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)。 但是，对于 F # 类型的属性可以从使用其他.NET 语言，或如果未在 F # 中，如.NET Framework 编写的 API 与使用该类型可以出现 null 值。

可以使用`option`中 F # 时可能会与另一种.NET 语言中可能的 null 值使用引用变量的类型。 而不是 null，使用 F #`option`类型，使用选项值`None`如果没有对象。 使用选项值`Some(obj)`与对象`obj`对象时。 有关详细信息，请参阅[选项](../options.md)。

`null`关键字是在 F # 语言中，有效的关键字，您必须使用.NET Framework Api 或其他用其他.NET 语言编写的 Api 时使用它。 两种情况中，您可能需要一个 null 值是和解释的返回值或输出参数从.NET 方法调用时调用.NET API 和作为参数传递 null 值。

要将 null 值传递给.NET 方法，只需使用`null`调用代码中的关键字。 下面的代码示例阐释了这一点。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

若要解释从.NET 方法获取一个 null 值，使用模式匹配，如果你知道如何操作。 下面的代码示例演示如何使用模式匹配来解释从返回的 null 值`ReadLine`当其尝试读取超出输入流的末尾。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

此外可以在其他方面，例如在使用生成的 F # 类型的 null 值`Array.zeroCreate`，它调用`Unchecked.defaultof`。 您必须要注意此类的代码来跟封装的 null 值。 仅用于 F # 库，不需要检查每个函数中的 null 值。 如果你正在编写用于与其他.NET 语言的互操作的库，您可能需要添加 null 检查输入参数，并引发`ArgumentNullException`，就像您在 C# 或 Visual Basic 代码中执行操作。

下面的代码可用于检查任意值是否为 null。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>请参阅

- [值](index.md)
- [match 表达式](../match-expressions.md)
