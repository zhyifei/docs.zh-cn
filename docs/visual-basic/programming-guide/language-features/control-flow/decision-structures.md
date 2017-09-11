---
title: "决策结构 (Visual Basic) |Microsoft 文档"
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
- statements [Visual Basic], control flow
- If statement, decision structures
- If statement, If...Then...Else
- control flow, decision structures
- decision structures
- conditional statements, decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
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
ms.openlocfilehash: dcbfb4bc3318d5f79870d04e606fab8bfa2dafb9
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="74ef5-102">决策结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74ef5-102">Decision Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="74ef5-103">允许您测试条件，然后执行不同的操作，具体取决于该测试的结果。</span><span class="sxs-lookup"><span data-stu-id="74ef5-103"> lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="74ef5-104">您可以测试条件是 true 还是 false，各种值的表达式或生成时执行一系列语句的各种异常。</span><span class="sxs-lookup"><span data-stu-id="74ef5-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="74ef5-105">下图显示的决策结构，将测试条件是，则返回 true 并采取不同的操作，具体取决于它是 true 还是 false。</span><span class="sxs-lookup"><span data-stu-id="74ef5-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 <span data-ttu-id="74ef5-106">![流图表的 If...然后...其他构造](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span><span class="sxs-lookup"><span data-stu-id="74ef5-106">![Flow chart of an If...Then...Else construction](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span></span>  
<span data-ttu-id="74ef5-107">条件为 true，为 false 时采用不同的操作</span><span class="sxs-lookup"><span data-stu-id="74ef5-107">Taking different actions when a condition is true and when it is false</span></span>  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="74ef5-108">如果...然后...其他构造</span><span class="sxs-lookup"><span data-stu-id="74ef5-108">If...Then...Else Construction</span></span>  
 <span data-ttu-id="74ef5-109">`If...Then...Else`构造，可以测试一个或多个条件，然后运行具体取决于每个条件的一个或多个语句。</span><span class="sxs-lookup"><span data-stu-id="74ef5-109">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="74ef5-110">您可以测试条件，然后按以下方式执行操作︰</span><span class="sxs-lookup"><span data-stu-id="74ef5-110">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="74ef5-111">如果条件为，运行一个或多个语句`True`</span><span class="sxs-lookup"><span data-stu-id="74ef5-111">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="74ef5-112">如果条件为，运行一个或多个语句`False`</span><span class="sxs-lookup"><span data-stu-id="74ef5-112">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="74ef5-113">如果条件为运行某些语句`True`和其他人是否`False`</span><span class="sxs-lookup"><span data-stu-id="74ef5-113">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="74ef5-114">如果前一个条件是，测试的附加条件`False`</span><span class="sxs-lookup"><span data-stu-id="74ef5-114">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="74ef5-115">提供所有这些可能性的控制结构[如果...然后...Else 语句](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="74ef5-115">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="74ef5-116">如果你有只需一个测试和要运行的一个语句，可以使用单行版本。</span><span class="sxs-lookup"><span data-stu-id="74ef5-116">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="74ef5-117">如果您有一组更复杂的条件和操作，您可以使用多个行版本。</span><span class="sxs-lookup"><span data-stu-id="74ef5-117">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="74ef5-118">选择...Case 构造</span><span class="sxs-lookup"><span data-stu-id="74ef5-118">Select...Case Construction</span></span>  
 <span data-ttu-id="74ef5-119">`Select...Case`构造，可以计算一次表达式，然后运行组不同的基于不同的可能值的语句。</span><span class="sxs-lookup"><span data-stu-id="74ef5-119">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="74ef5-120">有关详细信息，请参阅[选择...Case 语句](../../../../visual-basic/language-reference/statements/select-case-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="74ef5-120">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="74ef5-121">重试...Catch...最后构造</span><span class="sxs-lookup"><span data-stu-id="74ef5-121">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="74ef5-122">`Try...Catch...Finally`构造，可以运行的一组下的环境中，一直保留控件，如果您的语句的任何一个导致异常的语句。</span><span class="sxs-lookup"><span data-stu-id="74ef5-122">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="74ef5-123">您可以采取不同的操作为不同的异常。</span><span class="sxs-lookup"><span data-stu-id="74ef5-123">You can take different actions for different exceptions.</span></span> <span data-ttu-id="74ef5-124">您可以选择指定的前退出整个运行的代码块`Try...Catch...Finally`构造，而不考虑所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="74ef5-124">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="74ef5-125">有关详细信息，请参阅[重试...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="74ef5-125">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74ef5-126">对于许多控制结构，当您单击某个关键字在结构中的关键字的所有都会突出显示。</span><span class="sxs-lookup"><span data-stu-id="74ef5-126">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="74ef5-127">例如，当您单击`If`中`If...Then...Else`构造、 的所有实例`If`， `Then`， `ElseIf`， `Else`，和`End If`在构造过程中会突出显示。</span><span class="sxs-lookup"><span data-stu-id="74ef5-127">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="74ef5-128">若要将移动到下一步或上一个突出显示关键字，按 CTRL + SHIFT + 向下键或 CTRL + SHIFT + 向上键。</span><span class="sxs-lookup"><span data-stu-id="74ef5-128">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ef5-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74ef5-129">See Also</span></span>  
 <span data-ttu-id="74ef5-130">[控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="74ef5-130">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="74ef5-131"> [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="74ef5-131"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="74ef5-132"> [其他控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="74ef5-132"> [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span></span>  
<span data-ttu-id="74ef5-133"> [嵌套的控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="74ef5-133"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span></span>  
<span data-ttu-id="74ef5-134"> [If 运算符](../../../../visual-basic/language-reference/operators/if-operator.md)</span><span class="sxs-lookup"><span data-stu-id="74ef5-134"> [If Operator](../../../../visual-basic/language-reference/operators/if-operator.md)</span></span>
