---
title: "If...Then...Else 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 898b72055345e88ca35f805de211c0c57cd74200
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-statement-visual-basic"></a>If...Then...Else 语句 (Visual Basic)
根据表达式的值有条件地执行一组语句。  
  
## <a name="syntax"></a>语法  
  
```  
' Multiple-line syntax:  
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
  
## <a name="parts"></a>部件  
 `condition`  
 必需。 表达式。 计算结果必须为`True`或`False`，或隐式转换为的数据类型`Boolean`。  
  
 如果表达式为[可以为 Null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean`变量计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)，条件将被视为的表达式不是`True`，和`Else`块是执行。  
  
 `Then`  
 中的单行语法; 所需在多个行的语法中可选。  
  
 `statements`  
 可选。 一个或多个语句以下`If`...`Then`如果将执行该`condition`计算结果为`True`。  
  
 `elseifcondition`  
 如果存在`ElseIf`存在。 表达式。 计算结果必须为`True`或`False`，或隐式转换为的数据类型`Boolean`。  
  
 `elseifstatements`  
 可选。 一个或多个语句以下`ElseIf`...`Then`如果将执行该`elseifcondition`计算结果为`True`。  
  
 `elsestatements`  
 可选。 如果不再具有以前执行的一个或多个语句`condition`或`elseifcondition`表达式计算结果为`True`。  
  
 `End If`  
 终止`If`...`Then`...`Else`块。  
  
## <a name="remarks"></a>备注  
  
## <a name="multiple-line-syntax"></a>多个行语法  
 当`If`...`Then`...`Else`遇到语句时，`condition`测试。 如果`condition`是`True`，后面的语句`Then`执行。 如果`condition`是`False`，每个`ElseIf`语句 （如果有的话） 顺序计算。 当`True``elseifcondition`找到，紧跟在关联的语句`ElseIf`执行。 如果没有`elseifcondition`计算结果为`True`，或者是否有任何`ElseIf`，以下语句`Else`执行。 执行后面的语句后`Then`， `ElseIf`，或`Else`，继续后面的语句执行`End If`。  
  
 `ElseIf`和`Else`子句都是可选。 你可以作为许多`ElseIf`根据需要`If`...`Then`...`Else`语句，但不是`ElseIf`子句可以出现后`Else`子句。 `If`...`Then`...`Else`语句可以相互嵌套。  
  
 在多个行语法中，`If`语句必须是第一个行的唯一语句。 `ElseIf`， `Else`，和`End If`语句仅可以前面的行标签。 `If`...`Then`...`Else`块必须以结束`End If`语句。  
  
> [!TIP]
>  [选择...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)计算有几个可能值的单个表达式时可能会更有用。  
  
## <a name="single-line-syntax"></a>单行语法  
 对于较短的简单测试，可以使用的单行语法。 但是，多个行语法提供了多个结构和灵活性，并通常可以更轻松地读取、 维护和调试。  
  
 哪些如下所示`Then`关键字将检查以确定语句是否是单线条`If`。 如果注释之外的任何内容出现在`Then`上同一行中，该语句将被视为单线条`If`语句。 如果`Then`不存在，它必须是多个行的开头`If`...`Then`...`Else`.  
  
 在单行语法中，你可以有多个语句的结果作为执行`If`...`Then`决策。 所有语句必须是同一行上，并且由冒号分隔。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用的多个行语法`If`...`Then`...`Else`语句。  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb)]  
  
## <a name="example"></a>示例  
 下面的示例包含嵌套`If`...`Then`...`Else`语句。  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb)]  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用单线条语法。  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Select...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [嵌套的控件结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [决策结构](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [在 Visual Basic 中的逻辑和按位运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [If 运算符](../../../visual-basic/language-reference/operators/if-operator.md)
