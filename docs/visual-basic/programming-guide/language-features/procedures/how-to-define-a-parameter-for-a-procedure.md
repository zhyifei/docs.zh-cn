---
title: "如何：为过程定义参数 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c909cfe1b45a42aae91948917f310474575f225
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="1e8a2-102">如何：为过程定义参数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e8a2-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="1e8a2-103">A*参数*允许调用代码将值传递给过程时它将调用它。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="1e8a2-104">声明一个过程的每个参数相同的方式声明变量，指定其名称和数据类型。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="1e8a2-105">你还指定的传递机制，以及是否是可选参数。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="1e8a2-106">有关详细信息，请参阅[过程参数和自变量](./procedure-parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="1e8a2-107">若要定义过程参数</span><span class="sxs-lookup"><span data-stu-id="1e8a2-107">To define a procedure parameter</span></span>  
  
1.  <span data-ttu-id="1e8a2-108">在过程声明中，将添加到过程的参数列表中，用逗号将其与其他参数的参数名称。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2.  <span data-ttu-id="1e8a2-109">确定参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-109">Decide the data type of the parameter.</span></span>  
  
3.  <span data-ttu-id="1e8a2-110">参数名后面加上`As`子句以指定数据类型。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4.  <span data-ttu-id="1e8a2-111">确定所需的参数的传递机制。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="1e8a2-112">通常情况下参数按值传递，除非你想要能够更改其值调用的代码中的过程。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5.  <span data-ttu-id="1e8a2-113">参数名前面放置[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)指定的传递机制。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="1e8a2-114">有关详细信息，请参阅[差异之间传递自变量传递的值和按引用](./differences-between-passing-an-argument-by-value-and-by-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6.  <span data-ttu-id="1e8a2-115">如果参数是可选的位于之前使用的传递机制[可选](../../../../visual-basic/language-reference/modifiers/optional.md)并按照以等号的参数数据类型 (`=`) 和默认值。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="1e8a2-116">下面的示例定义的大纲`Sub`带有三个参数的过程。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="1e8a2-117">前两个是必需而且是可选的第三个。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="1e8a2-118">参数声明用逗号分隔的参数列表中。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     [!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     <span data-ttu-id="1e8a2-119">第一个参数接受`customer`对象，和`updateCustomer`可以直接更新传递给该变量`c`因为自变量传递[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-119">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="1e8a2-120">过程不能更改的最后两个自变量的值，因为它们的传递[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-120">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="1e8a2-121">如果调用的代码不会提供的值`level`参数，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]将其设置为默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-121">If the calling code does not supply a value for the `level` parameter, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="1e8a2-122">如果类型检查开关 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 是`Off`、`As`子句是可选的当定义参数。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="1e8a2-123">但是，如果任何一个参数使用`As`子句，所有这些必须使用它。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-123">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="1e8a2-124">如果类型检查开关`On`、`As`子句是必需的每个参数定义。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-124">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="1e8a2-125">指定所有编程元素的数据类型被称为*强类型化*。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-125">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="1e8a2-126">当你将设置`Option Strict On`，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]强制实施强类型化。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-126">When you set `Option Strict On`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] enforces strong typing.</span></span> <span data-ttu-id="1e8a2-127">这是强烈建议，原因如下：</span><span class="sxs-lookup"><span data-stu-id="1e8a2-127">This is strongly recommended, for the following reasons:</span></span>  
  
    -   <span data-ttu-id="1e8a2-128">它使对变量和参数的 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-128">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="1e8a2-129">这样，你可以查看其属性和其他成员，在你的代码中键入。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-129">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    -   <span data-ttu-id="1e8a2-130">它允许编译器执行类型检查。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-130">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="1e8a2-131">这将有助于捕捉可能会在运行时由于如溢出错误而导致失败的语句。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-131">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="1e8a2-132">它还不支持这些选项的对象上捕获对方法的调用。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-132">It also catches calls to methods on objects that do not support them.</span></span>  
  
    -   <span data-ttu-id="1e8a2-133">这会导致你的代码的执行速度更快。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-133">It results in faster execution of your code.</span></span> <span data-ttu-id="1e8a2-134">一个原因是，如果你不指定一个编程元素，数据类型[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器会将其分配`Object`类型。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-134">One reason for this is that if you do not specify a data type for a programming element, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler assigns it the `Object` type.</span></span> <span data-ttu-id="1e8a2-135">已编译的代码可能需要将之间来回转换`Object`和其他数据类型，这会降低性能。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-135">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e8a2-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e8a2-136">See Also</span></span>  
 [<span data-ttu-id="1e8a2-137">过程</span><span class="sxs-lookup"><span data-stu-id="1e8a2-137">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="1e8a2-138">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="1e8a2-138">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="1e8a2-139">Function 过程</span><span class="sxs-lookup"><span data-stu-id="1e8a2-139">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="1e8a2-140">如何：将自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="1e8a2-140">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="1e8a2-141">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="1e8a2-141">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="1e8a2-142">递归过程</span><span class="sxs-lookup"><span data-stu-id="1e8a2-142">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="1e8a2-143">过程重载</span><span class="sxs-lookup"><span data-stu-id="1e8a2-143">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="1e8a2-144">对象和类</span><span class="sxs-lookup"><span data-stu-id="1e8a2-144">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="1e8a2-145">面向对象的编程</span><span class="sxs-lookup"><span data-stu-id="1e8a2-145">Object-Oriented Programming</span></span>](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
