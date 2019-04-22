---
title: /= 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: d9d3fa021654d3be1b9d304beb83caa737660264
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813985"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="b8718-102">/= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8718-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="b8718-103">将表达式的值的变量或属性的值除以并将浮点结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="b8718-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8718-104">语法</span><span class="sxs-lookup"><span data-stu-id="b8718-104">Syntax</span></span>  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b8718-105">部件</span><span class="sxs-lookup"><span data-stu-id="b8718-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="b8718-106">必需。</span><span class="sxs-lookup"><span data-stu-id="b8718-106">Required.</span></span> <span data-ttu-id="b8718-107">任何数值变量或属性。</span><span class="sxs-lookup"><span data-stu-id="b8718-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="b8718-108">必需。</span><span class="sxs-lookup"><span data-stu-id="b8718-108">Required.</span></span> <span data-ttu-id="b8718-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="b8718-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8718-110">备注</span><span class="sxs-lookup"><span data-stu-id="b8718-110">Remarks</span></span>  
 <span data-ttu-id="b8718-111">在左侧和右侧的元素`/=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="b8718-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="b8718-112">变量或属性不能[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="b8718-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="b8718-113">`/=`运算符首先将变量或属性 （在运算符的左侧） 的值除以 （对运算符的右侧） 的表达式的值。</span><span class="sxs-lookup"><span data-stu-id="b8718-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="b8718-114">然后，该运算符将浮点运算的结果分配给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="b8718-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="b8718-115">此语句将分配`Double`给变量或在左侧的属性的值。</span><span class="sxs-lookup"><span data-stu-id="b8718-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="b8718-116">如果`Option Strict`是`On`，`variableorproperty`必须是`Double`。</span><span class="sxs-lookup"><span data-stu-id="b8718-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="b8718-117">如果`Option Strict`是`Off`，Visual Basic 执行的隐式转换和分配结果值输出到`variableorproperty`，可以在运行时错误。</span><span class="sxs-lookup"><span data-stu-id="b8718-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="b8718-118">有关详细信息，请参阅[Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)并[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="b8718-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b8718-119">重载</span><span class="sxs-lookup"><span data-stu-id="b8718-119">Overloading</span></span>  
 <span data-ttu-id="b8718-120">[/ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)可以是*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="b8718-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b8718-121">重载`/`运算符会影响的行为`/=`运算符。</span><span class="sxs-lookup"><span data-stu-id="b8718-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="b8718-122">如果你的代码使用`/=`上类或结构的重载`/`，确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="b8718-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b8718-123">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="b8718-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8718-124">示例</span><span class="sxs-lookup"><span data-stu-id="b8718-124">Example</span></span>  
 <span data-ttu-id="b8718-125">下面的示例使用`/=`运算符将一个`Integer`变量的第二个和分配给第一个变量的商。</span><span class="sxs-lookup"><span data-stu-id="b8718-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="b8718-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8718-126">See also</span></span>

- [<span data-ttu-id="b8718-127">/ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8718-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="b8718-128">\\= 运算符</span><span class="sxs-lookup"><span data-stu-id="b8718-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="b8718-129">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="b8718-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="b8718-130">算术运算符</span><span class="sxs-lookup"><span data-stu-id="b8718-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="b8718-131">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="b8718-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b8718-132">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="b8718-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b8718-133">语句</span><span class="sxs-lookup"><span data-stu-id="b8718-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
