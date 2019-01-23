---
title: GoTo 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: 729ff2a9cbeacaefdf0452a6c5868c229a8d05b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582521"
---
# <a name="goto-statement"></a><span data-ttu-id="958be-102">GoTo 语句</span><span class="sxs-lookup"><span data-stu-id="958be-102">GoTo Statement</span></span>
<span data-ttu-id="958be-103">无条件地分支到过程中指定的行。</span><span class="sxs-lookup"><span data-stu-id="958be-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="958be-104">语法</span><span class="sxs-lookup"><span data-stu-id="958be-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="958be-105">部件</span><span class="sxs-lookup"><span data-stu-id="958be-105">Part</span></span>  
 `line`  
 <span data-ttu-id="958be-106">必需。</span><span class="sxs-lookup"><span data-stu-id="958be-106">Required.</span></span> <span data-ttu-id="958be-107">所有行标签。</span><span class="sxs-lookup"><span data-stu-id="958be-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="958be-108">备注</span><span class="sxs-lookup"><span data-stu-id="958be-108">Remarks</span></span>  
 <span data-ttu-id="958be-109">`GoTo`语句只能跳转到它在其中出现的过程中的行。</span><span class="sxs-lookup"><span data-stu-id="958be-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="958be-110">在行必须具有的行标签`GoTo`可以引用。</span><span class="sxs-lookup"><span data-stu-id="958be-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="958be-111">有关详细信息，请参阅[如何：标记语句](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)。</span><span class="sxs-lookup"><span data-stu-id="958be-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="958be-112">`GoTo` 语句可以使代码难以阅读和维护。</span><span class="sxs-lookup"><span data-stu-id="958be-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="958be-113">只要有可能，请改为使用控制结构。</span><span class="sxs-lookup"><span data-stu-id="958be-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="958be-114">有关详细信息，请参阅[控制流](../../../visual-basic/programming-guide/language-features/control-flow/index.md)。</span><span class="sxs-lookup"><span data-stu-id="958be-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="958be-115">不能使用`GoTo`语句从外部`For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`，或`Using`...`End Using`构造中为标签。</span><span class="sxs-lookup"><span data-stu-id="958be-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="958be-116">分支和尝试构造</span><span class="sxs-lookup"><span data-stu-id="958be-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="958be-117">在`Try`...`Catch`...`Finally`构造中，以下规则适用于与分支`GoTo`语句。</span><span class="sxs-lookup"><span data-stu-id="958be-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="958be-118">块或区域</span><span class="sxs-lookup"><span data-stu-id="958be-118">Block or region</span></span>|<span data-ttu-id="958be-119">从外部中分支</span><span class="sxs-lookup"><span data-stu-id="958be-119">Branching in from outside</span></span>|<span data-ttu-id="958be-120">从内向外分支</span><span class="sxs-lookup"><span data-stu-id="958be-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="958be-121">`Try` 块</span><span class="sxs-lookup"><span data-stu-id="958be-121">`Try` block</span></span>|<span data-ttu-id="958be-122">只能从`Catch`相同的构造块<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="958be-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="958be-123">只能与整个构造外部</span><span class="sxs-lookup"><span data-stu-id="958be-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="958be-124">`Catch` 块</span><span class="sxs-lookup"><span data-stu-id="958be-124">`Catch` block</span></span>|<span data-ttu-id="958be-125">永远不允许</span><span class="sxs-lookup"><span data-stu-id="958be-125">Never allowed</span></span>|<span data-ttu-id="958be-126">只能与整个构造外部或设置为`Try`相同的构造块<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="958be-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="958be-127">`Finally` 块</span><span class="sxs-lookup"><span data-stu-id="958be-127">`Finally` block</span></span>|<span data-ttu-id="958be-128">永远不允许</span><span class="sxs-lookup"><span data-stu-id="958be-128">Never allowed</span></span>|<span data-ttu-id="958be-129">永远不允许</span><span class="sxs-lookup"><span data-stu-id="958be-129">Never allowed</span></span>|  
  
 <span data-ttu-id="958be-130"><sup>1</sup>如果一个`Try`...`Catch`...`Finally`构造嵌套在另一个，`Catch`块可以分支到`Try`块在其自己的嵌套级别，但不是到任何其他`Try`块。</span><span class="sxs-lookup"><span data-stu-id="958be-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="958be-131">嵌套`Try`...`Catch`...`Finally`构造必须完全在包含`Try`或`Catch`块在其中嵌套的构造。</span><span class="sxs-lookup"><span data-stu-id="958be-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="958be-132">下图显示了一个`Try`构造嵌套在另一个。</span><span class="sxs-lookup"><span data-stu-id="958be-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="958be-133">在这两个构造块之间的各分支将予以有效或无效。</span><span class="sxs-lookup"><span data-stu-id="958be-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 <span data-ttu-id="958be-134">![Try 构造结构分支示意图](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span><span class="sxs-lookup"><span data-stu-id="958be-134">![Graphic diagram of branching in Try constructions](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span></span>  
<span data-ttu-id="958be-135">Try 构造中的有效和无效的分支</span><span class="sxs-lookup"><span data-stu-id="958be-135">Valid and invalid branches in Try constructions</span></span>  
  
## <a name="example"></a><span data-ttu-id="958be-136">示例</span><span class="sxs-lookup"><span data-stu-id="958be-136">Example</span></span>  
 <span data-ttu-id="958be-137">下面的示例使用`GoTo`分支到过程中的线条标签的语句。</span><span class="sxs-lookup"><span data-stu-id="958be-137">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="958be-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="958be-138">See also</span></span>
- [<span data-ttu-id="958be-139">Do...Loop 语句</span><span class="sxs-lookup"><span data-stu-id="958be-139">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="958be-140">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="958be-140">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="958be-141">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="958be-141">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="958be-142">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="958be-142">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="958be-143">Select...Case 语句</span><span class="sxs-lookup"><span data-stu-id="958be-143">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="958be-144">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="958be-144">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="958be-145">While...End While 语句</span><span class="sxs-lookup"><span data-stu-id="958be-145">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="958be-146">With...End With 语句</span><span class="sxs-lookup"><span data-stu-id="958be-146">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
