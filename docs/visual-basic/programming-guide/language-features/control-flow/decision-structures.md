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
ms.openlocfilehash: 20b60fb425278dacb56ee5f888967554a1f76aeb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825373"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="b53f5-102">决策结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b53f5-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="b53f5-103">Visual Basic，可以测试条件，然后执行不同操作，具体取决于该测试的结果。</span><span class="sxs-lookup"><span data-stu-id="b53f5-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="b53f5-104">你可以测试条件是 true 或 false 的各种值的表达式，或生成时执行的一系列语句的各种异常。</span><span class="sxs-lookup"><span data-stu-id="b53f5-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="b53f5-105">下图显示了测试条件为 true，并采用不同的操作，具体取决于是否，则返回 true 或 false 的决策结构。</span><span class="sxs-lookup"><span data-stu-id="b53f5-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 <span data-ttu-id="b53f5-106">![If 的流程图...然后...其他构造](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span><span class="sxs-lookup"><span data-stu-id="b53f5-106">![Flow chart of an If...Then...Else construction](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span></span>  
<span data-ttu-id="b53f5-107">条件为 true，并且为 false 时执行不同操作</span><span class="sxs-lookup"><span data-stu-id="b53f5-107">Taking different actions when a condition is true and when it is false</span></span>  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="b53f5-108">如果...然后...其他构造</span><span class="sxs-lookup"><span data-stu-id="b53f5-108">If...Then...Else Construction</span></span>  
 <span data-ttu-id="b53f5-109">`If...Then...Else` 构造，可以对一个或多个条件测试，并运行一个或多个语句，具体取决于每个条件。</span><span class="sxs-lookup"><span data-stu-id="b53f5-109">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="b53f5-110">您可以测试条件，然后按以下方式执行操作：</span><span class="sxs-lookup"><span data-stu-id="b53f5-110">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="b53f5-111">如果条件为，运行一个或多个语句 `True`</span><span class="sxs-lookup"><span data-stu-id="b53f5-111">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="b53f5-112">如果条件为，运行一个或多个语句 `False`</span><span class="sxs-lookup"><span data-stu-id="b53f5-112">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="b53f5-113">如果条件为运行某些语句`True`和其他人是否它 `False`</span><span class="sxs-lookup"><span data-stu-id="b53f5-113">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="b53f5-114">如果前一个条件为，测试其他条件 `False`</span><span class="sxs-lookup"><span data-stu-id="b53f5-114">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="b53f5-115">提供了所有这些可能性的控制结构是[如果...然后...Else 语句](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="b53f5-115">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="b53f5-116">如果你有一个测试和运行一个语句，可以使用单个行版本。</span><span class="sxs-lookup"><span data-stu-id="b53f5-116">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="b53f5-117">如果有一组更复杂的条件和操作，您可以使用多个行版本。</span><span class="sxs-lookup"><span data-stu-id="b53f5-117">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="b53f5-118">选择...Case 构造</span><span class="sxs-lookup"><span data-stu-id="b53f5-118">Select...Case Construction</span></span>  
 <span data-ttu-id="b53f5-119">`Select...Case`构造可以评估一次表达式并运行不同的语句基于不同的可能值集。</span><span class="sxs-lookup"><span data-stu-id="b53f5-119">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="b53f5-120">有关详细信息，请参阅[选择...Case 语句](../../../../visual-basic/language-reference/statements/select-case-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="b53f5-120">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="b53f5-121">重试...Catch...最后构造</span><span class="sxs-lookup"><span data-stu-id="b53f5-121">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="b53f5-122">`Try...Catch...Finally` 构造，可以运行一组保留控件，如果您的语句的任何一个导致异常的环境下的语句。</span><span class="sxs-lookup"><span data-stu-id="b53f5-122">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="b53f5-123">您可以采取不同操作的不同异常。</span><span class="sxs-lookup"><span data-stu-id="b53f5-123">You can take different actions for different exceptions.</span></span> <span data-ttu-id="b53f5-124">您可以选择指定的退出整个之前运行的代码块`Try...Catch...Finally`构造，而不考虑所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="b53f5-124">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="b53f5-125">有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="b53f5-125">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b53f5-126">许多控件结构，当您单击某个关键字在结构中的关键字的所有突出显示。</span><span class="sxs-lookup"><span data-stu-id="b53f5-126">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="b53f5-127">例如，单击`If`中`If...Then...Else`构造、 的所有实例`If`， `Then`， `ElseIf`， `Else`，和`End If`构造中将突出显示。</span><span class="sxs-lookup"><span data-stu-id="b53f5-127">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="b53f5-128">若要将移动到下一步或上一个突出显示关键字，按 CTRL + SHIFT + 向下键或 CTRL + SHIFT + 向上键。</span><span class="sxs-lookup"><span data-stu-id="b53f5-128">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b53f5-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="b53f5-129">See also</span></span>

- [<span data-ttu-id="b53f5-130">控制流</span><span class="sxs-lookup"><span data-stu-id="b53f5-130">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="b53f5-131">循环结构</span><span class="sxs-lookup"><span data-stu-id="b53f5-131">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="b53f5-132">其他控件结构</span><span class="sxs-lookup"><span data-stu-id="b53f5-132">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="b53f5-133">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="b53f5-133">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="b53f5-134">If 运算符</span><span class="sxs-lookup"><span data-stu-id="b53f5-134">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
