---
title: += 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: f12a0560d984f871110c02f1df2c2ec42b68809b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604011"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="b0e01-102">+= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0e01-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="b0e01-103">将数值表达式的值添加到的数值变量或属性的值并将结果赋给该变量或属性。</span><span class="sxs-lookup"><span data-stu-id="b0e01-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="b0e01-104">此外可以使用要连接`String`表达式`String`变量或属性并将结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="b0e01-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0e01-105">语法</span><span class="sxs-lookup"><span data-stu-id="b0e01-105">Syntax</span></span>  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b0e01-106">部件</span><span class="sxs-lookup"><span data-stu-id="b0e01-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="b0e01-107">必须的。</span><span class="sxs-lookup"><span data-stu-id="b0e01-107">Required.</span></span> <span data-ttu-id="b0e01-108">任何数值或`String`变量或属性。</span><span class="sxs-lookup"><span data-stu-id="b0e01-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="b0e01-109">必须的。</span><span class="sxs-lookup"><span data-stu-id="b0e01-109">Required.</span></span> <span data-ttu-id="b0e01-110">任何数值或`String`表达式。</span><span class="sxs-lookup"><span data-stu-id="b0e01-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0e01-111">备注</span><span class="sxs-lookup"><span data-stu-id="b0e01-111">Remarks</span></span>  
 <span data-ttu-id="b0e01-112">在左侧的元素`+=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="b0e01-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="b0e01-113">变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="b0e01-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="b0e01-114">`+=`运算符将值添加到该变量或属性在其左侧，右侧，并将结果赋给该变量或与其左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="b0e01-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="b0e01-115">`+=`运算符还可以用于串联`String`到右侧的表达式`String`变量或在其左侧和将结果赋给变量的属性或与其左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="b0e01-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0e01-116">当你使用`+=`运算符，你可能不能以确定是否添加或字符串串联将出现。</span><span class="sxs-lookup"><span data-stu-id="b0e01-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="b0e01-117">使用`&=`的串联运算符，以消除多义性，并提供自说明代码。</span><span class="sxs-lookup"><span data-stu-id="b0e01-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="b0e01-118">此赋值运算符隐式执行扩大转换而不是收缩转换，如果编译环境强制执行严格的语义。</span><span class="sxs-lookup"><span data-stu-id="b0e01-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="b0e01-119">有关这些转换的详细信息，请参阅[扩大和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="b0e01-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="b0e01-120">严格和宽松语义的详细信息，请参阅[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="b0e01-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="b0e01-121">如果允许宽松语义，`+=`运算符隐式执行各种字符串和数字转换执行的转换相同`+`运算符。</span><span class="sxs-lookup"><span data-stu-id="b0e01-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="b0e01-122">有关这些转换的详细信息，请参阅[+ 运算符](../../../visual-basic/language-reference/operators/addition-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="b0e01-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b0e01-123">重载</span><span class="sxs-lookup"><span data-stu-id="b0e01-123">Overloading</span></span>  
 <span data-ttu-id="b0e01-124">`+`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="b0e01-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b0e01-125">重载`+`运算符会影响的行为`+=`运算符。</span><span class="sxs-lookup"><span data-stu-id="b0e01-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="b0e01-126">如果你的代码使用`+=`对类或重载的结构`+`，确保你理解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="b0e01-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b0e01-127">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="b0e01-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0e01-128">示例</span><span class="sxs-lookup"><span data-stu-id="b0e01-128">Example</span></span>  
 <span data-ttu-id="b0e01-129">下面的示例使用`+=`运算符将与另一个变量的值合并。</span><span class="sxs-lookup"><span data-stu-id="b0e01-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="b0e01-130">第一部分使用`+=`带有数值变量添加到另一个值。</span><span class="sxs-lookup"><span data-stu-id="b0e01-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="b0e01-131">第二部分使用`+=`与`String`变量以连接与另一个值。</span><span class="sxs-lookup"><span data-stu-id="b0e01-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="b0e01-132">在这两种情况下，结果被分配给第一个变量。</span><span class="sxs-lookup"><span data-stu-id="b0e01-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_1.vb)]  
  
 [!code-vb[VbVbalrOperators#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_2.vb)]  
  
 <span data-ttu-id="b0e01-133">值`num1`13 和的值现在是`str1`现在是"103"。</span><span class="sxs-lookup"><span data-stu-id="b0e01-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e01-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0e01-134">See Also</span></span>  
 [<span data-ttu-id="b0e01-135">+ 运算符</span><span class="sxs-lookup"><span data-stu-id="b0e01-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)  
 [<span data-ttu-id="b0e01-136">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="b0e01-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="b0e01-137">算术运算符</span><span class="sxs-lookup"><span data-stu-id="b0e01-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="b0e01-138">串联运算符</span><span class="sxs-lookup"><span data-stu-id="b0e01-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="b0e01-139">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="b0e01-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="b0e01-140">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="b0e01-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="b0e01-141">语句</span><span class="sxs-lookup"><span data-stu-id="b0e01-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
