---
title: 二元“If”表达式中的第一个操作数必须是可以为 null 的类型或引用类型
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 4b520949cb59b63ea39441632dc5e2c6d000d711
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249521"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>二元“If”表达式中的第一个操作数必须是可以为 null 的类型或引用类型
表达式`If`可以采用两个或三个参数。 仅发送两个参数时，第一个参数必须是引用类型或空值类型。 如果第一个参数计算为`Nothing`以外的任何内容，则返回其值。 如果第一个参数计算到`Nothing`，则计算并返回第二个参数。  
  
 例如，以下代码包含两`If`个表达式，一个包含三个参数，一个包含两个参数。 表达式计算并返回相同的值。  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 以下表达式导致此错误：  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **错误 ID：** BC33107  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 如果无法更改代码，以便第一个参数是空值类型或引用类型，请考虑转换为三个参数`If`表达式或语句。 `If...Then...Else`  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>请参阅

- [If 运算符](../../../visual-basic/language-reference/operators/if-operator.md)
- [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [可以为 null 的值类型](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
