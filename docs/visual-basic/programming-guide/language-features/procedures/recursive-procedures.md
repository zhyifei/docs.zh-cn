---
title: "递归过程 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 444eeaf043cf3710c5154fd7e8577590e3ce7d1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="7287a-102">递归过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7287a-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="7287a-103">A*递归*过程是指调用自身。</span><span class="sxs-lookup"><span data-stu-id="7287a-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="7287a-104">一般情况下，这不是最有效的方法来编写[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]代码。</span><span class="sxs-lookup"><span data-stu-id="7287a-104">In general, this is not the most effective way to write [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>  
  
 <span data-ttu-id="7287a-105">以下过程使用递归将计算其原始的自变量的阶乘。</span><span class="sxs-lookup"><span data-stu-id="7287a-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="7287a-106">递归过程注意事项</span><span class="sxs-lookup"><span data-stu-id="7287a-106">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="7287a-107">**限制条件**。</span><span class="sxs-lookup"><span data-stu-id="7287a-107">**Limiting Conditions**.</span></span> <span data-ttu-id="7287a-108">必须设计一个用于测试可以终止递归的至少一个条件的递归过程和你还必须处理其中任何此类条件满足中合理数目的递归调用这种情况。</span><span class="sxs-lookup"><span data-stu-id="7287a-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="7287a-109">没有可以满足而不会出现的至少一个条件，您的过程运行在无限循环中执行的高风险。</span><span class="sxs-lookup"><span data-stu-id="7287a-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="7287a-110">**内存使用率**。</span><span class="sxs-lookup"><span data-stu-id="7287a-110">**Memory Usage**.</span></span> <span data-ttu-id="7287a-111">将应用程序将有限的本地变量的空间量。</span><span class="sxs-lookup"><span data-stu-id="7287a-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="7287a-112">过程调用其自身，每次它使用多个该空间的其本地变量的其他副本。</span><span class="sxs-lookup"><span data-stu-id="7287a-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="7287a-113">如果此过程将无限期地继续，则最终会导致<xref:System.StackOverflowException>错误。</span><span class="sxs-lookup"><span data-stu-id="7287a-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="7287a-114">**效率**。</span><span class="sxs-lookup"><span data-stu-id="7287a-114">**Efficiency**.</span></span> <span data-ttu-id="7287a-115">您几乎总是可以替换递归循环。</span><span class="sxs-lookup"><span data-stu-id="7287a-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="7287a-116">循环没有初始化其他存储和返回值传递自变量的开销。</span><span class="sxs-lookup"><span data-stu-id="7287a-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="7287a-117">你的性能可以大幅提高递归调用。</span><span class="sxs-lookup"><span data-stu-id="7287a-117">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="7287a-118">**相互递归**。</span><span class="sxs-lookup"><span data-stu-id="7287a-118">**Mutual Recursion**.</span></span> <span data-ttu-id="7287a-119">如果两个过程调用相互，可能会发现很差的性能或甚至产生无限循环。</span><span class="sxs-lookup"><span data-stu-id="7287a-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="7287a-120">此类设计展示在单个递归过程中，相同的问题，但很难检测和调试。</span><span class="sxs-lookup"><span data-stu-id="7287a-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="7287a-121">**调用时使用括号**。</span><span class="sxs-lookup"><span data-stu-id="7287a-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="7287a-122">当`Function`过程调用其自身以递归方式，你必须在过程名后面加括号，即使没有自变量列表。</span><span class="sxs-lookup"><span data-stu-id="7287a-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="7287a-123">否则，执行的函数名称作为表示函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="7287a-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="7287a-124">**测试**。</span><span class="sxs-lookup"><span data-stu-id="7287a-124">**Testing**.</span></span> <span data-ttu-id="7287a-125">如果您编写一个递归的过程，你应测试它应非常仔细地以确保始终满足某些限制条件。</span><span class="sxs-lookup"><span data-stu-id="7287a-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="7287a-126">你还应该确保你不能运行由于递归调用过多的内存不足。</span><span class="sxs-lookup"><span data-stu-id="7287a-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7287a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7287a-127">See Also</span></span>  
 <xref:System.StackOverflowException>  
 [<span data-ttu-id="7287a-128">过程</span><span class="sxs-lookup"><span data-stu-id="7287a-128">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="7287a-129">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="7287a-129">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="7287a-130">Function 过程</span><span class="sxs-lookup"><span data-stu-id="7287a-130">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="7287a-131">属性过程</span><span class="sxs-lookup"><span data-stu-id="7287a-131">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="7287a-132">运算符过程</span><span class="sxs-lookup"><span data-stu-id="7287a-132">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="7287a-133">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="7287a-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="7287a-134">过程重载</span><span class="sxs-lookup"><span data-stu-id="7287a-134">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="7287a-135">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="7287a-135">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="7287a-136">循环结构</span><span class="sxs-lookup"><span data-stu-id="7287a-136">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="7287a-137">异常疑难解答：System.StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="7287a-137">Troubleshooting Exceptions: System.StackOverflowException</span></span>](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
