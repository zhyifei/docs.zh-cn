---
title: 'How to: Define a Conversion Operator'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 0ff95390206947e5a28f7a5b85547b496746a9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344898"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>如何：定义转换运算符 (Visual Basic)
如果已定义类或结构，则可以在类或结构的类型与另一种数据类型（如 `Integer`、`Double`或 `String`）之间定义类型转换运算符。  
  
 将类型转换定义为类或结构中的[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)过程。 必须 `Public Shared`所有转换过程，并且每个转换过程必须指定[扩大](../../../../visual-basic/language-reference/modifiers/widening.md)或[收缩](../../../../visual-basic/language-reference/modifiers/narrowing.md)。  
  
 在类或结构上定义运算符也称为*重载*运算符。  
  
## <a name="example"></a>示例  
 下面的示例定义名为 `digit` 和 `Byte`的结构之间的转换运算符。  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 可以通过以下代码测试 `digit` 的结构。  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>另请参阅

- [运算符过程](./operator-procedures.md)
- [如何：定义运算符](./how-to-define-an-operator.md)
- [如何：调用运算符过程](./how-to-call-an-operator-procedure.md)
- [如何：使用定义运算符的类](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [如何：声明结构](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [隐式转换和显式转换](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
