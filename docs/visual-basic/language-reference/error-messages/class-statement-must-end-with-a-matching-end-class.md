---
title: "&#39;类 &#39;语句必须以匹配 &#39; 结束End Class &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords: BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e8643a0a5b55e220ca8dd53065500fe4b1e473d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39class39-statement-must-end-with-a-matching-39end-class39"></a><span data-ttu-id="e06a3-102">&#39;类 &#39;语句必须以匹配 &#39; 结束End Class &#39;</span><span class="sxs-lookup"><span data-stu-id="e06a3-102">&#39;Class&#39; statement must end with a matching &#39;End Class&#39;</span></span>
<span data-ttu-id="e06a3-103">`Class`用于启动`Class`块; 因此它只能出现在块中，以匹配开头`End Class`语句结束块。</span><span class="sxs-lookup"><span data-stu-id="e06a3-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="e06a3-104">有冗余`Class`语句，或你有未结束你`Class`块`End Class`。</span><span class="sxs-lookup"><span data-stu-id="e06a3-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>  
  
 <span data-ttu-id="e06a3-105">**错误 ID:** BC30481</span><span class="sxs-lookup"><span data-stu-id="e06a3-105">**Error ID:** BC30481</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e06a3-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e06a3-106">To correct this error</span></span>  
  
-   <span data-ttu-id="e06a3-107">找到并删除不必要`Class`语句。</span><span class="sxs-lookup"><span data-stu-id="e06a3-107">Locate and remove the unnecessary `Class` statement.</span></span>  
  
-   <span data-ttu-id="e06a3-108">结束`Class`块以匹配`End Class`。</span><span class="sxs-lookup"><span data-stu-id="e06a3-108">Conclude the `Class` block with a matching `End Class`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e06a3-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e06a3-109">See Also</span></span>  
 [<span data-ttu-id="e06a3-110">结束\<关键字 > 语句</span><span class="sxs-lookup"><span data-stu-id="e06a3-110">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)  
 [<span data-ttu-id="e06a3-111">Class 语句</span><span class="sxs-lookup"><span data-stu-id="e06a3-111">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
