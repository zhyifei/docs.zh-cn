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
ms.openlocfilehash: 80c9a77494be95365899c6a25435fcfc5d2a7293
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175014"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="a5848-102">运算符过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5848-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="a5848-103">运算符过程是一系列定义标准运算符的行为的 Visual Basic 语句 (如`*`， `<>`，或`And`) 上的类或结构定义。</span><span class="sxs-lookup"><span data-stu-id="a5848-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="a5848-104">这也称为*运算符重载*。</span><span class="sxs-lookup"><span data-stu-id="a5848-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="a5848-105">何时定义运算符过程</span><span class="sxs-lookup"><span data-stu-id="a5848-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="a5848-106">当已定义的类或结构时，可声明为类或结构的类型的变量。</span><span class="sxs-lookup"><span data-stu-id="a5848-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="a5848-107">有时此类变量需要参与一个操作作为表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="a5848-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="a5848-108">若要执行此操作，它必须是运算符的操作数。</span><span class="sxs-lookup"><span data-stu-id="a5848-108">To do this, it must be an operand of an operator.</span></span>  
  
 <span data-ttu-id="a5848-109">Visual Basic 仅在其基本数据类型上定义运算符。</span><span class="sxs-lookup"><span data-stu-id="a5848-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="a5848-110">您可以定义一个运算符的行为或两个操作数均为类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="a5848-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="a5848-111">有关详细信息，请参阅[Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="a5848-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="a5848-112">类型的运算符过程</span><span class="sxs-lookup"><span data-stu-id="a5848-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="a5848-113">运算符过程可以是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="a5848-113">An operator procedure can be one of the following types:</span></span>  
  
-   <span data-ttu-id="a5848-114">其中的参数是类或结构的类型的一元运算符的定义。</span><span class="sxs-lookup"><span data-stu-id="a5848-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="a5848-115">其中至少一个参数是类或结构的类型的二进制运算符的定义。</span><span class="sxs-lookup"><span data-stu-id="a5848-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="a5848-116">其中的参数是类或结构的类型的转换运算符的定义。</span><span class="sxs-lookup"><span data-stu-id="a5848-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
-   <span data-ttu-id="a5848-117">转换运算符返回的类或结构类型的定义。</span><span class="sxs-lookup"><span data-stu-id="a5848-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="a5848-118">转换运算符始终是一元，并始终使用`CType`用作您定义的运算符。</span><span class="sxs-lookup"><span data-stu-id="a5848-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="a5848-119">声明语法</span><span class="sxs-lookup"><span data-stu-id="a5848-119">Declaration Syntax</span></span>  
 <span data-ttu-id="a5848-120">声明运算符过程的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5848-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`  <span data-ttu-id="a5848-121">*operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span><span class="sxs-lookup"><span data-stu-id="a5848-121">*operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="a5848-122">您使用`Widening`或`Narrowing`关键字仅在类型转换运算符。</span><span class="sxs-lookup"><span data-stu-id="a5848-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="a5848-123">运算符符号始终是[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)的类型转换运算符。</span><span class="sxs-lookup"><span data-stu-id="a5848-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="a5848-124">声明两个操作数定义二元运算符，并声明一个要定义一元运算符，包括类型转换运算符的操作数。</span><span class="sxs-lookup"><span data-stu-id="a5848-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="a5848-125">必须声明所有操作数`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="a5848-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="a5848-126">相同的方式声明的参数声明每个操作数[Sub 过程](./sub-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="a5848-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="a5848-127">数据类型</span><span class="sxs-lookup"><span data-stu-id="a5848-127">Data Type</span></span>  
 <span data-ttu-id="a5848-128">要在类或已定义的结构上定义运算符，因为至少一个操作数必须是类或结构的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a5848-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="a5848-129">有关类型转换运算符，操作数或返回类型必须是类或结构的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a5848-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="a5848-130">有关更多详细信息，请参阅[Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="a5848-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="a5848-131">调用语法</span><span class="sxs-lookup"><span data-stu-id="a5848-131">Calling Syntax</span></span>  
 <span data-ttu-id="a5848-132">通过在表达式中使用的运算符符号的隐式调用运算符过程。</span><span class="sxs-lookup"><span data-stu-id="a5848-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="a5848-133">提供操作数的相同方式为预定义的运算符。</span><span class="sxs-lookup"><span data-stu-id="a5848-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="a5848-134">隐式调用运算符过程的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5848-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 `Dim testStruct As`  *<span data-ttu-id="a5848-135">结构名称</span><span class="sxs-lookup"><span data-stu-id="a5848-135">structurename</span></span>*  
  
 `Dim testNewStruct As`  <span data-ttu-id="a5848-136">*structurename*  `= testStruct`  *operatorsymbol*</span><span class="sxs-lookup"><span data-stu-id="a5848-136">*structurename*  `= testStruct`  *operatorsymbol*</span></span>  `10`  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="a5848-137">声明和调用的插图</span><span class="sxs-lookup"><span data-stu-id="a5848-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="a5848-138">以下结构将 128 位带符号的整数值存储为构成的高序位，低位部分。</span><span class="sxs-lookup"><span data-stu-id="a5848-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="a5848-139">它定义`+`运算符将两个`veryLong`值，并生成生成`veryLong`值。</span><span class="sxs-lookup"><span data-stu-id="a5848-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 [!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]  
  
 <span data-ttu-id="a5848-140">下面的示例演示对典型调用`+`上定义的运算符`veryLong`。</span><span class="sxs-lookup"><span data-stu-id="a5848-140">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]  

## <a name="see-also"></a><span data-ttu-id="a5848-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5848-141">See also</span></span>

- [<span data-ttu-id="a5848-142">过程</span><span class="sxs-lookup"><span data-stu-id="a5848-142">Procedures</span></span>](./index.md)
- [<span data-ttu-id="a5848-143">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="a5848-143">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="a5848-144">Function 过程</span><span class="sxs-lookup"><span data-stu-id="a5848-144">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="a5848-145">Property 过程</span><span class="sxs-lookup"><span data-stu-id="a5848-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="a5848-146">过程形参和实参</span><span class="sxs-lookup"><span data-stu-id="a5848-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a5848-147">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="a5848-147">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="a5848-148">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="a5848-148">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="a5848-149">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="a5848-149">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="a5848-150">如何：调用运算符过程</span><span class="sxs-lookup"><span data-stu-id="a5848-150">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="a5848-151">如何：使用定义运算符的类</span><span class="sxs-lookup"><span data-stu-id="a5848-151">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
