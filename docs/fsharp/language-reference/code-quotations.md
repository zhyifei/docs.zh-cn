---
title: 代码引用
description: 了解F#代码引用, 它是一种语言功能, 可用于以编程方式F#生成和使用代码表达式。
ms.date: 05/16/2016
ms.openlocfilehash: c6ec0078c685a6452f49edd289b01491dd62e3db
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630413"
---
# <a name="code-quotations"></a>代码引用

> [!NOTE]
> API 参考链接将转至 MSDN。  Docs.microsoft.com API 参考尚未完成。

本主题介绍*代码引用*, 它是一种语言功能, 可用于以编程F#方式生成和使用代码表达式。 利用此功能, 您可以生成一个表示F#代码的抽象语法树。 然后, 可以根据应用程序的需要遍历和处理抽象语法树。 例如, 您可以使用树生成F#代码或以某种其他语言生成代码。

## <a name="quoted-expressions"></a>带引号的表达式

*带引号的表达式*是F#代码中的一个表达式, 它以不作为程序的一部分进行编译, 而是编译为表示F#表达式的对象。 可以通过以下两种方式之一来标记带引号的表达式: 使用类型信息或不包含类型信息。 如果要包括类型信息, 请使用符号`<@`并`@>`分隔带引号的表达式。 如果不需要类型信息, 则使用符号`<@@`和。 `@@>` 下面的代码显示类型化和非类型化的引用。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

如果不包含类型信息, 遍历大型表达式树的速度将更快。 使用类型化符号括起来的表达式的结果类型为`Expr<'T>`, 其中类型参数具有由F#编译器的类型推理算法确定的表达式的类型。 使用不带类型信息的代码引用时, 带引号的表达式的类型为非泛型类型[Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65)。 可以调用类型化[Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) `Expr`类的原始属性来获取非类型化`Expr`对象。

有多种静态方法可让你在F# `Expr`类中以编程方式生成表达式对象, 而无需使用带引号的表达式。

请注意, 代码引号必须包含完整的表达式。 例如, 对于绑定, 需要绑定名称和使用绑定的其他表达式的定义。 `let` 在详细语法中, 这是跟在`in`关键字后面的表达式。 在模块的顶层, 这只是模块中的下一个表达式, 但在引号中, 它是显式必需的。

因此, 下面的表达式无效。

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

但下面的表达式是有效的。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

若要F#评估报价, 必须使用[ F#引号计算器](https://github.com/fsprojects/FSharp.Quotations.Evaluator)。 它提供对计算和执行F#表达式对象的支持。

## <a name="expr-type"></a>Expr 类型

`Expr`类型的实例表示F#表达式。 库文档中记录了泛型和非`Expr`泛型类型。 F# 有关详细信息, 请参阅[Fsharp.core 命名空间](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d)和[引号。](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d)

## <a name="splicing-operators"></a>拼接运算符

拼接使你能够将文本代码引用与你以编程方式或从其他代码引用创建的表达式组合在一起。 使用`%`和`%%`运算符可以将F#表达式对象添加到代码引用中。 使用`%`运算符将类型化表达式对象插入类型化的引用中; `%%`使用运算符将非类型化的表达式对象插入非类型化的引用。 这两个运算符均为一元前缀运算符。 因此, `expr`如果是类型`Expr`的非类型化表达式, 以下代码是有效的。

```fsharp
<@@ 1 + %%expr @@>
```

如果`expr`是类型`Expr<int>`的类型化的引号, 则以下代码有效。

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>示例

### <a name="description"></a>描述

下面的示例演示如何使用代码引用将代码放F#入 expression 对象, 然后打印表示该表达式F#的代码。 定义了`println`一个函数, 该函数包含一个`print`递归函数, F#该函数以友好格式`Expr`显示 expression 对象 (类型为)。 可以使用[fsharp.core](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4)和[DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd)模块中的几个活动模式来分析表达式对象, 这种模式可用于分析表达式对象。 此示例不包括可能出现在F#表达式中的所有可能的模式。 任何无法识别的模式都会触发与通配符模式 (`_`) 的匹配, 并通过`ToString`使用方法呈现, 该方法`Expr`可让你了解要添加到匹配表达式的活动模式。

### <a name="code"></a>代码

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a>Output

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>示例

### <a name="description"></a>描述

您还可以使用[exprshape.rebuildshapecombination 模块](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de)中的三个活动模式来遍历具有较少活动模式的表达式树。 当你希望遍历树但你不需要大多数节点中的所有信息时, 这些活动模式会很有用。 当使用这些模式时, 任何F#表达式都将与以下三种模式之一`ShapeVar`匹配: 如果表达式为变量, `ShapeLambda`则为; 如果表达式是 lambda 表达式, `ShapeCombination`则为; 否则为。 如果使用活动模式遍历表达式树, 如前面的代码示例所示, 您必须使用更多的模式来处理所有可能F#的表达式类型, 并且您的代码将更复杂。 有关详细信息, 请参阅[exprshape.rebuildshapecombination.&#124;ShapeVar&#124;ShapeLambda ShapeCombination Active Pattern](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d)。

下面的代码示例可用作更复杂的遍历的基础。 在此代码中, 将为包含函数调用`add`的表达式创建表达式树。 [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d)活动模式用于检测对`add`表达式树中的任何调用。 此活动模式将调用的参数分配给`exprList`值。 在这种情况下, 只有两个, 因此会将其拉出, 并以递归方式对参数调用函数。 `mul`通过使用拼接运算符 (`%%`) 将结果插入到表示对的调用的代码中。 上`println`一示例中的函数用于显示结果。

其他活动模式分支中的代码只是重新生成相同的表达式树, 因此, 结果表达式中的唯一更改是从`add`到`mul`的更改。

### <a name="code"></a>代码

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a>Output

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
