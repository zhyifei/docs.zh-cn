---
title: "如何：从过程返回值 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ce7aa0942be413986cb010963753447ea18cdf2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="39cd6-102">如何：从过程返回值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39cd6-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="39cd6-103">A`Function`过程返回一个值给调用代码通过执行`Return`语句或在遇到`Exit Function`或`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="39cd6-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="39cd6-104">返回值使用 Return 语句</span><span class="sxs-lookup"><span data-stu-id="39cd6-104">To return a value using the Return statement</span></span>  
  
1.  <span data-ttu-id="39cd6-105">Put`Return`过程的任务已完成其中的点处的语句。</span><span class="sxs-lookup"><span data-stu-id="39cd6-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2.  <span data-ttu-id="39cd6-106">请按照`Return`想要返回到调用代码会生成值的表达式的关键字。</span><span class="sxs-lookup"><span data-stu-id="39cd6-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3.  <span data-ttu-id="39cd6-107">在同一过程中可拥有多个 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="39cd6-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="39cd6-108">以下`Function`过程计算的最长端或斜边直角三角形，并将其返回给调用代码。</span><span class="sxs-lookup"><span data-stu-id="39cd6-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     <span data-ttu-id="39cd6-109">下面的示例演示典型调用`hypotenuse`，它用于存储返回的值。</span><span class="sxs-lookup"><span data-stu-id="39cd6-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="39cd6-110">返回值使用退出函数或最终函数</span><span class="sxs-lookup"><span data-stu-id="39cd6-110">To return a value using Exit Function or End Function</span></span>  
  
1.  <span data-ttu-id="39cd6-111">在至少一个就地`Function`过程中，分配到过程的名称的值。</span><span class="sxs-lookup"><span data-stu-id="39cd6-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2.  <span data-ttu-id="39cd6-112">执行时`Exit Function`或`End Function`语句，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]返回最近分配给过程的名称的值。</span><span class="sxs-lookup"><span data-stu-id="39cd6-112">When you execute an `Exit Function` or `End Function` statement, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] returns the value most recently assigned to the procedure's name.</span></span>  
  
3.  <span data-ttu-id="39cd6-113">在同一过程中可拥有多个 `Exit Function` 语句，也可混合 `Return` 和 `Exit Function` 语句。</span><span class="sxs-lookup"><span data-stu-id="39cd6-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4.  <span data-ttu-id="39cd6-114">只能有一个`End Function`中的语句`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="39cd6-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="39cd6-115">有关详细信息及示例，请参阅"返回值" [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="39cd6-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39cd6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39cd6-116">See Also</span></span>  
 [<span data-ttu-id="39cd6-117">过程</span><span class="sxs-lookup"><span data-stu-id="39cd6-117">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="39cd6-118">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="39cd6-118">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="39cd6-119">属性过程</span><span class="sxs-lookup"><span data-stu-id="39cd6-119">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="39cd6-120">运算符过程</span><span class="sxs-lookup"><span data-stu-id="39cd6-120">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="39cd6-121">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="39cd6-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="39cd6-122">Function 语句</span><span class="sxs-lookup"><span data-stu-id="39cd6-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="39cd6-123">Return 语句</span><span class="sxs-lookup"><span data-stu-id="39cd6-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)  
 [<span data-ttu-id="39cd6-124">如何：创建返回值的过程</span><span class="sxs-lookup"><span data-stu-id="39cd6-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="39cd6-125">如何：调用返回值的过程</span><span class="sxs-lookup"><span data-stu-id="39cd6-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
