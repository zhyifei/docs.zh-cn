---
title: 决策结构 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: f0df649c4be50e9cadd51258c89137b68b4ffe22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963203"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="d13fd-102">决策结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d13fd-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="d13fd-103">Visual Basic 允许您测试条件并根据该测试的结果执行不同的操作。</span><span class="sxs-lookup"><span data-stu-id="d13fd-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="d13fd-104">对于表达式的各个值, 或者在执行一系列语句时生成的各种异常, 可以测试条件是 true 还是 false。</span><span class="sxs-lookup"><span data-stu-id="d13fd-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="d13fd-105">下图显示了一个决策结构, 该结构用于测试条件是否为 true, 并执行不同的操作, 具体取决于它是 true 还是 false。</span><span class="sxs-lookup"><span data-stu-id="d13fd-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 ![If...Then...Else 构造。](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="d13fd-107">If...Then...Else 构造</span><span class="sxs-lookup"><span data-stu-id="d13fd-107">If...Then...Else Construction</span></span>  
 <span data-ttu-id="d13fd-108">`If...Then...Else`构造使你可以测试一个或多个条件并根据每个条件运行一个或多个语句。</span><span class="sxs-lookup"><span data-stu-id="d13fd-108">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="d13fd-109">可以通过以下方式测试条件并采取措施:</span><span class="sxs-lookup"><span data-stu-id="d13fd-109">You can test conditions and take actions in the following ways:</span></span>  
  
- <span data-ttu-id="d13fd-110">如果条件为, 则运行一个或多个语句`True`</span><span class="sxs-lookup"><span data-stu-id="d13fd-110">Run one or more statements if a condition is `True`</span></span>  
  
- <span data-ttu-id="d13fd-111">如果条件为, 则运行一个或多个语句`False`</span><span class="sxs-lookup"><span data-stu-id="d13fd-111">Run one or more statements if a condition is `False`</span></span>  
  
- <span data-ttu-id="d13fd-112">如果条件为, 则运行某些`True`语句; 如果条件为, 则运行其他语句`False`</span><span class="sxs-lookup"><span data-stu-id="d13fd-112">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
- <span data-ttu-id="d13fd-113">如果先前的条件为, 则测试其他条件`False`</span><span class="sxs-lookup"><span data-stu-id="d13fd-113">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="d13fd-114">提供所有这些可能的控制结构是[If...Then...Else 语句](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d13fd-114">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="d13fd-115">如果仅有一个测试和一个语句要运行, 则可以使用单行版本。</span><span class="sxs-lookup"><span data-stu-id="d13fd-115">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="d13fd-116">如果有更复杂的条件和操作集, 则可以使用多行版本。</span><span class="sxs-lookup"><span data-stu-id="d13fd-116">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="d13fd-117">Select...Case 构造</span><span class="sxs-lookup"><span data-stu-id="d13fd-117">Select...Case Construction</span></span>  
 <span data-ttu-id="d13fd-118">使用`Select...Case`构造, 可以计算一次表达式, 并基于不同的可能值运行不同的语句集。</span><span class="sxs-lookup"><span data-stu-id="d13fd-118">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="d13fd-119">有关详细信息, 请参阅[Select ...Case 语句](../../../../visual-basic/language-reference/statements/select-case-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d13fd-119">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="d13fd-120">Try...Catch...Finally 构造</span><span class="sxs-lookup"><span data-stu-id="d13fd-120">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="d13fd-121">`Try...Catch...Finally`构造使你可以在某个环境下运行一组语句, 如果你的任何一个语句导致异常, 该环境将保留控制权。</span><span class="sxs-lookup"><span data-stu-id="d13fd-121">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="d13fd-122">对于不同的异常, 可以执行不同的操作。</span><span class="sxs-lookup"><span data-stu-id="d13fd-122">You can take different actions for different exceptions.</span></span> <span data-ttu-id="d13fd-123">您可以选择指定在退出整个`Try...Catch...Finally`构造之前运行的代码块, 而不管发生了什么情况。</span><span class="sxs-lookup"><span data-stu-id="d13fd-123">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="d13fd-124">有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d13fd-124">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d13fd-125">对于许多控制结构, 当您单击某个关键字时, 将突出显示该结构中的所有关键字。</span><span class="sxs-lookup"><span data-stu-id="d13fd-125">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="d13fd-126">`If`例如, 单击`If...Then...Else`构造时, 将突出显示构造中的、 `If` `Then`、 `ElseIf` `Else`、和`End If`的所有实例。</span><span class="sxs-lookup"><span data-stu-id="d13fd-126">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="d13fd-127">若要移动到下一个或上一个突出显示的关键字, 请按 CTRL + SHIFT + 向下键或 CTRL + SHIFT + 向上键。</span><span class="sxs-lookup"><span data-stu-id="d13fd-127">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d13fd-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d13fd-128">See also</span></span>

- [<span data-ttu-id="d13fd-129">控制流</span><span class="sxs-lookup"><span data-stu-id="d13fd-129">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="d13fd-130">循环结构</span><span class="sxs-lookup"><span data-stu-id="d13fd-130">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="d13fd-131">其他控件结构</span><span class="sxs-lookup"><span data-stu-id="d13fd-131">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="d13fd-132">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="d13fd-132">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="d13fd-133">If 运算符</span><span class="sxs-lookup"><span data-stu-id="d13fd-133">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
