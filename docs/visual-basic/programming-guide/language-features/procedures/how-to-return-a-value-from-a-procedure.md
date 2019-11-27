---
title: 如何：从过程返回值
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 1371e4ed0ff28f9caf56eabf2a1bb9290edbe75c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346031"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>如何：从过程返回值 (Visual Basic)
`Function` 过程通过执行 `Return` 语句或遇到 `Exit Function` 或 `End Function` 语句将值返回到调用代码。  
  
### <a name="to-return-a-value-using-the-return-statement"></a>使用 Return 语句返回值  
  
1. 在过程任务完成时，将 `Return` 语句放置在该点。  
  
2. 在 `Return` 关键字后面跟一个表达式，该表达式生成要返回到调用代码的值。  
  
3. 在同一过程中可拥有多个 `Return` 语句。  
  
     以下 `Function` 过程计算直角三角形的最长边（或斜边），并将其返回给调用代码。  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     下面的示例演示对 `hypotenuse`的典型调用，该调用存储返回的值。  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>使用 Exit 函数或 End 函数返回值  
  
1. 在 `Function` 过程中的至少一个位置，为过程名称赋值。  
  
2. 当执行 `Exit Function` 或 `End Function` 语句时，Visual Basic 返回最近分配给该过程的名称的值。  
  
3. 在同一过程中可拥有多个 `Exit Function` 语句，也可混合 `Return` 和 `Exit Function` 语句。  
  
4. `Function` 过程中只能有一个 `End Function` 语句。  
  
     有关详细信息和示例，请参阅[Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)中的 "返回值"。  
  
## <a name="see-also"></a>另请参阅

- [过程](./index.md)
- [Sub 过程](./sub-procedures.md)
- [属性过程](./property-procedures.md)
- [运算符过程](./operator-procedures.md)
- [过程参数和自变量](./procedure-parameters-and-arguments.md)
- [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Return 语句](../../../../visual-basic/language-reference/statements/return-statement.md)
- [如何：创建返回值的过程](./how-to-create-a-procedure-that-returns-a-value.md)
- [如何：调用返回值的过程](./how-to-call-a-procedure-that-returns-a-value.md)
