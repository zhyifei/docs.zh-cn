---
title: If...Then...Else 语句
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
ms.openlocfilehash: f505755caeb9cc3cfeeb1ba83b6de15f48314103
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351160"
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

本文包含一些示例，这些示例演示了 `If`...`Then`...`Else` 语句的用法：

- [多行语法示例](#multi-line)
- [嵌套语法示例](#nested)
- [单行语法示例](#single-line)

## <a name="parts"></a>部件

`condition` \
必需。 表达式. 的计算结果必须为 `True` 或 `False`或可隐式转换为 `Boolean`的数据类型。

如果表达式是可[为 null 的可为 null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)的 `Boolean`[变量，则](../../../visual-basic/language-reference/nothing.md)将条件视为 `False`的表达式，如果存在 `ElseIf` 块，则将对其进行计算; 如果存在，则执行 `Else` 块。

`Then` \
在单行语法中为必需;在多行语法中是可选的。

`statements` \
可选。 后面`If`的一个或多个语句 ...如果计算结果为`Then`，则执行。 `condition` `True`

`elseifcondition` \
如果 `ElseIf` 存在，则为必需。 表达式. 的计算结果必须为 `True` 或 `False`或可隐式转换为 `Boolean`的数据类型。

`elseifstatements` \
可选。 后面`ElseIf`的一个或多个语句 ...如果计算结果为`Then`，则执行。 `elseifcondition` `True`

`elsestatements` \
可选。 如果以前的 `condition` 或 `elseifcondition` 表达式的计算结果不为 `True`，则执行的一个或多个语句。

`End If` \
终止 `If`...`Then`...`Else` 块的多行版本。

## <a name="remarks"></a>备注

### <a name="multiline-syntax"></a>多行语法

如果遇到 `If``Then`...`Else` 语句，则 `condition` 进行测试。 如果 `True``condition`，则将执行 `Then` 后面的语句。 如果 `False``condition`，则按顺序计算每个 `ElseIf` 语句（如果有）。 如果找到 `True` `elseifcondition`，则将执行紧随关联的 `ElseIf` 后面的语句。 如果 `elseifcondition` 的计算结果不为 `True`，或者没有 `ElseIf` 语句，则将执行 `Else` 后的语句。 执行以下语句后 `Then`、`ElseIf`或 `Else`，将继续执行 `End If`后的语句。

`ElseIf` 和 `Else` 子句都是可选的。 您可以根据需要在 `If`...`Then`...`Else` 语句中包含任意数量的 `ElseIf` 子句，但 `ElseIf` 子句之后不能出现 `Else` 子句。 `If`...`Then``Else` 语句可以相互嵌套。

在多行语法中，`If` 语句必须是第一行中的唯一语句。 `ElseIf`、`Else`和 `End If` 语句前面只能有一个行标签。 `If``Then`...`Else` 块必须以 `End If` 语句结束。

> [!TIP]
> [Select .。。](../../../visual-basic/language-reference/statements/select-case-statement.md)当你评估具有多个可能值的单个表达式时，Case 语句可能更有用。

### <a name="single-line-syntax"></a>单行语法

对于一个条件，可以使用单行语法，如果该条件为 true，则执行代码。 不过，多行语法提供更多的结构和灵活性，更易于读取、维护和调试。

将检查 `Then` 关键字后面的内容，以确定语句是否为单行 `If`。 如果在同一行 `Then` 之后出现注释以外的任何内容，则该语句将被视为单行 `If` 语句。 如果 `Then` 不存在，则它必须是多行 `If`...`Then``Else`的开头。

在单行语法中，可以将多个语句作为 `If``Then` 决策的结果来执行。 所有语句必须位于同一行上，并由冒号分隔。

## <a name="multiline-syntax-example"></a>多行语法示例

<a name="multi-line"></a>

下面的示例演示如何使用 `If`...`Then`...`Else` 语句的多行语法。

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>嵌套语法示例

<a name="nested"></a>

下面的示例包含嵌套的 `If`...`Then`...`Else` 语句。

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>单行语法示例

<a name="single-line"></a>下面的示例演示单行语法的用法。

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Select...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [嵌套的控件结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [决策结构](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Visual Basic 中的逻辑运算符和位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [If 运算符](../../../visual-basic/language-reference/operators/if-operator.md)
