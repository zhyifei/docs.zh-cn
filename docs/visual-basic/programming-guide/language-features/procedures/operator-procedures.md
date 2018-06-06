---
title: 运算符过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: 5b4641ce8509e3111a11ed803d36194d5a301bce
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805706"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="9490e-102">运算符过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9490e-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="9490e-103">运算符过程是一系列定义一个标准的运算符的行为的 Visual Basic 语句 (如`*`， `<>`，或`And`) 对类或你定义的结构。</span><span class="sxs-lookup"><span data-stu-id="9490e-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="9490e-104">这也称为*运算符重载*。</span><span class="sxs-lookup"><span data-stu-id="9490e-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="9490e-105">何时定义运算符过程</span><span class="sxs-lookup"><span data-stu-id="9490e-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="9490e-106">当你已定义类或结构时，可声明为类或结构的类型的变量。</span><span class="sxs-lookup"><span data-stu-id="9490e-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="9490e-107">有时这种变量需要参与一个操作作为表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="9490e-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="9490e-108">若要执行此操作，它必须是运算符的操作数。</span><span class="sxs-lookup"><span data-stu-id="9490e-108">To do this, it must be an operand of an operator.</span></span>  
  
 <span data-ttu-id="9490e-109">Visual Basic 仅在其基本数据类型上定义运算符。</span><span class="sxs-lookup"><span data-stu-id="9490e-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="9490e-110">你可以定义一个运算符的行为或两个操作数均为你的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="9490e-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="9490e-111">有关详细信息，请参阅[Operator 语句](../../../../visual-basic/language-reference/statements/operator-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="9490e-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="9490e-112">类型的运算符过程</span><span class="sxs-lookup"><span data-stu-id="9490e-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="9490e-113">运算符过程可以是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="9490e-113">An operator procedure can be one of the following types:</span></span>  
  
-   <span data-ttu-id="9490e-114">一元运算符的自变量为类或结构类型的其中一个定义。</span><span class="sxs-lookup"><span data-stu-id="9490e-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="9490e-115">其中至少一个自变量是类或结构类型的二进制运算符的定义。</span><span class="sxs-lookup"><span data-stu-id="9490e-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="9490e-116">其中的自变量为类或结构类型转换运算符的定义。</span><span class="sxs-lookup"><span data-stu-id="9490e-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="9490e-117">返回的类或结构类型转换运算符的定义。</span><span class="sxs-lookup"><span data-stu-id="9490e-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="9490e-118">转换运算符始终是一元，并且会一直使用`CType`用作你定义的运算符。</span><span class="sxs-lookup"><span data-stu-id="9490e-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="9490e-119">声明语法</span><span class="sxs-lookup"><span data-stu-id="9490e-119">Declaration Syntax</span></span>  
 <span data-ttu-id="9490e-120">声明运算符过程的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="9490e-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="9490e-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol* `(` *operand1*`[,`*operand2* `]) As`*数据类型*</span><span class="sxs-lookup"><span data-stu-id="9490e-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="9490e-122">你使用`Widening`或`Narrowing`关键字仅在类型转换运算符。</span><span class="sxs-lookup"><span data-stu-id="9490e-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="9490e-123">运算符符号始终是[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)有关类型转换运算符。</span><span class="sxs-lookup"><span data-stu-id="9490e-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="9490e-124">声明两个操作数定义二元运算符，并声明一个要定义一元运算符，包括类型转换运算符的操作数。</span><span class="sxs-lookup"><span data-stu-id="9490e-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="9490e-125">所有操作数都必须都声明`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="9490e-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="9490e-126">声明每个操作数相同的方式声明的参数[Sub 过程](./sub-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="9490e-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="9490e-127">数据类型</span><span class="sxs-lookup"><span data-stu-id="9490e-127">Data Type</span></span>  
 <span data-ttu-id="9490e-128">因为你在类或你定义的结构上定义一个运算符，至少其中一个操作数必须是此类或结构的数据类型。</span><span class="sxs-lookup"><span data-stu-id="9490e-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="9490e-129">对于类型转换运算符，操作数或的返回类型必须是类或结构的数据类型。</span><span class="sxs-lookup"><span data-stu-id="9490e-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="9490e-130">有关更多详细信息，请参阅[Operator 语句](../../../../visual-basic/language-reference/statements/operator-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="9490e-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="9490e-131">调用语法</span><span class="sxs-lookup"><span data-stu-id="9490e-131">Calling Syntax</span></span>  
 <span data-ttu-id="9490e-132">通过在表达式中使用运算符的隐式调用运算符过程。</span><span class="sxs-lookup"><span data-stu-id="9490e-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="9490e-133">你提供操作数你对于预定义的运算符的相同方式。</span><span class="sxs-lookup"><span data-stu-id="9490e-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="9490e-134">隐式调用运算符过程的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="9490e-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="9490e-135">`Dim testStruct As`  *structurename*</span><span class="sxs-lookup"><span data-stu-id="9490e-135">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="9490e-136">`Dim testNewStruct As`  *structurename*`= testStruct`*operatorsymbol*  `10`</span><span class="sxs-lookup"><span data-stu-id="9490e-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="9490e-137">声明和调用图</span><span class="sxs-lookup"><span data-stu-id="9490e-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="9490e-138">以下结构存储构成的高顺序和低序位部分作为一个 128 位有符号的整数值。</span><span class="sxs-lookup"><span data-stu-id="9490e-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="9490e-139">它定义`+`运算符添加两个`veryLong`值，并生成生成`veryLong`值。</span><span class="sxs-lookup"><span data-stu-id="9490e-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 [!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 <span data-ttu-id="9490e-140">下面的示例演示典型调用`+`上定义的运算符`veryLong`。</span><span class="sxs-lookup"><span data-stu-id="9490e-140">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 <span data-ttu-id="9490e-141">有关详细信息和示例，请参阅 [Visual Basic 2005 中的运算符重载](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx)。</span><span class="sxs-lookup"><span data-stu-id="9490e-141">For more information and examples, see [Operator Overloading in Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9490e-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="9490e-142">See Also</span></span>  
 [<span data-ttu-id="9490e-143">过程</span><span class="sxs-lookup"><span data-stu-id="9490e-143">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="9490e-144">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="9490e-144">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="9490e-145">Function 过程</span><span class="sxs-lookup"><span data-stu-id="9490e-145">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="9490e-146">属性过程</span><span class="sxs-lookup"><span data-stu-id="9490e-146">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="9490e-147">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="9490e-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="9490e-148">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="9490e-148">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="9490e-149">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="9490e-149">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="9490e-150">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="9490e-150">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="9490e-151">如何：调用运算符过程</span><span class="sxs-lookup"><span data-stu-id="9490e-151">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="9490e-152">如何：使用定义运算符的类</span><span class="sxs-lookup"><span data-stu-id="9490e-152">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
