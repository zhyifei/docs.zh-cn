---
title: '\= 运算符'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 4ebbf2eca7fb3cd208d979d7f3c77aa106569119
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="-operator"></a><span data-ttu-id="6a349-102">\\= 运算符</span><span class="sxs-lookup"><span data-stu-id="6a349-102">\\= Operator</span></span>
<span data-ttu-id="6a349-103">除以表达式值的变量或属性的值并将整数结果赋给该变量或属性。</span><span class="sxs-lookup"><span data-stu-id="6a349-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a349-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a349-104">Syntax</span></span>  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="6a349-105">部件</span><span class="sxs-lookup"><span data-stu-id="6a349-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="6a349-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="6a349-106">Required.</span></span> <span data-ttu-id="6a349-107">任何数值变量或属性。</span><span class="sxs-lookup"><span data-stu-id="6a349-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="6a349-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="6a349-108">Required.</span></span> <span data-ttu-id="6a349-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="6a349-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a349-110">备注</span><span class="sxs-lookup"><span data-stu-id="6a349-110">Remarks</span></span>  
 <span data-ttu-id="6a349-111">在左侧的元素`\=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="6a349-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="6a349-112">变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="6a349-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="6a349-113">`\=`运算符除以右侧，值的变量或与其左侧的属性的值，并将整数结果赋给该变量或与其左侧的属性</span><span class="sxs-lookup"><span data-stu-id="6a349-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="6a349-114">整除的进一步信息，请参阅[\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="6a349-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="6a349-115">重载</span><span class="sxs-lookup"><span data-stu-id="6a349-115">Overloading</span></span>  
 <span data-ttu-id="6a349-116">`\`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="6a349-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="6a349-117">重载`\`运算符会影响的行为`\=`运算符。</span><span class="sxs-lookup"><span data-stu-id="6a349-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="6a349-118">如果你的代码使用`\=`对类或重载的结构`\`，确保你理解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="6a349-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="6a349-119">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="6a349-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a349-120">示例</span><span class="sxs-lookup"><span data-stu-id="6a349-120">Example</span></span>  
 <span data-ttu-id="6a349-121">下面的示例使用`\=`运算符将一个`Integer`变量中的第二个和分配给第一个变量的整数结果。</span><span class="sxs-lookup"><span data-stu-id="6a349-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](codesnippet/VisualBasic/integer-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6a349-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a349-122">See Also</span></span>  
 [<span data-ttu-id="6a349-123">\ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a349-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [<span data-ttu-id="6a349-124">/ = 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a349-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="6a349-125">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="6a349-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="6a349-126">算术运算符</span><span class="sxs-lookup"><span data-stu-id="6a349-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="6a349-127">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="6a349-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="6a349-128">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="6a349-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="6a349-129">语句</span><span class="sxs-lookup"><span data-stu-id="6a349-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
