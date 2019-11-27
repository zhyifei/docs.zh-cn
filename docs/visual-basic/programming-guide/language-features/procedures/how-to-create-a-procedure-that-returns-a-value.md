---
title: 如何：创建返回值的过程
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 218dbb52abc0100724d38d10be91ef24252d5226
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349718"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>如何：创建返回值的过程 (Visual Basic)
使用 `Function` 过程将值返回到调用代码。  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>创建返回值的过程  
  
1. 在任何其他过程之外，使用 `Function` 语句，后跟 `End Function` 语句。  
  
2. 在 `Function` 语句中，将 `Function` 关键字跟过程的名称一起，然后将参数列表放在括号中。  
  
3. 在括号后跟一个 `As` 子句以指定返回值的数据类型。  
  
4. 将过程的代码语句置于 `Function` 和 `End Function` 语句之间。  
  
5. 使用 `Return` 语句将值返回到调用代码。  
  
     以下 `Function` 过程将计算直角三角形的最长边（或斜边），并给出另一方的值。  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     下面的示例演示对 `hypotenuse`的典型调用。  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>另请参阅

- [过程](./index.md)
- [Sub 过程](./sub-procedures.md)
- [属性过程](./property-procedures.md)
- [运算符过程](./operator-procedures.md)
- [过程参数和自变量](./procedure-parameters-and-arguments.md)
- [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)
- [如何：从过程返回值](./how-to-return-a-value-from-a-procedure.md)
- [如何：调用返回值的过程](./how-to-call-a-procedure-that-returns-a-value.md)
