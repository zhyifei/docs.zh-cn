---
title: Null 值 (F#)
description: '了解如何在 F # 编程语言中使用 null 值。'
ms.date: 05/16/2016
ms.openlocfilehash: 7367b35cb6e910f926179e52992d5533e5cdda0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="null-values"></a>Null 值

本主题介绍如何在 F # 中使用 null 值。


## <a name="null-value"></a>Null 值
Null 值不通常用于在 F # 中的值或变量。 但是，在某些情况下异常值都会显示 null。 如果在 F # 中定义了类型，null 不允许作为正则值除非[AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f)属性应用于该类型。 如果类型在定义某些其他.NET 语言中，null，则是一个可能的值，并且时进行互操作与此类类型，F # 代码可能会遇到 null 值。

对于在 F # 中定义的从 F # 使用严格的类型，创建 null 值直接使用 F # 库的唯一方法是使用[Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977)或[Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)。 但是，F # 类型，用于从其他.NET 语言，或如果你正在使用一个 API，则不会写在 F # 中，如.NET Framework 中，该类型可以出现 null 值。

你可以使用`option`F # 时可能会与其他.NET 语言中的可能的 null 值使用引用变量中的类型。 而不是 null，F #`option`类型，使用选项值`None`如果没有对象。 使用选项值`Some(obj)`的对象`obj`对象时。 有关详细信息，请参阅[选项](../options.md)。

`null`关键字是有效的关键字在 F # 语言中，并且你必须在使用.NET Framework Api 或其他.NET 语言编写的其他 Api 时使用它。 中，您可能需要一个 null 值的两种情况是当您调用.NET API 和传递 null 值作为参数，并且在解释返回值或从.NET 方法调用输出参数。

若要将 null 值传递给.NET 方法，只需使用`null`调用代码中的关键字。 下面的代码示例阐释了这一点。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

若要解释从.NET 方法获得一个 null 值，使用模式匹配，如果你知道如何操作。 下面的代码示例演示如何使用模式匹配来解释从返回的 null 值`ReadLine`时试图读取输入流的末尾。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

也可以在其他方面，例如，当你使用生成的 F # 类型的 null 值`Array.zeroCreate`，哪些调用`Unchecked.defaultof`。 必须小心使用此类代码保留封装空值。 在库仅用于 F # 中，无需检查每个函数中的 null 值。 如果你正在编写用于与其他.NET 语言间的互操作的库，你可能需要添加针对 null 检查输入参数和引发`ArgumentNullException`，就像在 C# 或 Visual Basic 代码中。

下面的代码可用于检查任意值是否为 null。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>请参阅
[值](index.md)

[match 表达式](../match-expressions.md)
