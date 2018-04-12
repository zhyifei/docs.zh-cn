---
title: Continue 语句 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a47819600a6c1d58f09c2f8ed3443632e9dab68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="5b003-102">Continue 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b003-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="5b003-103">传输控制立即传递给循环的下一个迭代。</span><span class="sxs-lookup"><span data-stu-id="5b003-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b003-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b003-104">Syntax</span></span>  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="5b003-105">备注</span><span class="sxs-lookup"><span data-stu-id="5b003-105">Remarks</span></span>  
 <span data-ttu-id="5b003-106">你可以将从传输内`Do`， `For`，或`While`到该循环的下一个迭代的循环。</span><span class="sxs-lookup"><span data-stu-id="5b003-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="5b003-107">控制将传递给循环条件测试，这等效于将传输到立即`For`或`While`语句，或`Do`或`Loop`包含语句`Until`或`While`子句。</span><span class="sxs-lookup"><span data-stu-id="5b003-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="5b003-108">你可以使用`Continue`允许传输该循环中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="5b003-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="5b003-109">允许控制的转移的规则是与相同[GoTo 语句](../../../visual-basic/language-reference/statements/goto-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="5b003-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="5b003-110">例如，如果循环是完全包含在`Try`块，`Catch`块，或`Finally`块中，你可以使用`Continue`传输出循环。</span><span class="sxs-lookup"><span data-stu-id="5b003-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="5b003-111">另一方面，如果`Try`...`End Try`结构是否包含在循环内，不能使用`Continue`来将控制转移出`Finally`块中，你可以使用它来转移出`Try`或`Catch`阻止仅在完全外传输`Try`...`End Try`结构。</span><span class="sxs-lookup"><span data-stu-id="5b003-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="5b003-112">如果你有嵌套的循环相同的类型，例如`Do`另循环内的`Do`循环，`Continue Do`语句将跳到下一个迭代的最内层`Do`包含它的循环。</span><span class="sxs-lookup"><span data-stu-id="5b003-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="5b003-113">不能使用`Continue`跳到包含相同类型的循环的下一个迭代。</span><span class="sxs-lookup"><span data-stu-id="5b003-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="5b003-114">如果你有嵌套的循环的不同的类型，例如`Do`循环内`For`循环，则可以跳到任一循环的下一个迭代使用`Continue Do`或`Continue For`。</span><span class="sxs-lookup"><span data-stu-id="5b003-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b003-115">示例</span><span class="sxs-lookup"><span data-stu-id="5b003-115">Example</span></span>  
 <span data-ttu-id="5b003-116">下面的代码示例使用`Continue While`语句跳到下一列的数组，如果除数为零。</span><span class="sxs-lookup"><span data-stu-id="5b003-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="5b003-117">`Continue While`位于`For`循环。</span><span class="sxs-lookup"><span data-stu-id="5b003-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="5b003-118">它传输到`While col < lastcol`语句，这是最内层的下一个迭代`While`循环包含`For`循环。</span><span class="sxs-lookup"><span data-stu-id="5b003-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5b003-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b003-119">See Also</span></span>  
 [<span data-ttu-id="5b003-120">Do...Loop 语句</span><span class="sxs-lookup"><span data-stu-id="5b003-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="5b003-121">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="5b003-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="5b003-122">While...End While 语句</span><span class="sxs-lookup"><span data-stu-id="5b003-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="5b003-123">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="5b003-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
