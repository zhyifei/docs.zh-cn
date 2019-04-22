---
title: 语句不能在“If”语句行之外结束块
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 85573099ec0a3f8a23c17bdf384c4c105f9157df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825784"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="63996-102">语句不能在“If”语句行之外结束块</span><span class="sxs-lookup"><span data-stu-id="63996-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="63996-103">单行`If`语句包含多个语句之一就是的冒号 （:） 分隔`End`语句的控制块的外部的单行`If`。</span><span class="sxs-lookup"><span data-stu-id="63996-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="63996-104">单行`If`语句不使用`End If`语句。</span><span class="sxs-lookup"><span data-stu-id="63996-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="63996-105">**错误 ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="63996-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="63996-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="63996-106">To correct this error</span></span>  
  
-   <span data-ttu-id="63996-107">移动的单行`If`语句包含的控制块之外`End If`语句。</span><span class="sxs-lookup"><span data-stu-id="63996-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63996-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="63996-108">See also</span></span>

- [<span data-ttu-id="63996-109">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="63996-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
