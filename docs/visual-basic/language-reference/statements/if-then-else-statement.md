---
title: If...Then...Else 语句 (Visual Basic)
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: db81a1c41809b563d5f9d0777c3feb064c5e540b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400712"
---
# <a name="ifthenelse-statement-visual-basic"></a>If...Then...Else 语句 (Visual Basic)

根据表达式的值有条件地执行一组语句。

## <a name="syntax"></a>语法

```vb
' Multiline syntax:
If condition [ Then ]
    [ statements ]
[ ElseIf elseifcondition [ Then ]
    [ elseifstatements ] ]
[ Else
    [ elsestatements ] ]
End If

' Single-line syntax:
If condition Then [ statements ] [ Else [ elsestatements ] ]
```

## <a name="quick-links-to-example-code"></a>示例代码的快速链接

本文包含一些示例，这些示例演示了`If`.。。`Then`...`Else`语句：

- [多行语法示例](#multi-line)
- [嵌套语法示例](#nested)
- [单行语法示例](#single-line)

## <a name="parts"></a>部件

`condition` \
必需。 表达式. 的计算结果`True`必须`False`为或，或者是可隐式转换为`Boolean`的数据类型。

如果该表达式是一个计算结果为 " [Nothing](../../../visual-basic/language-reference/nothing.md)" 的[可以为 null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean`的变量，则该条件`False`将被视为`ElseIf` "表达式"，并在它们存在的`Else`情况下计算块，或者块是如果它存在，则执行。

`Then` \
在单行语法中为必需;在多行语法中是可选的。

`statements` \
可选。 后面`If`的一个或多个语句 .。。如果计算结果为`True`，则执行。 `condition` `Then`

`elseifcondition` \
如果`ElseIf`存在，则为必需。 表达式. 的计算结果`True`必须`False`为或，或者是可隐式转换为`Boolean`的数据类型。

`elseifstatements` \
可选。 后面`ElseIf`的一个或多个语句 .。。如果计算结果为`True`，则执行。 `elseifcondition` `Then`

`elsestatements` \
可选。 如果上`condition` `elseifcondition`一个或表达式的计算结果为`True`，则执行的一个或多个语句。

`End If` \
终止的`If`多行版本 .。。`Then`...`Else`块。

## <a name="remarks"></a>备注

### <a name="multiline-syntax"></a>多行语法

`If`当 .。。`Then`...语句时， `condition`将对其进行测试。 `Else` 如果`condition` `Then`为`True`，则执行以下语句。 如果`condition` `ElseIf`为`False`，则按顺序对每个语句（如果有）进行求值。 找到后，将执行紧随关联`ElseIf`的后面的语句。 `True` `elseifcondition` 如果计算`elseifcondition`结果不`True`为， `ElseIf`或者没有语句，则将执行下面`Else`的语句。 执行完后的语句`Then` `ElseIf` `Else`后，将继续执行后面`End If`的语句。

`ElseIf` 和`Else`子句均可选。 你可以`ElseIf` `If`在 ... 中包含任意数量的子句`Then`...语句后， `Else`子句`ElseIf`中不能出现子句。 `Else` `If`...`Then`...`Else`语句可以相互嵌套。

在多行语法中， `If`语句必须是第一行中的唯一语句。 `ElseIf`、和语句`End If`前面只能有一个行标签。 `Else` `If`.。。`Then`...`Else`块必须`End If`以语句结束。

> [!TIP]
> [Select .。。](../../../visual-basic/language-reference/statements/select-case-statement.md)当你评估具有多个可能值的单个表达式时，Case 语句可能更有用。

### <a name="single-line-syntax"></a>单行语法

对于一个条件，可以使用单行语法，如果该条件为 true，则执行代码。 不过，多行语法提供更多的结构和灵活性，更易于读取、维护和调试。

检查关键字后面`Then`的内容，以确定语句是否为单行`If`语句。 如果在同一行之后`Then`出现注释以外的任何内容，则该语句将被视为单行`If`语句。 如果`Then`不存在，则必须为多行`If`的开头 .。。`Then`...`Else`.

在单行语法中，你可以将多个语句作为`If`.。。`Then`决策。 所有语句必须位于同一行上，并由冒号分隔。

## <a name="multiline-syntax-example"></a>多行语法示例

<a name="multi-line"></a>

下面的示例演示如何使用的多行语法`If`。`Then`...`Else`语句。

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>嵌套语法示例

<a name="nested"></a>

下面的示例包含嵌套`If`.。。`Then`...`Else`语句。

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>单行语法示例

<a name="single-line"></a>下面的示例演示单行语法的用法。

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Select...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [嵌套的控件结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [决策结构](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Visual Basic 中的逻辑运算符和位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [If 运算符](../../../visual-basic/language-reference/operators/if-operator.md)
