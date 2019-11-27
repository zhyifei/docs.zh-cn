---
title: 如何：创建返回值的过程
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 218dbb52abc0100724d38d10be91ef24252d5226
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349718"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="c0642-102">如何：创建返回值的过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0642-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="c0642-103">使用 `Function` 过程将值返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="c0642-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="c0642-104">创建返回值的过程</span><span class="sxs-lookup"><span data-stu-id="c0642-104">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="c0642-105">在任何其他过程之外，使用 `Function` 语句，后跟 `End Function` 语句。</span><span class="sxs-lookup"><span data-stu-id="c0642-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="c0642-106">在 `Function` 语句中，将 `Function` 关键字跟过程的名称一起，然后将参数列表放在括号中。</span><span class="sxs-lookup"><span data-stu-id="c0642-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="c0642-107">在括号后跟一个 `As` 子句以指定返回值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c0642-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4. <span data-ttu-id="c0642-108">将过程的代码语句置于 `Function` 和 `End Function` 语句之间。</span><span class="sxs-lookup"><span data-stu-id="c0642-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5. <span data-ttu-id="c0642-109">使用 `Return` 语句将值返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="c0642-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="c0642-110">以下 `Function` 过程将计算直角三角形的最长边（或斜边），并给出另一方的值。</span><span class="sxs-lookup"><span data-stu-id="c0642-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="c0642-111">下面的示例演示对 `hypotenuse`的典型调用。</span><span class="sxs-lookup"><span data-stu-id="c0642-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="c0642-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0642-112">See also</span></span>

- [<span data-ttu-id="c0642-113">过程</span><span class="sxs-lookup"><span data-stu-id="c0642-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c0642-114">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="c0642-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="c0642-115">属性过程</span><span class="sxs-lookup"><span data-stu-id="c0642-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="c0642-116">运算符过程</span><span class="sxs-lookup"><span data-stu-id="c0642-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="c0642-117">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="c0642-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="c0642-118">Function 语句</span><span class="sxs-lookup"><span data-stu-id="c0642-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="c0642-119">如何：从过程返回值</span><span class="sxs-lookup"><span data-stu-id="c0642-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="c0642-120">如何：调用返回值的过程</span><span class="sxs-lookup"><span data-stu-id="c0642-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
