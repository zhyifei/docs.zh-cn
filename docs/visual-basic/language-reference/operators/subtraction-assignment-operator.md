---
title: -= 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: be1ff4f10f6b30d8448d2441ee3ad2c1e2f80e2d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58815896"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="3f98c-102">-= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f98c-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="3f98c-103">减去表达式的值的变量或属性的值，并将结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="3f98c-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f98c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f98c-104">Syntax</span></span>  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="3f98c-105">部件</span><span class="sxs-lookup"><span data-stu-id="3f98c-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="3f98c-106">必需。</span><span class="sxs-lookup"><span data-stu-id="3f98c-106">Required.</span></span> <span data-ttu-id="3f98c-107">任何数值变量或属性。</span><span class="sxs-lookup"><span data-stu-id="3f98c-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="3f98c-108">必需。</span><span class="sxs-lookup"><span data-stu-id="3f98c-108">Required.</span></span> <span data-ttu-id="3f98c-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="3f98c-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f98c-110">备注</span><span class="sxs-lookup"><span data-stu-id="3f98c-110">Remarks</span></span>  
 <span data-ttu-id="3f98c-111">在左侧和右侧的元素`-=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="3f98c-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="3f98c-112">变量或属性不能[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="3f98c-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="3f98c-113">`-=`运算符第一次 （对运算符的右侧） 的表达式的值从值中减去的变量或属性 （在运算符的左侧）。</span><span class="sxs-lookup"><span data-stu-id="3f98c-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="3f98c-114">然后，运算符将该操作的结果分配给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="3f98c-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="3f98c-115">重载</span><span class="sxs-lookup"><span data-stu-id="3f98c-115">Overloading</span></span>  
 <span data-ttu-id="3f98c-116">[-运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md)可以是*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="3f98c-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="3f98c-117">重载`-`运算符会影响的行为`-=`运算符。</span><span class="sxs-lookup"><span data-stu-id="3f98c-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="3f98c-118">如果你的代码使用`-=`上类或结构的重载`-`，确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="3f98c-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="3f98c-119">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="3f98c-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f98c-120">示例</span><span class="sxs-lookup"><span data-stu-id="3f98c-120">Example</span></span>  
 <span data-ttu-id="3f98c-121">下面的示例使用`-=`运算符中减去 1`Integer`从另一个变量并将结果发送到后一种变量赋值。</span><span class="sxs-lookup"><span data-stu-id="3f98c-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="3f98c-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f98c-122">See also</span></span>

- [<span data-ttu-id="3f98c-123">-运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f98c-123">- Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="3f98c-124">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="3f98c-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="3f98c-125">算术运算符</span><span class="sxs-lookup"><span data-stu-id="3f98c-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="3f98c-126">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="3f98c-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="3f98c-127">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="3f98c-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="3f98c-128">语句</span><span class="sxs-lookup"><span data-stu-id="3f98c-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
