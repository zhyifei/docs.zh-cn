---
title: '&#39;#ElseIf&#39;前面必须是匹配的&#39;#If&#39;或&#39;#ElseIf&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: ef904173b1791309f6c2722bd959cabdad1d71da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588143"
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a>&#39;#ElseIf&#39;前面必须是匹配的&#39;#If&#39;或&#39;#ElseIf&#39;
`#ElseIf` 是条件编译指令。 `#ElseIf`子句的前面必须是匹配的`#If`或`#ElseIf`子句。  
  
 **错误 ID:** BC30014  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查前面`#If`或`#ElseIf`未已脱离此`#ElseIf`插入的条件编译块或放置有误`#End If`。  
  
2.  如果`#ElseIf`前面是`#Else`指令，请移除`#Else`或将其更改为`#ElseIf`。  
  
3.  如果其他一切正常，请将 `#If` 指令添加到条件编译块的开头。  
  
## <a name="see-also"></a>请参阅  
 [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
