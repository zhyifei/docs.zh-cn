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
ms.openlocfilehash: 4a76b2565c343e69ac3c11441035a7682a8f08ec
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318931"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="18b6b-102">决策结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18b6b-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="18b6b-103">Visual Basic，可以测试条件，然后执行不同操作，具体取决于该测试的结果。</span><span class="sxs-lookup"><span data-stu-id="18b6b-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="18b6b-104">你可以测试条件是 true 或 false 的各种值的表达式，或生成时执行的一系列语句的各种异常。</span><span class="sxs-lookup"><span data-stu-id="18b6b-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="18b6b-105">下图显示了测试条件为 true，并采用不同的操作，具体取决于是否，则返回 true 或 false 的决策结构。</span><span class="sxs-lookup"><span data-stu-id="18b6b-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 ![如果流图表...然后...其他构造。](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="18b6b-107">如果...然后...其他构造</span><span class="sxs-lookup"><span data-stu-id="18b6b-107">If...Then...Else Construction</span></span>  
 `If...Then...Else` <span data-ttu-id="18b6b-108">构造，可以对一个或多个条件测试，并运行一个或多个语句，具体取决于每个条件。</span><span class="sxs-lookup"><span data-stu-id="18b6b-108">constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="18b6b-109">您可以测试条件，然后按以下方式执行操作：</span><span class="sxs-lookup"><span data-stu-id="18b6b-109">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="18b6b-110">如果条件为，运行一个或多个语句</span><span class="sxs-lookup"><span data-stu-id="18b6b-110">Run one or more statements if a condition is</span></span> `True`  
  
-   <span data-ttu-id="18b6b-111">如果条件为，运行一个或多个语句</span><span class="sxs-lookup"><span data-stu-id="18b6b-111">Run one or more statements if a condition is</span></span> `False`  
  
-   <span data-ttu-id="18b6b-112">如果条件为运行某些语句`True`和其他人是否它</span><span class="sxs-lookup"><span data-stu-id="18b6b-112">Run some statements if a condition is `True` and others if it is</span></span> `False`  
  
-   <span data-ttu-id="18b6b-113">如果前一个条件为，测试其他条件</span><span class="sxs-lookup"><span data-stu-id="18b6b-113">Test an additional condition if a prior condition is</span></span> `False`  
  
 <span data-ttu-id="18b6b-114">提供了所有这些可能性的控制结构是[如果...然后...Else 语句](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="18b6b-114">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="18b6b-115">如果你有一个测试和运行一个语句，可以使用单个行版本。</span><span class="sxs-lookup"><span data-stu-id="18b6b-115">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="18b6b-116">如果有一组更复杂的条件和操作，您可以使用多个行版本。</span><span class="sxs-lookup"><span data-stu-id="18b6b-116">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="18b6b-117">选择...Case 构造</span><span class="sxs-lookup"><span data-stu-id="18b6b-117">Select...Case Construction</span></span>  
 <span data-ttu-id="18b6b-118">`Select...Case`构造可以评估一次表达式并运行不同的语句基于不同的可能值集。</span><span class="sxs-lookup"><span data-stu-id="18b6b-118">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="18b6b-119">有关详细信息，请参阅[选择...Case 语句](../../../../visual-basic/language-reference/statements/select-case-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="18b6b-119">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="18b6b-120">重试...Catch...最后构造</span><span class="sxs-lookup"><span data-stu-id="18b6b-120">Try...Catch...Finally Construction</span></span>  
 `Try...Catch...Finally` <span data-ttu-id="18b6b-121">构造，可以运行一组保留控件，如果您的语句的任何一个导致异常的环境下的语句。</span><span class="sxs-lookup"><span data-stu-id="18b6b-121">constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="18b6b-122">您可以采取不同操作的不同异常。</span><span class="sxs-lookup"><span data-stu-id="18b6b-122">You can take different actions for different exceptions.</span></span> <span data-ttu-id="18b6b-123">您可以选择指定的退出整个之前运行的代码块`Try...Catch...Finally`构造，而不考虑所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="18b6b-123">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="18b6b-124">有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="18b6b-124">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18b6b-125">许多控件结构，当您单击某个关键字在结构中的关键字的所有突出显示。</span><span class="sxs-lookup"><span data-stu-id="18b6b-125">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="18b6b-126">例如，单击`If`中`If...Then...Else`构造、 的所有实例`If`， `Then`， `ElseIf`， `Else`，和`End If`构造中将突出显示。</span><span class="sxs-lookup"><span data-stu-id="18b6b-126">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="18b6b-127">若要将移动到下一步或上一个突出显示关键字，按 CTRL + SHIFT + 向下键或 CTRL + SHIFT + 向上键。</span><span class="sxs-lookup"><span data-stu-id="18b6b-127">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b6b-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="18b6b-128">See also</span></span>

- [<span data-ttu-id="18b6b-129">控制流</span><span class="sxs-lookup"><span data-stu-id="18b6b-129">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="18b6b-130">循环结构</span><span class="sxs-lookup"><span data-stu-id="18b6b-130">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="18b6b-131">其他控件结构</span><span class="sxs-lookup"><span data-stu-id="18b6b-131">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="18b6b-132">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="18b6b-132">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="18b6b-133">If 运算符</span><span class="sxs-lookup"><span data-stu-id="18b6b-133">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
