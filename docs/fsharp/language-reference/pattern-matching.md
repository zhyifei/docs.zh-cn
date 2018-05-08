---
title: 模式匹配 (F#)
description: '了解如何使用模式在 F # 中进行比较的逻辑结构的数据、 将数据分解为组成部分，或从数据中提取信息。'
ms.date: 05/16/2016
ms.openlocfilehash: 64f5b2534190552db71a67b30ece41bafed3d16e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="pattern-matching"></a>模式匹配

模式是用于转换输入的数据的规则。 它们整个都使用 F # 语言比较使用逻辑结构或结构的数据、 将数据分解为组成部分，或从以各种方式的数据中提取信息。


## <a name="remarks"></a>备注
在许多语言构造，如用于模式`match`表达式。 当处理函数的自变量使用它们`let`绑定、 lambda 表达式，并在与关联的异常处理`try...with`表达式。 有关详细信息，请参阅[匹配表达式](match-expressions.md)， [let 绑定](functions/let-bindings.md)， [Lambda 表达式：`fun`关键字](functions/lambda-expressions-the-fun-keyword.md)，和[异常： `try...with`表达式](exception-handling/the-try-with-expression.md)。

例如，在`match`表达式，*模式*是什么遵循管道符号。

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

每个模式充当转换输入以某种方式的规则。 在`match`表达式，每个模式将反过来检查以确定输入的数据是否与模式兼容。 如果找到匹配项，则执行的结果表达式。 如果未找到匹配项，则测试的下一个模式规则。 可选在*条件*一部分述[匹配表达式](match-expressions.md)。

支持的模式均显示下表中。 在运行时，输入测试针对每个表中列出的顺序中的以下模式和模式都是以递归方式应用，从第一次到最后一个要与出现在代码中，并从左到右的模式的每个行。

|名称|描述|示例|
|----|-----------|-------|
|常量模式|任何数字、 字符或字符串文本、 枚举常量或定义的文本标识符|`1.0`, `"test"`, `30`, `Color.Red`|
|标识符模式|可区分的联合、 异常标签或活动模式用例的用例值|`Some(x)`<br /><br />`Failure(msg)`|
|变量模式|*identifier*|`a`|
|`as` 模式|*模式*作为*标识符*|`(a, b) as tuple1`|
|或模式|*模式 1* &#124; *模式 2*|<code>([h] &#124; [h; _])</code>|
|和模式|*模式 1* &amp; *模式 2*|`(a, b) & (_, "test")`|
|Cons 模式|*标识符*::*列表标识符*|`h :: t`|
|列表模式|[*模式 1*;...;*模式 n* ]|`[ a; b; c ]`|
|数组模式|[&#124; *模式 1*;..;*模式 n* &#124;]|<code>[&#124; a; b; c &#124;]</code>|
|带括号模式|(*模式*)|`( a )`|
|元组模式|(*模式 1*，...，*模式 n* )|`( a, b )`|
|记录模式|{ *identifier1* = *模式 1*;...;*标识符 n* = *模式 n* }|`{ Name = name; }`|
|通配符模式|_|`_`|
|带有类型批注的模式|*模式*:*类型*|`a : int`|
|类型测试模式|:? *类型*[作为*标识符*]|`:? System.DateTime as dt`|
|Null 模式|null|`null`|

## <a name="constant-patterns"></a>常量模式
常量模式是数字、 字符和字符串文本、 枚举常量 （包括枚举类型名称）。 A`match`只有常量模式的表达式可以与其他语言中的 case 语句进行比较。 输入比较的文字值，并且如果这些值相等，则匹配模式。 文本的类型必须与输入的类型兼容。

下面的示例演示如何使用文本模式，并使用一个变量的模式和或模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

文本模式的另一个示例是基于枚举常量的模式。 当你使用枚举常量时，必须指定枚举类型名称。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a>标识符模式
如果该模式受窗体是有效的标识符的字符串，该标识符的形式将确定如何匹配的模式。 如果标识符的长度超过单个字符，并且开头大写字符，编译器会尝试对标识符模式进行匹配。 此模式的标识符可能是标记的文本属性、 可区分联合用例、 异常标识符或活动模式用例的值。 如果不找到任何匹配的标识符，则匹配失败和下一步模式规则，变量的模式中，输入与进行比较。

可区分联合模式可以是简单的名为情况下，或者它们可具有一个值或包含多个值的元组。 如果没有一个值，则必须指定值的标识符。 对于一个元组，必须提供具有元组的每个元素的标识符或具有一个的字段名称的标识符的元组模式或多个命名联合的字段。 请参阅本部分中用于示例的代码示例。

`option`类型是具有两种情况下，可区分的联合`Some`和`None`。 一种情况下 (`Some`) 具有一个值，而另 (`None`) 是只是命名的用例。 因此，`Some`需要具有与关联的值的变量`Some`分大小写，但`None`必须单独出现。 在下面的代码中，变量`var1`都提供了获得的匹配值`Some`用例。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

在下面的示例中，`PersonName`可区分的联合包含混合的字符串和字符表示可能形式的名称。 可区分联合的情形是`FirstOnly`， `LastOnly`，和`FirstLast`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

对于已命名的字段的可区分联合，你使用等号 （=） 提取命名字段的值。 例如，考虑如下所示的声明的可区分的联合。

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

可以使用模式匹配的表达式中的命名的字段，如下所示。

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

使用命名的字段是可选的因此在前面的示例中，同时`Circle(r)`和`Circle(radius = r)`具有相同的效果。

当指定多个字段时，请使用分号 （;） 作为分隔符。

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

活动模式，可定义更复杂的自定义模式匹配。 有关活动模式的详细信息，请参阅[活动模式](active-patterns.md)。

异常处理程序的上下文中匹配的模式中所用顺序标识符是一个例外的情况。 有关异常处理中的模式匹配的信息，请参阅[异常：`try...with`表达式](exception-handling/the-try-with-expression.md)。


## <a name="variable-patterns"></a>变量模式
变量模式将与变量名称，然后在右侧的执行表达式中使用该名称匹配的值分配`->`符号。 变量模式单独匹配任何输入，但变量模式通常出现在其他模式，因此启用更复杂的结构，例如，元组和阵列可以分解为变量。

下面的示例演示在元组模式变量模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a>as 模式
`as`模式是一种模式具有`as`子句附加到它。 `as`子句将匹配的值绑定到一个名称，可以用于在执行表达式的`match`表达式，或在此模式中的使用位置的情况下`let`绑定，名称将添加为一种绑定到本地作用域。

下面的示例使用`as`模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a>或模式
当输入的数据可匹配多个模式，而你想要因此执行相同的代码，则使用 OR 模式。 OR 模式的两侧的类型必须兼容。

下面的示例演示 OR 模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a>和模式
AND 模式要求输入匹配两种模式。 AND 模式的两侧的类型必须兼容。

以下示例类似，`detectZeroTuple`中所示[元组模式](https://msdn.microsoft.com/library/#tuple)更高版本中本主题中，但此处这两个部分`var1`和`var2`通过使用 AND 模式获得作为值。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a>Cons 模式
Cons 模式用于将列表分解为第一个元素，*头*，并包含剩余元素的列表*结尾*。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a>列表模式
列表模式使列表以分解成的元素数。 列表模式本身可以匹配的特定数量的元素组成的列表。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a>数组模式
数组模式与列表模式相似，并且可以用于将分解特定长度的数组。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a>带括号模式
可以围绕模式以实现所需的关联性分组括号。 在下面的示例中，使用括号来控制 AND 模式和 cons 模式之间的关联性。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a>元组模式
元组模式与输入元组形式匹配并启用要进行分解为其构成元素，通过使用模式匹配的元组中每个位置的变量的元组。

下面的示例演示元组模式，并使用文本模式、 变量模式和通配符模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a>记录模式
记录模式用于将分解记录提取字段的值。 不需要引用所有字段的记录; 该记录模式任何省略的字段只需不参与匹配，然后将不会提取。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a>通配符模式
通配符模式由下划线 (`_`) 字符并匹配任何输入，就像的变量的模式一样，只不过输入将被丢弃而不是分配给变量。 通配符模式通常用于在其他模式作为占位符且无需在右侧的表达式的值`->`符号。 也经常在模式的列表的末尾使用通配符模式匹配任何不匹配的输入。 在本主题中的许多代码示例演示了通配符模式。 请参阅前面的代码示例。


## <a name="patterns-that-have-type-annotations"></a>具有类型批注的模式
模式可以有类型批注。 这些行为类似于其他类型批注和指导推理等其他类型批注。 类型批注中模式要求使用括号。 下面的代码演示具有的类型批注的模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a>类型测试模式
类型测试模式用于匹配针对一种类型的输入。 如果输入的类型与匹配的项 （或派生的类型的） 都会成功在模式中，匹配指定的类型。

下面的示例演示类型测试模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a>Null 模式
Null 模式匹配时你正在使用允许 null 值的类型，可能出现的 null 值。 与.NET Framework 代码交互操作时，经常使用 null 模式。 例如，.NET API 的返回值可能的输入`match`表达式。 你可以控制程序流基于是否返回值为 null，并且也将在返回的值的其他特征。 Null 模式可用于防止 null 值传播到你的程序的其余部分。

下面的示例使用 null 模式和变量的模式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a>请参阅
[match 表达式](match-expressions.md)

[活动模式](active-patterns.md)

[F# 语言参考](index.md)
