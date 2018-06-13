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
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a><span data-ttu-id="400bd-102">&#39;#ElseIf&#39;前面必须是匹配的&#39;#If&#39;或&#39;#ElseIf&#39;</span><span class="sxs-lookup"><span data-stu-id="400bd-102">&#39;#ElseIf&#39; must be preceded by a matching &#39;#If&#39; or &#39;#ElseIf&#39;</span></span>
<span data-ttu-id="400bd-103">`#ElseIf` 是条件编译指令。</span><span class="sxs-lookup"><span data-stu-id="400bd-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="400bd-104">`#ElseIf`子句的前面必须是匹配的`#If`或`#ElseIf`子句。</span><span class="sxs-lookup"><span data-stu-id="400bd-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="400bd-105">**错误 ID:** BC30014</span><span class="sxs-lookup"><span data-stu-id="400bd-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="400bd-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="400bd-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="400bd-107">检查前面`#If`或`#ElseIf`未已脱离此`#ElseIf`插入的条件编译块或放置有误`#End If`。</span><span class="sxs-lookup"><span data-stu-id="400bd-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2.  <span data-ttu-id="400bd-108">如果`#ElseIf`前面是`#Else`指令，请移除`#Else`或将其更改为`#ElseIf`。</span><span class="sxs-lookup"><span data-stu-id="400bd-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3.  <span data-ttu-id="400bd-109">如果其他一切正常，请将 `#If` 指令添加到条件编译块的开头。</span><span class="sxs-lookup"><span data-stu-id="400bd-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="400bd-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="400bd-110">See Also</span></span>  
 [<span data-ttu-id="400bd-111">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="400bd-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
