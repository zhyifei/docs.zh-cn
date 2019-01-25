---
title: '&#39;#ElseIf&#39;前面必须是匹配的&#39;#If&#39;或&#39;#ElseIf&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 1e63595ee573e9356f6870a02b2131897c725baf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505778"
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a>&#39;#ElseIf&#39;前面必须是匹配的&#39;#If&#39;或&#39;#ElseIf&#39;
`#ElseIf` 是条件编译指令。 `#ElseIf`子句的前面必须是匹配`#If`或`#ElseIf`子句。  
  
 **错误 ID:** BC30014  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查前面`#If`或`#ElseIf`不从该分离`#ElseIf`插入的条件编译块或放置有误`#End If`。  
  
2.  如果`#ElseIf`的前面有`#Else`指令，请移除`#Else`或将其更改为`#ElseIf`。  
  
3.  如果其他一切正常，请将 `#If` 指令添加到条件编译块的开头。  
  
## <a name="see-also"></a>请参阅
- [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
