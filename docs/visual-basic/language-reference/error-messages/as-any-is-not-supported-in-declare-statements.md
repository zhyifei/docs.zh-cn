---
title: “Declare”语句中不支持“As Any”
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: b3fb3f208f3396f454388ec0c10406815fa957d8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974791"
---
# <a name="as-any-is-not-supported-in-declare-statements"></a>“Declare”语句中不支持“As Any”
`Any`数据类型用于`Declare`Visual Basic 6.0 和早期版本，以允许使用自变量，可以包含任何类型的数据中的语句。 Visual Basic 支持重载，但是，也因此使得`Any`数据类型已过时。  
  
 **错误 ID:** BC30828  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  声明你想要使用; 特定类型的参数有关示例。  
  
     [!code-vb[VbVbalrStatements#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#95)]  
  
2.  使用<xref:System.Runtime.InteropServices.MarshalAsAttribute>属性指定`As Any`时`Void*`预期由被调用的过程。  
  
     [!code-vb[VbVbalrStatements#96](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#96)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [演练：调用 Windows API](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)
- [在托管代码中创建原型](../../../framework/interop/creating-prototypes-in-managed-code.md)
