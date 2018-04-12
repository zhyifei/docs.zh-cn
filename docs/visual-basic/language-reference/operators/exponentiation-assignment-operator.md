---
title: ^= 运算符 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fa9d87d2f090a8c18aaab742e73878c7b80f55c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="166c6-102">^= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="166c6-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="166c6-103">引发的变量或表达式的次幂的属性的值，并将结果赋回给该变量或属性。</span><span class="sxs-lookup"><span data-stu-id="166c6-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="166c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="166c6-104">Syntax</span></span>  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="166c6-105">部件</span><span class="sxs-lookup"><span data-stu-id="166c6-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="166c6-106">必需。</span><span class="sxs-lookup"><span data-stu-id="166c6-106">Required.</span></span> <span data-ttu-id="166c6-107">任何数值变量或属性。</span><span class="sxs-lookup"><span data-stu-id="166c6-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="166c6-108">必需。</span><span class="sxs-lookup"><span data-stu-id="166c6-108">Required.</span></span> <span data-ttu-id="166c6-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="166c6-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="166c6-110">备注</span><span class="sxs-lookup"><span data-stu-id="166c6-110">Remarks</span></span>  
 <span data-ttu-id="166c6-111">在左侧的元素`^=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="166c6-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="166c6-112">变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="166c6-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="166c6-113">`^=`运算符首先引发 （运算符右侧） 表达式的值的幂的值的变量或属性 （该运算符左侧）。</span><span class="sxs-lookup"><span data-stu-id="166c6-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="166c6-114">然后，运算符将该操作的结果赋回给该变量或属性。</span><span class="sxs-lookup"><span data-stu-id="166c6-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="166c6-115">Visual Basic 始终执行求幂中的[Double 数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="166c6-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="166c6-116">任何其他类型的操作数将转换为`Double`，并且结果始终为`Double`。</span><span class="sxs-lookup"><span data-stu-id="166c6-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="166c6-117">值`expression`可以是小数，负的、 和/或文件名。</span><span class="sxs-lookup"><span data-stu-id="166c6-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="166c6-118">重载</span><span class="sxs-lookup"><span data-stu-id="166c6-118">Overloading</span></span>  
 <span data-ttu-id="166c6-119">[^ 运算符](../../../visual-basic/language-reference/operators/exponentiation-operator.md)可以是*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="166c6-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="166c6-120">重载`^`运算符会影响的行为`^=`运算符。</span><span class="sxs-lookup"><span data-stu-id="166c6-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="166c6-121">如果你的代码使用`^=`对类或重载的结构`^`，确保你理解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="166c6-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="166c6-122">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="166c6-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="166c6-123">示例</span><span class="sxs-lookup"><span data-stu-id="166c6-123">Example</span></span>  
 <span data-ttu-id="166c6-124">下面的示例使用`^=`运算符来引发的一个值`Integer`变量的第二个变量中，并将结果赋给第一个变量次幂。</span><span class="sxs-lookup"><span data-stu-id="166c6-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="166c6-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="166c6-125">See Also</span></span>  
 [<span data-ttu-id="166c6-126">^ 运算符</span><span class="sxs-lookup"><span data-stu-id="166c6-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)  
 [<span data-ttu-id="166c6-127">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="166c6-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="166c6-128">算术运算符</span><span class="sxs-lookup"><span data-stu-id="166c6-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="166c6-129">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="166c6-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="166c6-130">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="166c6-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="166c6-131">语句</span><span class="sxs-lookup"><span data-stu-id="166c6-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
