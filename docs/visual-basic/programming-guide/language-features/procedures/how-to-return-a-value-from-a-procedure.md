---
title: 如何：从过程 (Visual Basic 中) 中返回值
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 293234346053034b544866b6a2eff84974d8a02b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824554"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="32d79-102">如何：从过程 (Visual Basic 中) 中返回值</span><span class="sxs-lookup"><span data-stu-id="32d79-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="32d79-103">一个`Function`过程返回一个值到调用代码可以通过执行`Return`语句或在遇到`Exit Function`或`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="32d79-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="32d79-104">返回值使用 Return 语句</span><span class="sxs-lookup"><span data-stu-id="32d79-104">To return a value using the Return statement</span></span>  
  
1.  <span data-ttu-id="32d79-105">放置`Return`语句在完成该过程的任务时的点。</span><span class="sxs-lookup"><span data-stu-id="32d79-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2.  <span data-ttu-id="32d79-106">请按照`Return`想要返回到调用代码会生成值的表达式的关键字。</span><span class="sxs-lookup"><span data-stu-id="32d79-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3.  <span data-ttu-id="32d79-107">在同一过程中可拥有多个 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="32d79-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="32d79-108">以下`Function`过程计算的最长边或斜边的直角三角形而言，并将其返回给调用代码。</span><span class="sxs-lookup"><span data-stu-id="32d79-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="32d79-109">下面的示例演示对典型调用`hypotenuse`，用于存储返回的值。</span><span class="sxs-lookup"><span data-stu-id="32d79-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="32d79-110">返回值使用 Exit 函数或最终函数</span><span class="sxs-lookup"><span data-stu-id="32d79-110">To return a value using Exit Function or End Function</span></span>  
  
1.  <span data-ttu-id="32d79-111">中至少一个就地`Function`过程中，分配到过程的名称的值。</span><span class="sxs-lookup"><span data-stu-id="32d79-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2.  <span data-ttu-id="32d79-112">当您执行`Exit Function`或`End Function`语句，Visual Basic 将返回最近分配给该过程的名称的值。</span><span class="sxs-lookup"><span data-stu-id="32d79-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3.  <span data-ttu-id="32d79-113">在同一过程中可拥有多个 `Exit Function` 语句，也可混合 `Return` 和 `Exit Function` 语句。</span><span class="sxs-lookup"><span data-stu-id="32d79-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4.  <span data-ttu-id="32d79-114">只能有一个`End Function`中的语句`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="32d79-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="32d79-115">详细信息和示例，请参阅"返回值"中的[Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="32d79-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d79-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="32d79-116">See also</span></span>

- [<span data-ttu-id="32d79-117">过程</span><span class="sxs-lookup"><span data-stu-id="32d79-117">Procedures</span></span>](./index.md)
- [<span data-ttu-id="32d79-118">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="32d79-118">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="32d79-119">属性过程</span><span class="sxs-lookup"><span data-stu-id="32d79-119">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="32d79-120">运算符过程</span><span class="sxs-lookup"><span data-stu-id="32d79-120">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="32d79-121">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="32d79-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="32d79-122">Function 语句</span><span class="sxs-lookup"><span data-stu-id="32d79-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="32d79-123">Return 语句</span><span class="sxs-lookup"><span data-stu-id="32d79-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="32d79-124">如何：创建一个过程，返回一个值</span><span class="sxs-lookup"><span data-stu-id="32d79-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="32d79-125">如何：调用返回的值的过程</span><span class="sxs-lookup"><span data-stu-id="32d79-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
