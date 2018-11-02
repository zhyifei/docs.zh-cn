---
title: F# 教程
description: 检查某些 F# 编程语言中的代码示例本教程的主要功能。
ms.date: 02/28/2018
ms.openlocfilehash: 7a512b5fead8de69f025e791b6086c60dbfc1b24
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "50235708"
---
# <a name="tour-of-f"></a>F# 教程 #

若要了解有关 F# 的最佳方法是读取和写入 F# 代码。  本文将充当浏览一些 F# 语言的主要功能，并为您提供您的计算机可以执行一些代码片段。  若要了解如何设置开发环境，请查看[Getting Started](tutorials/getting-started/index.md)。

F# 中有两个主要概念： 函数和类型。  本教程将重点介绍语言的功能，这些功能划分为这两个概念。

## <a name="functions-and-modules"></a>函数和模块

任何 F# 程序的最基本的片段都***函数***组织成***模块***。  [函数](language-reference/functions/index.md)输入生成输出，对执行工作和下组织[模块](language-reference/modules.md)，这是组 F# 中的操作的主要方法。  定义使用它们[`let`绑定](language-reference/functions/let-bindings.md)，它为函数提供一个名称并定义其参数。

[!code-fsharp[BasicFunctions](../../samples/snippets/fsharp/tour.fs#L101-L133)]

`let` 绑定也是如何将值绑定到的名称，类似于其他语言中的变量。  `let` 绑定是***不可变***默认情况下，这意味着，一旦值或函数绑定到一个名称，它不能更改在原位。  这与在其他语言中，这些变量***可变***，这意味着它们的值可以更改任何位置的时间。  如果你需要一个可变的绑定，则可以使用`let mutable ...`语法。

[!code-fsharp[Immutability](../../samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>数字、 布尔值和字符串

作为一种.NET 语言，F# 支持相同的基础[基元类型](language-reference/primitive-types.md).NET 中存在的。

下面是如何各种数值类型都包含在 F#:

[!code-fsharp[Numbers](../../samples/snippets/fsharp/tour.fs#L49-L68)]

下面是布尔值，并执行基本的条件逻辑如下所示：

[!code-fsharp[Bools](../../samples/snippets/fsharp/tour.fs#L142-L152)]

下面是哪些 basic[字符串](language-reference/strings.md)操作如下所示：

[!code-fsharp[Strings](../../samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>元组

[元组](language-reference/tuples.md)是 F# 中是什么大问题。  它们是未命名，但有序值，可将其视为值本身的分组。  将它们视为与其他值汇总的值。  它们有许多用途，例如方便地从一个函数，返回多个值或对一些即席便利的值进行分组。

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L186-L203)]

截至 F# 4.1 中，你可以创建`struct`元组。  这些也进行互操作完全使用 C# 7/Visual 基本 15 元组，这两项也`struct`元组：

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L205-L218)]

务必要注意因为`struct`元组是值类型，它们不能隐式转换为引用元组，反之亦然。  必须显式转换之间的引用和结构的元组。

## <a name="pipelines-and-composition"></a>管道和组合

如运算符通过管道传递`|>`处理 F# 中的数据时广泛使用。 这些运算符是函数，可用于以灵活的方式建立的函数的"管道"。 下面的示例将指导完成如何，您可以充分利用这些运算符来构建一个简单的功能管道：

[!code-fsharp[Pipelines](../../samples/snippets/fsharp/tour.fs#L227-L282)]

前面的示例所做的许多功能 F# 中，包括列表处理函数，第一类函数的使用和[部分应用](language-reference/functions/index.md#partial-application-of-arguments)。 尽管每个这些概念的深入了解可以变得有点高级，它应该很清楚如何轻松地使用函数来生成管道时处理数据。

## <a name="lists-arrays-and-sequences"></a>列表、 数组和序列

列表、 数组和序列是 F# 核心库中的三个主要的集合类型。

[列出了](language-reference/lists.md)是相同类型的元素的有序的、 不可变集合。  它们是单向链接列表中，这意味着如果它们大型它们专门为枚举，但针对随机访问和串联的选择不当。  这与其他流行的语言，通常不使用单向链接列表来表示列表中的列表。

[!code-fsharp[Lists](../../samples/snippets/fsharp/tour.fs#L309-L359)]

[数组](language-reference/arrays.md)是固定大小*可变*相同类型的元素的集合。  它们支持快速随机访问的元素，并不是 F# 列表，因为它们是只需连续内存块的速度更快。

[!code-fsharp[Arrays](../../samples/snippets/fsharp/tour.fs#L368-L407)]

[序列](language-reference/sequences.md)是以逻辑序列的所有相同类型的元素。  这些是列表和数组，能够为任何逻辑系列的元素在"视图"比更普通的类型。  它们还脱颖而出，因为它们可以是***延迟***，这意味着仅在需要时可计算元素。

[!code-fsharp[Sequences](../../samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>递归函数

处理集合或序列的元素通常是与[递归](language-reference/functions/index.md#recursive-functions)F# 中。  尽管 F# 的 for 循环和命令式编程的支持，但递归是首选，因为它是更轻松地保证正确性。

>[!NOTE]
下面的示例使用通过模式匹配的`match`表达式。  更高版本中这篇文章介绍了此基本构造。

[!code-fsharp[RecursiveFunctions](../../samples/snippets/fsharp/tour.fs#L461-L500)]

F# 也具有完全支持尾调用优化，这是一种方法来优化递归调用，以便这些循环构造一样快。

## <a name="record-and-discriminated-union-types"></a>记录和可区分联合类型

记录与联合类型是 F# 代码中使用的两种基本数据类型，它们通常表示 F# 程序中的数据的最佳方式。  尽管这可以使其类似于类用其他语言，其主要区别之一是它们具有结构相等性语义。  这意味着，它们是"本机"可比较和相等性非常简单-只需检查是否等于另一个。

[记录](language-reference/records.md)是与可选成员 （如方法） 的命名值的聚合。  如果您熟悉 C# 或 Java，然后这些感觉类似于 Poco 或 Pojo-只需使用结构相等性和更低的方案。

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L507-L559)]

截至 F# 4.1，您还可以表示记录作为`struct`s。  这通过`[<Struct>]`属性：

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L561-L568)]

[可区分联合 (Du)](language-reference/discriminated-unions.md)是可能的命名窗体或事例数的值。  存储类型中的数据可以是多个非重复值之一。

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L575-L631)]

你还可以使用作为 Du*单用例的可区分联合*，以帮助与域建模基元类型。  通常情况下，字符串和其他基元类型用于表示某件事情，并因此提供了特定的含义。  但是，使用仅基元数据的表示形式可能会导致错误地分配不正确的值 ！  表示每种类型的信息作为一个不同的单用例联合可以强制执行在此方案中的正确性。

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L633-L654)]

如上面的示例所示，若要获取的基础值中单用例的可区分联合，您必须显式 unwrap。

此外，Du 还支持递归定义，从而可以轻松地表示树和本质上是递归数据。  例如，下面是如何可以表示具有的二进制搜索树`exists`和`insert`函数。

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L656-L683)]

Du 可以表示的树中的数据类型的递归结构，因为运行该递归结构非常简单，保证正确性。  它还支持在模式匹配，如下所示。

此外，可以表示为 Du`struct`与`[<Struct>]`属性：

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L685-L696)]

但是，有以下两个执行此操作时，需要注意的事项：

1. 结构 DU 不能以递归方式定义。
2. 结构 DU 必须具有其情况下的每个唯一的名称。

未能遵循上述将导致编译错误。

## <a name="pattern-matching"></a>模式匹配

[模式匹配](language-reference/pattern-matching.md)是 F# 语言功能，从而使 F# 类型上操作的准确性。  在上述示例中，您可能已经注意到很多`match x with ...`语法。  该构造允许编译器可以理解的数据类型，您不必考虑所有可能的情况下，使用通过通常所说的数据类型作为详尽模式匹配时的"形状"。  这是为了确保准确性，功能非常强大，可巧妙地用于"提升"通常是运行时需考虑到编译时什么。

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L705-L742)]

此外可以使用速记`function`进行模式匹配，这很有用，当您编写的函数，这使得使用的构造[部分应用](language-reference/functions/index.md#partial-application-of-arguments):

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L744-L762)]

您可能已经注意到的内容是使用`_`模式。  这称为[通配符模式](language-reference/pattern-matching.md#wildcard-pattern)，它是"我不关心的内容是"，显示的方式。  虽然方便，但可以意外地不详尽模式匹配，而不再受益编译时强制要求，如果您不小心使用`_`。  您不关心段分解的类型时最好使用时具有枚举模式匹配表达式中的所有有意义的情况下当模式匹配，或最后一个子句。

[活动模式](language-reference/active-patterns.md)是另一个功能强大的构造与模式匹配一起使用。  它们允许您输入的数据进行分区到自定义窗体，将它们分解的模式匹配调用站点上。  它们可以还进行参数化，从而允许将定义为一个函数的分区。  扩展前面的示例以支持活动模式就会像这样：

[!code-fsharp[ActivePatterns](../../samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a>可选类型

可区分联合类型的一个特殊情况是选项类型，这是很有用，它是 F# 核心库的一部分。

[选项类型](language-reference/options.md)是两种情况之一的类型： 一个值，或在所有执行任何操作。  在任何方案，其中可能会或可能不会造成从某一特定操作的值中使用。  这然后会强制地使其编译时需考虑而不是运行时需考虑这两种情况。  通常在 Api 中使用这些位置`null`用来表示"nothing"相反，因此无需担心`NullReferenceException`在许多情况下。

[!code-fsharp[Options](../../samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a>度量单位

F# 类型系统的一项独特功能是能够为通过度量单位的数字文本提供上下文。

[度量单位](language-reference/units-of-measure.md)，可以将关联到一个单元，例如，单位为米数值类型和具有函数中执行工作单元而不是数字文本。  这使编译器能够验证传入的数字文本的类型在某些上下文下有意义，这样可以减少运行时错误与此类任务相关联。

[!code-fsharp[UnitsOfMeasure](../../samples/snippets/fsharp/tour.fs#L817-L842)]

F# 核心库定义了许多的 SI 单位类型和单位转换。  若要了解详细信息，请查看[Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d)。

## <a name="classes-and-interfaces"></a>类和接口

F# 还具有对.NET 类的完全支持[接口](language-reference/interfaces.md)，[抽象类](language-reference/abstract-classes.md)，[继承](language-reference/inheritance.md)，依次类推。

[类](language-reference/classes.md)类型表示的.NET 对象，它可以具有属性、 方法和事件作为其[成员](language-reference/members/index.md)。

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L845-L880)]

定义泛型类也是非常简单。

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L883-L908)]

若要实现接口，可以使用任一`interface ... with`语法或[对象表达式](language-reference/object-expressions.md)。

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a>使用哪些类型

类、 记录、 可区分联合和元组的存在产生了一个重要问题： 您将使用？  像大多数中的所有内容生命，答案取决于您的环境。

元组非常适合用于从函数，返回多个值并使用 ad hoc 聚合的值作为值本身。

记录是"的进一步"具有名为标签和支持可选的成员的元组。  它们非常适合用于数据在传输中通过应用程序的低繁琐程序表示形式。  因为它们具有结构相等性，它们是易于使用的比较。

可区分的联合具有许多用途，但核心权益是能够与模式匹配的所有可能"形状"的数据可以有结合使用它们。  

类非常适合用于大量的原因，例如当需要表示信息并还将绑定到功能的信息。  根据经验，必须从概念上讲与一些数据绑定的功能时使用类和面向对象编程的原理是很大的优势。  类还有首选的数据类型与 C# 和 Visual Basic 互操作时为这些语言中使用的几乎都类。

## <a name="next-steps"></a>后续步骤

现在，已了解的一些主要功能的语言，您应准备好开始编写第一个 F# 程序 ！  请查看[Getting Started](tutorials/getting-started/index.md)若要了解如何设置开发环境，编写一些代码。

了解更多的后续步骤可以是任意，但我们建议[中的函数编程简介F#](introduction-to-functional-programming/index.md)熟悉函数编程的核心概念。  这些将是在中构建 F# 中的可靠程序必不可少。

此外，请查看[F# 语言参考](language-reference/index.md)若要查看有关 F# 的概念内容全面集合。
