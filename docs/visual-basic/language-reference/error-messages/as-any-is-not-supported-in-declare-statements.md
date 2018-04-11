---
title: '&#39;作为任何 &#39;中不支持 &#39; Declare &#39;语句'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59120622688ee38d5b8f45c08dfc3ae40711fb8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a>&#39;作为任何 &#39;中不支持 &#39; Declare &#39;语句
`Any`与使用的数据类型`Declare`Visual Basic 6.0 和早期版本，以允许使用的自变量，无法包含任何类型的数据中的语句。 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]支持重载，但是，也因此使得`Any`数据类型已过时。  
  
 **错误 ID:** BC30828  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  声明你想要使用; 特定类型的参数例如。  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  使用<xref:System.Runtime.InteropServices.MarshalAsAttribute>特性来指定`As Any`时`Void*`期望在被调用的过程。  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [演练：调用 Windows API](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [在托管代码中创建原型](../../../framework/interop/creating-prototypes-in-managed-code.md)
