---
title: "-= 运算符 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.-=
dev_langs:
- VB
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements, compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
caps.latest.revision: 19
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
ms.openlocfilehash: 694033ec89e32b5fdba4092bd60292af536f58dd
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---
# <a name="--operator-visual-basic"></a><span data-ttu-id="92d20-102">-= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92d20-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="92d20-103">减去表达式的值的变量或属性的值并将结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="92d20-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92d20-104">语法</span><span class="sxs-lookup"><span data-stu-id="92d20-104">Syntax</span></span>  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="92d20-105">部件</span><span class="sxs-lookup"><span data-stu-id="92d20-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="92d20-106">必需。</span><span class="sxs-lookup"><span data-stu-id="92d20-106">Required.</span></span> <span data-ttu-id="92d20-107">任何数值变量或属性。</span><span class="sxs-lookup"><span data-stu-id="92d20-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="92d20-108">必需。</span><span class="sxs-lookup"><span data-stu-id="92d20-108">Required.</span></span> <span data-ttu-id="92d20-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="92d20-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92d20-110">备注</span><span class="sxs-lookup"><span data-stu-id="92d20-110">Remarks</span></span>  
 <span data-ttu-id="92d20-111">在左侧元素`-=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="92d20-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="92d20-112">该变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="92d20-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="92d20-113">`-=`运算符第一次 （对该运算符的右侧） 的表达式的值将从中减去的值的变量或属性 （该运算符左侧）。</span><span class="sxs-lookup"><span data-stu-id="92d20-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="92d20-114">该运算符会将该操作的结果分配给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="92d20-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="92d20-115">重载</span><span class="sxs-lookup"><span data-stu-id="92d20-115">Overloading</span></span>  
 <span data-ttu-id="92d20-116">[-运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md)可以是*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="92d20-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="92d20-117">重载`-`运算符影响的应用程序行为`-=`运算符。</span><span class="sxs-lookup"><span data-stu-id="92d20-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="92d20-118">如果您的代码使用`-=`对类或结构，它重载`-`，请确保您了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="92d20-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="92d20-119">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="92d20-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="92d20-120">示例</span><span class="sxs-lookup"><span data-stu-id="92d20-120">Example</span></span>  
 <span data-ttu-id="92d20-121">下面的示例使用`-=`运算符中减去&1;`Integer`从另一个变量并将结果赋给前一个变量。</span><span class="sxs-lookup"><span data-stu-id="92d20-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 <span data-ttu-id="92d20-122">[!code-vb[VbVbalrOperators #&11;](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="92d20-122">[!code-vb[VbVbalrOperators#11](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92d20-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92d20-123">See Also</span></span>  
 <span data-ttu-id="92d20-124">[-运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) </span><span class="sxs-lookup"><span data-stu-id="92d20-124">[- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) </span></span>  
<span data-ttu-id="92d20-125"> [赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md) </span><span class="sxs-lookup"><span data-stu-id="92d20-125"> [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md) </span></span>  
<span data-ttu-id="92d20-126"> [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="92d20-126"> [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="92d20-127"> [在 Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="92d20-127"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="92d20-128"> [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="92d20-128"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="92d20-129"> [语句](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="92d20-129"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>

