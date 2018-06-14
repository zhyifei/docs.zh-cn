---
title: 如何：使用定义运算符的类 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: 7e1d5698c1e83f0adf1be67245e0726aecaabdac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650600"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>如何：使用定义运算符的类 (Visual Basic)
如果你使用的类或结构，它定义自己的运算符，则可以从 Visual Basic 中访问这些运算符。  
  
 在类或结构上定义一个运算符也称为*重载*运算符。  
  
## <a name="example"></a>示例  
 以下示例访问 SQL 结构<xref:System.Data.SqlTypes.SqlString>，后者定义转换运算符 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)) 中的 SQL 字符串和 Visual Basic 字符串之间的两个方向。 使用`CType(` *SQL 字符串表达式*，`String)`将 SQL 字符串转换为 Visual Basic 字符串，和`CType(` *Visual Basic 字符串表达式*， <xref:System.Data.SqlTypes.SqlString> `)`在另一个方向转换。  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 <xref:System.Data.SqlTypes.SqlString>结构定义的转换运算符 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)) 从`String`到<xref:System.Data.SqlTypes.SqlString>，另一个从<xref:System.Data.SqlTypes.SqlString>到`String`。 将分配的语句`title`到`jobTitle`使用第一个运算符，与<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>函数调用使用第二个。  
  
## <a name="compiling-the-code"></a>编译代码  
 请确保类或结构将定义你想要使用的运算符。 不要假定的类或结构已定义每个可用于重载的运算符。 可用运算符的列表，请参阅[Operator 语句](../../../../visual-basic/language-reference/statements/operator-statement.md)。  
  
 应包括适当`Imports`SQL 字符串的开头的源文件的语句 (在这种情况下<xref:System.Data.SqlTypes>)。  
  
 你的项目必须具有对 System.Data 和 System.XML 的引用。  
  
## <a name="see-also"></a>请参阅  
 [运算符过程](./operator-procedures.md)  
 [如何：定义运算符](./how-to-define-an-operator.md)  
 [如何：定义转换运算符](./how-to-define-a-conversion-operator.md)  
 [如何：调用运算符过程](./how-to-call-an-operator-procedure.md)  
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [如何：声明结构](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [隐式转换和显式转换](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
