---
title: 如何：创建返回值的过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 472f55173a4897a23a82812a2b24bf1646c1a6ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>如何：创建返回值的过程 (Visual Basic)
你使用`Function`值返回给调用代码的过程。  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>创建过程中返回一个值  
  
1.  在任何其他过程之外使用`Function`语句后, 跟`End Function`语句。  
  
2.  在`Function`语句，请按照`Function`关键字的过程，然后在括号中的参数列表的名称。  
  
3.  括号后跟`As`子句指定返回的值的数据类型。  
  
4.  放置过程的代码语句之间`Function`和`End Function`语句。  
  
5.  使用`Return`语句返回值返回到调用代码。  
  
     以下`Function`过程计算的最长端或斜边直角三角形，其他两条边为给定的值。  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     下面的示例演示典型调用`hypotenuse`。  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [Sub 过程](./sub-procedures.md)  
 [属性过程](./property-procedures.md)  
 [运算符过程](./operator-procedures.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [如何：从过程返回值](./how-to-return-a-value-from-a-procedure.md)  
 [如何：调用返回值的过程](./how-to-call-a-procedure-that-returns-a-value.md)
