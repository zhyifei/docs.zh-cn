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
ms.openlocfilehash: b4855e8270a329f9345339060a323b5ca9cd9792
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592179"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="90119-102">/= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90119-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="90119-103">将变量或属性的值除以表达式的值，并将浮点结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="90119-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90119-104">语法</span><span class="sxs-lookup"><span data-stu-id="90119-104">Syntax</span></span>  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="90119-105">部件</span><span class="sxs-lookup"><span data-stu-id="90119-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="90119-106">必需。</span><span class="sxs-lookup"><span data-stu-id="90119-106">Required.</span></span> <span data-ttu-id="90119-107">任何数值变量或属性。</span><span class="sxs-lookup"><span data-stu-id="90119-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="90119-108">必需。</span><span class="sxs-lookup"><span data-stu-id="90119-108">Required.</span></span> <span data-ttu-id="90119-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="90119-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90119-110">备注</span><span class="sxs-lookup"><span data-stu-id="90119-110">Remarks</span></span>  
 <span data-ttu-id="90119-111">@No__t-0 运算符左侧的元素可以是简单的标量变量、属性或数组元素。</span><span class="sxs-lookup"><span data-stu-id="90119-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="90119-112">变量或属性不能是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的。</span><span class="sxs-lookup"><span data-stu-id="90119-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="90119-113">@No__t-0 运算符首先将变量或属性（位于运算符左侧）的值除以表达式的值（在运算符的右侧），这是一个值。</span><span class="sxs-lookup"><span data-stu-id="90119-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="90119-114">然后，运算符将该操作的浮点结果分配给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="90119-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="90119-115">此语句将 @no__t 0 值分配给左侧的变量或属性。</span><span class="sxs-lookup"><span data-stu-id="90119-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="90119-116">如果 `Option Strict` @no__t 为-1，则 `variableorproperty` 必须 @no__t 为3。</span><span class="sxs-lookup"><span data-stu-id="90119-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="90119-117">如果 `Option Strict` @no__t 为-1，Visual Basic 将执行隐式转换，并将生成的值分配给 `variableorproperty`，在运行时可能会出现错误。</span><span class="sxs-lookup"><span data-stu-id="90119-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="90119-118">有关详细信息，请参阅[扩大和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)和[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90119-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="90119-119">重载</span><span class="sxs-lookup"><span data-stu-id="90119-119">Overloading</span></span>  
 <span data-ttu-id="90119-120">[/运算符（Visual Basic）](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)可以*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="90119-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="90119-121">重载 `/` 运算符会影响 @no__t 1 运算符的行为。</span><span class="sxs-lookup"><span data-stu-id="90119-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="90119-122">如果你的代码在重载 @no__t 的类或结构上使用 `/=`，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="90119-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="90119-123">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="90119-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="90119-124">示例</span><span class="sxs-lookup"><span data-stu-id="90119-124">Example</span></span>  
 <span data-ttu-id="90119-125">下面的示例使用 `/=` 运算符将一个 @no__t 1 变量除以第二个变量，并将商分配给第一个变量。</span><span class="sxs-lookup"><span data-stu-id="90119-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="90119-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="90119-126">See also</span></span>

- [<span data-ttu-id="90119-127">/运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="90119-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="90119-128">\\ = 运算符</span><span class="sxs-lookup"><span data-stu-id="90119-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="90119-129">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="90119-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="90119-130">算术运算符</span><span class="sxs-lookup"><span data-stu-id="90119-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="90119-131">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="90119-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="90119-132">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="90119-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="90119-133">语句</span><span class="sxs-lookup"><span data-stu-id="90119-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
