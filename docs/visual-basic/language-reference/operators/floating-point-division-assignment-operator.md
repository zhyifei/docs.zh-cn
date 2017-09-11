---
title: "/ = 运算符 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./=
dev_langs:
- VB
helpviewer_keywords:
- assignment statements, compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e877e98104b5c9fd679485b50a88943fac80a696
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---
# <a name="-operator-visual-basic"></a><span data-ttu-id="c084a-102">/= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c084a-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="c084a-103">除以表达式值的变量或属性的值并将浮点型结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="c084a-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c084a-104">语法</span><span class="sxs-lookup"><span data-stu-id="c084a-104">Syntax</span></span>  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="c084a-105">部件</span><span class="sxs-lookup"><span data-stu-id="c084a-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="c084a-106">必需。</span><span class="sxs-lookup"><span data-stu-id="c084a-106">Required.</span></span> <span data-ttu-id="c084a-107">任何数值变量或属性。</span><span class="sxs-lookup"><span data-stu-id="c084a-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="c084a-108">必需。</span><span class="sxs-lookup"><span data-stu-id="c084a-108">Required.</span></span> <span data-ttu-id="c084a-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="c084a-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c084a-110">备注</span><span class="sxs-lookup"><span data-stu-id="c084a-110">Remarks</span></span>  
 <span data-ttu-id="c084a-111">在左侧元素`/=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="c084a-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="c084a-112">该变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="c084a-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="c084a-113">`/=`运算符首先将该变量或属性 （该运算符左侧） 值除以 （对该运算符的右侧） 的表达式的值。</span><span class="sxs-lookup"><span data-stu-id="c084a-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="c084a-114">该运算符会将该操作的浮点型结果分配给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="c084a-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="c084a-115">该语句将`Double`给变量或在左侧的属性的值。</span><span class="sxs-lookup"><span data-stu-id="c084a-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="c084a-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span><span class="sxs-lookup"><span data-stu-id="c084a-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="c084a-117">如果`Option Strict`是`Off`，Visual Basic 执行隐式转换和生成将值分配给`variableorproperty`，并可能在运行时错误。</span><span class="sxs-lookup"><span data-stu-id="c084a-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="c084a-118">有关详细信息，请参阅[扩大和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)和[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="c084a-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c084a-119">重载</span><span class="sxs-lookup"><span data-stu-id="c084a-119">Overloading</span></span>  
 <span data-ttu-id="c084a-120">[/ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)可以是*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="c084a-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c084a-121">重载`/`运算符影响的应用程序行为`/=`运算符。</span><span class="sxs-lookup"><span data-stu-id="c084a-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="c084a-122">如果您的代码使用`/=`对类或结构，它重载`/`，请确保您了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="c084a-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c084a-123">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="c084a-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c084a-124">示例</span><span class="sxs-lookup"><span data-stu-id="c084a-124">Example</span></span>  
 <span data-ttu-id="c084a-125">下面的示例使用`/=`运算符将一个`Integer`变量中的第二个和分配给第一个变量的商。</span><span class="sxs-lookup"><span data-stu-id="c084a-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 <span data-ttu-id="c084a-126">[!code-vb[VbVbalrOperators #&17;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c084a-126">[!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c084a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c084a-127">See Also</span></span>  
 <span data-ttu-id="c084a-128">[/ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) </span><span class="sxs-lookup"><span data-stu-id="c084a-128">[/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) </span></span>  
<span data-ttu-id="c084a-129"> [\\= 运算符](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="c084a-129"> [\\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span></span>  
<span data-ttu-id="c084a-130"> [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md) </span><span class="sxs-lookup"><span data-stu-id="c084a-130"> [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md) </span></span>  
<span data-ttu-id="c084a-131"> [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="c084a-131"> [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="c084a-132"> [在 Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="c084a-132"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="c084a-133"> [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="c084a-133"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="c084a-134"> [语句](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="c084a-134"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>

