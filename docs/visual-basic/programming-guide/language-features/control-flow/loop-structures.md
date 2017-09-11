---
title: "循环结构 (Visual Basic) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- control flow, loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures
- statements [Visual Basic], loop
- Do statement, Do loops
- conditional statements, loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
caps.latest.revision: 18
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
ms.openlocfilehash: eba728d782bb5a6259467fb48f738f35580049c0
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="69069-102">循环结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69069-102">Loop Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="69069-103">循环结构允许您重复运行的代码的一个或多个行。</span><span class="sxs-lookup"><span data-stu-id="69069-103"> loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="69069-104">您可以重复循环结构中的语句，直到条件为`True`，直到条件为`False`、 在集合中指定的次数，或者一次为每个元素。</span><span class="sxs-lookup"><span data-stu-id="69069-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="69069-105">下图显示运行的一组语句，直到条件变为真后在循环结构。</span><span class="sxs-lookup"><span data-stu-id="69069-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true.</span></span>  
  
 <span data-ttu-id="69069-106">![流程图显示了 do...循环](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span><span class="sxs-lookup"><span data-stu-id="69069-106">![Flow chart of a Do...Until loop](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span></span>  
<span data-ttu-id="69069-107">运行一组语句，直到条件变为 true</span><span class="sxs-lookup"><span data-stu-id="69069-107">Running a set of statements until a condition becomes true</span></span>  
  
## <a name="while-loops"></a><span data-ttu-id="69069-108">While 循环</span><span class="sxs-lookup"><span data-stu-id="69069-108">While Loops</span></span>  
 <span data-ttu-id="69069-109">The `While`...`End While`构造，只要中指定的条件运行的一组语句`While`语句是`True`。</span><span class="sxs-lookup"><span data-stu-id="69069-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="69069-110">有关详细信息，请参阅[时...While 语句结束](../../../../visual-basic/language-reference/statements/while-end-while-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="69069-110">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="69069-111">Do 循环</span><span class="sxs-lookup"><span data-stu-id="69069-111">Do Loops</span></span>  
 <span data-ttu-id="69069-112">The `Do`...`Loop`构造允许您开头或末尾循环结构对条件进行测试。</span><span class="sxs-lookup"><span data-stu-id="69069-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="69069-113">您还可以指定是否在条件时重复循环`True`或直到它成为`True`。</span><span class="sxs-lookup"><span data-stu-id="69069-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="69069-114">有关详细信息，请参阅[做...循环语句](../../../../visual-basic/language-reference/statements/do-loop-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="69069-114">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="69069-115">For 循环</span><span class="sxs-lookup"><span data-stu-id="69069-115">For Loops</span></span>  
 <span data-ttu-id="69069-116">The `For`...`Next`构造执行循环次数。</span><span class="sxs-lookup"><span data-stu-id="69069-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="69069-117">它使用循环控制变量，也称为*计数器*，若要跟踪的重复。</span><span class="sxs-lookup"><span data-stu-id="69069-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="69069-118">指定的开始和结束此计数器的数值，您可以选择指定的量递增一次重复从下一步。</span><span class="sxs-lookup"><span data-stu-id="69069-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="69069-119">有关详细信息，请参阅[为...下一条语句](../../../../visual-basic/language-reference/statements/for-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="69069-119">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="69069-120">For Each 循环</span><span class="sxs-lookup"><span data-stu-id="69069-120">For Each Loops</span></span>  
 <span data-ttu-id="69069-121">The `For Each`...`Next`构造为集合中运行的一组对于每个元素执行一次的语句。</span><span class="sxs-lookup"><span data-stu-id="69069-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="69069-122">指定循环控制变量，但不是需要确定启动或终止值。</span><span class="sxs-lookup"><span data-stu-id="69069-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="69069-123">有关详细信息，请参阅[为每个...下一条语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="69069-123">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69069-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69069-124">See Also</span></span>  
 <span data-ttu-id="69069-125">[控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="69069-125">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="69069-126"> [决策结构](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span><span class="sxs-lookup"><span data-stu-id="69069-126"> [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span></span>  
<span data-ttu-id="69069-127"> [其他控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="69069-127"> [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span></span>  
<span data-ttu-id="69069-128"> [嵌套的控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)</span><span class="sxs-lookup"><span data-stu-id="69069-128"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)</span></span>
