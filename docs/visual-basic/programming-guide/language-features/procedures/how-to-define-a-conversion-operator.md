---
title: 如何：定义转换运算符 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 24bbe41af67f757cae661a78d482a423ff0ffd85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648468"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>如何：定义转换运算符 (Visual Basic)
如果已定义类或结构，则可以定义的类或结构类型和另一个数据类型之间的类型转换运算符 (如`Integer`， `Double`，或`String`)。  
  
 定义类型转换为[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)类或结构中的过程。 所有转换过程都必须`Public Shared`，和每个必须指定[Widening](../../../../visual-basic/language-reference/modifiers/widening.md)或[Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)。  
  
 在类或结构上定义一个运算符也称为*重载*运算符。  
  
## <a name="example"></a>示例  
 下面的示例定义一个称为结构之间的转换运算符`digit`和`Byte`。  
  
 [!code-vb[VbVbcnProcedures#27](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_1.vb)]  
  
 你可以测试结构`digit`替换为以下代码。  
  
 [!code-vb[VbVbcnProcedures#28](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_2.vb)]  
  
## <a name="see-also"></a>请参阅  
 [运算符过程](./operator-procedures.md)  
 [如何：定义运算符](./how-to-define-an-operator.md)  
 [如何：调用运算符过程](./how-to-call-an-operator-procedure.md)  
 [如何：使用定义运算符的类](./how-to-use-a-class-that-defines-operators.md)  
 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [如何：声明结构](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [隐式转换和显式转换](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
