---
title: 常量和 Literal 数据类型
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8ebecddfab0724023c269e92c1fc5534f096bf1c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333728"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>常量和 Literal 数据类型 (Visual Basic)
文本是一个值，它表示为自身，而不是作为变量的值或表达式的结果，如数字3或字符串 "Hello"。 常量是有意义的名称，用于代替文本，并在整个程序中保留此相同的值，而不是变量（其值可能会更改）。  
  
 当[选项推断](../../../../visual-basic/language-reference/statements/option-infer-statement.md)为 `Off` 并且[option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) `On`时，必须使用数据类型显式声明所有常量。 在下面的示例中，`MyByte` 的数据类型显式声明为数据类型 `Byte`：  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 如果 `Option Infer` `On` 或 `Option Strict` `Off`，则可以声明常量，而无需使用 `As` 子句指定数据类型。 编译器将确定表达式的类型的常量类型。 默认情况下，将数值转换为 `Integer` 数据类型。 浮点数的默认数据类型为 `Double`，关键字 `True` 和 `False` 指定 `Boolean` 常量。  
  
## <a name="literals-and-type-coercion"></a>文本和类型强制  
 在某些情况下，可能需要将文本强制用于特定的数据类型;例如，将一个特别大的整数文本值分配到 `Decimal`类型的变量时。 下面的示例生成错误：  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 此错误是由文本的表示形式导致的。 `Decimal` 数据类型可以保存此大值，但文本隐式表示为 `Long`，这是不可能的。  
  
 可以通过两种方式将文本强制转换为特定数据类型：向其追加类型字符，或将其放在封闭字符内。 类型字符或封闭字符必须紧跟在文本之前和/或之后，无需任何插入空格或任何类型的字符。  
  
 若要使上面的示例正常运行，可以将 `D` 类型字符追加到文本中，这会使其表示为 `Decimal`：  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 下面的示例演示类型字符和封闭字符的正确用法：  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 下表显示 Visual Basic 中可用的封闭字符和类型字符。  
  
|数据类型|封闭字符|追加的类型字符|  
|---|---|---|  
|`Boolean`|(无)|(无)|  
|`Byte`|(无)|(无)|  
|`Char`|"|C|  
|`Date`|#|(无)|  
|`Decimal`|(无)|D 或@|  
|`Double`|(无)|R 或#|  
|`Integer`|(无)|I 或%|  
|`Long`|(无)|L 或 &|  
|`Short`|(无)|S|  
|`Single`|(无)|F 或！|  
|`String`|"|(无)|  
  
## <a name="see-also"></a>另请参阅

- [用户定义的常量](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [如何：声明常量](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [常量概述](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Option Explicit 语句](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [枚举概述](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [如何：声明枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [数据类型](../../../../visual-basic/language-reference/data-types/index.md)
- [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)
