---
title: "代码引用 (F#)"
description: "了解有关 F # 代码引用，使你可以生成并以编程方式使用 F # 的代码表达式的语言功能。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4559e659-2b04-48bd-8a0b-8527920eec95
ms.openlocfilehash: f7a08013bc6487b570a62576bb01ca2dd65ce8b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="code-quotations"></a>代码引用

> [!NOTE]
API 参考链接将转至 MSDN。  Docs.microsoft.com API 参考尚未完成。

本主题介绍*代码引用*，使你可以生成并以编程方式使用 F # 的代码表达式的语言功能。 此功能允许你生成一个表示 F # 代码的抽象语法树。 可以然后遍历抽象语法树，并为其根据你的应用程序的需要处理。 例如，可以使用树来生成 F # 代码，或者某些其他语言生成代码。


## <a name="quoted-expressions"></a>用引号括起来的表达式
A*带引号的表达式*是在代码中分隔它未编译的程序中，一部分的方式，但会编译成一个对象，表示 F # 表达式的 F # 表达式。 你可以将标记的表达式用引号括起来的两种方式之一： 使用类型信息或没有类型信息。 如果你想要包括类型信息，则使用符号`<@`和`@>`来分隔用引号括起来的表达式。 如果不需要类型信息，则使用符号`<@@`和`@@>`。 下面的代码演示了类型化和非类型化的引用。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

大型表达式树的遍历是不包括类型信息的情况下更快。 使用类型化的符号引起来的表达式的结果类型是`Expr<'T>`，其中类型参数都有由 F # 编译器的类型推理算法确定表达式的类型。 当使用不包含类型信息的代码引用时，用引号括起来的表达式的类型为非泛型类型[Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65)。 你可以调用[Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2)上类型化的属性`Expr`类来获取的非类型化`Expr`对象。

有大量的静态方法可让你可以生成 F # 表达式对象以编程方式在`Expr`类而不使用带引号的表达式。

请注意，代码引号必须包含一个完整的表达式。 有关`let`绑定，例如，你需要定义的绑定的名称和其他表达式使用的绑定。 在详细语法中，这是一个表达式后面`in`关键字。 在顶级模块中，这是仅在模块中下, 一个表达式，但在引号中，它是明确要求。

因此，下面的表达式不是有效的。

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

但是，以下表达式均无效。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

若要使用代码引用，必须添加导入声明 (使用`open`关键字)，这将打开[Microsoft.FSharp.Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2)命名空间。

F # PowerPack 评估和执行 F # 表达式对象提供支持。


## <a name="expr-type"></a>Expr 类型
实例`Expr`类型表示的 F # 表达式。 泛型和非泛型`Expr`类型均记录在 F # 库文档。 有关详细信息，请参阅[Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d)和[Quotations.Expr 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d)。


## <a name="splicing-operators"></a>拼接运算符
将接合允许用户将组合使用您已创建了以编程方式或从另一个代码引用的表达式的文本的代码引用。 `%`和`%%`运算符使您能够将 F # 表达式对象添加到代码引号。 你使用`%`运算符将类型化的表达式对象插入的类型化的引用; 你可以使用`%%`运算符以将非类型化的表达式对象插入非类型化的引号。 这两个运算符是一元前缀运算符。 因此如果`expr`类型的非类型化表达式`Expr`，下面的代码是有效。

```fsharp
<@@ 1 + %%expr @@>
```

如果`expr`是类型的类型化的引用`Expr<int>`，下面的代码是有效。

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>示例

### <a name="description"></a>描述
下面的示例演示如何使用 F # 代码放入到表达式对象，然后打印表示表达式的 F # 代码的代码引用。 函数`println`定义包含递归函数`print`显示 F # 表达式对象 (类型的`Expr`) 中的友好的格式。 有几个活动模式中的[Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4)和[Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd)模块，它们可以用于分析表达式对象。 此示例不包括在 F # 表达式中可能会出现的所有可能的模式。 任何无法识别的模式将触发与通配符模式匹配的项 (`_`) 并通过使用呈现`ToString`方法，而后者上`Expr`键入，让您知道要将添加到你匹配表达式的活动模式。


### <a name="code"></a>代码
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet601.fs)]
    
### <a name="output"></a>输出

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>示例

### <a name="description"></a>描述
你还可以使用中的三个活动模式[ExprShape 模块](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de)遍历较少活动模式与表达式树。 当你想要遍历树，但不是需要其中大部分节点中的所有信息时，这些活动模式很有用。 当你使用这些模式时，任何 F # 表达式匹配的以下三种模式之一：`ShapeVar`如果表达式是一个变量，`ShapeLambda`如果表达式是 lambda 表达式，或`ShapeCombination`如果表达式为任何其他内容。 如果通过使用如前面的代码示例所示的活动模式遍历表达式树，你需要使用更多的模式来处理所有可能的 F # 表达式类型，并且你的代码将更复杂。 有关详细信息，请参阅[ExprShape.ShapeVar &#124;ShapeLambda &#124;ShapeCombination 活动模式](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d)。

下面的代码示例可以用作更为复杂的遍历基础。 在此代码中，为包含函数调用的表达式创建表达式树`add`。 [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d)活动模式用于检测到任何调用`add`的表达式树中。 此活动的模式将分配到调用的自变量`exprList`值。 在这种情况下，有只有两个，因此这些拉出和的自变量以递归方式调用该函数。 结果插入到表示对的调用的代码引用`mul`使用接合运算符 (`%%`)。 `println`上一示例中的函数用于显示结果。

其他活动模式分支中的代码只是重新生成相同的表达式树，因此生成的表达式中的唯一更改是从更改`add`到`mul`。


### <a name="code"></a>代码
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]
    
### <a name="output"></a>输出

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>另请参阅
[F# 语言参考](index.md)

