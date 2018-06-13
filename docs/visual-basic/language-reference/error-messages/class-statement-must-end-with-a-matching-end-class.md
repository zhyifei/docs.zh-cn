---
title: '&#39;类&#39;语句必须以匹配结束&#39;结束类&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 7c9051b15f6d9cf37d7d0245f758905467d5bbc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585510"
---
# <a name="39class39-statement-must-end-with-a-matching-39end-class39"></a><span data-ttu-id="125cc-102">&#39;类&#39;语句必须以匹配结束&#39;结束类&#39;</span><span class="sxs-lookup"><span data-stu-id="125cc-102">&#39;Class&#39; statement must end with a matching &#39;End Class&#39;</span></span>
<span data-ttu-id="125cc-103">`Class` 用于启动`Class`块; 因此它只能出现在块中，以匹配开头`End Class`语句结束块。</span><span class="sxs-lookup"><span data-stu-id="125cc-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="125cc-104">有冗余`Class`语句，或你有未结束你`Class`块`End Class`。</span><span class="sxs-lookup"><span data-stu-id="125cc-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>  
  
 <span data-ttu-id="125cc-105">**错误 ID:** BC30481</span><span class="sxs-lookup"><span data-stu-id="125cc-105">**Error ID:** BC30481</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="125cc-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="125cc-106">To correct this error</span></span>  
  
-   <span data-ttu-id="125cc-107">找到并删除不必要`Class`语句。</span><span class="sxs-lookup"><span data-stu-id="125cc-107">Locate and remove the unnecessary `Class` statement.</span></span>  
  
-   <span data-ttu-id="125cc-108">结束`Class`块以匹配`End Class`。</span><span class="sxs-lookup"><span data-stu-id="125cc-108">Conclude the `Class` block with a matching `End Class`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="125cc-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="125cc-109">See Also</span></span>  
 [<span data-ttu-id="125cc-110">结束\<关键字 > 语句</span><span class="sxs-lookup"><span data-stu-id="125cc-110">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)  
 [<span data-ttu-id="125cc-111">Class 语句</span><span class="sxs-lookup"><span data-stu-id="125cc-111">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
