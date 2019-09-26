---
title: 递归过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: b08a06a07f134b7c95251848862d39339e59fe61
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274345"
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="7081b-102">递归过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7081b-102">Recursive Procedures (Visual Basic)</span></span>

<span data-ttu-id="7081b-103">*递归*过程是指调用自身的过程。</span><span class="sxs-lookup"><span data-stu-id="7081b-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="7081b-104">通常，这并不是编写 Visual Basic 代码的最有效方法。</span><span class="sxs-lookup"><span data-stu-id="7081b-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="7081b-105">下面的过程使用递归来计算其原始参数的阶乘。</span><span class="sxs-lookup"><span data-stu-id="7081b-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="7081b-106">递归过程的注意事项</span><span class="sxs-lookup"><span data-stu-id="7081b-106">Considerations with Recursive Procedures</span></span>

 <span data-ttu-id="7081b-107">**限制条件**。</span><span class="sxs-lookup"><span data-stu-id="7081b-107">**Limiting Conditions**.</span></span> <span data-ttu-id="7081b-108">必须设计一个递归过程来测试至少一个可以终止递归的条件，并且还必须处理在合理的递归调用中不满足此类条件的情况。</span><span class="sxs-lookup"><span data-stu-id="7081b-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="7081b-109">如果至少有一种情况不会失败，则您的过程会在无限循环中运行。</span><span class="sxs-lookup"><span data-stu-id="7081b-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>

 <span data-ttu-id="7081b-110">**内存使用率**。</span><span class="sxs-lookup"><span data-stu-id="7081b-110">**Memory Usage**.</span></span> <span data-ttu-id="7081b-111">应用程序的本地变量空间量有限。</span><span class="sxs-lookup"><span data-stu-id="7081b-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="7081b-112">当过程每次调用自身时，它会使用更多的空间来获取其局部变量的其他副本。</span><span class="sxs-lookup"><span data-stu-id="7081b-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="7081b-113">如果此过程持续下去，最终会导致<xref:System.StackOverflowException>错误。</span><span class="sxs-lookup"><span data-stu-id="7081b-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>

 <span data-ttu-id="7081b-114">**效率**。</span><span class="sxs-lookup"><span data-stu-id="7081b-114">**Efficiency**.</span></span> <span data-ttu-id="7081b-115">几乎始终可以将递归替换为循环。</span><span class="sxs-lookup"><span data-stu-id="7081b-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="7081b-116">循环不会产生传递参数的开销、初始化附加存储以及返回值。</span><span class="sxs-lookup"><span data-stu-id="7081b-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="7081b-117">如果没有递归调用，性能可能会更好。</span><span class="sxs-lookup"><span data-stu-id="7081b-117">Your performance can be much better without recursive calls.</span></span>

 <span data-ttu-id="7081b-118">**相互递归**。</span><span class="sxs-lookup"><span data-stu-id="7081b-118">**Mutual Recursion**.</span></span> <span data-ttu-id="7081b-119">如果两个过程相互调用，你可能会发现性能非常差，甚至会出现无限循环。</span><span class="sxs-lookup"><span data-stu-id="7081b-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="7081b-120">此类设计与单个递归过程表现出相同的问题，但可以更难检测和调试。</span><span class="sxs-lookup"><span data-stu-id="7081b-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>

 <span data-ttu-id="7081b-121">**调用括号**。</span><span class="sxs-lookup"><span data-stu-id="7081b-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="7081b-122">`Function`如果过程以递归方式调用自身，则必须在过程名称后面加上括号，即使没有参数列表也是如此。</span><span class="sxs-lookup"><span data-stu-id="7081b-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="7081b-123">否则，函数名称将采用表示函数的返回值的形式。</span><span class="sxs-lookup"><span data-stu-id="7081b-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>

 <span data-ttu-id="7081b-124">**测试**。</span><span class="sxs-lookup"><span data-stu-id="7081b-124">**Testing**.</span></span> <span data-ttu-id="7081b-125">如果编写递归过程，应仔细测试该过程，以确保它始终满足某些限制条件。</span><span class="sxs-lookup"><span data-stu-id="7081b-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="7081b-126">你还应确保不会因为有太多递归调用而耗尽内存。</span><span class="sxs-lookup"><span data-stu-id="7081b-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="7081b-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="7081b-127">See also</span></span>

- <xref:System.StackOverflowException>
- [<span data-ttu-id="7081b-128">过程</span><span class="sxs-lookup"><span data-stu-id="7081b-128">Procedures</span></span>](index.md)
- [<span data-ttu-id="7081b-129">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="7081b-129">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="7081b-130">Function 过程</span><span class="sxs-lookup"><span data-stu-id="7081b-130">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="7081b-131">属性过程</span><span class="sxs-lookup"><span data-stu-id="7081b-131">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="7081b-132">运算符过程</span><span class="sxs-lookup"><span data-stu-id="7081b-132">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="7081b-133">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="7081b-133">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="7081b-134">过程重载</span><span class="sxs-lookup"><span data-stu-id="7081b-134">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="7081b-135">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="7081b-135">Troubleshooting Procedures</span></span>](troubleshooting-procedures.md)
- [<span data-ttu-id="7081b-136">循环结构</span><span class="sxs-lookup"><span data-stu-id="7081b-136">Loop Structures</span></span>](../control-flow/loop-structures.md)
