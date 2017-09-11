---
title: "如何︰ 调用返回一个值 (Visual Basic 中) 的过程 |Microsoft 文档"
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
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
- procedures, returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
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
ms.openlocfilehash: cc1e274a705618213c830d7cf4f61a5e64afd980
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="e77f3-102">如何：调用返回值的过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e77f3-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="e77f3-103">一个`Function`过程返回到调用代码的值。</span><span class="sxs-lookup"><span data-stu-id="e77f3-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="e77f3-104">它通过调用包括其名称和参数放在赋值语句或表达式中的右边。</span><span class="sxs-lookup"><span data-stu-id="e77f3-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="e77f3-105">若要调用表达式在 Function 过程</span><span class="sxs-lookup"><span data-stu-id="e77f3-105">To call a Function procedure within an expression</span></span>  
  
1.  <span data-ttu-id="e77f3-106">使用`Function`过程名称相同的方式使用变量。</span><span class="sxs-lookup"><span data-stu-id="e77f3-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="e77f3-107">您可以使用`Function`过程调用可以在表达式中使用变量或常量的任何位置。</span><span class="sxs-lookup"><span data-stu-id="e77f3-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2.  <span data-ttu-id="e77f3-108">过程名后面加上括号将参数列表括起来。</span><span class="sxs-lookup"><span data-stu-id="e77f3-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="e77f3-109">如果不有任何参数，可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="e77f3-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="e77f3-110">但是，使用括号使代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="e77f3-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="e77f3-111">将参数放在括号内，用逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="e77f3-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="e77f3-112">请确保您的相同顺序的参数提供的`Function`过程定义对应的参数。</span><span class="sxs-lookup"><span data-stu-id="e77f3-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="e77f3-113">或者，您可以按名称传递一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="e77f3-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="e77f3-114">有关详细信息，请参阅[传递的参数按位置和名称](./passing-arguments-by-position-and-by-name.md)。</span><span class="sxs-lookup"><span data-stu-id="e77f3-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4.  <span data-ttu-id="e77f3-115">从过程返回的值参与只是作为值的表达式的变量或常数那样。</span><span class="sxs-lookup"><span data-stu-id="e77f3-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="e77f3-116">若要在赋值语句中调用 Function 过程</span><span class="sxs-lookup"><span data-stu-id="e77f3-116">To call a Function procedure in an assignment statement</span></span>  
  
1.  <span data-ttu-id="e77f3-117">使用`Function`过程名称后面等号 (`=`) 登录赋值语句。</span><span class="sxs-lookup"><span data-stu-id="e77f3-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2.  <span data-ttu-id="e77f3-118">过程名后面加上括号将参数列表括起来。</span><span class="sxs-lookup"><span data-stu-id="e77f3-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="e77f3-119">如果不有任何参数，可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="e77f3-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="e77f3-120">但是，使用括号使代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="e77f3-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="e77f3-121">将参数放在括号内，用逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="e77f3-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="e77f3-122">请确保您的相同顺序的参数提供的`Function`过程定义相应的参数，除非您按名称传递它们。</span><span class="sxs-lookup"><span data-stu-id="e77f3-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4.  <span data-ttu-id="e77f3-123">从过程返回的值存储在变量或赋值语句左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="e77f3-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e77f3-124">示例</span><span class="sxs-lookup"><span data-stu-id="e77f3-124">Example</span></span>  
 <span data-ttu-id="e77f3-125">下面的示例调用[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<xref:Microsoft.VisualBasic.Interaction.Environ%2A>来检索操作系统环境变量的值。</xref:Microsoft.VisualBasic.Interaction.Environ%2A></span><span class="sxs-lookup"><span data-stu-id="e77f3-125">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="e77f3-126">第一个行调用`Environ`内使用表达式，并且第二个行调用它在赋值语句。</span><span class="sxs-lookup"><span data-stu-id="e77f3-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="e77f3-127">`Environ`将变量名称作为其唯一的参数。</span><span class="sxs-lookup"><span data-stu-id="e77f3-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="e77f3-128">它返回到调用代码的变量的值。</span><span class="sxs-lookup"><span data-stu-id="e77f3-128">It returns the variable's value to the calling code.</span></span>  
  
 <span data-ttu-id="e77f3-129">[!code-vb[VbVbcnProcedures #&7;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e77f3-129">[!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77f3-130">请参见</span><span class="sxs-lookup"><span data-stu-id="e77f3-130">See Also</span></span>  
 <span data-ttu-id="e77f3-131">[Function 过程](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="e77f3-131">[Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="e77f3-132"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="e77f3-132"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="e77f3-133"> [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e77f3-133"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="e77f3-134"> [如何︰ 创建返回一个值的过程](./how-to-create-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="e77f3-134"> [How to: Create a Procedure that Returns a Value](./how-to-create-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="e77f3-135"> [如何︰ 从过程返回值](./how-to-return-a-value-from-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="e77f3-135"> [How to: Return a Value from a Procedure](./how-to-return-a-value-from-a-procedure.md) </span></span>  
<span data-ttu-id="e77f3-136"> [如何：调用不返回值的过程](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="e77f3-136"> [How to: Call a Procedure that Does Not Return a Value](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span></span>
