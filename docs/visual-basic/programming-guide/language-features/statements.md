---
title: 语句
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- colons (:) [Visual Basic]
- constants [Visual Basic], defining
- underlines
- constants [Visual Basic], statements
- blue underline [Visual Basic]
- procedures [Visual Basic], statements
- variables [Visual Basic], assigning
- line breaks [Visual Basic], in code
- executable statements [Visual Basic]
- variables [Visual Basic], defining
- statements [Visual Basic], about statements
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
ms.openlocfilehash: f63f0f0212913f95baab2a8a43c4b7f25a859cd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401465"
---
# <a name="statements-in-visual-basic"></a>语句 (Visual Basic)

Visual Basic 中的语句是一个完整的指令。 它可以包含关键字、运算符、变量、常量和表达式。 每个语句都属于以下类别之一：

- **声明语句**，用于命名变量、常量或过程，也可以指定数据类型。

- **可执行语句**，启动操作。 这些语句可以调用方法或函数，并且它们可以循环或分支代码块。 可执行语句包括**赋值语句**，用于将值或表达式分配给变量或常量。

本主题介绍每个类别。 此外，本主题还介绍如何在一行上组合多个语句，以及如何在多行上继续语句。

## <a name="declaration-statements"></a>声明语句

使用声明语句命名和定义过程、变量、属性、数组和常量。 声明编程元素时，还可以定义其数据类型、访问级别和范围。 有关详细信息，请参阅[声明的元素特征](./declared-elements/declared-element-characteristics.md)。

下面的示例包含三个声明。

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

第一个声明是`Sub`语句。 与其匹配`End Sub`语句一起，它声明名为 的过程`applyFormat`。 它还指定 是`applyFormat``Public`，这意味着任何可以引用它的代码都可以调用它。

第二个声明是`Const`语句，它声明常量`limit`，指定`Integer`数据类型和值 33。

第三个声明是`Dim`语句，它声明变量`thisWidget`。 数据类型是特定对象，即从`Widget`类创建的对象。 可以将变量声明为任何基本数据类型或正在使用的应用程序中公开的任何对象类型。

### <a name="initial-values"></a>初始值

当包含声明语句的代码运行时，Visual Basic 保留声明元素所需的内存。 如果元素包含一个值，Visual Basic 会将其初始化为其数据类型的默认值。 有关详细信息，请参阅[Dim 语句](../../language-reference/statements/dim-statement.md)中的"行为"。

您可以为其声明的一部分为变量分配初始值，如下例所示。

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

如果变量是对象变量，则可以在使用[New 运算符](../../../visual-basic/language-reference/operators/new-operator.md)关键字声明其类时显式创建其类的实例，如下例所示。

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

请注意，在执行到达其声明语句之前，声明语句中指定的初始值不会分配给变量。 在此之前，变量包含其数据类型的默认值。

## <a name="executable-statements"></a>可执行语句

可执行语句执行操作。 它可以调用过程、分支到代码中的另一个位置、循环访问多个语句或计算表达式。 赋值语句是可执行语句的特殊情况。

下面的示例使用`If...Then...Else`控件结构根据变量的值运行不同的代码块。 在每个代码块中，循环`For...Next`运行指定的次数。

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

上`If`例中的语句检查 参数`clockwise`的值 。 如果值为`True`，则调用`spinClockwise`方法`aWidget`。 如果值为`False`，则调用`spinCounterClockwise`方法`aWidget`。 控制`If...Then...Else`结构以`End If`结尾。

每个`For...Next`块中的循环调用适当的方法的次数等于`revolutions`参数的值。

## <a name="assignment-statements"></a>分配语句

分配语句执行赋值操作，其中包括获取赋值运算符 （`=`） 右侧的值并将其存储在左侧的元素中，如以下示例所示。

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

在前面的示例中，赋值语句在变量`v`中存储文本值 42。

### <a name="eligible-programming-elements"></a>合格的编程元素

赋值运算符左侧的编程元素必须能够接受并存储值。 这意味着它必须是一个变量或属性，它不是[ReadOnly，](../../../visual-basic/language-reference/modifiers/readonly.md)或者它必须是数组元素。 在赋值语句的上下文中，此类元素有时称为*lvalue，* 表示为"左值"。

赋值运算符右侧的值由表达式生成，表达式可以由文本、常量、变量、属性、数组元素、其他表达式或函数调用的任意组合组成。 下面的示例对此进行了演示。

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

前面的示例将变量`y`中持有的值添加到变量`z`中的值，然后添加调用 函数 返回的值。 `findResult` 然后，此表达式的总值存储在变量`x`中。

### <a name="data-types-in-assignment-statements"></a>赋值语句中的数据类型

除了数值之外，赋值运算符还可以分配`String`值，如下例所示。

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

您还可以使用`Boolean`文本或`Boolean`表达式`Boolean`分配值，如下例所示。

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

同样，您可以为`Char`的编程元素分配适当的值，`Date`或`Object`数据类型的编程元素。 还可以将对象实例分配给声明为创建该实例的类的元素。

### <a name="compound-assignment-statements"></a>复合赋值语句

*复合赋值语句*首先对表达式执行操作，然后再将其分配给编程元素。 下面的示例说明了这些运算符之一 ，`+=`该运算符将运算符左侧变量的值由右侧表达式的值递增。

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

前面的示例将 1 添加到`n`的值，然后将新值存储在 中。 `n` 它是以下语句的速记等效项：

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

可以使用此类运算符执行各种复合赋值操作。 有关这些运算符的列表及其的详细信息，请参阅[分配运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)。

串联赋值运算符 （`&=`） 可用于将字符串添加到现有字符串的末尾，如下例所示。

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>在分配语句中键入转换

分配给变量、属性或数组元素的值必须为适合该目标元素的数据类型。 通常，应尝试生成与目标元素相同的数据类型的值。 但是，某些类型可以在分配期间转换为其他类型的类型。

有关数据类型之间转换的信息，请参阅[可视化基本 中的"类型转换](./data-types/type-conversions.md)"。 简而言之，Visual Basic 会自动将给定类型的值转换为它扩展到的任何其他类型。 *加宽转换*是始终在运行时成功且不会丢失任何数据的转换。 例如，Visual `Integer` Basic 将值转换为适当`Double`值，因为`Integer`范围将扩大为`Double`。 有关详细信息，请参阅 [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md)。

*缩小转换*（未扩大的转换）有在运行时失败或数据丢失的风险。 您可以使用类型转换函数显式执行缩小转换，也可以通过设置`Option Strict Off`来指示编译器隐式执行所有转换。 有关详细信息，请参阅[隐式和显式转换](./data-types/implicit-and-explicit-conversions.md)。

## <a name="putting-multiple-statements-on-one-line"></a>将多个语句放在一行上

单行上的多个语句由冒号 （`:`） 字符分隔。 下面的示例对此进行了演示。

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

虽然偶尔方便，但这种语法形式使代码难以阅读和维护。 因此，建议您将一个语句保留为一行。

## <a name="continuing-a-statement-over-multiple-lines"></a>在多行上继续语句

语句通常适合一行，但当太长时，可以使用行延续序列将其延续到下一行上，该序列由空格后跟下划线字符 （`_`） 后跟回车符组成。 在下面的示例中，`MsgBox`可执行语句在两行上继续。

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>隐式行延续

在许多情况下，您可以在下一条连续行上继续语句，而无需使用下划线字符 （`_`。 以下语法元素隐式地继续下一行代码上的语句。

- 逗号后 （`,`。 例如：

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- 开放括号后 （`(`） 或关闭括号之前 （`)`） 例如：

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- 打开大括号 （`{`） 后或关闭大括号 （`}`） 之前。 例如：

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    有关详细信息，请参阅[对象初始化器：命名和匿名类型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)或[集合初始化器](./collection-initializers/index.md)。

- 在 XML 文本中`<%=`打开的嵌入表达式 （ ） 之后`%>`或嵌入表达式 （ ） 关闭之前。 例如：

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   有关详细信息，请参阅[XML 中的嵌入式表达式](./xml/embedded-expressions-in-xml.md)。

- 串联运算符后 （`&`。 例如：

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。

- 分配运算符后`=`（、 `:=` `&=` `+=`、 `-=` `*=`、 `/=` `\=`、 `^=` `<<=`、 `>>=`、 、 、 、 、 、 、 、 例如：

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。

- After binary operators (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) within an expression. 例如：

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。

- 和`Is``IsNot`运算符之后。 例如：

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。

- 在成员限定符之后`.`（ ） 和成员名称之前。 例如：

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   但是，当您在类型的初始化列表中使用语句或`_`提供值时，`With`必须在成员限定符字符之后包含行延续字符 （ ）。 使用`=``With`语句或对象初始化列表时，请考虑在赋值运算符（例如）之后中断行。 例如：

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   有关详细信息，请参阅[...结尾与语句](../../../visual-basic/language-reference/statements/with-end-with-statement.md)或[对象初始化器：命名和匿名类型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)。

- 在 XML 轴属性限定`.`符`.@` `...`（ 或 ） 之后。 但是，在使用 关键字时指定成员限定符`_`时，`With`必须包含行延续字符 （ ）。 例如：

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   有关详细信息，请参阅[XML 轴属性](../../../visual-basic/language-reference/xml-axis/index.md)。

- 指定属性时，小于符号 （<） 后或大于符号 （`>`） 之前。 指定属性时，在大于符号`>`（ ） 之后。 但是，在指定装配体级或模块级属性`_`时，必须包含一个线延续字符 （ 。 例如：

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   有关详细信息，请参阅[属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)。

- 查询运算符（、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、`Aggregate` `Distinct` `From` `Group By` `Group Join` `Join` `Let` `Order By` `Select` `Skip` `Skip While` `Take` `Take While` `Where` `In` `Into` `On` `Ascending` `Descending` 不能在`Order By`由多个关键字 （、、`Group Join``Take While`和`Skip While`） 组成的查询运算符的关键字之间换行。 例如：

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   有关详细信息，请参阅[查询](../../../visual-basic/language-reference/queries/index.md)。

- 语句中的`In``For Each`关键字之后。 例如：

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   有关详细信息，请参阅[每个...下一个语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md).

- 在`From`集合初始化器中的关键字之后。 例如：

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   有关详细信息，请参阅[集合初始值设定项](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)。

## <a name="adding-comments"></a>添加注释

源代码并不总是不言自明的，即使是编写源代码的程序员也是如此。 因此，为了帮助记录他们的代码，大多数程序员都自由使用嵌入式注释。 代码中的注释可以向以后阅读或使用它的人解释过程或特定指令。 Visual Basic 在编译过程中忽略注释，它们不会影响编译的代码。

注释行以撇号开头或`'``REM`后跟空格。 它们可以添加到代码中的任意位置，但字符串中除外。 若要在语句上附加注释，请插入撇号或`REM`语句后，然后插入注释。 注释也可以单独行。 下面的示例演示了这些可能性。

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>检查编译错误

如果在键入一行代码后，行以波浪蓝色下划线显示（也可能显示错误消息），则语句中存在语法错误。 您必须找出该语句的问题所在（通过查看任务列表，或用鼠标指针悬停在错误上并读取错误消息），并更正它。 在修复代码中的所有语法错误之前，程序将无法正确编译。

## <a name="related-sections"></a>相关章节

|术语|定义|
|---|---|
|[赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)|提供指向语言参考页的链接，这些页涵盖赋`=`值`*=`运算符（`&=`如 ）和 。|
|[运算符和表达式](./operators-and-expressions/index.md)|演示如何将元素与运算符组合以生成新值。|
|[如何：在代码中拆分和合并语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|演示如何将单个语句分成多行，以及如何在同一行上放置多个语句。|
|[如何：标记语句](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|演示如何标记代码行。|
