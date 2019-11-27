---
title: 如何：从过程返回值
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 1371e4ed0ff28f9caf56eabf2a1bb9290edbe75c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346031"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="ec803-102">如何：从过程返回值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec803-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="ec803-103">`Function` 过程通过执行 `Return` 语句或遇到 `Exit Function` 或 `End Function` 语句将值返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="ec803-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="ec803-104">使用 Return 语句返回值</span><span class="sxs-lookup"><span data-stu-id="ec803-104">To return a value using the Return statement</span></span>  
  
1. <span data-ttu-id="ec803-105">在过程任务完成时，将 `Return` 语句放置在该点。</span><span class="sxs-lookup"><span data-stu-id="ec803-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2. <span data-ttu-id="ec803-106">在 `Return` 关键字后面跟一个表达式，该表达式生成要返回到调用代码的值。</span><span class="sxs-lookup"><span data-stu-id="ec803-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3. <span data-ttu-id="ec803-107">在同一过程中可拥有多个 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="ec803-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="ec803-108">以下 `Function` 过程计算直角三角形的最长边（或斜边），并将其返回给调用代码。</span><span class="sxs-lookup"><span data-stu-id="ec803-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="ec803-109">下面的示例演示对 `hypotenuse`的典型调用，该调用存储返回的值。</span><span class="sxs-lookup"><span data-stu-id="ec803-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="ec803-110">使用 Exit 函数或 End 函数返回值</span><span class="sxs-lookup"><span data-stu-id="ec803-110">To return a value using Exit Function or End Function</span></span>  
  
1. <span data-ttu-id="ec803-111">在 `Function` 过程中的至少一个位置，为过程名称赋值。</span><span class="sxs-lookup"><span data-stu-id="ec803-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2. <span data-ttu-id="ec803-112">当执行 `Exit Function` 或 `End Function` 语句时，Visual Basic 返回最近分配给该过程的名称的值。</span><span class="sxs-lookup"><span data-stu-id="ec803-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3. <span data-ttu-id="ec803-113">在同一过程中可拥有多个 `Exit Function` 语句，也可混合 `Return` 和 `Exit Function` 语句。</span><span class="sxs-lookup"><span data-stu-id="ec803-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4. <span data-ttu-id="ec803-114">`Function` 过程中只能有一个 `End Function` 语句。</span><span class="sxs-lookup"><span data-stu-id="ec803-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="ec803-115">有关详细信息和示例，请参阅[Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)中的 "返回值"。</span><span class="sxs-lookup"><span data-stu-id="ec803-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec803-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec803-116">See also</span></span>

- [<span data-ttu-id="ec803-117">过程</span><span class="sxs-lookup"><span data-stu-id="ec803-117">Procedures</span></span>](./index.md)
- [<span data-ttu-id="ec803-118">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="ec803-118">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="ec803-119">属性过程</span><span class="sxs-lookup"><span data-stu-id="ec803-119">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="ec803-120">运算符过程</span><span class="sxs-lookup"><span data-stu-id="ec803-120">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="ec803-121">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="ec803-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="ec803-122">Function 语句</span><span class="sxs-lookup"><span data-stu-id="ec803-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="ec803-123">Return 语句</span><span class="sxs-lookup"><span data-stu-id="ec803-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="ec803-124">如何：创建返回值的过程</span><span class="sxs-lookup"><span data-stu-id="ec803-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="ec803-125">如何：调用返回值的过程</span><span class="sxs-lookup"><span data-stu-id="ec803-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
