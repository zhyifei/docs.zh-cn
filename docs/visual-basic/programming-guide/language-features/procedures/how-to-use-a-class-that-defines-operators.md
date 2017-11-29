---
title: "如何：使用定义运算符的类 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 223b3fc84fe75d1d530cd182c9332e5c663aa519
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>如何：使用定义运算符的类 (Visual Basic)
如果你使用的类或结构，它定义自己的运算符，则可以访问这些运算符从[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。  
  
 在类或结构上定义一个运算符也称为*重载*运算符。  
  
## <a name="example"></a>示例  
 以下示例访问 SQL 结构<xref:System.Data.SqlTypes.SqlString>，后者定义转换运算符 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)) 中的 SQL 字符串之间进行双向和[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]字符串。 使用`CType(` *SQL 字符串表达式*， `String)` SQL 将字符串转换为[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]字符串，和`CType(` *Visual Basic 字符串表达式*， <xref:System.Data.SqlTypes.SqlString>`)`在另一个方向转换。  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 <xref:System.Data.SqlTypes.SqlString>结构定义的转换运算符 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)) 从`String`到<xref:System.Data.SqlTypes.SqlString>，另一个从<xref:System.Data.SqlTypes.SqlString>到`String`。 将分配的语句`title`到`jobTitle`使用第一个运算符，与<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>函数调用使用第二个。  
  
## <a name="compiling-the-code"></a>编译代码  
 请确保类或结构将定义你想要使用的运算符。 不要假定的类或结构已定义每个可用于重载的运算符。 可用运算符的列表，请参阅[Operator 语句](../../../../visual-basic/language-reference/statements/operator-statement.md)。  
  
 应包括适当`Imports`SQL 字符串的开头的源文件的语句 (在这种情况下<xref:System.Data.SqlTypes>)。  
  
 你的项目必须具有对 System.Data 和 System.XML 的引用。  
  
## <a name="see-also"></a>另请参阅  
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
