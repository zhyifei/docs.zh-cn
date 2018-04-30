---
title: '介绍 F # 的'
description: '检查某些 F # 编程语言中使用代码示例本教程的主要功能。'
author: cartermp
ms.author: phcart
ms.date: 02/28/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 6821c74827b928cdd0c5aff101be4f9103986e3e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="tour-of-f"></a>介绍 F # 的 #

若要了解有关 F # 的最佳方法是读取和写入 F # 代码。  本文将充当浏览了某些 F # 语言的主要功能并使你可以在您的计算机执行某些代码片段。  若要了解有关设置开发环境的信息，请查看[入门](tutorials/getting-started/index.md)。

F # 中有两个主要概念： 函数和类型。  本教程将强调的语言功能，这些功能划分为这两个概念。

## <a name="functions-and-modules"></a>函数和模块

任何 F # 程序的最基本的块是***函数***组织成***模块***。  [函数](language-reference/functions/index.md)输入生成输出，在执行工作和其下组织[模块](language-reference/modules.md)，这是组 F # 中的操作的主要方法。  它们定义使用[`let`绑定](language-reference/functions/let-bindings.md)，它为函数提供一个名称，并定义其自变量。

[!code-fsharp[BasicFunctions](../../samples/snippets/fsharp/tour.fs#L101-L133)]

`let` 绑定也是如何将一个值绑定到类似于其他语言中的变量的名称。  `let` 绑定是***不可变***默认情况下，这意味着，一旦值或函数绑定到一个名称，它不能更改在原位。  这是在其他语言中，这些变量相反的***可变***，这意味着它们的值可以更改的任何时刻时间。  如果你需要使用可变绑定，则可以使用`let mutable ...`语法。

[!code-fsharp[Immutability](../../samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>数字、 布尔值和字符串

作为一种.NET 语言，F # 支持相同的基础[基元类型](language-reference/primitive-types.md).NET 中存在。

下面是如何各种数值类型表示在 F # 中：

[!code-fsharp[Numbers](../../samples/snippets/fsharp/tour.fs#L49-L68)]

下面是布尔值和执行基本的条件逻辑如下所示：

[!code-fsharp[Bools](../../samples/snippets/fsharp/tour.fs#L142-L152)]

这是什么 basic[字符串](language-reference/strings.md)操作如下所示：

[!code-fsharp[Strings](../../samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>元组

[元组](language-reference/tuples.md)是 F # 中了不起。  它们是未命名，但有序值，可以被视为值本身的分组。  可以将它们视为汇总从其他值的值。  它们有许多用途，例如方便地从一个函数，返回多个值或分组一些即席便利的值。

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L186-L203)]

截至 F # 4.1 中，你可以创建`struct`元组。  这些还与进行互操作完全 C# 7/Visual 基本 15 元组，也是`struct`元组：

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L205-L218)]

务必请注意，因为`struct`元组是值类型，它们不能隐式转换以引用元组，反之亦然。  你必须显式转换之间的引用和结构的元组。

## <a name="pipelines-and-composition"></a>管道和组合

管道运算符 (`|>`， `<|`， `||>`， `<||`， `|||>`， `<|||`) 和组合运算符 (`>>`和`<<`) 处理 F # 中的数据时广泛使用。  这些运算符是可用于以灵活的方式建立"管道"的函数的函数。  下面的示例将指导你无法在如何充分利用这些运算符来生成简单的功能管道。

[!code-fsharp[Pipelines](../../samples/snippets/fsharp/tour.fs#L227-L300)]

上面的示例中所做的许多 F # 的功能，包括列表处理功能，第一类函数的使用和[部分应用](language-reference/functions/index.md#partial-application-of-arguments)。  尽管这些概念的深入了解可以变得有点高级，应该已经很明确如何轻松地使用函数来生成管道时处理数据。

## <a name="lists-arrays-and-sequences"></a>列表、 数组和序列

列表、 数组和序列是 F # 核心库中的三个主要集合类型。

[列出](language-reference/lists.md)是相同类型的元素的有序的、 不可变集合。  它们是单向链接列表中，这意味着它们必须为枚举，但随机访问和串联的不佳选择如果他们是大。  这与其他流行的语言，通常不使用单向链接列表来表示列表中的列表。

[!code-fsharp[Lists](../../samples/snippets/fsharp/tour.fs#L309-L359)]

[数组](language-reference/arrays.md)是固定大小、*可变*相同类型的元素组成的集合。  它们支持快速随机访问的元素，并不是 F # 列出因为它们是只是连续内存块的能力，速度更快。

[!code-fsharp[Arrays](../../samples/snippets/fsharp/tour.fs#L368-L407)]

[序列](language-reference/sequences.md)是逻辑的一系列元素，所有相同的类型。  这些是比列表和数组，可为任何逻辑系列的元素"视图"更多常规类型。  它们还醒目因为它们可以是***延迟***，这意味着仅在需要时可以计算元素。

[!code-fsharp[Sequences](../../samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>递归函数

通常使用完成处理集合或元素的序列[递归](language-reference/functions/index.md#recursive-functions)F # 中。  尽管 F # 具有对循环和命令性编程的支持，但递归是首选，因为它是更轻松地保证正确性。

>[!NOTE]
下面的示例使用的模式匹配通过`match`表达式。  更高版本中这篇文章介绍了此基本结构。

[!code-fsharp[RecursiveFunctions](../../samples/snippets/fsharp/tour.fs#L461-L500)]

F # 还具有完全支持尾调用优化，这是一种优化递归调用，以便它们循环构造一样快。

## <a name="record-and-discriminated-union-types"></a>记录和可区分联合类型

记录和联合类型是在 F # 代码中，使用的两个基本数据类型，通常是用于表示在 F # 程序中的数据的最佳方式。  虽然这使得它们成为类似于类以其他语言，其主要区别之一是它们具有结构上相等语义。  这意味着它们是"本机"比较和相等性非常简单-只检查是否等于另一个。

[记录](language-reference/records.md)是已命名的值，与 （如方法） 的可选成员聚合。  如果你熟悉 C# 或 Java，然后这些应感觉类似于 POCOs 或 Pojo-只需与结构相等性和更低的方案。

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L507-L559)]

截至 F # 4.1 中，你还可以表示记录作为`struct`s。  这通过完成`[<Struct>]`属性：

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L561-L568)]

[可区分联合 (Du)](language-reference/discriminated-unions.md)值可以是大量命名窗体或用例。  类型中存储的数据可以是多个非重复值之一。

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L575-L631)]

你还可以使用作为 Du*单用例可区分联合*，来帮助与域通过基元类型建模。  通常情况下，字符串和其他基元类型用于表示的一些东西，并因此具有特殊含义。  但是，使用仅基元数据的表示形式可能会导致错误地分配的值不正确 ！  表示每种类型的信息作为一个不同的单用例联合可以强制执行在此方案中的正确性。

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L633-L654)]

如上面的示例所示，若要在单用例可区分联合，获取基础值必须显式打开它。

此外，Du 还支持递归定义，从而可以轻松地表示树和本质上是递归数据。  例如，下面是如何可以表示具有二进制搜索树`exists`和`insert`函数。

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L656-L683)]

因为 Du 使您可以表示的树中的数据类型的递归结构，对此递归结构非常简单，可保证正确性。  它还支持在模式匹配，如下所示。

此外，您可以表示为 Du`struct`与`[<Struct>]`属性：

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L685-L696)]

但是，有两个执行此操作时需要牢记的重要事项：

1. 太平洋结构不能以递归方式定义。
2. 结构是必须具有唯一的名称，为每个及其用例。

未能遵循上述将导致编译错误。

## <a name="pattern-matching"></a>模式匹配

[模式匹配](language-reference/pattern-matching.md)是 F # 语言功能，这样对 F # 类型的正确性。  在上面的示例中，你可能注意到相当多的`match x with ...`语法。  该构造允许编译器可以理解的数据类型，以强制你来应对所有可能的情况下，使用通过通常所说的数据类型作为详尽模式匹配时的"形状"。  这是非常强大的正确性，，，可以巧妙地使用以"提升"通常是运行时需考虑到编译时什么。

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L705-L739)]

你还可以使用速记`function`与模式匹配，这很有用，当你编写的函数使您能够使用的构造[部分应用](language-reference/functions/index.md#partial-application-of-arguments):

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L741-L759)]

你可能已经注意到的内容是使用`_`模式。  这称为[通配符模式](language-reference/pattern-matching.md#wildcard-pattern)，这是一种说"我不会关心的内容是"。  虽然便利，然而可以意外绕过详尽模式匹配并且不再受益执行进行编译时，如果你不小心使用`_`。  它最适用时你不关心分解后的类型的某些部分时模式匹配，或最终的子句时具有枚举所有有意义的情况下在模式匹配表达式。

[活动模式](language-reference/active-patterns.md)是另一个功能强大的结构与模式匹配一起使用。  它们允许您输入的数据分区到自定义窗体，将它们分解的模式匹配调用站点。  它们还可参数化，从而允许为函数定义分区。  扩展前面的示例以支持活动模式如下所示：

[!code-fsharp[ActivePatterns](../../samples/snippets/fsharp/tour.fs#L761-L783)]

## <a name="optional-types"></a>可选类型

可区分联合类型使用了一个特殊的情况下是选项类型，这是很有用，它是 F # 核心库的一部分。

[选项类型](language-reference/options.md)是类型表示两种情况之一： 一个值，或在所有执行任何操作。  它用在任何方案，其中可能或可能不会造成从某一特定操作的值。  这将强制你以这两种情况，因而编译时需考虑，而不是运行时需考虑的帐户。  这些通常在 Api 中使用其中`null`用于表示"nothing"相反，因此不再需要担心`NullReferenceException`在许多情况下。

[!code-fsharp[Options](../../samples/snippets/fsharp/tour.fs#L791-L811)]

## <a name="units-of-measure"></a>度量单位

F # 类型系统的独特功能是能够通过度量单位的数值为提供的上下文。

[度量单位](language-reference/units-of-measure.md)允许您将关联到一个单元，如米，数值类型和具有函数执行单位，而不是数值。  这使编译器若要验证传入的数值的类型在某些上下文有意义，从而消除运行时错误与该类型的工作。

[!code-fsharp[UnitsOfMeasure](../../samples/snippets/fsharp/tour.fs#L818-L839)]

F # 核心库定义了许多 SI 单位类型和单元转换。  若要了解详细信息，请查看[Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d)。

## <a name="classes-and-interfaces"></a>类和接口

F # 还具有对.NET 类的完全支持[接口](language-reference/interfaces.md)，[抽象类](language-reference/abstract-classes.md)，[继承](language-reference/inheritance.md)，依次类推。

[类](language-reference/classes.md)是表示.NET 对象的类型可以属性、 方法和事件作为其[成员](language-reference/members/index.md)。

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L848-L877)]

定义泛型类也是非常简单的。

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L884-L905)]

若要实现接口，你可以使用`interface ... with`语法或[对象表达式](language-reference/object-expressions.md)。

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L912-L931)]

## <a name="which-types-to-use"></a>使用哪些类型

类、 记录、 可区分联合和元组是否存在产生了一个重要问题： 你应使用的？  如大多数中的所有内容生命，答案取决于你的情况。

元组则非常适合用于从一个函数，返回多个值，并使用作为值本身的值的即席聚合。

记录是"中的步骤向上"具有名为标签和支持可选的成员的元组。  它们是非常适合于正在传输的数据通过你计划的低方案表示。  因为它们具有结构相等性，它们是比较易于使用。

可区分的联合有许多用途，但核心优势是能够与模式匹配来应对所有可能"形状"可以具有数据结合使用它们。  

类非常适合用于大量的原因，例如，当你需要表示信息以及还如何关联到功能该信息。  根据经验，你会获得对某些数据，从概念上讲绑定的功能时使用类和的面向对象的编程原则是很大的优势。  类也是首选的数据类型与 C# 和 Visual Basic 互操作时为这些语言几乎所有操作使用的类。

## <a name="next-steps"></a>后续步骤

现在，你已了解的一些主要功能的语言，你应该已准备好编写第一个 F # 程序 ！  签出[入门](tutorials/getting-started/index.md)若要了解如何设置开发环境和编写一些代码。

若要了解有关的后续步骤可以是你希望的任何内容，但我们建议[函数作为一类值](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming in F#](introduction-to-functional-programming/index.md)-->获取熟悉函数编程的核心概念。  这些将是基本中生成 F # 中的可靠程序。

此外，请查看[F # 语言参考](language-reference/index.md)以在 F # 中查看概念性内容的全面集合。
