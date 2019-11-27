---
title: 如何：为过程定义参数
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: 411959a7be92ea49a59558b508e992bfba8eff95
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344889"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="6abf1-102">如何：为过程定义参数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6abf1-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="6abf1-103">*参数*允许调用代码在调用时将值传递给过程。</span><span class="sxs-lookup"><span data-stu-id="6abf1-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="6abf1-104">声明过程的每个参数的方式与声明变量的方式相同，即指定其名称和数据类型。</span><span class="sxs-lookup"><span data-stu-id="6abf1-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="6abf1-105">还可指定传递机制，以及参数是否为可选。</span><span class="sxs-lookup"><span data-stu-id="6abf1-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="6abf1-106">有关详细信息，请参阅[过程参数和参数](./procedure-parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="6abf1-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="6abf1-107">定义过程参数</span><span class="sxs-lookup"><span data-stu-id="6abf1-107">To define a procedure parameter</span></span>  
  
1. <span data-ttu-id="6abf1-108">在过程声明中，将参数名称添加到过程的参数列表，并将其与其他参数之间用逗号分隔开。</span><span class="sxs-lookup"><span data-stu-id="6abf1-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2. <span data-ttu-id="6abf1-109">确定参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="6abf1-109">Decide the data type of the parameter.</span></span>  
  
3. <span data-ttu-id="6abf1-110">请在参数名称后面加上一个 `As` 子句来指定数据类型。</span><span class="sxs-lookup"><span data-stu-id="6abf1-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4. <span data-ttu-id="6abf1-111">确定要用于参数的传递机制。</span><span class="sxs-lookup"><span data-stu-id="6abf1-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="6abf1-112">通常，按值传递参数，除非您希望该过程能够在调用代码中更改其值。</span><span class="sxs-lookup"><span data-stu-id="6abf1-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5. <span data-ttu-id="6abf1-113">在参数名称前面加上[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)来指定传递机制。</span><span class="sxs-lookup"><span data-stu-id="6abf1-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="6abf1-114">有关详细信息，请参阅[按值传递参数和通过引用传递参数之间的差异](./differences-between-passing-an-argument-by-value-and-by-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="6abf1-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6. <span data-ttu-id="6abf1-115">如果该参数是可选的，请在传递机制之前加上[optional](../../../../visual-basic/language-reference/modifiers/optional.md) ，并使用等号（`=`）和默认值作为参数数据类型。</span><span class="sxs-lookup"><span data-stu-id="6abf1-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="6abf1-116">下面的示例使用三个参数定义 `Sub` 过程的轮廓。</span><span class="sxs-lookup"><span data-stu-id="6abf1-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="6abf1-117">前两个参数是必需的，第三个参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="6abf1-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="6abf1-118">参数声明在参数列表中用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="6abf1-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     <span data-ttu-id="6abf1-119">第一个参数接受 `customer` 对象，`updateCustomer` 可以直接[更新传递给](../../../../visual-basic/language-reference/modifiers/byref.md)`c` 的变量，因为参数是传递的。</span><span class="sxs-lookup"><span data-stu-id="6abf1-119">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="6abf1-120">此过程无法更改最后两个参数的值，因为它们是通过[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)传递的。</span><span class="sxs-lookup"><span data-stu-id="6abf1-120">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="6abf1-121">如果调用代码未提供 `level` 参数的值，则 Visual Basic 将其设置为默认值0。</span><span class="sxs-lookup"><span data-stu-id="6abf1-121">If the calling code does not supply a value for the `level` parameter, Visual Basic sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="6abf1-122">如果 `Off`类型检查开关（[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)），则在定义参数时，`As` 子句是可选的。</span><span class="sxs-lookup"><span data-stu-id="6abf1-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="6abf1-123">但是，如果任何一个参数使用 `As` 子句，则所有参数都必须使用它。</span><span class="sxs-lookup"><span data-stu-id="6abf1-123">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="6abf1-124">如果类型检查开关 `On`，则每个参数定义都需要 `As` 子句。</span><span class="sxs-lookup"><span data-stu-id="6abf1-124">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="6abf1-125">为所有编程元素指定数据类型称为*强*类型。</span><span class="sxs-lookup"><span data-stu-id="6abf1-125">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="6abf1-126">设置 `Option Strict On`时，Visual Basic 强制执行强类型化。</span><span class="sxs-lookup"><span data-stu-id="6abf1-126">When you set `Option Strict On`, Visual Basic enforces strong typing.</span></span> <span data-ttu-id="6abf1-127">出于以下原因，强烈建议执行此操作：</span><span class="sxs-lookup"><span data-stu-id="6abf1-127">This is strongly recommended, for the following reasons:</span></span>  
  
    - <span data-ttu-id="6abf1-128">它为你的变量和参数启用 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="6abf1-128">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="6abf1-129">这使您可以在代码中键入时查看它们的属性和其他成员。</span><span class="sxs-lookup"><span data-stu-id="6abf1-129">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    - <span data-ttu-id="6abf1-130">它允许编译器执行类型检查。</span><span class="sxs-lookup"><span data-stu-id="6abf1-130">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="6abf1-131">这有助于捕获由于溢出等错误而在运行时可能会失败的语句。</span><span class="sxs-lookup"><span data-stu-id="6abf1-131">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="6abf1-132">它还会捕获对不支持这些对象的方法的调用。</span><span class="sxs-lookup"><span data-stu-id="6abf1-132">It also catches calls to methods on objects that do not support them.</span></span>  
  
    - <span data-ttu-id="6abf1-133">这会使代码的执行速度更快。</span><span class="sxs-lookup"><span data-stu-id="6abf1-133">It results in faster execution of your code.</span></span> <span data-ttu-id="6abf1-134">导致这种情况的原因之一是，如果未指定编程元素的数据类型，则 Visual Basic 编译器会为其分配 `Object` 类型。</span><span class="sxs-lookup"><span data-stu-id="6abf1-134">One reason for this is that if you do not specify a data type for a programming element, the Visual Basic compiler assigns it the `Object` type.</span></span> <span data-ttu-id="6abf1-135">已编译的代码可能必须在 `Object` 和其他数据类型之间来回转换，这会降低性能。</span><span class="sxs-lookup"><span data-stu-id="6abf1-135">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6abf1-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6abf1-136">See also</span></span>

- [<span data-ttu-id="6abf1-137">过程</span><span class="sxs-lookup"><span data-stu-id="6abf1-137">Procedures</span></span>](./index.md)
- [<span data-ttu-id="6abf1-138">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="6abf1-138">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="6abf1-139">Function 过程</span><span class="sxs-lookup"><span data-stu-id="6abf1-139">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="6abf1-140">如何：将自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="6abf1-140">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="6abf1-141">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="6abf1-141">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="6abf1-142">递归过程</span><span class="sxs-lookup"><span data-stu-id="6abf1-142">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="6abf1-143">过程重载</span><span class="sxs-lookup"><span data-stu-id="6abf1-143">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="6abf1-144">对象和类</span><span class="sxs-lookup"><span data-stu-id="6abf1-144">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="6abf1-145">面向对象的编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6abf1-145">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
