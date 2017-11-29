---
title: Comparison Operators in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- comparison operators [Visual Basic], comparing objects
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers [Visual Basic], comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values [Visual Basic], comparing
- comparison operators [Visual Basic], comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d8bf37ad30f410251f18aea6747734fc24d42cd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="comparison-operators-in-visual-basic"></a>Comparison Operators in Visual Basic
比较运算符比较两个表达式，并返回`Boolean`值，该值表示其值的关系。 有关比较数值，用于比较字符串，运算符和运算符对于比较对象有运算符。 此处讨论了所有三种类型的运算符。  
  
## <a name="comparing-numeric-values"></a>比较数值  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]使用六个数值比较运算符的数字值进行比较。 每个运算符将两个表达式计算结果为数字值作为操作数。 下表列出了运算符，并显示每个示例。  
  
|运算符|测试的条件|示例|  
|--------------|----------------------|--------------|  
|`=`（相等）|第一个表达式相等的值是否为第二个值？|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>`（不等）|是第一个表达式的值不等于第二个值？|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<`（小于）|第一个表达式的值小于第二个值是多少？|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>`（大于）|是第一个表达式的值大于第二个值？|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=`（小于或等于）|是第一个表达式的值小于或等于第二个值？|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=`（大于或等于）|是第一个表达式的值大于或等于第二个值？|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>比较字符串  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]比较字符串使用[Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)以及数值比较运算符。 `Like`运算符，你可以指定的模式。 针对的模式，然后比较字符串和如果匹配，则结果是`True`。 否则，结果是`False`。 数值运算符，你可以比较`String`值基于其排序顺序，如以下示例所示。  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 前面的示例中的结果将`True`因为第一个字符串中的第一个字符的排序之前第二个字符串中的第一个字符。 如果第一个字符相等，比较将继续到两个字符串中的下一个字符，依次类推。 你还可以测试使用相等运算符，如以下示例所示的字符串相等。  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 如果一个字符串是否与另一一个前缀，例如"aa"和"aaa"，则被视为较长的字符串可大于较短的字符串。 下面的示例阐释了这一点。  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 排序顺序基于二进制比较或具体取决于的设置的文本比较`Option Compare`。 有关详细信息请参阅[选项比较语句](../../../../visual-basic/language-reference/statements/option-compare-statement.md)。  
  
## <a name="comparing-objects"></a>比较对象  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]比较两个对象引用变量与[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)和[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)。 你可以使用其中任一运算符以确定是否两个引用变量引用同一对象实例。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbalrOperators#65](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 在前面的示例中，`x Is y`计算结果为`True`，因为这两个变量引用相同实例。 将此结果与下面的示例作一个对比。  
  
 [!code-vb[VbVbalrOperators#66](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]  
  
 在前面的示例中，`x Is y`计算结果为`False`，因为尽管两个变量引用指向同一类型的对象，它们是指该类型的不同实例。  
  
 当你想要测试的两个对象不指向同一个实例，`IsNot`运算符可以帮助您避免的语法非常笨拙组合`Not`和`Is`。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbalrOperators#67](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]  
  
 在前面的示例中，`If a IsNot b`等效于`If Not a Is b`。  
  
### <a name="comparing-object-type"></a>比较对象类型  
 你可以测试是否具有特定类型的对象是`TypeOf`...`Is`表达式。 语法如下所示：  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 当`typename`指定接口类型，则`TypeOf`...`Is`表达式返回`True`如果对象实现的接口类型。 当`typename`是类类型，则该表达式返回`True`如果对象是指定类或派生自指定类的类的实例。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbalrOperators#68](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]  
  
 在前面的示例中，`TypeOf x Is Control`表达式计算结果为`True`因为的一种`x`是`Button`，它继承自`Control`。  
  
 有关详细信息，请参阅[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)。  
  
## <a name="see-also"></a>另请参阅  
 [值的比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [比较运算符](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [运算符](../../../../visual-basic/language-reference/operators/index.md)  
 [在 Visual Basic 中的算术运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [在 Visual Basic 中的串联运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [在 Visual Basic 中的逻辑和按位运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
