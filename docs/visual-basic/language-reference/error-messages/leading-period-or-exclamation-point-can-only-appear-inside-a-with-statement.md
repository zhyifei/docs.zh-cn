---
title: "前导 &#39;。&#39;或 &#39; ！&#39;只能出现在 &#39;使用 &#39;语句"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords: BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 961f2d737123ab68b200d5fc7658cb81291a5de6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a><span data-ttu-id="52889-102">前导 &#39;。&#39;或 &#39; ！&#39;只能出现在 &#39;使用 &#39;语句</span><span class="sxs-lookup"><span data-stu-id="52889-102">Leading &#39;.&#39; or &#39;!&#39; can only appear inside a &#39;With&#39; statement</span></span>
<span data-ttu-id="52889-103">句点 （.） 或感叹号 （！） 不内部`With`块没有左侧的表达式时出现。</span><span class="sxs-lookup"><span data-stu-id="52889-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="52889-104">成员访问 (`.`) 和字典成员访问 (`!`) 需要一个表达式来指定包含该成员的元素。</span><span class="sxs-lookup"><span data-stu-id="52889-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="52889-105">这必须紧靠的左边的访问器或作为目标的`With`包含成员访问的块。</span><span class="sxs-lookup"><span data-stu-id="52889-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="52889-106">**错误 ID:** BC30157</span><span class="sxs-lookup"><span data-stu-id="52889-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="52889-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="52889-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="52889-108">确保`With`块的格式正确。</span><span class="sxs-lookup"><span data-stu-id="52889-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2.  <span data-ttu-id="52889-109">如果没有任何`With`块中，将表达式添加到包含成员的定义元素的计算结果的访问器的左侧。</span><span class="sxs-lookup"><span data-stu-id="52889-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52889-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52889-110">See Also</span></span>  
 [<span data-ttu-id="52889-111">代码中的特殊字符</span><span class="sxs-lookup"><span data-stu-id="52889-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [<span data-ttu-id="52889-112">With...End With 语句</span><span class="sxs-lookup"><span data-stu-id="52889-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
