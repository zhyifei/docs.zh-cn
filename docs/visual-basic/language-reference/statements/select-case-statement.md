---
title: Select...Case 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
ms.openlocfilehash: d035118febc5ea9d1ea8e5cc0145cb030626b030
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583248"
---
# <a name="selectcase-statement-visual-basic"></a>Select...Case 语句 (Visual Basic)
根据表达式的值运行若干组语句中的一个。  
  
## <a name="syntax"></a>语法  
  
```vb  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`testexpression`|必须的。 表达式. 的计算结果必须为基本数据类型之一（`Boolean`、`Byte`、`Char`、`Date`、`Double`、`Decimal`、`Integer`、`Long`、`Object`、`SByte`、0、1、2、3、4 和 5）。|  
|`expressionlist`|在 `Case` 语句中是必需的。 表示 `testexpression` 的匹配值的表达式子句的列表。 多个表达式子句之间用逗号分隔。 每个子句可以采用以下形式之一：<br /><br /> -   *表达式*2 *`To` 2*<br />-[`Is`] *.comparisonoperator* *表达式*<br />-   *表达式*<br /><br /> 使用 `To` 关键字指定 `testexpression` 的匹配值范围的边界。 @No__t_0 的值必须小于或等于 `expression2` 的值。<br /><br /> 将 `Is` 关键字与比较运算符（`=`、`<>`、`<`、`<=`、`>` 或 `>=`）结合使用，以指定 `testexpression` 匹配值的限制。 如果未提供 `Is` 关键字，则自动将其插入 *.comparisonoperator*之前。<br /><br /> 仅指定 `expression` 的窗体被视为 `Is` 窗体的特殊情况，其中 *.comparisonoperator*是等号（`=`）。 此形式的计算结果为 `testexpression`  =  `expression`。<br /><br /> @No__t_0 中的表达式可以是任何数据类型，前提是它们可隐式转换为 `testexpression` 的类型，并且相应的 `comparisonoperator` 对于它与之一起使用的两个类型都有效。|  
|`statements`|可选。 如果 `testexpression` 与 `expressionlist` 中的任何子句匹配，则 `Case` 运行的一个或多个语句。|  
|`elsestatements`|可选。 如果 `testexpression` 与任何 `Case` 语句的 `expressionlist` 中的任何子句都不匹配，则在运行 `Case Else` 后面的一个或多个语句。|  
|`End Select`|终止的定义`Select`...`Case`构造。|  
  
## <a name="remarks"></a>备注  
 如果 `testexpression` 与任何 `Case` `expressionlist` 子句匹配，则遵循该 `Case` 语句的语句将运行到下一个 `Case`、`Case Else` 或 `End Select` 语句之后。 然后，控件传递到 `End Select` 后面的语句。 如果 `testexpression` 在多个 `Case` 子句中匹配 `expressionlist` 子句，则仅运行第一个匹配后的语句。  
  
 如果在任何其他 `Case` 语句的 `testexpression` 和 `expressionlist` 子句之间找不到匹配项，则使用 `Case Else` 语句引入要运行的 `elsestatements`。 虽然不是必需的，但最好在 `Select Case` 构造中使用 `Case Else` 语句来处理不可预见的 `testexpression` 值。 如果没有 `Case` `expressionlist` 子句匹配 `testexpression`，并且没有 `Case Else` 语句，控制将传递到 `End Select` 后面的语句。  
  
 可以在每个 `Case` 子句中使用多个表达式或范围。 例如，下面的行是有效的。  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> @No__t_1 和 `Case Else` 语句中使用的 `Is` 关键字与[Is 运算符](../../../visual-basic/language-reference/operators/is-operator.md)不同，后者用于对象引用比较。  
  
 您可以为字符串指定范围和多个表达式。 在下面的示例中，`Case` 匹配任何完全等于 "苹果" 的字符串，其值介于 "螺母" 和 "soup" 之间按字母顺序排序，或者包含与 `testItem` 的当前值完全相同的值。  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 @No__t_0 的设置可能会影响字符串比较。 在 `Option Compare Text` 下，字符串 "苹果" 和 "苹果" 的比较结果相等，但在 `Option Compare Binary` 下，它们不会。  
  
> [!NOTE]
> 具有多个子句的 `Case` 语句可以表现称为 "*短路*" 的行为。 Visual Basic 从左到右计算子句，并且如果一个生成与 `testexpression` 的匹配项，则不会计算剩余的子句。 短路可以提高性能，但如果希望计算 `expressionlist` 中的每个表达式，则可能产生意外的结果。 有关短路的详细信息，请参阅[布尔表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)。  
  
 如果 `Case` 或 `Case Else` 语句块内的代码不需要在块中运行任何更多语句，则它可以使用 `Exit Select` 语句退出块。 这会将控制立即传输到 `End Select` 后面的语句中。  
  
 `Select Case` 构造可以嵌套。 每个嵌套 `Select Case` 构造必须具有匹配的 `End Select` 语句，并且必须完全包含在其嵌套的外部 `Select Case` 构造的单个 `Case` 或 `Case Else` 语句块内。  
  
## <a name="example"></a>示例  
 下面的示例使用 `Select Case` 构造来编写与 `number` 变量的值相对应的行。 第二个 `Case` 语句包含与 `number` 的当前值相匹配的值，因此，将运行写入 "6 到8个（含）" 的语句。  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [End 语句](../../../visual-basic/language-reference/statements/end-statement.md)
- [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Option Compare 语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)
