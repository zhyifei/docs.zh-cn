---
title: 作为一类值的函数 (F#)
description: '了解如何提升到 F # 编程语言中的第一类状态的函数。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 7db99aa23211ce4a7af5cdfcc809017fafb1d5a1
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="functions-as-first-class-values"></a>作为一类值的函数

函数编程语言的定义特征是提升到第一类状态的函数。 你应能够执行的函数具有的任何你可以使用其他内置类型的值执行的操作和能够完成此操作可比较程度的工作量。

典型的度量值的第一类的状态如下所示：

- 你可以将函数绑定到标识符？ 也就是说，你能大概给它们名称？

- 可以存储函数中数据结构，如在列表中？

- 你可以向函数传递作为函数调用中的参数？

- 你可以从一个函数调用返回一个函数？

最后两个度量值定义所谓的*更高序位操作*或*高阶函数*。 高阶函数接受作为自变量的函数，并返回函数作为函数调用的值。 这些操作支持这种作为映射函数和函数的组合的函数编程。


## <a name="give-the-value-a-name"></a>为指定名称的值

如果一个函数是一类值，你必须能够将其命名，就像可以命名整数、 字符串和其他内置类型。 这是在绑定到的值的标识符函数编程语言中称为。 F # 使用[`let`绑定](../language-reference/functions/let-bindings.md)要绑定到值的名称： `let <identifier> = <value>`。 下面的代码演示了两个示例。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet20.fs)]

可以将名称轻松地为函数。 下面的示例定义一个名为函数`squareIt`由绑定标识符`squareIt`到[lambda 表达式](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`。 函数`squareIt`具有一个参数、 `n`，并返回该参数的平方。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

F # 提供了以下更简洁的语法以实现使用较少键入相同的结果。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet22.fs)]

主要下面的示例中使用的第一个样式， `let <function-name> = <lambda-expression>`，以强调函数的声明和其他类型的值的声明之间的相似之处。 但是，还可以使用简洁的语法编写所有命名的函数。 用这两种方式编写的一些示例。


## <a name="store-the-value-in-a-data-structure"></a>应用商店中的数据结构的值

第一类值可以存储在数据结构。 下面的代码演示将值存储在列表和元组中的示例。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet23.fs)]

若要验证存储元组中的函数名称中的事实未计算结果为一个函数，下面的示例使用`fst`和`snd`运算符以从元组中提取的第一个和第二个元素`funAndArgTuple`。 元组中的第一个元素是`squareIt`和第二个元素是`num`。 标识符`num`绑定中前一示例中为整数 10 的有效参数`squareIt`函数。 第二个表达式适用于此元组中的第二个元素的元组中的第一个元素： `squareIt num`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet24.fs)]

同样，就像标识符`num`和整数 10 可以互换使用，因此可以标识符`squareIt`和 lambda 表达式`fun n -> n * n`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet25.fs)]
    
## <a name="pass-the-value-as-an-argument"></a>将值作为参数传递

如果值有一种语言中的第一类的状态，你可以它作为参数传递给函数。 例如，很常见整型和字符串作为参数传递。 下面的代码演示整数和 F # 中作为参数传递的字符串。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet26.fs)]

如果函数的第一类的状态，你必须能够将它们作为参数传递的方式相同。 请记住，这是高阶函数的第一个特性。

在下面的示例中，函数`applyIt`具有两个参数，`op`和`arg`。 如果你发送的函数中，具有一个参数的`op`和到函数的相应自变量`arg`，该函数返回的结果应用`op`到`arg`。 在以下示例中，该函数参数，整数自变量会发送相同的方式，通过使用其名称。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet27.fs)]

能够将一个函数作为自变量发送到另一个函数是常见抽象函数编程语言，如映射或筛选器操作的基础。 映射操作，例如，是捕获共享单步执行列表、 于每个元素执行操作，然后返回结果的列表的函数的计算，高阶函数。 你可能想要递增的整数，列表中每个元素方形每个元素，或以将转换为大写的字符串列表中每个元素。 计算的易出错的一部分是通过列表该步骤的递归过程和生成要返回的结果的列表。 映射函数中捕获该部分。 你只需编写特定的应用程序是你想要单独应用于每个列表元素的函数 （添加、 相乘、 更改大小写）。 函数作为自变量映射函数中，只需将作为发送给`squareIt`发送到`applyIt`在前面的示例。

F # 提供的大多数集合类型，包括映射方法[列出](../language-reference/lists.md)，[数组](../language-reference/arrays.md)，和[序列](../language-reference/sequences.md)。 下面的示例使用列表。 语法是`List.map <the function> <the list>`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet28.fs)]

有关详细信息，请参阅[列出](../language-reference/lists.md)。

## <a name="return-the-value-from-a-function-call"></a>从函数调用返回值

最后，如果函数具有一种语言中的第一类的状态，你必须能够将其返回作为值的函数调用，就像返回其他类型，如整数和字符串。

下面的函数调用返回整数，并将其显示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet29.fs)]

以下函数调用返回的字符串。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet30.fs)]

内联声明，在以下函数调用返回一个布尔值。 显示的值是`True`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet31.fs)]

返回一个函数作为函数调用的值的功能是高阶函数的第二个特征。 在下面的示例中，`checkFor`定义为采用一个自变量的函数`item`，并返回一个新函数作为其值。 返回函数作为其自变量列表`lst`，并搜索`item`中`lst`。 如果`item`不存在，该函数将返回`true`。 如果`item`不存在，该函数将返回`false`。 下面的代码如下所示上一节中，使用提供的列表函数[List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8)，以在列表中搜索。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

下面的代码使用`checkFor`创建采用一个自变量、 列表和 7 搜索列表中的新函数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet33.fs)]

下面的示例使用 F # 中的函数的第一类状态来声明函数， `compose`，返回两个函数自变量的组合。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet34.fs)]
    
>[!NOTE]
有关甚至更短的版本，请参阅以下部分中，"扩充函数。"


下面的代码将两个函数作为自变量发送`compose`，这两个的这需要相同类型的单个参数。 返回值是一个新函数，则两个函数参数的组合。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet35.fs)]
    
>[!NOTE] 
F # 提供了两个运算符，`<<`和`>>`，它们构成函数。 例如，`let squareAndDouble2 = doubleIt << squareIt`等效于`let squareAndDouble = compose doubleIt squareIt`在前面的示例。

作为函数调用值返回函数的下面的示例创建一个简单的猜测游戏。 若要创建一个游戏，调用`makeGame`值与你希望让人猜出为传入的`target`。 函数的返回值`makeGame`是采用一个自变量 （猜测） 和报告猜测是正确的函数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet36.fs)]

下面的代码调用`makeGame`，将值发送`7`为`target`。 标识符`playGame`绑定到返回的 lambda 表达式。 因此，`playGame`是采用作为它的一个参数值为一个函数`guess`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet37.fs)]
    
## <a name="curried-functions"></a>扩充的函数

可以通过利用的隐式更确切地编写的许多上一节中示例*扩充*F # 函数声明中。 扩充是一个转换具有多个参数为一系列的嵌入式函数，其中每个具有单个参数的函数的过程。 在 F # 中，都会被扩充具有多个参数的函数。 例如，`compose`从上一节可以编写以下的简洁样式，带有三个参数中所示。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet38.fs)]

但是，结果是返回反过来返回的一个参数，另一个函数的一个参数的函数中所示的一个参数的函数`compose4curried`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet39.fs)]

你可以访问此函数在几种方法中。 每个以下的示例返回并显示 18。 你可以替换`compose4`与`compose4curried`示例中。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet40.fs)]

若要验证，该函数仍适用像以前一样，重试原始测试用例。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet41.fs)]
    
>[!NOTE] 
你可以限制扩充括在元组中的参数。 有关详细信息，请参阅"参数模式"[参数和自变量](../language-reference/parameters-and-arguments.md)。

下面的示例使用隐式扩充要写入的简短版本`makeGame`。 方法的详细信息`makeGame`构造并返回`game`函数不太明确按以下格式，但你可以通过使用原始的结果是相同的测试用例来验证。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet42.fs)]

有关扩充的详细信息，请参见"部分应用程序的参数"中[函数](../language-reference/functions/index.md)。


## <a name="identifier-and-function-definition-are-interchangeable"></a>标识符和函数定义是可互换
变量名称`num`在前面示例的计算结果为 10 的整数，它也就不足为奇，因为`num`是有效，10 也是有效的。 这同样适用函数标识符及其值的： 可以位置可以使用函数的名称，使用绑定到 lambda 表达式。

下面的示例定义`Boolean`函数调用`isNegative`，然后互换使用的函数名称和函数的定义。 接下来三个示例都返回并显示`False`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet43.fs)]

若要进一步它一个步骤，将替换值的`applyIt`绑定到`applyIt`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a>函数是在 F # 中的第一类值 #

前几节中的示例演示 F # 中的函数满足正在 F # 中的一类值的条件：

- 你可以绑定到函数定义的标识符。
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

- 可以将函数存储的数据结构。
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet45.fs)]

- 可以将函数作为参数传递。
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet46.fs)]

- 你可以返回函数作为函数调用的值。
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

有关 F # 的详细信息，请参阅[F # 语言参考](../language-reference/index.md)。

## <a name="example"></a>示例

### <a name="description"></a>描述

下面的代码包含本主题中的所有示例。

### <a name="code"></a>代码

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet47.fs)]
    
## <a name="see-also"></a>请参阅

[列表](../language-reference/lists.md)

[元组](../language-reference/tuples.md)

[函数](../language-reference/functions/index.md)

[`let` 绑定](../language-reference/functions/let-bindings.md)

[Lambda 表达式：`fun`关键字](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
