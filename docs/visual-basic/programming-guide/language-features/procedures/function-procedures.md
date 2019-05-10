---
title: Function 过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: 4fd24369380e5f8ccf8de939c36ba72a12dc872e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649614"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="da987-102">Function 过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da987-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="da987-103">一个`Function`过程是 Visual Basic 语句括在一系列`Function`和`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="da987-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="da987-104">`Function`过程执行一项任务，再将控制权返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="da987-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="da987-105">当它返回控制时，它还向调用代码返回一个值。</span><span class="sxs-lookup"><span data-stu-id="da987-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="da987-106">每次调用该过程时，运行时，其语句开头的第一个可执行语句后`Function`语句，并与第一个结束`End Function`， `Exit Function`，或`Return`遇到语句。</span><span class="sxs-lookup"><span data-stu-id="da987-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="da987-107">您可以定义`Function`模块、 类或结构中的过程。</span><span class="sxs-lookup"><span data-stu-id="da987-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="da987-108">它是`Public`默认情况下，这意味着可以从任何位置调用在有权访问模块、 类或结构定义它的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="da987-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="da987-109">一个`Function`过程可以采用自变量，如常量、 变量或表达式，通过调用代码传递给它。</span><span class="sxs-lookup"><span data-stu-id="da987-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="da987-110">声明语法</span><span class="sxs-lookup"><span data-stu-id="da987-110">Declaration Syntax</span></span>  
 <span data-ttu-id="da987-111">声明的语法`Function`过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="da987-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="da987-112">*修饰符*可以指定访问级别和重载、 重写、 共享和隐藏有关的信息。</span><span class="sxs-lookup"><span data-stu-id="da987-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="da987-113">有关详细信息，请参阅[Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="da987-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="da987-114">将每个参数声明为执行操作的相同方式[Sub 过程](./sub-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="da987-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="da987-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="da987-115">Data Type</span></span>  
 <span data-ttu-id="da987-116">每个`Function`过程具有数据类型，只需为每个变量执行。</span><span class="sxs-lookup"><span data-stu-id="da987-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="da987-117">通过指定此数据类型`As`子句中的`Function`语句，并且它确定该函数将返回到调用代码的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="da987-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="da987-118">下面的示例声明说明这一点。</span><span class="sxs-lookup"><span data-stu-id="da987-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="da987-119">详细信息，请参阅"部分"中[Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="da987-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="da987-120">返回值</span><span class="sxs-lookup"><span data-stu-id="da987-120">Returning Values</span></span>  
 <span data-ttu-id="da987-121">值`Function`过程将发送回调用代码名为其返回值。</span><span class="sxs-lookup"><span data-stu-id="da987-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="da987-122">此过程返回此值在两种方式之一：</span><span class="sxs-lookup"><span data-stu-id="da987-122">The procedure returns this value in one of two ways:</span></span>  
  
- <span data-ttu-id="da987-123">它使用`Return`语句以指定返回值，并返回到调用程序立即控制。</span><span class="sxs-lookup"><span data-stu-id="da987-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="da987-124">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="da987-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
- <span data-ttu-id="da987-125">它将值分配给自己的过程的一个或多个语句中的函数名称。</span><span class="sxs-lookup"><span data-stu-id="da987-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="da987-126">控件不返回给调用程序直到`Exit Function`或`End Function`执行语句。</span><span class="sxs-lookup"><span data-stu-id="da987-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="da987-127">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="da987-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="da987-128">将返回值分配给函数名称的优点是，控件才会返回的过程中遇到`Exit Function`或`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="da987-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="da987-129">这样，您可以分配的初步值和更高版本调整，如有必要。</span><span class="sxs-lookup"><span data-stu-id="da987-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="da987-130">有关返回值的详细信息，请参阅[Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="da987-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="da987-131">返回数组的信息，请参阅[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="da987-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="da987-132">调用语法</span><span class="sxs-lookup"><span data-stu-id="da987-132">Calling Syntax</span></span>  
 <span data-ttu-id="da987-133">调用`Function`过程的方法是将其名称和参数放在赋值语句或表达式中的右侧。</span><span class="sxs-lookup"><span data-stu-id="da987-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="da987-134">您必须是不可选的所有自变量提供值，必须将参数列表括在括号中。</span><span class="sxs-lookup"><span data-stu-id="da987-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="da987-135">如果未不提供任何参数，可以选择性地省略括号。</span><span class="sxs-lookup"><span data-stu-id="da987-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="da987-136">对的调用语法`Function`过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="da987-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="da987-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="da987-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="da987-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span><span class="sxs-lookup"><span data-stu-id="da987-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="da987-139">当您调用`Function`过程中，您无需使用它的返回值。</span><span class="sxs-lookup"><span data-stu-id="da987-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="da987-140">如果不这样做，将执行的函数的所有操作，而将忽略返回值。</span><span class="sxs-lookup"><span data-stu-id="da987-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="da987-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 以这种方式通常称为。</span><span class="sxs-lookup"><span data-stu-id="da987-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="da987-142">声明和调用的插图</span><span class="sxs-lookup"><span data-stu-id="da987-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="da987-143">以下`Function`过程计算的最长边或斜边的直角三角形而言，其他两个方面为给定的值。</span><span class="sxs-lookup"><span data-stu-id="da987-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
 <span data-ttu-id="da987-144">下面的示例演示对典型调用`hypotenuse`。</span><span class="sxs-lookup"><span data-stu-id="da987-144">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="da987-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="da987-145">See also</span></span>

- [<span data-ttu-id="da987-146">过程</span><span class="sxs-lookup"><span data-stu-id="da987-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="da987-147">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="da987-147">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="da987-148">属性过程</span><span class="sxs-lookup"><span data-stu-id="da987-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="da987-149">运算符过程</span><span class="sxs-lookup"><span data-stu-id="da987-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="da987-150">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="da987-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="da987-151">Function 语句</span><span class="sxs-lookup"><span data-stu-id="da987-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="da987-152">如何：创建一个过程，返回一个值</span><span class="sxs-lookup"><span data-stu-id="da987-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="da987-153">如何：从过程返回值</span><span class="sxs-lookup"><span data-stu-id="da987-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="da987-154">如何：调用返回的值的过程</span><span class="sxs-lookup"><span data-stu-id="da987-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
