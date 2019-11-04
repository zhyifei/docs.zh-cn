---
title: F# 教程
description: 在本教程中，通过代码示例F#查看编程语言的一些重要功能。
ms.date: 11/06/2018
ms.openlocfilehash: cfea2827dcec65f9e3606e8528179029e1f2db84
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423810"
---
# <a name="tour-of-f"></a>F\# 教程

要了解的最佳方法F#是阅读和编写F#代码。 本文将介绍F#语言的一些主要功能，并提供可在计算机上执行的一些代码片段。 若要了解如何设置开发环境，请查看[入门](get-started/index.md)。

中F#有两个主要概念：函数和类型。  本教程将重点介绍这两个概念的语言功能。

## <a name="executing-the-code-online"></a>联机执行代码

如果未在计算机F#上安装，则可以在浏览器[ F# ](https://tryfsharp.fsbolero.io/)中执行 WebAssembly 中的所有示例。 Fable 是直接在你F#的浏览器中执行的的方言。 若要查看复制中跟随的示例，请查看**示例 > 了解F#**  Fable 复制的左侧菜单栏中的 > 教程。

## <a name="functions-and-modules"></a>函数和模块

任何F#程序的最基本部分都是组织到***模块***中的***功能***。  [函数](./language-reference/functions/index.md)在输入时执行工作，以生成输出，它们在 "[模块](./language-reference/modules.md)" 下进行组织，这是作为分组依据F#的主要方式。  它们是使用[`let` 绑定](./language-reference/functions/let-bindings.md)定义的，该绑定为函数指定名称并定义其参数。

[!code-fsharp[BasicFunctions](~/samples/snippets/fsharp/tour.fs#L101-L133)]

`let` 绑定也是将值绑定到名称（类似于其他语言中的变量）的方式。  默认情况下，`let` 绑定是***不可变***的，这意味着一旦值或函数绑定到名称，就不能就地更改。  这与其他语言中的变量不同，后者是***可变***的，这意味着在任何时间点都可以更改其值。  如果需要可变绑定，可以使用 `let mutable ...` 语法。

[!code-fsharp[Immutability](~/samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a>数字、布尔值和字符串

作为一种 .NET 语言F# ，支持 .net 中存在的相同基础[基元类型](language-reference/basic-types.md)。

下面介绍如何在中F#表示各种数值类型：

[!code-fsharp[Numbers](~/samples/snippets/fsharp/tour.fs#L49-L68)]

下面是布尔值和执行基本条件逻辑的形式：

[!code-fsharp[Bools](~/samples/snippets/fsharp/tour.fs#L142-L152)]

基本[字符串](./language-reference/strings.md)操作如下所示：

[!code-fsharp[Strings](~/samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a>元组

[元组](./language-reference/tuples.md)是一项F#重大交易。  它们是未命名但有序值的分组，可被视为值本身。  将它们视为聚合自其他值的值。  它们有很多用途，如从函数中方便地返回多个值，或者为某些即席的便利分组值。

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L186-L203)]

从F# 4.1，你还可以创建 `struct` 元组。  它们还与 c # 7/Visual Basic 15 元组完全互操作，这两个元组也 `struct` 元组：

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L205-L218)]

请务必注意，因为 `struct` 元组是值类型，所以它们不能隐式转换为引用元组，反之亦然。  必须在 reference 和 struct 元组之间显式转换。

## <a name="pipelines-and-composition"></a>管道和组合

管道运算符（如 `|>`）在处理中F#的数据时广泛使用。 这些运算符是允许您以灵活的方式建立函数的 "管道" 的函数。 下面的示例演示如何利用这些运算符来生成简单的功能管道：

[!code-fsharp[Pipelines](~/samples/snippets/fsharp/tour.fs#L227-L282)]

之前的示例使用了许多功能F#，包括列表处理函数、第一类函数和[部分应用程序](./language-reference/functions/index.md#partial-application-of-arguments)。 尽管深入了解其中每个概念可能会变得很简单，但应清楚地了解如何在生成管道时使用函数来处理数据。

## <a name="lists-arrays-and-sequences"></a>列表、数组和序列

列表、数组和序列是F#核心库中的三种主要集合类型。

[列表](./language-reference/lists.md)是具有相同类型的元素的有序集合，不可变集合。  它们是一种单向链接列表，这意味着它们适用于枚举，但如果它们很大，则随机访问和串联的选择会很糟糕。  这与其他常用语言的列表相反，后者通常不使用单向链接列表来表示列表。

[!code-fsharp[Lists](~/samples/snippets/fsharp/tour.fs#L309-L359)]

[数组](./language-reference/arrays.md)是具有相同类型的元素的固定大小、*可变*集合。  它们支持快速随机访问元素，并且比F#列表更快，因为它们只是连续的内存块。

[!code-fsharp[Arrays](~/samples/snippets/fsharp/tour.fs#L368-L407)]

[序列](./language-reference/sequences.md)是一系列逻辑元素，它们都属于同一类型。  这些是比列表和数组更通用的类型，可以是 "视图" 到任何逻辑序列的元素。  它们还会显得很明显，因为它们可能是***延迟***的，也就是说，仅当需要时才可以计算元素。

[!code-fsharp[Sequences](~/samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a>递归函数

处理集合或元素序列通常是通过中F#的[递归](./language-reference/functions/index.md#recursive-functions)来完成的。  尽管F#支持循环和命令式编程，但递归是首选的，因为这样可以更轻松地保证正确性。

> [!NOTE]
> 下面的示例通过 `match` 表达式利用模式匹配。  本文的后面部分介绍了这一基本构造。

[!code-fsharp[RecursiveFunctions](~/samples/snippets/fsharp/tour.fs#L461-L500)]

F#还完全支持对尾调用优化，这是一种优化递归调用的方法，使其与循环构造一样快。

## <a name="record-and-discriminated-union-types"></a>记录和可区分联合类型

记录类型和联合类型是代码中F#使用的两种基本数据类型，通常是在F#程序中表示数据的最佳方式。  虽然这使得它们类似于其他语言中的类，但其主要区别之一是它们具有结构相等语义。  这意味着，它们是 "本机" 可比较的，相等非常简单-只需检查是否有一个与另一个相等。

[记录](./language-reference/records.md)是命名值的聚合，具有可选成员（例如方法）。  如果你熟悉C#或 Java，则这些内容应类似于 Poco 或 pojo，只是具有结构相等性和不足的情况。

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L507-L559)]

从F# 4.1，你还可以将记录表示为 `struct`。  这是通过 `[<Struct>]` 属性完成的：

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L561-L568)]

可[区分联合（du）](./language-reference/discriminated-unions.md)是可能是一些命名窗体或事例的值。  类型中存储的数据可以是多个不同值之一。

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L575-L631)]

你还可以使用 Du 作为*单用例可区分联合*，以帮助进行基于基元类型的域建模。  通常情况下，字符串和其他基元类型用于表示某些内容，因此具有特定的含义。  但是，仅使用数据的基元表示形式可能会导致错误地分配不正确的值！  将每种类型的信息表示为不同的单用例联合可在这种情况下强制执行正确性。

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L633-L654)]

如上面的示例所示，若要获取单个用例可区分联合的基础值，必须将其显式解包。

此外，Du 还支持递归定义，使你能够轻松地表示树和本质上递归的数据。  例如，下面介绍了如何使用 `exists` 和 `insert` 函数来表示二进制搜索树。

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L656-L683)]

由于 Du 允许您在数据类型中表示树的递归结构，因此，对此递归结构进行操作非常简单，并且保证正确性。  它还支持模式匹配，如下所示。

此外，还可以将 Du 表示为具有 `[<Struct>]` 属性的 `struct`：

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L685-L696)]

但是，在执行此操作时，请记住以下两个重要事项：

1. 不能以递归方式定义结构 DU。
2. 结构 DU 的每个事例都必须具有唯一的名称。

如果未遵循上述操作，则会导致编译错误。

## <a name="pattern-matching"></a>模式匹配

[模式匹配](./language-reference/pattern-matching.md)是一F#种语言功能，可用于对F#类型进行操作。  在上述示例中，您可能注意到了很多 `match x with ...` 语法。  此构造允许编译器（可以理解数据类型的 "形状"）强制你考虑使用数据类型（通过所谓的 "完全模式匹配"）时的所有可能情况。  这是非常强大的功能，可以巧妙用于 "提升" 通常是运行时问题的编译时问题。

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L705-L742)]

您可能已注意到，使用了 `_` 模式。  这称为[通配符模式](./language-reference/pattern-matching.md#wildcard-pattern)，这是一种 "我不在意什么内容" 的方法。  尽管很方便，但如果不小心使用 `_`，则可能会意外绕过穷举模式匹配，并且不再受益于编译时操作。  当您在模式匹配时不关心分解类型的某些部分时，最好使用此方法; 当您枚举了模式匹配表达式中的所有有意义的事例时，最好使用该方法。

[活动模式](./language-reference/active-patterns.md)是另一个功能强大的构造，可与模式匹配一起使用。  它们允许您将输入数据分区为自定义窗体，并在模式匹配调用站点分解它们。  它们也可以参数化，从而允许将分区定义为函数。  扩展前面的示例以支持活动模式，如下所示：

[!code-fsharp[ActivePatterns](~/samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a>可选类型

区分联合类型的一种特殊情况是 "选项类型"，它非常有用，因为它是F#核心库的一部分。

[选项类型](./language-reference/options.md)是一种类型，该类型表示以下两种情况之一：值或根本不显示任何内容。  它用于某个值可能因特定操作而不会产生的任何情况。  这会强制你考虑这两种情况，使其成为编译时问题，而不是运行时问题。  这通常用于 `null` 用来表示 "nothing" 的 Api，从而无需担心在许多情况下 `NullReferenceException`。

[!code-fsharp[Options](~/samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a>度量单位

类型系统的一F#项独特功能是能够通过度量单位为数字文本提供上下文。

[度量单位](./language-reference/units-of-measure.md)允许您将数值类型与单位（例如计量）相关联，并使函数可对单元（而不是数字文本）执行工作。  这使编译器能够验证传入的数值类型在特定上下文中是否有效，从而消除了与此类工作相关的运行时错误。

[!code-fsharp[UnitsOfMeasure](~/samples/snippets/fsharp/tour.fs#L817-L842)]

F#核心库定义了许多 SI 单元类型和单位转换。  若要了解详细信息，请查看[Microsoft.FSharp.Data.UnitSystems.SI 命名空间](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d)。

## <a name="classes-and-interfaces"></a>类和接口

F#还对 .NET 类、[接口](./language-reference/interfaces.md)、[抽象类](./language-reference/abstract-classes.md)、[继承](./language-reference/inheritance.md)等提供完全支持。

[类](./language-reference/classes.md)是表示 .net 对象的类型，这些对象可以具有属性、方法和事件作为其[成员](./language-reference/members/index.md)。

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L845-L880)]

定义泛型类也非常简单。

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L883-L908)]

若要实现接口，可以使用 `interface ... with` 语法或[对象表达式](./language-reference/object-expressions.md)。

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a>要使用的类型

类、记录、可区分联合和元组的存在导致了重要问题：应使用哪一个？  与生活中的大多数操作一样，答案取决于你的情况。

元组非常适合从函数返回多个值，并使用临时值聚合作为值本身。

记录是元组中的 "单步执行"，其命名标签和对可选成员的支持。  它们非常适用于通过您的程序传输的数据的低计划表示形式。  由于它们具有结构相等性，因此它们可用于比较。

可区分联合具有许多用途，但核心好处是能够将它们与模式匹配一起使用，以考虑数据可以具有的所有可能的 "形状"。  

类对于大量原因非常有用，例如，当你需要表示信息并将该信息绑定到功能时。  作为经验法则，当你具有在概念上与某些数据关联的功能时，使用类和面向对象编程的原则是一项巨大的好处。  与C#和 Visual Basic 互操作时，类也是首选的数据类型，因为这些语言几乎都使用类。

## <a name="next-steps"></a>后续步骤

现在，你已了解了语言的一些主要功能，你应该已准备好编写你的第一个F#程序！  请查看[入门](get-started/index.md)，了解如何设置开发环境并编写一些代码。

用于了解详细信息的后续步骤可以是你喜欢的任何内容，但建议你[在中F#介绍函数编程](./introduction-to-functional-programming/index.md)，以熟悉核心功能编程概念。  这对于在中F#构建可靠的程序非常重要。

另外，请查看[ F#语言参考](./language-reference/index.md)，查看上F#的概念内容的完整集合。
