---
title: 已禁用函数求值，因为前一个函数求值超时
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: 6231d48f3f90d8e436dc80bf4670886c1d030387
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587643"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="89074-102">已禁用函数求值，因为前一个函数求值超时</span><span class="sxs-lookup"><span data-stu-id="89074-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="89074-103">由于以前的函数求值的操作已超时，已禁用函数求值。若要重新启用函数求值，请再次单步执行或重新启动调试。</span><span class="sxs-lookup"><span data-stu-id="89074-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="89074-104">在 Visual Studio 调试器中，表达式指定一个过程调用，但另一个计算已超时。</span><span class="sxs-lookup"><span data-stu-id="89074-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="89074-105">超时的过程调用的可能原因包括无限循环或*无限循环*。</span><span class="sxs-lookup"><span data-stu-id="89074-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="89074-106">有关详细信息，请参阅[为...下一条语句](../../../visual-basic/language-reference/statements/for-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="89074-106">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="89074-107">一个无限循环的特殊情况是*递归*。</span><span class="sxs-lookup"><span data-stu-id="89074-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="89074-108">有关详细信息，请参阅[递归过程](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="89074-108">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="89074-109">**错误 ID:** BC30957</span><span class="sxs-lookup"><span data-stu-id="89074-109">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="89074-110">更正此错误</span><span class="sxs-lookup"><span data-stu-id="89074-110">To correct this error</span></span>  
  
1.  <span data-ttu-id="89074-111">如果可能，请确定前一个函数求值是什么以及引起超时。否则，你可能会再次遇到此错误。</span><span class="sxs-lookup"><span data-stu-id="89074-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>  
  
2.  <span data-ttu-id="89074-112">请再次，调试器单步执行或终止并重新启动调试。</span><span class="sxs-lookup"><span data-stu-id="89074-112">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89074-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="89074-113">See Also</span></span>  
 [<span data-ttu-id="89074-114">在 Visual Studio 中进行调试</span><span class="sxs-lookup"><span data-stu-id="89074-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)  
 [<span data-ttu-id="89074-115">使用调试器浏览代码</span><span class="sxs-lookup"><span data-stu-id="89074-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
