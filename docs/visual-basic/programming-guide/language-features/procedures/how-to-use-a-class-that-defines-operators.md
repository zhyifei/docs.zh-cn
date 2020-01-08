---
title: 如何：使用定义运算符的类
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
ms.openlocfilehash: 455c839702b90738ec5aea37c1b09d72eba42ff4
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347894"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>如何：使用定义运算符的类 (Visual Basic)
如果你使用的是定义其自己的运算符的类或结构，则可以从 Visual Basic 访问这些运算符。  
  
 在类或结构上定义运算符也称为*重载*运算符。  
  
## <a name="example"></a>示例  
 下面的示例访问 SQL 结构 <xref:System.Data.SqlTypes.SqlString>，它在 SQL 字符串和 Visual Basic 字符串之间的两个方向定义转换运算符（[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)）。 使用 `CType(`*sql 字符串表达式*`String)`，将 sql 字符串转换为 Visual Basic 字符串，并 `CType(`Visual Basic*字符串表达式*，<xref:System.Data.SqlTypes.SqlString>`)` 以进行双向转换。  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <xref:System.Data.SqlTypes.SqlString> 结构定义了从 `String` 到 <xref:System.Data.SqlTypes.SqlString>，另一个从 <xref:System.Data.SqlTypes.SqlString> 到 `String`的转换运算符（[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)）。 将 `title` 分配给 `jobTitle` 的语句使用第一个运算符，而 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 函数调用使用第二个运算符。  
  
## <a name="compile-the-code"></a>编译代码  
 请确保所用的类或结构定义要使用的运算符。 不要假设类或结构已定义每个可用于重载的运算符。 有关可用运算符的列表，请参阅[Operator 语句](../../../../visual-basic/language-reference/statements/operator-statement.md)。  
  
 在源文件开头包含 SQL 字符串的相应 `Imports` 语句（在本例中为 <xref:System.Data.SqlTypes>）。  
  
 你的项目必须引用了 System.web 和 System.object。  
  
## <a name="see-also"></a>另请参阅

- [运算符过程](./operator-procedures.md)
- [如何：定义运算符](./how-to-define-an-operator.md)
- [如何：定义转换运算符](./how-to-define-a-conversion-operator.md)
- [如何：调用运算符过程](./how-to-call-an-operator-procedure.md)
- [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [如何：声明结构](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [隐式转换和显式转换](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
