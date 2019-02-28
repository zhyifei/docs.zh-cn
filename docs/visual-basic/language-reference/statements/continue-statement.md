---
title: Continue 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 7aa0bda9c87553a5c9dae38517b5d546f782bed0
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974076"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="0c26a-102">Continue 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c26a-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="0c26a-103">传输控制立即传递给循环的下一个迭代。</span><span class="sxs-lookup"><span data-stu-id="0c26a-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c26a-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c26a-104">Syntax</span></span>  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="0c26a-105">备注</span><span class="sxs-lookup"><span data-stu-id="0c26a-105">Remarks</span></span>  
 <span data-ttu-id="0c26a-106">您可以从内部`Do`， `For`，或`While`到该循环的下一个迭代循环。</span><span class="sxs-lookup"><span data-stu-id="0c26a-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="0c26a-107">控制将传递给循环条件测试，相当于将转移到立即`For`或`While`语句，或设置为`Do`或`Loop`包含的语句`Until`或`While`子句。</span><span class="sxs-lookup"><span data-stu-id="0c26a-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="0c26a-108">可以使用`Continue`循环，以便传输中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="0c26a-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="0c26a-109">允许控制传输的规则将与具有相同[GoTo 语句](../../../visual-basic/language-reference/statements/goto-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="0c26a-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="0c26a-110">例如，如果循环是指完全包含在`Try`块中，`Catch`块中，或`Finally`块中，可以使用`Continue`将跳出循环。</span><span class="sxs-lookup"><span data-stu-id="0c26a-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="0c26a-111">如果在另一只手， `Try`...`End Try`结构是否包含在循环内，则不能使用`Continue`若要将控制转移出`Finally`块中，您可以使用它来转移出`Try`或`Catch`阻止仅在完全传输共时`Try`...`End Try`结构。</span><span class="sxs-lookup"><span data-stu-id="0c26a-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="0c26a-112">如果您具有嵌套的循环的相同的类型，例如`Do`在另一个循环`Do`循环中，`Continue Do`语句将跳到下一个迭代的最内层`Do`包含它的循环。</span><span class="sxs-lookup"><span data-stu-id="0c26a-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="0c26a-113">不能使用`Continue`跳到相同类型的包含循环的下一个迭代。</span><span class="sxs-lookup"><span data-stu-id="0c26a-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="0c26a-114">如果您有嵌套的循环的不同类型，例如`Do`内循环`For`循环中，则可以跳到任一循环的下一迭代使用`Continue Do`或`Continue For`。</span><span class="sxs-lookup"><span data-stu-id="0c26a-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c26a-115">示例</span><span class="sxs-lookup"><span data-stu-id="0c26a-115">Example</span></span>  
 <span data-ttu-id="0c26a-116">下面的代码示例使用`Continue While`语句可以跳到下一列的数组，如果除数为零。</span><span class="sxs-lookup"><span data-stu-id="0c26a-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="0c26a-117">`Continue While`位于`For`循环。</span><span class="sxs-lookup"><span data-stu-id="0c26a-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="0c26a-118">将对传输`While col < lastcol`语句，这是最内层的下一个迭代`While`循环包含`For`循环。</span><span class="sxs-lookup"><span data-stu-id="0c26a-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="0c26a-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c26a-119">See also</span></span>
- [<span data-ttu-id="0c26a-120">Do...Loop 语句</span><span class="sxs-lookup"><span data-stu-id="0c26a-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="0c26a-121">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="0c26a-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="0c26a-122">While...End While 语句</span><span class="sxs-lookup"><span data-stu-id="0c26a-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="0c26a-123">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="0c26a-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
