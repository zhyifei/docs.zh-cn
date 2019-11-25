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
You call an operator procedure by using the operator symbol in an expression. In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.  
  
 You do not call operator procedures explicitly. You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator. Visual Basic makes the call to the operator procedure.  
  
 Defining an operator on a class or structure is also called *overloading* the operator.  
  
### <a name="to-call-an-operator-procedure"></a>To call an operator procedure  
  
1. Use the operator symbol in an expression in the ordinary way.  
  
2. Be sure the data types of the operands are appropriate for the operator, and in the correct order.  
  
3. The operator contributes to the value of the expression as expected.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>To call a conversion operator procedure  
  
1. Use `CType` inside an expression.  
  
2. Be sure the data types of the operands are appropriate for the conversion, and in the correct order.  
  
3. `CType` calls the conversion operator procedure and returns the converted value.  
  
## <a name="example"></a>示例  
 The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure. The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.  
  
 For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compiling-the-code"></a>编译代码  
 Be sure the class or structure you are using defines the operator you want to use.  
  
## <a name="see-also"></a>请参阅

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
