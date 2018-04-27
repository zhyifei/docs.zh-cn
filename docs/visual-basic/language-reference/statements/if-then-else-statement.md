---
title: If...Then...Else 语句 (Visual Basic)
ms.date: 04/16/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: conceptual
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
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1080a17cfcc493175c1e2f3527837030b4254bc2
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="ifthenelse-statement-visual-basic"></a>If...Then...Else 语句 (Visual Basic)
根据表达式的值有条件地执行一组语句。  
  
## <a name="syntax"></a>语法  
  
```  
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

## <a name="quick-links-to-example-code"></a>指向代码示例的快速链接

本文包括几个示例演示使用`If`...`Then`...`Else`语句：

* [多行的语法示例](#multi-line)
* [嵌套的语法示例](#nested)
* [单行语法示例](#single-line)

## <a name="parts"></a>部件  
 `condition`  
 必须的。 表达式。 计算结果必须为`True`或`False`，或隐式转换为的数据类型`Boolean`。  
  
 如果表达式为[可以为 Null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean`变量计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)，条件将被视为表达式是`False`和`Else`执行块。  
  
 `Then`  
 中的单行语法; 所需在多行的语法中可选。  
  
 `statements`  
 可选。 一个或多个语句以下`If`...`Then`如果将执行该`condition`计算结果为`True`。  
  
 `elseifcondition`  
 如果存在`ElseIf`存在。 表达式。 计算结果必须为`True`或`False`，或隐式转换为的数据类型`Boolean`。  
  
 `elseifstatements`  
 可选。 一个或多个语句以下`ElseIf`...`Then`如果将执行该`elseifcondition`计算结果为`True`。  
  
 `elsestatements`  
 可选。 如果不再具有以前执行的一个或多个语句`condition`或`elseifcondition`表达式计算结果为`True`。  
  
 `End If`  
 终止的多行版本`If`...`Then`...`Else`块。  
  
## <a name="remarks"></a>备注  
  
### <a name="multiline-syntax"></a>多行的语法  
 当`If`...`Then`...`Else`遇到语句时，`condition`测试。 如果`condition`是`True`，后面的语句`Then`执行。 如果`condition`是`False`，每个`ElseIf`语句 （如果有的话） 顺序计算。 当`True``elseifcondition`找到，紧跟在关联的语句`ElseIf`执行。 如果没有`elseifcondition`计算结果为`True`，或者是否有任何`ElseIf`，以下语句`Else`执行。 执行后面的语句后`Then`， `ElseIf`，或`Else`，继续后面的语句执行`End If`。  
  
 `ElseIf`和`Else`子句都是可选。 你可以作为许多`ElseIf`根据需要`If`...`Then`...`Else`语句，但不是`ElseIf`子句可以出现后`Else`子句。 `If`...`Then`...`Else`语句可以相互嵌套。  
  
 在多行的语法中，`If`语句必须是第一个行的唯一语句。 `ElseIf`， `Else`，和`End If`语句仅可以前面的行标签。 `If`...`Then`...`Else`块必须以结束`End If`语句。  
  
> [!TIP]
>  [选择...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)计算有几个可能值的单个表达式时可能会更有用。  
  
### <a name="single-line-syntax"></a>单行语法  
 可以针对单个条件，代码使用的单行语法执行如果为 true。 但是，多个行语法提供了多个结构和灵活性，并且可以更轻松地读取、 维护和调试。  
  
 哪些如下所示`Then`关键字将检查以确定语句是否是单线条`If`。 如果注释之外的任何内容出现在`Then`上同一行中，该语句将被视为单线条`If`语句。 如果`Then`不存在，它必须是多个行的开头`If`...`Then`...`Else`.  
  
 在单行语法中，你可以有多个语句的结果作为执行`If`...`Then`决策。 所有语句必须是同一行上，并且由冒号分隔。  

## <a name="multiline-syntax-example"></a>多行的语法示例

<a name="multi-line"></a>
 
 下面的示例演示如何使用的多行的语法`If`...`Then`...`Else`语句。  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb?highlight=11,14,17,19)]

## <a name="nested-syntax-example"></a>嵌套的语法示例

<a name="nested"></a>

 下面的示例包含嵌套`If`...`Then`...`Else`语句。  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb?highlight=14,15,17,19,20,21,23,25,26,28)]

## <a name="single-line-syntax-example"></a>单行语法示例
  
<a name="single-line"></a> 下面的示例演示如何使用单线条语法。  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb?highlight=18)]
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Select...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [嵌套的控件结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [决策结构](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [在 Visual Basic 中的逻辑和按位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [If 运算符](../../../visual-basic/language-reference/operators/if-operator.md)
