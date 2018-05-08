---
title: '&#39;#Region&#39;和&#39;#End 区域&#39;语句不是在方法正文多行 lambda 内无效'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: bf3843e0ec3009f3dc7d60e91c340a7f20543231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>&#39;#Region&#39;和&#39;#End 区域&#39;语句不是在方法体/多行 lambda 内无效
`#Region`块必须声明类、 模块或命名空间级别。 可折叠区域可以包含一个或多个过程，但它无法开头或结尾在过程内。  
  
 **错误 ID:** BC32025  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  确保前面的过程均已正确终止与`End Function`或`End Sub`语句。  
  
2.  确保`#Region`和`#End Region`指令是一种在同一个代码块中。  
  
## <a name="see-also"></a>请参阅  
 [#Region 指令](../../../visual-basic/language-reference/directives/region-directive.md)
