---
title: 语句 (Visual Basic)
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
ms.openlocfilehash: e66acae5e98d561883f4ad59853dfd862c8ebfee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946453"
---
# <a name="statements-in-visual-basic"></a>语句 (Visual Basic)

在 Visual Basic 中的语句是完整的指令。 它可以包含关键字、 运算符、 变量、 常量和表达式。 每个语句都属于以下类别之一：

- **声明语句**，其中命名变量、 常量或过程中，并还可以指定数据类型。

- **可执行语句**，它启动操作。 这些语句可以调用的方法或函数，并且它们可以循环或分支的代码块。 可执行语句包括**赋值语句**，其中将一个值或表达式分配给变量或常量。

本主题介绍每个类别。 此外，本主题介绍如何组合在单个行上的多个语句以及如何通过多个线路 continue 语句。

## <a name="declaration-statements"></a>声明语句

使用声明语句进行命名和定义过程、 变量、 属性、 数组和常量。 声明编程元素时，您还可以定义其数据类型、 访问级别和作用域。 有关详细信息，请参阅[声明元素的特性](./declared-elements/declared-element-characteristics.md)。

下面的示例包含三个声明。

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

第一个声明是`Sub`语句。 以及其匹配`End Sub`语句，它声明一个名为过程`applyFormat`。 它还指定`applyFormat`是`Public`，这意味着可以引用它的任何代码可以调用它。

第二个声明`Const`语句，用于声明常量`limit`，并指定`Integer`数据类型和 33 的值。

第三个声明是`Dim`语句，用于声明变量`thisWidget`。 数据类型是特定对象，即从创建对象`Widget`类。 您可以声明为具有任何基本数据类型，或在您使用的应用程序中公开的任何对象类型的变量。

### <a name="initial-values"></a>初始值

包含声明语句的代码运行时，Visual Basic 会保留已声明元素所需的内存。 如果该元素具有一个值，则 Visual Basic 会将它初始化为其数据类型的默认值。 详细信息，请参阅"行为"中[Dim 语句](../../language-reference/statements/dim-statement.md)。

如以下示例所示，您可以将初始值分配给一个变量，作为其声明的一部分。

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

如果变量是对象变量，可以显式创建它的类的实例时通过使用声明[New 运算符](../../../visual-basic/language-reference/operators/new-operator.md)关键字，如下面的示例说明了。

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

请注意直到执行到达的声明语句，在声明语句中指定的初始值未分配给一个变量。 在此之前，该变量包含其数据类型的默认值。

## <a name="executable-statements"></a>可执行语句

一个可执行语句执行的操作。 它可以调用的过程，在代码中，只需遍历多个语句的另一个位置的分支或计算的表达式。 赋值语句是一种特殊情况的一个可执行语句。

下面的示例使用`If...Then...Else`控制结构来运行不同的变量的值所基于的代码块。 在每个代码块中，`For...Next`循环运行指定的次数。

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

`If`前面的示例中的语句将检查参数的值`clockwise`。 如果值为`True`，它将调用`spinClockwise`方法的`aWidget`。 如果值为`False`，它将调用`spinCounterClockwise`方法的`aWidget`。 `If...Then...Else`控制结构结尾`End If`。

`For...Next`循环中每个块调用适当的方法数乘以的值相等`revolutions`参数。

## <a name="assignment-statements"></a>赋值语句

赋值语句执行分配操作，包括获取赋值运算符右侧的值 (`=`) 并将其存储在左侧，如以下示例所示的元素中。

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

在前面的示例中，在赋值语句将存储在变量中的文本值 42 `v`。

### <a name="eligible-programming-elements"></a>符合条件的编程元素

赋值运算符左侧的编程元素必须能够接受并存储的值。 这意味着它必须是变量或属性不是[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)，必须为数组元素。 在赋值语句的上下文中，有时称为这样的元素*左值*，"左值。"

赋值运算符右侧的值生成一个表达式，其可以包含文本、 常量、 变量、 属性、 数组元素、 其他表达式或函数调用的任意组合。 下面的示例阐释了这一点。

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

前面的示例将添加在变量中保存的值`y`变量中保存的值为`z`，然后添加对函数的调用返回的值`findResult`。 此表达式的总值然后存储在变量`x`。

### <a name="data-types-in-assignment-statements"></a>赋值语句中的数据类型

除数值外，还可以将赋值运算符`String`值，如以下示例所示。

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

你还可以分配`Boolean`值，使用`Boolean`文字或`Boolean`表达式，如下面的示例将说明。

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

同样，将适当的值分配到的编程元素`Char`， `Date`，或`Object`数据类型。 此外可以声明为从其创建该实例的类的元素分配对象实例。

### <a name="compound-assignment-statements"></a>复合赋值语句

*复合赋值语句*首先执行的操作之前将其分配到编程元素中的表达式。 下面的示例说明了这些运算符之一`+=`，右侧表达式的值的运算符左侧的变量值时都会增加。

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

前面的示例将 1 添加到的值`n`，然后将存储在该新值`n`。 它是一种速记属性等效于以下语句：

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

可以使用此类型的运算符执行多种不同的复合赋值操作。 有关这些运算符和相关的详细信息的列表，请参阅[赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)。

串联赋值运算符 (`&=`) 可用于将字符串添加到现有的末尾字符串，如以下示例所示。

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>赋值语句中的类型转换

适用于该目标元素的数据类型必须是将分配给变量、 属性或数组元素的值。 一般情况下，应尝试生成相同的数据类型与目标元素的值。 但是，某些类型可以在分配期间转换为其他类型中。

有关数据类型之间进行转换的信息，请参阅[在 Visual Basic 中的类型转换](./data-types/type-conversions.md)。 简单地说，Visual Basic 会自动将给定类型的值转换为其扩大的任何其他类型。 一个*扩大转换*是中的一个始终在运行时成功，不会丢失任何数据。 例如，Visual Basic 将转换`Integer`值设为`Double`在适当的时候，因为`Integer`加宽到`Double`。 有关详细信息，请参阅 [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md)。

*收缩转换*（那些不扩大转换） 执行的运行时，在发生故障或数据丢失的风险。 您可以通过使用类型转换函数，显式执行收缩转换或可以指示编译器通过设置隐式执行所有转换`Option Strict Off`。 有关详细信息，请参阅[隐式转换和显式转换](./data-types/implicit-and-explicit-conversions.md)。

## <a name="putting-multiple-statements-on-one-line"></a>将多个语句放在同一行

在由冒号分隔的单一行中可以有多个语句 (`:`) 字符。 下面的示例阐释了这一点。

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

虽然偶尔带来方便，则这种形式的语法使代码难以阅读和维护。 因此，建议您保留到行的一条语句。

## <a name="continuing-a-statement-over-multiple-lines"></a>跨多行继续一条语句

语句通常可以在一行，但太长时，您可以继续其在使用行继续符序列，其中包括空格和下划线字符的下一行 (`_`) 后跟回车符。 在以下示例中，`MsgBox`可执行语句连续超过两行。

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>隐式行继续符

在许多情况下，你可以继续语句在下一步的后续行而无需使用下划线字符 (`_`)。 在下一行代码中的以下语法元素隐式继续该语句。

- 逗号 (`,`)。 例如：

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- 左括号之后 (`(`) 或右括号之前 (`)`)。 例如：

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- 在左大括号 (`{`) 或右大括号前 (`}`)。 例如：

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    有关详细信息，请参阅[对象初始值设定项：命名和匿名类型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)或[集合初始值设定项](./collection-initializers/index.md)。

- 后一种开放嵌入式表达式 (`<%=`) 或嵌入式表达式结束之前 (`%>`) 在 XML 文本中。 例如：

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   有关详细信息，请参阅[XML 中的嵌入式表达式](./xml/embedded-expressions-in-xml.md)。

- 串联运算符后 (`&`)。 例如：

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   有关详细信息，请参阅[运算符按功能列出](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。

- 在赋值运算符 (`=`， `&=`， `:=`， `+=`， `-=`， `*=`， `/=`， `\=`， `^=`， `<<=`， `>>=`)。 例如：

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   有关详细信息，请参阅[运算符按功能列出](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。

- 在二元运算符 (`+`， `-`， `/`， `*`， `Mod`， `<>`， `<`， `>`， `<=`， `>=`， `^`， `>>`，`<<`， `And`， `AndAlso`， `Or`， `OrElse`， `Like`， `Xor`) 表达式中。 例如：

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   有关详细信息，请参阅[运算符按功能列出](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。

- 之后`Is`和`IsNot`运算符。 例如：

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   有关详细信息，请参阅[运算符按功能列出](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。

- 成员的限定符字符后 (`.`) 和成员名称前。 例如：

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   但是，您必须包含行继续符 (`_`) 时使用以下成员的限定符字符`With`语句或提供一种类型的初始化列表中的值。 请考虑之后赋值运算符换行 (例如， `=`) 使用时`With`语句或对象初始化列表。 例如：

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   有关详细信息，请参阅[使用...使用语句结束](../../../visual-basic/language-reference/statements/with-end-with-statement.md)或[对象初始值设定项：命名和匿名类型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)。

- XML 轴属性限定符后 (`.`或`.@`或`...`)。 但是，您必须包含行继续符 (`_`) 在使用时，指定成员限定符的时`With`关键字。 例如：

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   有关详细信息，请参阅[XML 轴属性](../../../visual-basic/language-reference/xml-axis/index.md)。

- 在小于-号 (<) 或更高版本之前的登录比 (`>`) 指定属性时。 此外后更高版本的登录比 (`>`) 指定属性时。 但是，您必须包含行继续符 (`_`) 指定程序集级别或模块级属性时。 例如：

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   有关详细信息，请参阅[的特性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)。

- 之前和之后查询运算符 (`Aggregate`， `Distinct`， `From`， `Group By`， `Group Join`， `Join`， `Let`， `Order By`， `Select`， `Skip`， `Skip While`， `Take`， `Take While`， `Where`， `In`， `Into`， `On`， `Ascending`，和`Descending`)。 不能中断的组成的多个关键字的查询运算符关键字之间的行 (`Order By`， `Group Join`， `Take While`，和`Skip While`)。 例如：

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   有关详细信息，请参阅[查询](../../../visual-basic/language-reference/queries/index.md)。

- 之后`In`中的关键字`For Each`语句。 例如：

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   有关详细信息，请参阅[为每个...下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)。

- 之后`From`集合初始值设定项中的关键字。 例如：

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   有关详细信息，请参阅[集合初始值设定项](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)。

## <a name="adding-comments"></a>添加注释

源代码并不总是很容易理解，甚至对程序员而言。 为了帮助说明其代码，因此，大多数编程人员可以自由利用嵌入的注释。 在代码中的注释可以解释的过程或任何人读取或更高版本使用它的特定指令。 Visual Basic 在编译期间，将忽略注释，它们不会影响已编译的代码。

注释行开头撇号 (`'`) 或`REM`跟一个空格。 可以将它们添加任意位置在代码中，除字符串中。 要追加到一条语句注释，插入一个撇号或`REM`后面添加注释的语句之后。 注释还可以在其自己单独的行上。 下面的示例演示了各种选项。

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>检查编译错误

如果键入一行代码后，该行显示的蓝色波浪下划线 （也可能会显示一条错误消息），则语句中有语法错误。 必须了解什么是错误的语句 （通过在任务列表中，查找或悬停鼠标指针错误和读取的错误消息） 并更正它。 在代码中修复所有语法错误，直到你的程序将无法正确编译。

## <a name="related-sections"></a>相关章节

|术语|定义|
|---|---|
|[赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)|提供一些链接，如涉及赋值运算符的语言参考页`=`， `*=`，和`&=`。|
|[运算符和表达式](./operators-and-expressions/index.md)|演示如何组合元素和运算符以生成新值。|
|[如何：在代码中拆分和合并语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|演示如何拆分为多行的一条语句以及如何将多个语句置于同一行上。|
|[如何：标记语句](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|演示如何标记代码行。|
