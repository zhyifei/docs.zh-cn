---
title: 如何：定义参数的过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: 55925b0f007b1be2f5d46ffc0854601f483b2e2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863696"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="c9564-102">如何：定义参数的过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9564-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="c9564-103">一个*参数*允许调用代码将调用它时，将值传递给过程。</span><span class="sxs-lookup"><span data-stu-id="c9564-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="c9564-104">声明过程每个参数相同的方式声明变量，指定其名称和数据类型。</span><span class="sxs-lookup"><span data-stu-id="c9564-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="c9564-105">您还指定的传递机制，以及该参数是否可选。</span><span class="sxs-lookup"><span data-stu-id="c9564-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="c9564-106">有关详细信息，请参阅[过程形参和实参](./procedure-parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="c9564-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="c9564-107">若要定义过程参数</span><span class="sxs-lookup"><span data-stu-id="c9564-107">To define a procedure parameter</span></span>  
  
1. <span data-ttu-id="c9564-108">在过程声明中，将添加到过程的参数列表中，使用逗号将其与其他参数的参数名称。</span><span class="sxs-lookup"><span data-stu-id="c9564-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2. <span data-ttu-id="c9564-109">决定参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c9564-109">Decide the data type of the parameter.</span></span>  
  
3. <span data-ttu-id="c9564-110">在参数名称后的加`As`子句指定的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c9564-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4. <span data-ttu-id="c9564-111">确定所需的参数的传递机制。</span><span class="sxs-lookup"><span data-stu-id="c9564-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="c9564-112">通常情况下，按值传递参数，除非你想要能够调用代码中更改其值的过程。</span><span class="sxs-lookup"><span data-stu-id="c9564-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5. <span data-ttu-id="c9564-113">参数名称前面加上[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)指定的传递机制。</span><span class="sxs-lookup"><span data-stu-id="c9564-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="c9564-114">有关详细信息，请参阅[差异之间传递参数值和按引用来](./differences-between-passing-an-argument-by-value-and-by-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="c9564-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6. <span data-ttu-id="c9564-115">如果参数是可选的前, 加上使用的传递机制[可选](../../../../visual-basic/language-reference/modifiers/optional.md)并按照参数的数据类型以等号 (`=`) 和默认值。</span><span class="sxs-lookup"><span data-stu-id="c9564-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="c9564-116">下面的示例定义的大纲`Sub`具有三个参数的过程。</span><span class="sxs-lookup"><span data-stu-id="c9564-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="c9564-117">所需的前两个和第三个是可选的。</span><span class="sxs-lookup"><span data-stu-id="c9564-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="c9564-118">参数声明由逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="c9564-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     <span data-ttu-id="c9564-119">第一个参数接受`customer`对象，并`updateCustomer`可以直接更新变量传递给`c`因为将实参传递[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)。</span><span class="sxs-lookup"><span data-stu-id="c9564-119">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="c9564-120">该过程不能更改的最后两个参数的值，因为它们的传递[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="c9564-120">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="c9564-121">如果调用代码不会提供的值`level`参数，Visual Basic 将其设置为默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="c9564-121">If the calling code does not supply a value for the `level` parameter, Visual Basic sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="c9564-122">如果类型检查开关 ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 是`Off`，则`As`子句是可选的时定义的参数。</span><span class="sxs-lookup"><span data-stu-id="c9564-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="c9564-123">但是，如果任何一个参数使用`As`子句中，所有这些必须使用它。</span><span class="sxs-lookup"><span data-stu-id="c9564-123">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="c9564-124">如果类型检查开关`On`，则`As`子句是必需的每个参数定义。</span><span class="sxs-lookup"><span data-stu-id="c9564-124">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="c9564-125">指定所有编程元素的数据类型被称为*强类型化*。</span><span class="sxs-lookup"><span data-stu-id="c9564-125">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="c9564-126">当您将设置`Option Strict On`，Visual Basic 强制实施强类型化。</span><span class="sxs-lookup"><span data-stu-id="c9564-126">When you set `Option Strict On`, Visual Basic enforces strong typing.</span></span> <span data-ttu-id="c9564-127">这是强烈建议，原因如下：</span><span class="sxs-lookup"><span data-stu-id="c9564-127">This is strongly recommended, for the following reasons:</span></span>  
  
    -   <span data-ttu-id="c9564-128">这样，对变量和参数的 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="c9564-128">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="c9564-129">这样可以查看其属性和其他成员，当您键入代码。</span><span class="sxs-lookup"><span data-stu-id="c9564-129">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    -   <span data-ttu-id="c9564-130">它允许编译器执行类型检查。</span><span class="sxs-lookup"><span data-stu-id="c9564-130">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="c9564-131">这有助于 catch 语句可以在运行时因等溢出错误而失败。</span><span class="sxs-lookup"><span data-stu-id="c9564-131">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="c9564-132">不支持它们的对象，它还捕获对方法的调用。</span><span class="sxs-lookup"><span data-stu-id="c9564-132">It also catches calls to methods on objects that do not support them.</span></span>  
  
    -   <span data-ttu-id="c9564-133">这会导致代码更快地执行。</span><span class="sxs-lookup"><span data-stu-id="c9564-133">It results in faster execution of your code.</span></span> <span data-ttu-id="c9564-134">原因之一就是，如果不指定编程元素的数据类型，Visual Basic 编译器为其分配`Object`类型。</span><span class="sxs-lookup"><span data-stu-id="c9564-134">One reason for this is that if you do not specify a data type for a programming element, the Visual Basic compiler assigns it the `Object` type.</span></span> <span data-ttu-id="c9564-135">已编译的代码可能需要将之间来回转换`Object`和其他数据类型，这会降低性能。</span><span class="sxs-lookup"><span data-stu-id="c9564-135">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9564-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9564-136">See also</span></span>

- [<span data-ttu-id="c9564-137">过程</span><span class="sxs-lookup"><span data-stu-id="c9564-137">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c9564-138">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="c9564-138">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="c9564-139">Function 过程</span><span class="sxs-lookup"><span data-stu-id="c9564-139">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="c9564-140">如何：将参数传递给过程</span><span class="sxs-lookup"><span data-stu-id="c9564-140">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="c9564-141">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="c9564-141">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="c9564-142">递归过程</span><span class="sxs-lookup"><span data-stu-id="c9564-142">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="c9564-143">过程重载</span><span class="sxs-lookup"><span data-stu-id="c9564-143">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="c9564-144">对象和类</span><span class="sxs-lookup"><span data-stu-id="c9564-144">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="c9564-145">面向对象的编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9564-145">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
