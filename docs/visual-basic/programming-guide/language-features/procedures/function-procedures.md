---
title: "函数过程 (Visual Basic 中) |Microsoft 文档"
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
- Function procedures
- return values, function procedures
- Visual Basic code, procedures
- procedures, calling
- procedures, Function procedures
- syntax, function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fb36ee41e4b53f6e690ce5d48d34bbfc9f86c177
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="12e81-102">Function 过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12e81-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="12e81-103">一个`Function`过程是一系列[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]语句括`Function`和`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="12e81-103">A `Function` procedure is a series of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="12e81-104">`Function`过程执行一项任务，再将控制权返回给调用代码。</span><span class="sxs-lookup"><span data-stu-id="12e81-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="12e81-105">当此方法返回控制时，它还向调用代码返回一个值。</span><span class="sxs-lookup"><span data-stu-id="12e81-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="12e81-106">每次调用该过程时，运行时，其语句开头的第一个可执行语句后`Function`语句，并与第一个结束`End Function`， `Exit Function`，或`Return`遇到的语句。</span><span class="sxs-lookup"><span data-stu-id="12e81-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="12e81-107">您可以定义`Function`模块、 类或结构中的过程。</span><span class="sxs-lookup"><span data-stu-id="12e81-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="12e81-108">它是`Public`默认情况下，这意味着可以从任何位置调用在有权访问模块、 类或结构定义它的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="12e81-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="12e81-109">一个`Function`过程可以采用参数，如常量、 变量或表达式，通过调用代码传递给它。</span><span class="sxs-lookup"><span data-stu-id="12e81-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="12e81-110">声明语法</span><span class="sxs-lookup"><span data-stu-id="12e81-110">Declaration Syntax</span></span>  
 <span data-ttu-id="12e81-111">声明的语法`Function`过程是，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="12e81-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="12e81-112">*修饰符*可以指定访问级别和重载、 重写、 共享和隐藏有关的信息。</span><span class="sxs-lookup"><span data-stu-id="12e81-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="12e81-113">有关详细信息，请参阅[Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="12e81-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="12e81-114">声明每个参数相同的方式相似， [Sub 过程](./sub-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="12e81-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="12e81-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="12e81-115">Data Type</span></span>  
 <span data-ttu-id="12e81-116">每个`Function`过程具有一种数据类型，只需为每个变量一样。</span><span class="sxs-lookup"><span data-stu-id="12e81-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="12e81-117">此数据类型由指定`As`中的子句`Function`语句，并且它确定该函数将返回到调用代码的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="12e81-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="12e81-118">下面的示例声明说明这一点。</span><span class="sxs-lookup"><span data-stu-id="12e81-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="12e81-119">有关详细信息，请参阅"部件" [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="12e81-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="12e81-120">返回值</span><span class="sxs-lookup"><span data-stu-id="12e81-120">Returning Values</span></span>  
 <span data-ttu-id="12e81-121">值`Function`过程将发送回调用代码调用它的返回值。</span><span class="sxs-lookup"><span data-stu-id="12e81-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="12e81-122">此过程返回此值在两种方式之一︰</span><span class="sxs-lookup"><span data-stu-id="12e81-122">The procedure returns this value in one of two ways:</span></span>  
  
-   <span data-ttu-id="12e81-123">它使用`Return`语句来指定返回值，并返回给调用程序立即控制。</span><span class="sxs-lookup"><span data-stu-id="12e81-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="12e81-124">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="12e81-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   <span data-ttu-id="12e81-125">它将值分配给其自己的函数名称在一个或多个语句中的过程。</span><span class="sxs-lookup"><span data-stu-id="12e81-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="12e81-126">控制不返回给调用程序直到`Exit Function`或`End Function`执行语句。</span><span class="sxs-lookup"><span data-stu-id="12e81-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="12e81-127">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="12e81-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="12e81-128">返回值分配给函数名的优点是，控件才会返回过程中遇到`Exit Function`或`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="12e81-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="12e81-129">这样，您可以分配一个初步的值和更高版本调整，如有必要。</span><span class="sxs-lookup"><span data-stu-id="12e81-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="12e81-130">有关返回值的详细信息，请参阅[Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="12e81-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="12e81-131">有关返回数组的信息，请参阅[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="12e81-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="12e81-132">调用语法</span><span class="sxs-lookup"><span data-stu-id="12e81-132">Calling Syntax</span></span>  
 <span data-ttu-id="12e81-133">您可以调用`Function`过程的方法是将其名称和参数放在赋值语句或表达式中的右侧。</span><span class="sxs-lookup"><span data-stu-id="12e81-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="12e81-134">您必须提供值的所有参数，不是可选的并且必须将参数列表括在括号中。</span><span class="sxs-lookup"><span data-stu-id="12e81-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="12e81-135">如果未不提供任何参数，可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="12e81-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="12e81-136">对的调用语法`Function`过程是，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="12e81-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="12e81-137">*左值*`=`*functionname* `[(` *argumentlist*    `)]`</span><span class="sxs-lookup"><span data-stu-id="12e81-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="12e81-138">`If ((`*functionname* `[(` *argumentlist* `)] / 3) <=`*表达式*  `) Then`</span><span class="sxs-lookup"><span data-stu-id="12e81-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="12e81-139">当您调用`Function`的过程中，您无需使用其返回值。</span><span class="sxs-lookup"><span data-stu-id="12e81-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="12e81-140">如果不这样做，将执行的函数的所有操作，但将忽略返回值。</span><span class="sxs-lookup"><span data-stu-id="12e81-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="12e81-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>通常会调用这种方式。</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="12e81-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="12e81-142">声明和调用的插图</span><span class="sxs-lookup"><span data-stu-id="12e81-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="12e81-143">以下`Function`过程计算的最长边或斜边直角三角形而言，给定的其他两个方面。</span><span class="sxs-lookup"><span data-stu-id="12e81-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 <span data-ttu-id="12e81-144">[!code-vb[VbVbcnProcedures #&1;](./codesnippet/VisualBasic/function-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="12e81-144">[!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="12e81-145">下面的示例演示如何调用典型`hypotenuse`。</span><span class="sxs-lookup"><span data-stu-id="12e81-145">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 <span data-ttu-id="12e81-146">[!code-vb[VbVbcnProcedures #&6;](./codesnippet/VisualBasic/function-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="12e81-146">[!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e81-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12e81-147">See Also</span></span>  
 <span data-ttu-id="12e81-148">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="12e81-148">[Procedures](./index.md) </span></span>  
<span data-ttu-id="12e81-149"> [Sub 过程](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="12e81-149"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="12e81-150"> [属性过程](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="12e81-150"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="12e81-151"> [运算符过程](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="12e81-151"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="12e81-152"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="12e81-152"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="12e81-153"> [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="12e81-153"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="12e81-154"> [如何︰ 创建返回一个值的过程](./how-to-create-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="12e81-154"> [How to: Create a Procedure that Returns a Value](./how-to-create-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="12e81-155"> [如何︰ 从过程返回值](./how-to-return-a-value-from-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="12e81-155"> [How to: Return a Value from a Procedure](./how-to-return-a-value-from-a-procedure.md) </span></span>  
<span data-ttu-id="12e81-156"> [如何：调用返回值的过程](./how-to-call-a-procedure-that-returns-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="12e81-156"> [How to: Call a Procedure That Returns a Value](./how-to-call-a-procedure-that-returns-a-value.md)</span></span>
