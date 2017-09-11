---
title: "递归过程 (Visual Basic 中) |Microsoft 文档"
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
- Visual Basic code, procedures
- procedures, that call themselves
- procedures, recursive
- procedures, calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
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
ms.openlocfilehash: 5e4838bb14125dcfd27798acf0c196f351ba5b90
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="4e65a-102">递归过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e65a-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="4e65a-103">一个*递归*过程是指调用自身。</span><span class="sxs-lookup"><span data-stu-id="4e65a-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="4e65a-104">一般情况下，这不是最有效的方法来编写[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]代码。</span><span class="sxs-lookup"><span data-stu-id="4e65a-104">In general, this is not the most effective way to write [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
 <span data-ttu-id="4e65a-105">下面的过程使用递归来计算其原始参数的阶乘。</span><span class="sxs-lookup"><span data-stu-id="4e65a-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 <span data-ttu-id="4e65a-106">[!code-vb[VbVbcnProcedures #&51;](./codesnippet/VisualBasic/recursive-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4e65a-106">[!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]</span></span>  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="4e65a-107">递归过程方面的注意事项</span><span class="sxs-lookup"><span data-stu-id="4e65a-107">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="4e65a-108">**限制条件**。</span><span class="sxs-lookup"><span data-stu-id="4e65a-108">**Limiting Conditions**.</span></span> <span data-ttu-id="4e65a-109">您必须在设计递归过程以测试可以终止此递归的至少一个条件和还必须处理任何此类条件均在合理数量的递归调用这种情况。</span><span class="sxs-lookup"><span data-stu-id="4e65a-109">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="4e65a-110">没有可以满足而不会出现的至少一个条件，您的过程运行高风险的在无限循环中执行。</span><span class="sxs-lookup"><span data-stu-id="4e65a-110">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="4e65a-111">**内存使用量**。</span><span class="sxs-lookup"><span data-stu-id="4e65a-111">**Memory Usage**.</span></span> <span data-ttu-id="4e65a-112">将应用程序将有限的数量的空间用于本地变量。</span><span class="sxs-lookup"><span data-stu-id="4e65a-112">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="4e65a-113">过程调用其本身，每次都会占用更多空间的其他副本的本地变量。</span><span class="sxs-lookup"><span data-stu-id="4e65a-113">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="4e65a-114">如果此过程持续下去，最终会导致<xref:System.StackOverflowException>错误。</xref:System.StackOverflowException></span><span class="sxs-lookup"><span data-stu-id="4e65a-114">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="4e65a-115">**效率**。</span><span class="sxs-lookup"><span data-stu-id="4e65a-115">**Efficiency**.</span></span> <span data-ttu-id="4e65a-116">您几乎总是可以替换为递归循环。</span><span class="sxs-lookup"><span data-stu-id="4e65a-116">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="4e65a-117">一个循环并没有初始化附加存储空间和返回值传递参数的系统开销。</span><span class="sxs-lookup"><span data-stu-id="4e65a-117">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="4e65a-118">您的性能可以大幅提高递归调用。</span><span class="sxs-lookup"><span data-stu-id="4e65a-118">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="4e65a-119">**相互递归**。</span><span class="sxs-lookup"><span data-stu-id="4e65a-119">**Mutual Recursion**.</span></span> <span data-ttu-id="4e65a-120">如果两个过程调用对方，可能会发现性能非常差或甚至产生无限循环。</span><span class="sxs-lookup"><span data-stu-id="4e65a-120">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="4e65a-121">此类设计提出一个递归过程中，与相同的问题，但很难检测和调试。</span><span class="sxs-lookup"><span data-stu-id="4e65a-121">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="4e65a-122">**调用时使用括号**。</span><span class="sxs-lookup"><span data-stu-id="4e65a-122">**Calling with Parentheses**.</span></span> <span data-ttu-id="4e65a-123">当`Function`过程调用其自身以递归方式，您必须过程名后面加上括号，即使没有参数列表。</span><span class="sxs-lookup"><span data-stu-id="4e65a-123">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="4e65a-124">否则，执行的函数名称作为表示该函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="4e65a-124">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="4e65a-125">**测试**。</span><span class="sxs-lookup"><span data-stu-id="4e65a-125">**Testing**.</span></span> <span data-ttu-id="4e65a-126">如果您编写的递归过程，您应该测试它应非常小心以确保它总是能满足某些限制条件。</span><span class="sxs-lookup"><span data-stu-id="4e65a-126">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="4e65a-127">您还应确保您不能运行由于递归调用过多的内存不足。</span><span class="sxs-lookup"><span data-stu-id="4e65a-127">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e65a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e65a-128">See Also</span></span>  
 <span data-ttu-id="4e65a-129"><xref:System.StackOverflowException></xref:System.StackOverflowException></span><span class="sxs-lookup"><span data-stu-id="4e65a-129"><xref:System.StackOverflowException></span></span>   
<span data-ttu-id="4e65a-130"> [过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="4e65a-130"> [Procedures](./index.md) </span></span>  
<span data-ttu-id="4e65a-131"> [Sub 过程](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="4e65a-131"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="4e65a-132"> [Function 过程](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="4e65a-132"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="4e65a-133"> [属性过程](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="4e65a-133"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="4e65a-134"> [运算符过程](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="4e65a-134"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="4e65a-135"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="4e65a-135"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="4e65a-136"> [过程重载](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="4e65a-136"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="4e65a-137"> [故障排除过程](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="4e65a-137"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="4e65a-138"> [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="4e65a-138"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="4e65a-139"> [异常疑难解答：System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)</span><span class="sxs-lookup"><span data-stu-id="4e65a-139"> [Troubleshooting Exceptions: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)</span></span>
