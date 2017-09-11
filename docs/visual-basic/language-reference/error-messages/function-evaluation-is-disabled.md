---
title: "已禁用函数求值，因为前一个函数求值超时 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30957
- vbc30957
dev_langs:
- VB
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 127f89f4c7ddaf794f58707d8925731a511f3740
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="45815-102">已禁用函数求值，因为前一个函数求值超时</span><span class="sxs-lookup"><span data-stu-id="45815-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="45815-103">由于上一个函数求值超时，已禁用函数求值。</span><span class="sxs-lookup"><span data-stu-id="45815-103">Function evaluation is disabled because a previous function evaluation timed out.</span></span> <span data-ttu-id="45815-104">若要重新启用函数求值，请再次单步执行或重新启动调试。</span><span class="sxs-lookup"><span data-stu-id="45815-104">To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="45815-105">在 Visual Studio 调试器中，表达式可以指定过程调用，但另一个计算已超时。</span><span class="sxs-lookup"><span data-stu-id="45815-105">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="45815-106">超时时间的过程调用的可能原因包括无限循环或*无穷循环*。</span><span class="sxs-lookup"><span data-stu-id="45815-106">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="45815-107">有关详细信息，请参阅[为...下一条语句](../../../visual-basic/language-reference/statements/for-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="45815-107">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="45815-108">无限循环的一种特殊情况是*递归*。</span><span class="sxs-lookup"><span data-stu-id="45815-108">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="45815-109">有关详细信息，请参阅[递归过程](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="45815-109">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="45815-110">**错误 ID:** BC30957</span><span class="sxs-lookup"><span data-stu-id="45815-110">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="45815-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="45815-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="45815-112">如果可能，请确定前一个函数求值是什么以及引起超时。</span><span class="sxs-lookup"><span data-stu-id="45815-112">If possible, determine what the previous function evaluation was and what caused it to time out.</span></span> <span data-ttu-id="45815-113">否则，可能会再次遇到此错误。</span><span class="sxs-lookup"><span data-stu-id="45815-113">Otherwise, you might encounter this error again.</span></span>  
  
2.  <span data-ttu-id="45815-114">请再次，调试器单步执行或终止并重新启动调试。</span><span class="sxs-lookup"><span data-stu-id="45815-114">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45815-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45815-115">See Also</span></span>  
 <span data-ttu-id="45815-116">[在 Visual Studio 中进行调试](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="45815-116">[Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span></span>  
<span data-ttu-id="45815-117"> [使用调试器浏览代码](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)</span><span class="sxs-lookup"><span data-stu-id="45815-117"> [Navigating through Code with the Debugger](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)</span></span>
