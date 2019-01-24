---
title: '&#39;类&#39;语句必须以匹配结束&#39;结束类&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 4e80ce58048bfa7f2fecc65e7167479df07bf57c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715082"
---
# <a name="39class39-statement-must-end-with-a-matching-39end-class39"></a><span data-ttu-id="a1dec-102">&#39;类&#39;语句必须以匹配结束&#39;结束类&#39;</span><span class="sxs-lookup"><span data-stu-id="a1dec-102">&#39;Class&#39; statement must end with a matching &#39;End Class&#39;</span></span>
<span data-ttu-id="a1dec-103">`Class` 用于启动`Class`块; 因此它可以仅出现在块中，以匹配的开头`End Class`语句结束块。</span><span class="sxs-lookup"><span data-stu-id="a1dec-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="a1dec-104">也有冗余`Class`语句，或你有未结束您`Class`块`End Class`。</span><span class="sxs-lookup"><span data-stu-id="a1dec-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>  
  
 <span data-ttu-id="a1dec-105">**错误 ID:** BC30481</span><span class="sxs-lookup"><span data-stu-id="a1dec-105">**Error ID:** BC30481</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a1dec-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="a1dec-106">To correct this error</span></span>  
  
-   <span data-ttu-id="a1dec-107">找到并删除不必要的 `Class` 语句。</span><span class="sxs-lookup"><span data-stu-id="a1dec-107">Locate and remove the unnecessary `Class` statement.</span></span>  
  
-   <span data-ttu-id="a1dec-108">得出的结论`Class`块以匹配的`End Class`。</span><span class="sxs-lookup"><span data-stu-id="a1dec-108">Conclude the `Class` block with a matching `End Class`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1dec-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1dec-109">See also</span></span>
- [<span data-ttu-id="a1dec-110">结束\<关键字 > 语句</span><span class="sxs-lookup"><span data-stu-id="a1dec-110">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
- [<span data-ttu-id="a1dec-111">Class 语句</span><span class="sxs-lookup"><span data-stu-id="a1dec-111">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
