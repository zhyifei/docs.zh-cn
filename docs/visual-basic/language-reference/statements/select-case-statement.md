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
ms.openlocfilehash: 627318677270ba4ffa8ee430febea7ddf83bd245
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957648"
---
# <a name="selectcase-statement-visual-basic"></a>Select...Case 语句 (Visual Basic)
根据表达式的值运行若干组语句中的一个。  
  
## <a name="syntax"></a>语法  
  
```  
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
|`testexpression`|必需。 表达式. 的计算结果必须为其中一种基本数据`Boolean`类型`Byte`（ `Char`、 `Date` `Integer`、 `Double`、 `Decimal`、 `Long` `Object`、 、、、、、、`SByte` `Short``Single`、 、`String` 、和`UShort`）。 `UInteger` `ULong`|  
|`expressionlist`|在语句中`Case`是必需的。 表示的匹配值`testexpression`的表达式子句的列表。 多个表达式子句之间用逗号分隔。 每个子句可以采用以下形式之一：<br /><br /> -   *expression1* `To` *expression2*<br />-   [ `Is` ] *comparisonoperator* *expression*<br />-   *表达式*<br /><br /> 使用关键字可以指定的匹配`testexpression`值范围的边界。 `To` 的`expression1`值必须小于或等于的`expression2`值。<br /><br /> `<` `<>` `<=`使用关键字和`>=`比较`=`运算符（、、 `testexpression`、 、或）来指定对的匹配值的限制。`>` `Is` 如果未提供关键字，则自动将其插入.comparisonoperator`Is`之前。<br /><br /> 仅`expression`指定的窗体被视为`Is`窗体的一种特殊情况，其中 *.comparisonoperator*是等号`=`（）。 此形式的计算结果`testexpression`为 =  `expression`。<br /><br /> 中`expressionlist`的表达式可以是任何数据类型，前提是它们可隐式转换为的`testexpression`类型，并且相应`comparisonoperator`的对于与之一起使用的两种类型都有效。|  
|`statements`|可选。 如果与中`Case` `testexpression` 的任何`expressionlist`子句匹配，则为运行的一个或多个语句。|  
|`elsestatements`|可选。 如果`Case Else` 不`testexpression` 与任何`Case`语句的中的任何子句匹配，则为`expressionlist`运行的一个或多个语句。|  
|`End Select`|终止的定义`Select`...`Case`构造。|  
  
## <a name="remarks"></a>备注  
 如果`testexpression`与 any `Case` `End Select` `Case` `Case Else`子句匹配，则该`Case`语句后面的语句将运行到下一个、或语句。 `expressionlist` 然后，控制将传递到后面`End Select`的语句。 如果`testexpression`在多`expressionlist`个`Case`子句中匹配某个子句，则只运行第一个匹配后的语句。  
  
 如果`Case Else`在任何其他`testexpression` `expressionlist` `elsestatements` 语句中的和子句之间找不到匹配项，则该语句用于引入要运行的。`Case` 尽管这不是必需的，但最好`Case Else` `Select Case`在构造中具有语句来处理不可预见`testexpression`的值。 如果没有`Case`任何`expressionlist`子句`testexpression` `End Select`匹配并且没有语句，控制将传递到后面的语句。`Case Else`  
  
 可以在每个`Case`子句中使用多个表达式或范围。 例如，下面的行是有效的。  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> `Case` 和 `Case Else` 语句中使用的 `Is` 关键字与 [is 运算符](../../../visual-basic/language-reference/operators/is-operator.md)不同，后者用于对象引用比较。  
  
 您可以为字符串指定范围和多个表达式。 在下面的示例中`Case` ，匹配任何完全等于 "苹果" 的字符串，其值介于 "螺母" 和 "soup" 之间的字母顺序之间，或包含与当前值完全相同的`testItem`值。  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 的设置`Option Compare`可能会影响字符串比较。 在`Option Compare Text`下，字符串 "苹果" 和 "苹果" 比较视为相等，但在`Option Compare Binary`下，它们不会。  
  
> [!NOTE]
> 具有`Case`多个子句的语句可以表现称为 "*短路*" 的行为。 Visual Basic 从左到右计算子句的值，并且如果一个语句生成匹配`testexpression`项，则不会计算剩余的子句。 短路可以提高性能，但如果希望计算中的`expressionlist`每个表达式，则可能产生意外的结果。 有关短路的详细信息，请参阅[布尔表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)。  
  
 如果`Case` `Exit Select`或`Case Else`语句块内的代码不需要在块中运行任何更多语句，则可以使用语句退出块。 这会将控制立即传输到后面`End Select`的语句。  
  
 `Select Case`构造可以嵌套。 每个`Select Case`嵌套构造都必须具有`End Select`匹配的语句，并且必须完全包含在`Case`嵌套`Case Else`它的外部`Select Case`构造的单个或语句块内。  
  
## <a name="example"></a>示例  
 下面的示例使用`Select Case`构造来编写与变量`number`的值相对应的行。 第二`Case`个语句包含的值与的当前`number`值匹配，因此将运行写入 "6 到8个（含）" 的语句。  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [End 语句](../../../visual-basic/language-reference/statements/end-statement.md)
- [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Option Compare 语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)
