---
title: 如何：从过程返回值 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 62e8a52e488247d4dfcde2a560920447abe1c182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>如何：从过程返回值 (Visual Basic)
A`Function`过程返回一个值给调用代码通过执行`Return`语句或在遇到`Exit Function`或`End Function`语句。  
  
### <a name="to-return-a-value-using-the-return-statement"></a>返回值使用 Return 语句  
  
1.  Put`Return`过程的任务已完成其中的点处的语句。  
  
2.  请按照`Return`想要返回到调用代码会生成值的表达式的关键字。  
  
3.  在同一过程中可拥有多个 `Return` 语句。  
  
     以下`Function`过程计算的最长端或斜边直角三角形，并将其返回给调用代码。  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     下面的示例演示典型调用`hypotenuse`，它用于存储返回的值。  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>返回值使用退出函数或最终函数  
  
1.  在至少一个就地`Function`过程中，分配到过程的名称的值。  
  
2.  执行时`Exit Function`或`End Function`语句，Visual Basic 将返回最近分配给过程的名称的值。  
  
3.  在同一过程中可拥有多个 `Exit Function` 语句，也可混合 `Return` 和 `Exit Function` 语句。  
  
4.  只能有一个`End Function`中的语句`Function`过程。  
  
     有关详细信息及示例，请参阅"返回值" [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [Sub 过程](./sub-procedures.md)  
 [属性过程](./property-procedures.md)  
 [运算符过程](./operator-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Return 语句](../../../../visual-basic/language-reference/statements/return-statement.md)  
 [如何：创建返回值的过程](./how-to-create-a-procedure-that-returns-a-value.md)  
 [如何：调用返回值的过程](./how-to-call-a-procedure-that-returns-a-value.md)
