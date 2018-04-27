---
title: 语句 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: beb33b8f2c30723158e41244cbb5c9cfca108a53
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="statements-in-visual-basic"></a>语句 (Visual Basic)
在 Visual Basic 中的语句是完整的指令。 它可以包含关键字、 运算符、 变量、 常量和表达式。 每个语句都属于以下类别之一：  
  
-   **声明语句**，其中命名变量、 常量或过程，并还可以指定数据类型。  
  
-   **可执行语句**，该启动操作。 这些语句可以调用的方法或函数，并且它们可以循环或分支的代码块。 可执行语句包括**赋值语句**，这将分配的值或表达式，并为变量或常量。  
  
 本主题介绍每个类别。 此外，本主题介绍如何合并多个语句在单独的行以及如何通过多个线路继续一条语句。  
  
## <a name="declaration-statements"></a>声明语句  
 使用声明语句进行命名和定义过程、 变量、 属性、 数组和常量。 在声明编程元素时，你还可以定义其数据类型、 访问级别和作用域。 有关详细信息，请参阅[声明元素的特性](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)。  
  
 下面的示例包含三个声明。  
  
 [!code-vb[VbVbalrStatements#80](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_1.vb)]  
  
 第一个声明是`Sub`语句。 以及其匹配`End Sub`语句，它声明一个名为的过程`applyFormat`。 它还指定`applyFormat`是`Public`，这意味着，任何可以引用它的代码可以调用它。  
  
 第二个声明`Const`语句，声明常量`limit`，并指定`Integer`数据类型和值的 33。  
  
 第三个声明是`Dim`语句，它声明了变量`thisWidget`。 数据类型的特定对象，即从创建对象`Widget`类。 你可以声明任何的变量基本数据类型或为在你使用的应用程序中公开任意对象类型。  
  
### <a name="initial-values"></a>初始值  
 包含声明语句的代码运行时，Visual Basic 将保留已声明的元素所需的内存。 如果该元素具有一个值，则 Visual Basic 会将它初始化为其数据类型的默认值。 有关详细信息，请参阅"行为" [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。  
  
 如下面的示例所示，你可以将初始值分配给一个变量，作为其声明的一部分。  
  
 [!code-vb[VbVbalrStatements#81](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_2.vb)]  
  
 如果变量是一个对象变量，你可以通过使用声明时地显式创建其类的实例[New 运算符](../../../visual-basic/language-reference/operators/new-operator.md)关键字，如下面的示例演示。  
  
 [!code-vb[VbVbalrStatements#82](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_3.vb)]  
  
 请注意直到执行达到其声明语句，在声明语句中指定的初始值未分配给变量。 在此之前，该变量包含其数据类型的默认值。  
  
## <a name="executable-statements"></a>可执行语句  
 一个可执行语句执行一个操作。 它可以调用的过程，在代码中，循环访问的多条语句，另一个位置的分支，或计算表达式。 赋值语句是一种特殊情况的一个可执行语句。  
  
 下面的示例使用`If...Then...Else`控制结构运行不同的变量的值的代码块。 在每个代码块中，`For...Next`循环运行指定的次数。  
  
 [!code-vb[VbVbalrStatements#83](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_4.vb)]  
  
 `If`语句在前面的示例将检查参数的值`clockwise`。 如果值为`True`，它调用`spinClockwise`方法`aWidget`。 如果值为`False`，它调用`spinCounterClockwise`方法`aWidget`。 `If...Then...Else`控件结构结尾`End If`。  
  
 `For...Next`循环内每个块调用相应方法的次数等于的值`revolutions`参数。  
  
## <a name="assignment-statements"></a>赋值语句  
 赋值语句执行分配操作，包括获取赋值运算符右侧的值 (`=`) 并将其存储在左侧，如以下示例所示元素中。  
  
 [!code-vb[VbVbalrStatements#73](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_5.vb)]  
  
 在前面的示例中，赋值语句将存储在变量中的文本值 42 `v`。  
  
### <a name="eligible-programming-elements"></a>合格的编程元素  
 赋值运算符左侧的编程元素必须能够以接受并存储一个值。 这意味着它必须是变量或属性不是[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)，或它必须是一个数组元素。 在赋值语句的上下文中，此类元素有时称为*左值*，"左值。"  
  
 赋值运算符右侧的值由一个表达式，它可以包含文本、 常量、 变量、 属性、 数组元素、 其他表达式或函数调用的任意组合的生成。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbalrStatements#74](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_6.vb)]  
  
 前面的示例将值保存在变量中添加`y`到变量中保存的值`z`，然后添加对函数的调用返回的值`findResult`。 此表达式的总计值然后存储在变量`x`。  
  
### <a name="data-types-in-assignment-statements"></a>赋值语句中的数据类型  
 除了数值，赋值运算符还可以分配`String`值，如下面的示例所示。  
  
 [!code-vb[VbVbalrStatements#75](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_7.vb)]  
  
 你还可以分配`Boolean`值，使用`Boolean`文本或`Boolean`表达式，如下面的示例阐释了。  
  
 [!code-vb[VbVbalrStatements#76](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_8.vb)]  
  
 同样，可以将适当的值分配到的编程元素`Char`， `Date`，或`Object`数据类型。 你还可以为要从中创建该实例的类中声明的元素分配对象实例。  
  
### <a name="compound-assignment-statements"></a>复合赋值语句  
 *复合赋值语句*首先执行之前将其分配到编程元素中的表达式上的操作。 下面的示例阐释了这些运算符之一`+=`，右侧表达式的值上运算符左侧的变量的值时都会增加。  
  
 [!code-vb[VbVbalrStatements#77](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_9.vb)]  
  
 前面的示例将 1 添加到的值`n`，然后将存储在该新值`n`。 它是一种速记等效的以下语句：  
  
 [!code-vb[VbVbalrStatements#78](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_10.vb)]  
  
 可以使用此类型的运算符执行各种复合赋值操作。 有关这些运算符和有关它们的详细信息的列表，请参阅[赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)。  
  
 串联赋值运算符 (`&=`) 可用于将字符串添加到现有的末尾字符串，如下面的示例所示。  
  
 [!code-vb[VbVbalrStatements#79](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_11.vb)]  
  
### <a name="type-conversions-in-assignment-statements"></a>赋值语句中的类型转换  
 你将分配给变量、 属性或数组元素的值必须是适合于该目标元素的数据类型。 一般情况下，你应尝试生成与目标元素相同的数据类型的值。 但是，某些类型可以在分配期间转换为其他类型中。  
  
 有关数据类型之间进行转换的信息，请参阅[在 Visual Basic 中的类型转换](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)。 简单地说，Visual Basic 会自动将给定类型的值转换为其扩大的任何其他类型。 A*扩大转换*是一个程序中始终成功运行时，不会丢失任何数据。 例如，Visual Basic 会将转换`Integer`值赋给`Double`在适当的时候，因为`Integer`扩大到`Double`。 有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。  
  
 *收缩转换*（那些不扩大） 执行的运行时，在发生故障或数据丢失的风险。 你可以通过使用类型转换函数，显式执行收缩转换，或者你可以直接将编译器隐式执行所有转换，通过设置`Option Strict Off`。 有关详细信息，请参阅[隐式和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)。  
  
## <a name="putting-multiple-statements-on-one-line"></a>将多个语句放置在一个行  
 在用冒号分隔的单一行中可以有多个语句 (`:`) 字符。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbalrStatements#70](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_12.vb)]  
  
 虽然偶尔带来方便，因此这种形式的语法使代码更难读取和维护。 因此，建议你保留到行的一个语句。  
  
## <a name="continuing-a-statement-over-multiple-lines"></a>跨多行继续一条语句  
 语句通常符合在一行上，但太长时，你可以继续到下一步的行使用续行符序列，其中包括空格和下划线字符 (`_`) 跟回车符。 在下面的示例中，`MsgBox`可执行的语句将继续运行在两个行。  
  
 [!code-vb[VbVbalrStatements#71](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_13.vb)]  
  
### <a name="implicit-line-continuation"></a>隐式行继续标志  
 在许多情况下，可以在下一步的后续行 continue 语句，而无需使用下划线字符 (_)。 下表列出隐式在下一个代码行继续该语句的语法元素。  
  
|语法元素|示例|  
|---|---|  
|在逗号之后 (`,`)。|[!code-vb[VbVbalrLineContinuation#1](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_14.vb)]|  
|打开括号后 (`(`) 或右括号之前 (`)`)。|[!code-vb[VbVbalrLineContinuation#2](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_15.vb)]|  
|在左大括号后 (`{`) 或右大括号之前 (`}`)。|[!code-vb[VbVbalrLineContinuation#3](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_16.vb)]<br /><br /> 有关详细信息，请参阅[对象初始值设定项： 命名类型和匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)或[集合初始值设定项](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)。|  
|在打开后嵌入表达式 (`<%=`) 或之前的嵌入式表达式的关闭 (`%>`) 在 XML 文本。|[!code-vb[VbVbalrLineContinuation#4](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_17.vb)]<br /><br /> 有关详细信息，请参阅[XML 中的嵌入式表达式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。|  
|串联运算符之后 (`&`)。|[!code-vb[VbVbcnConventions#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_18.vb)]<br /><br /> 有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。|  
|赋值运算符后 (`=`， `&=`， `:=`， `+=`， `-=`， `*=`， `/=`， `\=`， `^=`， `<<=`， `>>=`)。|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br /><br /> 有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。|  
|二元运算符后 (`+`， `-`， `/`， `*`， `Mod`， `<>`， `<`， `>`， `<=`， `>=`， `^`， `>>`，`<<`， `And`， `AndAlso`， `Or`， `OrElse`， `Like`， `Xor`) 在表达式中。|[!code-vb[VbVbalrLineContinuation#7](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_20.vb)]<br /><br /> 有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。|  
|后`Is`和`IsNot`运算符。|[!code-vb[VbVbalrLineContinuation#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_21.vb)]<br /><br /> 有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。|  
|成员限定符字符之后 (`.`) 和之前的成员名称。 但是，必须包含以下成员限定符，当你使用行继续符 (_)`With`语句或提供一种类型的初始化列表中的值。 请考虑之后赋值运算符换行 (例如， `=`) 如果要使用`With`语句或对象初始化列表。|[!code-vb[VbVbalrLineContinuation#5](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_19.vb)]<br />[!code-vb[VbVbalrLineContinuation#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_22.vb)]<br /><br /> 有关详细信息，请参阅[与...使用语句结束](../../../visual-basic/language-reference/statements/with-end-with-statement.md)或[对象初始值设定项： 命名类型和匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)。|  
|XML 轴属性限定符后 (`.`或`.@`或`...`)。 但是，必须包括行继续符 (_)，当你使用指定的成员限定符时`With`关键字。|[!code-vb[VbVbalrLineContinuation#9](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_23.vb)]<br /><br /> 有关详细信息，请参阅[XML 轴属性](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)。|  
|在小于-号 (<) 或之前大于-号 (`>`) 时指定属性。 此外后大于-号 (`>`) 时指定属性。 但是，在指定程序集级别或模块级特性时必须包括行继续符 (_)。|[!code-vb[VbVbalrLineContinuation#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_24.vb)]<br /><br /> 有关详细信息，请参阅[的特性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)。|  
|之前和之后查询运算符 (`Aggregate`， `Distinct`， `From`， `Group By`， `Group Join`， `Join`， `Let`， `Order By`， `Select`， `Skip`， `Skip While`， `Take`， `Take While`， `Where`， `In`， `Into`， `On`， `Ascending`，和`Descending`)。 不能中断由组成的多个关键字的查询运算符关键字之间的连线 (`Order By`， `Group Join`， `Take While`，和`Skip While`)。|[!code-vb[VbVbalrLineContinuation#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_25.vb)]<br /><br /> 有关详细信息，请参阅[查询](../../../visual-basic/language-reference/queries/queries.md)。|  
|后`In`中的关键字`For Each`语句。|[!code-vb[VbVbalrLineContinuation#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_26.vb)]<br /><br /> 有关详细信息，请参阅[每个...下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)。|  
|后`From`集合初始值设定项中的关键字。|[!code-vb[VbVbalrLineContinuation#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/statements_27.vb)]<br /><br /> 有关详细信息，请参阅[集合初始值设定项](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)。|  
  
## <a name="adding-comments"></a>添加注释  
 源代码并不总是具有自我说明性，甚至到编写它的程序员。 若要帮助说明其代码，因此，大多数程序员来说请自由使用嵌入的注释。 过程或特定指令的读取或更高版本使用它的任何人都可以解释代码中的注释。 Visual Basic 中忽略注释在编译期间，并且不会影响已编译的代码。  
  
 注释行开头撇号 (`'`) 或`REM`跟一个空格。 它们都可添加任何位置在代码中，除字符串中。 要追加到一条语句的注释，插入撇号或`REM`后面添加注释的语句之后。 注释还可以在其自己单独的行上。 下面的示例演示这些可能的匹配项。  
  
 [!code-vb[VbVbalrStatements#72](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/statements_28.vb)]  
  
## <a name="checking-compilation-errors"></a>检查编译错误  
 如果键入的代码行后，该行显示有蓝色波浪下划线 （也会出现一条错误消息），则语句中有语法错误。 你必须找出错误的语句 （通过在任务列表中，查找或将鼠标悬停在带有鼠标指针的错误并读取错误消息），并更正它。 直到在代码中修复所有语法错误，程序将无法正确编译。  
  
## <a name="related-sections"></a>相关章节  
  
|术语|定义|  
|---|---|  
|[赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)|提供一些主题的链接，如涵盖赋值运算符的语言参考页`=`， `*=`，和`&=`。|  
|[运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)|演示如何组合元素和运算符以生成新值。|  
|[如何：在代码中拆分和合并语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|演示如何拆分为多行的单个语句以及如何在同一行上放置多个语句。|  
|[如何：标记语句](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|演示如何标记代码行。|
