---
title: 语句不能结束行之外的块&#39;如果&#39;语句
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 78fe136acbd09e202b1daeb16dd540cf42ada390
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574711"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a><span data-ttu-id="bcc3b-102">语句不能结束行之外的块&#39;如果&#39;语句</span><span class="sxs-lookup"><span data-stu-id="bcc3b-102">Statement cannot end a block outside of a line &#39;If&#39; statement</span></span>
<span data-ttu-id="bcc3b-103">单行`If`语句包含多个语句之一就是的冒号 （:） 分隔`End`语句的控制块的外部的单行`If`。</span><span class="sxs-lookup"><span data-stu-id="bcc3b-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="bcc3b-104">单行`If`语句不使用`End If`语句。</span><span class="sxs-lookup"><span data-stu-id="bcc3b-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="bcc3b-105">**错误 ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="bcc3b-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bcc3b-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="bcc3b-106">To correct this error</span></span>  
  
-   <span data-ttu-id="bcc3b-107">移动的单行`If`语句包含的控制块之外`End If`语句。</span><span class="sxs-lookup"><span data-stu-id="bcc3b-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc3b-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="bcc3b-108">See also</span></span>
- [<span data-ttu-id="bcc3b-109">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="bcc3b-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
