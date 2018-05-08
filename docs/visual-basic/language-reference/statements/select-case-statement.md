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
ms.openlocfilehash: 9d24b455d92cbd00b268df26283aab082b7703a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="selectcase-statement-visual-basic"></a>Select...Case 语句 (Visual Basic)
运行的语句，具体取决于表达式的值的多个组之一。  
  
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
|`testexpression`|必须的。 表达式。 计算结果必须为基本数据类型之一 (`Boolean`， `Byte`， `Char`， `Date`， `Double`， `Decimal`， `Integer`， `Long`， `Object`， `SByte`， `Short`，`Single`， `String`， `UInteger`， `ULong`，和`UShort`)。|  
|`expressionlist`|中所需`Case`语句。 表示匹配值的表达式子句的列表`testexpression`。 用逗号分隔多个表达式子句。 每个子句可以采用以下形式之一：<br /><br /> -   *expression1* `To` *expression2*<br />-[ `Is` ]*比较运算符**表达式*<br />-   *表达式*<br /><br /> 使用`To`关键字来指定匹配项的范围的边界值`testexpression`。 值`expression1`必须小于或等于的值`expression2`。<br /><br /> 使用`Is`使用比较运算符关键字 (`=`， `<>`， `<`， `<=`， `>`，或`>=`) 来匹配值的指定限制`testexpression`。 如果`Is`未提供关键字，它将自动插入之前*比较运算符*。<br /><br /> 仅指定窗体`expression`视为一种特殊情况的`Is`形成 where*比较运算符*等号 (`=`)。 此窗体计算为`testexpression`  =  `expression`。<br /><br /> 中的表达式`expressionlist`可以是任何数据类型，它们可以隐式转换为的类型提供`testexpression`适当`comparisonoperator`对与一起使用的两种类型有效。|  
|`statements`|可选。 一个或多个语句以下`Case`，运行的如果`testexpression`匹配中的任何子句`expressionlist`。|  
|`elsestatements`|可选。 一个或多个语句以下`Case Else`，运行的如果`testexpression`中的任何子句不匹配`expressionlist`任一种情况`Case`语句。|  
|`End Select`|终止的定义`Select`...`Case`构造。|  
  
## <a name="remarks"></a>备注  
 如果`testexpression`与任何匹配`Case``expressionlist`子句，该语句`Case`语句运行，直至遇到下一个`Case`， `Case Else`，或`End Select`语句。 控制权然后传递给后面的语句`End Select`。 如果`testexpression`匹配`expressionlist`中多个子句`Case`子句，仅按照第一个匹配项的语句运行。  
  
 `Case Else`语句用于引入`elsestatements`运行如果之间不找到任何匹配`testexpression`和`expressionlist`中任何其他子句`Case`语句。 尽管没有要求，它是具有一个好办法`Case Else`中的语句你`Select Case`构造来处理出现未预见`testexpression`值。 如果没有`Case``expressionlist`子句匹配`testexpression`并且没有任何`Case Else`语句中，控件传递到后面的语句`End Select`。  
  
 你可以使用多个表达式或范围中每个`Case`子句。 例如，下面的行是有效的。  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  `Is`中使用的关键字`Case`和`Case Else`语句不是相同[Is 运算符](../../../visual-basic/language-reference/operators/is-operator.md)，后者用于对象的引用比较。  
  
 你可以指定范围和多个表达式的字符字符串。 在下面的示例中，`Case`匹配任何字符串都是完全等于"对象"、"螺母"和"浓汤"之间的值按字母顺序，或包含完全相同的值的当前值`testItem`。  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 设置`Option Compare`可能会影响字符串比较。 下`Option Compare Text`，字符串"对象"和"对象"比较为相等，但在`Option Compare Binary`，它们不这样做。  
  
> [!NOTE]
>  A`Case`具有多个子句的语句会表现出行为称为*短路*。 Visual Basic 从左到右，这些子句的计算结果和如果一个将生成包含的匹配项`testexpression`，剩余的子句不会评估。 短路可以提高性能，但是，如果你预期会在每个表达式，它可能会产生意外的结果`expressionlist`要进行求值。 有关短路的详细信息，请参阅[布尔表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)。  
  
 如果中的代码内`Case`或`Case Else`语句块不需要运行更多的语句块中，它可以通过使用退出块`Exit Select`语句。 此控件将立即转移到后面的语句`End Select`。  
  
 `Select Case` 可以嵌套的构造。 每个嵌套`Select Case`构造必须有匹配`End Select`语句必须完全包含在单个`Case`或`Case Else`语句块的外部`Select Case`构造它嵌套在其中。  
  
## <a name="example"></a>示例  
 下面的示例使用`Select Case`构造写入变量的值相对应的行`number`。 第二个`Case`语句包含匹配的当前值的值`number`，因此该语句，它将写入"在 6 到 8，非独占"之间运行。  
  
 [!code-vb[VbVbalrStatements#54](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/select-case-statement_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 [End 语句](../../../visual-basic/language-reference/statements/end-statement.md)  
 [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Option Compare 语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)
