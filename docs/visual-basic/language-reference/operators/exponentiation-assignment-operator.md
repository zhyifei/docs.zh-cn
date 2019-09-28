---
title: ^= 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: 382e0b27c2dbf27e5acccf29f1b8d2b002cb6664
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592224"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ed92a-102">^= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed92a-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="ed92a-103">将变量或属性的值提升为表达式的幂，并将结果赋回给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="ed92a-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed92a-104">语法</span><span class="sxs-lookup"><span data-stu-id="ed92a-104">Syntax</span></span>  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="ed92a-105">部件</span><span class="sxs-lookup"><span data-stu-id="ed92a-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="ed92a-106">必需。</span><span class="sxs-lookup"><span data-stu-id="ed92a-106">Required.</span></span> <span data-ttu-id="ed92a-107">任何数值变量或属性。</span><span class="sxs-lookup"><span data-stu-id="ed92a-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="ed92a-108">必需。</span><span class="sxs-lookup"><span data-stu-id="ed92a-108">Required.</span></span> <span data-ttu-id="ed92a-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="ed92a-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed92a-110">备注</span><span class="sxs-lookup"><span data-stu-id="ed92a-110">Remarks</span></span>  
 <span data-ttu-id="ed92a-111">@No__t-0 运算符左侧的元素可以是简单的标量变量、属性或数组元素。</span><span class="sxs-lookup"><span data-stu-id="ed92a-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="ed92a-112">变量或属性不能是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的。</span><span class="sxs-lookup"><span data-stu-id="ed92a-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="ed92a-113">@No__t-0 运算符首先引发变量或属性（位于运算符左侧）的值，以使表达式的值（在运算符的右侧）的值的幂。</span><span class="sxs-lookup"><span data-stu-id="ed92a-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="ed92a-114">然后，运算符将该操作的结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="ed92a-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="ed92a-115">Visual Basic 总是对[Double 数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)执行幂运算。</span><span class="sxs-lookup"><span data-stu-id="ed92a-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="ed92a-116">任何不同类型的操作数都将转换为 `Double`，并且结果始终 @no__t 为-1。</span><span class="sxs-lookup"><span data-stu-id="ed92a-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="ed92a-117">@No__t-0 的值可以是小数、负数或同时为两者。</span><span class="sxs-lookup"><span data-stu-id="ed92a-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ed92a-118">重载</span><span class="sxs-lookup"><span data-stu-id="ed92a-118">Overloading</span></span>  
 <span data-ttu-id="ed92a-119">[^ 运算符](../../../visual-basic/language-reference/operators/exponentiation-operator.md)可*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="ed92a-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ed92a-120">重载 `^` 运算符会影响 @no__t 1 运算符的行为。</span><span class="sxs-lookup"><span data-stu-id="ed92a-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="ed92a-121">如果你的代码在重载 @no__t 的类或结构上使用 `^=`，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="ed92a-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ed92a-122">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="ed92a-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed92a-123">示例</span><span class="sxs-lookup"><span data-stu-id="ed92a-123">Example</span></span>  
 <span data-ttu-id="ed92a-124">下面的示例使用 `^=` 运算符将一个 @no__t 变量的值提升为第二个变量的幂，并将结果赋给第一个变量。</span><span class="sxs-lookup"><span data-stu-id="ed92a-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="ed92a-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed92a-125">See also</span></span>

- [<span data-ttu-id="ed92a-126">^ 运算符</span><span class="sxs-lookup"><span data-stu-id="ed92a-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [<span data-ttu-id="ed92a-127">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="ed92a-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="ed92a-128">算术运算符</span><span class="sxs-lookup"><span data-stu-id="ed92a-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="ed92a-129">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="ed92a-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="ed92a-130">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="ed92a-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="ed92a-131">语句</span><span class="sxs-lookup"><span data-stu-id="ed92a-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
