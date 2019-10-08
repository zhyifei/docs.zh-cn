---
title: Continue 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 9ee5fb19db6eafeb7e4bed12935d0b950d6368d6
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005102"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="79c9f-102">Continue 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79c9f-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="79c9f-103">将控制立即传输到循环的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="79c9f-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79c9f-104">语法</span><span class="sxs-lookup"><span data-stu-id="79c9f-104">Syntax</span></span>  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="79c9f-105">备注</span><span class="sxs-lookup"><span data-stu-id="79c9f-105">Remarks</span></span>  
 <span data-ttu-id="79c9f-106">可以从 `Do`、`For` 或 `While` 循环内传输到循环的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="79c9f-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="79c9f-107">控制权会立即传递到循环条件测试，这等效于转移到 `For` 或 `While` 语句，或传递到包含 @no__t 或 @no__t 子句的 `Do` 或 @no__t 3 语句。</span><span class="sxs-lookup"><span data-stu-id="79c9f-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="79c9f-108">可以在允许传输的循环中的任意位置使用 `Continue`。</span><span class="sxs-lookup"><span data-stu-id="79c9f-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="79c9f-109">允许传输控件的规则与[GoTo 语句](../../../visual-basic/language-reference/statements/goto-statement.md)相同。</span><span class="sxs-lookup"><span data-stu-id="79c9f-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="79c9f-110">例如，如果一个循环完全包含在 @no__t 0 块、@no__t 块或 @no__t 2 块中，则可以使用 `Continue` 来传出循环。</span><span class="sxs-lookup"><span data-stu-id="79c9f-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="79c9f-111">另一方面，如果 `Try` ... `End Try` 结构包含在循环中，则不能使用 `Continue` 来将控制转移出 `Finally` 块，并且仅当完全从 @no__t 传输时，才能使用它从 @no__t 或 @no_ 块中传出_t-6 `End Try` 结构。</span><span class="sxs-lookup"><span data-stu-id="79c9f-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="79c9f-112">如果有相同类型的嵌套循环（例如，另一个 `Do` 循环内的 @no__t 0 循环），则 `Continue Do` 语句将跳转到包含它的最 @no__t 内层的第3个循环的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="79c9f-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="79c9f-113">不能使用 `Continue` 跳到相同类型的包含循环的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="79c9f-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="79c9f-114">如果具有不同类型的嵌套循环（例如，在 @no__t 1 循环内的 @no__t 0 循环），则可以使用 `Continue Do` 或 `Continue For` 跳到任一循环的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="79c9f-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79c9f-115">示例</span><span class="sxs-lookup"><span data-stu-id="79c9f-115">Example</span></span>  
 <span data-ttu-id="79c9f-116">下面的代码示例使用 `Continue While` 语句跳转到数组的下一列（如果除数为零）。</span><span class="sxs-lookup"><span data-stu-id="79c9f-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="79c9f-117">@No__t-0 在 @no__t 循环中。</span><span class="sxs-lookup"><span data-stu-id="79c9f-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="79c9f-118">它传输到 `While col < lastcol` 语句，该语句是包含 @no__t 2 循环的最内层 `While` 循环的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="79c9f-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="79c9f-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="79c9f-119">See also</span></span>

- [<span data-ttu-id="79c9f-120">Do...Loop 语句</span><span class="sxs-lookup"><span data-stu-id="79c9f-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="79c9f-121">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="79c9f-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="79c9f-122">While...End While 语句</span><span class="sxs-lookup"><span data-stu-id="79c9f-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="79c9f-123">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="79c9f-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
