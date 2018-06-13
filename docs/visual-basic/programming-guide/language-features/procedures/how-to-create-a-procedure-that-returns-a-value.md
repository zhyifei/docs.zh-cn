---
title: 如何：创建返回值的过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 472f55173a4897a23a82812a2b24bf1646c1a6ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648432"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="8c6d8-102">如何：创建返回值的过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c6d8-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="8c6d8-103">你使用`Function`值返回给调用代码的过程。</span><span class="sxs-lookup"><span data-stu-id="8c6d8-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="8c6d8-104">创建过程中返回一个值</span><span class="sxs-lookup"><span data-stu-id="8c6d8-104">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="8c6d8-105">在任何其他过程之外使用`Function`语句后, 跟`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="8c6d8-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="8c6d8-106">在`Function`语句，请按照`Function`关键字的过程，然后在括号中的参数列表的名称。</span><span class="sxs-lookup"><span data-stu-id="8c6d8-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="8c6d8-107">括号后跟`As`子句指定返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="8c6d8-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4.  <span data-ttu-id="8c6d8-108">放置过程的代码语句之间`Function`和`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="8c6d8-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5.  <span data-ttu-id="8c6d8-109">使用`Return`语句返回值返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="8c6d8-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="8c6d8-110">以下`Function`过程计算的最长端或斜边直角三角形，其他两条边为给定的值。</span><span class="sxs-lookup"><span data-stu-id="8c6d8-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     <span data-ttu-id="8c6d8-111">下面的示例演示典型调用`hypotenuse`。</span><span class="sxs-lookup"><span data-stu-id="8c6d8-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8c6d8-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c6d8-112">See Also</span></span>  
 [<span data-ttu-id="8c6d8-113">过程</span><span class="sxs-lookup"><span data-stu-id="8c6d8-113">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="8c6d8-114">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="8c6d8-114">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="8c6d8-115">属性过程</span><span class="sxs-lookup"><span data-stu-id="8c6d8-115">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="8c6d8-116">运算符过程</span><span class="sxs-lookup"><span data-stu-id="8c6d8-116">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="8c6d8-117">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="8c6d8-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="8c6d8-118">Function 语句</span><span class="sxs-lookup"><span data-stu-id="8c6d8-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="8c6d8-119">如何：从过程返回值</span><span class="sxs-lookup"><span data-stu-id="8c6d8-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="8c6d8-120">如何：调用返回值的过程</span><span class="sxs-lookup"><span data-stu-id="8c6d8-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
