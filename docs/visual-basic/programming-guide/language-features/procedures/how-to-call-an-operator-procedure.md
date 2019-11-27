---
title: 如何：调用运算符过程
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
ms.openlocfilehash: a685be7cc3b346b271413e2c29faae5a839313f4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340247"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>如何：调用运算符过程 (Visual Basic)
在表达式中使用运算符符号调用运算符过程。 在转换运算符的情况下，调用[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)将值从一种数据类型转换为另一种数据类型。  
  
 不要显式调用运算符过程。 你只需在赋值语句或表达式中使用运算符或 `CType` 函数，这与通常使用运算符的方式相同。 Visual Basic 调用运算符过程。  
  
 在类或结构上定义运算符也称为*重载*运算符。  
  
### <a name="to-call-an-operator-procedure"></a>调用运算符过程  
  
1. 用普通方法在表达式中使用运算符符号。  
  
2. 确保操作数的数据类型适用于运算符，并按正确的顺序排列。  
  
3. 运算符会按预期方式分配表达式的值。  
  
### <a name="to-call-a-conversion-operator-procedure"></a>调用转换运算符过程  
  
1. 在表达式中使用 `CType`。  
  
2. 确保操作数的数据类型适用于转换，并按正确的顺序排列。  
  
3. `CType` 调用转换运算符过程，并返回转换后的值。  
  
## <a name="example"></a>示例  
 下面的示例创建两个 <xref:System.TimeSpan> 结构，将它们相加，然后将结果存储在第三个 <xref:System.TimeSpan> 结构中。 <xref:System.TimeSpan> 结构定义运算符过程以重载多个标准运算符。  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 由于 <xref:System.TimeSpan> 会重载标准 `+` 运算符，因此在计算 `combinedSpan`的值时，上面的示例将调用一个运算符过程。  
  
 有关调用会话运算符过程的示例，请参阅[如何：使用定义运算符的类](./how-to-use-a-class-that-defines-operators.md)。  
  
## <a name="compiling-the-code"></a>编译代码  
 请确保所用的类或结构定义要使用的运算符。  
  
## <a name="see-also"></a>另请参阅

- [运算符过程](./operator-procedures.md)
- [如何：定义运算符](./how-to-define-an-operator.md)
- [如何：定义转换运算符](./how-to-define-a-conversion-operator.md)
- [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [如何：声明结构](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [隐式转换和显式转换](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
