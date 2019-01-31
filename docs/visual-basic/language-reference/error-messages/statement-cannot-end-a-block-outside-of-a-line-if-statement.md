---
title: 语句不能在“If”语句行之外结束块
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 0cee52f0ca00395d93c469aae6498fd3793f1085
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266304"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="0aef7-102">语句不能在“If”语句行之外结束块</span><span class="sxs-lookup"><span data-stu-id="0aef7-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="0aef7-103">单行`If`语句包含多个语句之一就是的冒号 （:） 分隔`End`语句的控制块的外部的单行`If`。</span><span class="sxs-lookup"><span data-stu-id="0aef7-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="0aef7-104">单行`If`语句不使用`End If`语句。</span><span class="sxs-lookup"><span data-stu-id="0aef7-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="0aef7-105">**错误 ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="0aef7-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0aef7-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0aef7-106">To correct this error</span></span>  
  
-   <span data-ttu-id="0aef7-107">移动的单行`If`语句包含的控制块之外`End If`语句。</span><span class="sxs-lookup"><span data-stu-id="0aef7-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aef7-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="0aef7-108">See also</span></span>
- [<span data-ttu-id="0aef7-109">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="0aef7-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
