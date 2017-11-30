---
title: "常量和 Literal 数据类型 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 554753e26d185593ce43b741b3b2f9e3cb1ad6dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="constant-and-literal-data-types-visual-basic"></a>常量和 Literal 数据类型 (Visual Basic)
文本是一个值，表示为本身而不是变量的值或表达式，如数字 3 或字符串"Hello"的结果。 常量是有意义的名称，它接受文本的位置，并保留在整个程序，而不是一个变量，其值可能会更改此相同的值。  
  
 当[Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)是`Off`和[Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)是`On`，你必须显式声明所有常量具有数据类型。 以下示例中中的数据类型`MyByte`显式声明数据类型为`Byte`:  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 当`Option Infer`是`On`或`Option Strict`是`Off`，你可以声明变量，而无需指定的数据类型`As`子句。 编译器确定常量的表达式的类型的类型。 数字的整数文本被强制转换为默认情况下`Integer`数据类型。 默认数据类型为浮点数字`Double`，和关键字`True`和`False`指定`Boolean`常量。  
  
## <a name="literals-and-type-coercion"></a>文本和类型强制  
 在某些情况下，你可能想要文本强制转换为特定的数据类型;例如，将特别大的整型文本值分配给类型的变量时`Decimal`。 下面的示例将生成错误：  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 中的文本表示形式的错误结果。 `Decimal`数据类型可以保存值过大，但文本隐式表示为`Long`，哪些不能。  
  
 可以强制转换为特定数据类型以两种方式是文本： 通过将类型字符追加到它，或将它放置在封闭字符。 类型字符或封闭字符必须立即之前和/或之后的文本，没有干预空格或任何类型的字符。  
  
 若要使前面的示例工作，你可以将附加`D`键入文本，使其表示为字符`Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 下面的示例演示如何正确使用类型字符和封闭字符：  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 下表显示了包含的字符和类型字符位于[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。  
  
|数据类型|封闭字符|追加的类型字符|  
|---|---|---|  
|`Boolean`|(无)|(无)|  
|`Byte`|(无)|(无)|  
|`Char`|"|C|  
|`Date`|#|(无)|  
|`Decimal`|(无)|D 或 @|  
|`Double`|(无)|R 或 #|  
|`Integer`|(无)|I 或 %|  
|`Long`|(无)|L 或 （& a)|  
|`Short`|(无)|S|  
|`Single`|(无)|F 或 ！|  
|`String`|"|(无)|  
  
## <a name="see-also"></a>另请参阅  
 [用户定义的常量](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [如何：声明常量](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [常量概述](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Option Explicit 语句](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [枚举概述](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [如何： 声明枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)
