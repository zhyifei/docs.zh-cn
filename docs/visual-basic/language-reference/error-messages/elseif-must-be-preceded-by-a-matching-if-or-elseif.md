---
title: “#ElseIf”前面必须是匹配的“#If”或“#ElseIf”
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 4832fb80cfbe42c7a1303e0de69f36784711c05a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311053"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="31585-102">“#ElseIf”前面必须是匹配的“#If”或“#ElseIf”</span><span class="sxs-lookup"><span data-stu-id="31585-102">'#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>
<span data-ttu-id="31585-103">`#ElseIf` 是条件编译指令。</span><span class="sxs-lookup"><span data-stu-id="31585-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="31585-104">`#ElseIf`子句的前面必须是匹配`#If`或`#ElseIf`子句。</span><span class="sxs-lookup"><span data-stu-id="31585-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="31585-105">**错误 ID:** BC30014</span><span class="sxs-lookup"><span data-stu-id="31585-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="31585-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="31585-106">To correct this error</span></span>  
  
1. <span data-ttu-id="31585-107">检查前面`#If`或`#ElseIf`不从该分离`#ElseIf`插入的条件编译块或放置有误`#End If`。</span><span class="sxs-lookup"><span data-stu-id="31585-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2. <span data-ttu-id="31585-108">如果`#ElseIf`的前面有`#Else`指令，请移除`#Else`或将其更改为`#ElseIf`。</span><span class="sxs-lookup"><span data-stu-id="31585-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3. <span data-ttu-id="31585-109">如果其他一切正常，请将 `#If` 指令添加到条件编译块的开头。</span><span class="sxs-lookup"><span data-stu-id="31585-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31585-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="31585-110">See also</span></span>

- [<span data-ttu-id="31585-111">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="31585-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
