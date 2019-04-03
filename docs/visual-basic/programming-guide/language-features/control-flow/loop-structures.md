---
title: 循环结构 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
ms.openlocfilehash: 56165eecce5e73c4e06235dac1691774fb39b794
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833293"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="380a3-102">循环结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="380a3-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="380a3-103">Visual Basic 循环结构，可运行的代码的一个或多个行重复损坏。</span><span class="sxs-lookup"><span data-stu-id="380a3-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="380a3-104">您可以重复循环结构中的语句，直到条件为`True`，直到条件为`False`、 在集合中指定的次数，或者一次的每个元素。</span><span class="sxs-lookup"><span data-stu-id="380a3-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="380a3-105">下图显示了运行一组语句，直到条件变为 true 的循环结构：</span><span class="sxs-lookup"><span data-stu-id="380a3-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![流程图，显示操作...Until 循环。](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="380a3-107">While 循环</span><span class="sxs-lookup"><span data-stu-id="380a3-107">While Loops</span></span>  
 <span data-ttu-id="380a3-108">`While`...`End While`构造运行一组语句中指定的条件，只要`While`语句是`True`。</span><span class="sxs-lookup"><span data-stu-id="380a3-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="380a3-109">有关详细信息，请参阅[时...While 语句结束](../../../../visual-basic/language-reference/statements/while-end-while-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="380a3-109">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="380a3-110">Do 循环</span><span class="sxs-lookup"><span data-stu-id="380a3-110">Do Loops</span></span>  
 <span data-ttu-id="380a3-111">`Do`...`Loop`构造允许您在开始或结束循环结构对条件进行测试。</span><span class="sxs-lookup"><span data-stu-id="380a3-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="380a3-112">此外可以指定是否在重复循环条件保持`True`或直到其变为`True`。</span><span class="sxs-lookup"><span data-stu-id="380a3-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="380a3-113">有关详细信息，请参阅[执行操作...循环语句](../../../../visual-basic/language-reference/statements/do-loop-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="380a3-113">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="380a3-114">For 循环</span><span class="sxs-lookup"><span data-stu-id="380a3-114">For Loops</span></span>  
 <span data-ttu-id="380a3-115">`For`...`Next`构造执行循环次数。</span><span class="sxs-lookup"><span data-stu-id="380a3-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="380a3-116">它使用循环控制变量，也称为*计数器*，若要跟踪的重复项。</span><span class="sxs-lookup"><span data-stu-id="380a3-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="380a3-117">指定的起始和结束此计数器的数值，您可以选择指定的量递增一次重复从到下一步。</span><span class="sxs-lookup"><span data-stu-id="380a3-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="380a3-118">有关详细信息，请参阅[为...下一条语句](../../../../visual-basic/language-reference/statements/for-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="380a3-118">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="380a3-119">For Each 循环</span><span class="sxs-lookup"><span data-stu-id="380a3-119">For Each Loops</span></span>  
 <span data-ttu-id="380a3-120">`For Each`...`Next`构造为集合中运行一组一次为每个元素的语句。</span><span class="sxs-lookup"><span data-stu-id="380a3-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="380a3-121">指定循环控制变量，但不是需要确定启动或为其结束值。</span><span class="sxs-lookup"><span data-stu-id="380a3-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="380a3-122">有关详细信息，请参阅[为每个...下一条语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="380a3-122">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="380a3-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="380a3-123">See also</span></span>

- [<span data-ttu-id="380a3-124">控制流</span><span class="sxs-lookup"><span data-stu-id="380a3-124">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="380a3-125">决策结构</span><span class="sxs-lookup"><span data-stu-id="380a3-125">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="380a3-126">其他控件结构</span><span class="sxs-lookup"><span data-stu-id="380a3-126">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="380a3-127">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="380a3-127">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
