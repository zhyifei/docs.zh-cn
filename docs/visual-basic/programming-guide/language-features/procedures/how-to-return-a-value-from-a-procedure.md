---
title: "如何︰ 从过程 (Visual Basic 中) 返回一个值 |Microsoft 文档"
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
- procedures, returning from
- procedures, returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
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
ms.openlocfilehash: 601cd3adca0105eb829bb6156f94289b5c9f5f72
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="b5acd-102">如何：从过程返回值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5acd-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="b5acd-103">一个`Function`过程将值返回到调用代码可以通过执行`Return`语句或在遇到`Exit Function`或`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="b5acd-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="b5acd-104">返回值使用 Return 语句</span><span class="sxs-lookup"><span data-stu-id="b5acd-104">To return a value using the Return statement</span></span>  
  
1.  <span data-ttu-id="b5acd-105">放置`Return`语句完成该过程的任务时的时刻。</span><span class="sxs-lookup"><span data-stu-id="b5acd-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2.  <span data-ttu-id="b5acd-106">请按照`Return`想要返回到调用代码会生成值的表达式的关键字。</span><span class="sxs-lookup"><span data-stu-id="b5acd-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3.  <span data-ttu-id="b5acd-107">您可以有多个`Return`相同的过程中的语句。</span><span class="sxs-lookup"><span data-stu-id="b5acd-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="b5acd-108">以下`Function`过程计算的最长边或斜边直角三角形，并将其返回给调用代码。</span><span class="sxs-lookup"><span data-stu-id="b5acd-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     <span data-ttu-id="b5acd-109">[!code-vb[VbVbcnProcedures #&1;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b5acd-109">[!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="b5acd-110">下面的示例演示如何调用典型`hypotenuse`，它用于存储返回的值。</span><span class="sxs-lookup"><span data-stu-id="b5acd-110">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     <span data-ttu-id="b5acd-111">[!code-vb[VbVbcnProcedures #&6;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b5acd-111">[!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]</span></span>  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="b5acd-112">返回值使用退出函数或结束函数</span><span class="sxs-lookup"><span data-stu-id="b5acd-112">To return a value using Exit Function or End Function</span></span>  
  
1.  <span data-ttu-id="b5acd-113">在至少一个就地`Function`的过程中，赋值为该过程的名称。</span><span class="sxs-lookup"><span data-stu-id="b5acd-113">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2.  <span data-ttu-id="b5acd-114">当您执行`Exit Function`或`End Function`语句，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]返回最近分配给过程的名称的值。</span><span class="sxs-lookup"><span data-stu-id="b5acd-114">When you execute an `Exit Function` or `End Function` statement, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] returns the value most recently assigned to the procedure's name.</span></span>  
  
3.  <span data-ttu-id="b5acd-115">您可以有多个`Exit Function`中的语句相同的过程，以及您可以混合使用`Return`和`Exit Function`相同的过程中的语句。</span><span class="sxs-lookup"><span data-stu-id="b5acd-115">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4.  <span data-ttu-id="b5acd-116">只能有一个`End Function`中的语句`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="b5acd-116">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="b5acd-117">有关详细信息和示例，请参阅"返回值" [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="b5acd-117">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5acd-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5acd-118">See Also</span></span>  
 <span data-ttu-id="b5acd-119">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="b5acd-119">[Procedures](./index.md) </span></span>  
<span data-ttu-id="b5acd-120"> [Sub 过程](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="b5acd-120"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="b5acd-121"> [属性过程](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="b5acd-121"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="b5acd-122"> [运算符过程](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="b5acd-122"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="b5acd-123"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="b5acd-123"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="b5acd-124"> [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b5acd-124"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="b5acd-125"> [Return 语句](../../../../visual-basic/language-reference/statements/return-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b5acd-125"> [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md) </span></span>  
<span data-ttu-id="b5acd-126"> [如何︰ 创建返回一个值的过程](./how-to-create-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="b5acd-126"> [How to: Create a Procedure that Returns a Value](./how-to-create-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="b5acd-127"> [如何：调用返回值的过程](./how-to-call-a-procedure-that-returns-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="b5acd-127"> [How to: Call a Procedure That Returns a Value](./how-to-call-a-procedure-that-returns-a-value.md)</span></span>
