---
title: 循环结构 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8c13f2cc6546a652f0967bd83369d8af5998f7e2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="4d6bd-102">循环结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d6bd-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="4d6bd-103">Visual Basic 循环结构，可以重复运行的代码的一个或多个行。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="4d6bd-104">您可以重复循环结构中的语句，直到条件为`True`，直到条件`False`，集合中指定的次数，或者一次每个元素。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="4d6bd-105">下图显示运行一组语句，直到条件变为真循环结构。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true.</span></span>  
  
 <span data-ttu-id="4d6bd-106">![流程图显示了 do...直到循环](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span><span class="sxs-lookup"><span data-stu-id="4d6bd-106">![Flow chart of a Do...Until loop](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span></span>  
<span data-ttu-id="4d6bd-107">运行一组语句，直到条件变为 true</span><span class="sxs-lookup"><span data-stu-id="4d6bd-107">Running a set of statements until a condition becomes true</span></span>  
  
## <a name="while-loops"></a><span data-ttu-id="4d6bd-108">While 循环</span><span class="sxs-lookup"><span data-stu-id="4d6bd-108">While Loops</span></span>  
 <span data-ttu-id="4d6bd-109">`While`...`End While`构造只要中指定的条件运行一组语句`While`语句是`True`。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="4d6bd-110">有关详细信息，请参阅[时...While 语句结束](../../../../visual-basic/language-reference/statements/while-end-while-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-110">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="4d6bd-111">Do 循环</span><span class="sxs-lookup"><span data-stu-id="4d6bd-111">Do Loops</span></span>  
 <span data-ttu-id="4d6bd-112">`Do`...`Loop`构造允许您开头或末尾 loop 结构对条件进行测试。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="4d6bd-113">你还可以指定是否重复循环，该条件在保持`True`或变为之前将其`True`。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="4d6bd-114">有关详细信息，请参阅[执行...循环语句](../../../../visual-basic/language-reference/statements/do-loop-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-114">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="4d6bd-115">For 循环</span><span class="sxs-lookup"><span data-stu-id="4d6bd-115">For Loops</span></span>  
 <span data-ttu-id="4d6bd-116">`For`...`Next`构造执行循环次数。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="4d6bd-117">它使用循环控制变量，也称为*计数器*，来跟踪重复。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="4d6bd-118">请指定开始和结束此计数器的值，并且你可以选择指定的量依据它从增加一次重复到下一步。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="4d6bd-119">有关详细信息，请参阅[为...下一条语句](../../../../visual-basic/language-reference/statements/for-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-119">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="4d6bd-120">For Each 循环</span><span class="sxs-lookup"><span data-stu-id="4d6bd-120">For Each Loops</span></span>  
 <span data-ttu-id="4d6bd-121">`For Each`...`Next`构造为集合中运行一组语句对于每个元素执行一次。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="4d6bd-122">指定循环控制变量，但不是需要确定启动或为其结束值。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="4d6bd-123">有关详细信息，请参阅[每个...下一条语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="4d6bd-123">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d6bd-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d6bd-124">See Also</span></span>  
 [<span data-ttu-id="4d6bd-125">控制流</span><span class="sxs-lookup"><span data-stu-id="4d6bd-125">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="4d6bd-126">决策结构</span><span class="sxs-lookup"><span data-stu-id="4d6bd-126">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="4d6bd-127">其他控件结构</span><span class="sxs-lookup"><span data-stu-id="4d6bd-127">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="4d6bd-128">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="4d6bd-128">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
