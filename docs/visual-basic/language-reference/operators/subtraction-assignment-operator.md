---
title: -= 运算符
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
ms.openlocfilehash: 44cb226d64e9f0b86c6566eb25fbafd6323a6d4c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347814"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="cfcf0-102">-= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfcf0-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="cfcf0-103">从变量或属性的值中减去表达式的值，并将结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfcf0-104">语法</span><span class="sxs-lookup"><span data-stu-id="cfcf0-104">Syntax</span></span>  
  
```vb  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="cfcf0-105">部件</span><span class="sxs-lookup"><span data-stu-id="cfcf0-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="cfcf0-106">必需。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-106">Required.</span></span> <span data-ttu-id="cfcf0-107">任何数值变量或属性。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="cfcf0-108">必需。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-108">Required.</span></span> <span data-ttu-id="cfcf0-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfcf0-110">备注</span><span class="sxs-lookup"><span data-stu-id="cfcf0-110">Remarks</span></span>  
 <span data-ttu-id="cfcf0-111">`-=` 运算符左侧的元素可以是简单的标量变量、属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="cfcf0-112">变量或属性不能是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="cfcf0-113">`-=` 运算符首先从变量或属性（位于运算符左侧）的值中减去该表达式的值（在运算符的右侧，该表达式的值）。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="cfcf0-114">然后，运算符将该操作的结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="cfcf0-115">重载</span><span class="sxs-lookup"><span data-stu-id="cfcf0-115">Overloading</span></span>  
 <span data-ttu-id="cfcf0-116">[-Operator （Visual Basic）](../../../visual-basic/language-reference/operators/subtraction-operator.md)可以*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="cfcf0-117">重载 `-` 运算符会影响 `-=` 运算符的行为。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="cfcf0-118">如果你的代码在重载 `-`的类或结构上使用 `-=`，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="cfcf0-119">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfcf0-120">示例</span><span class="sxs-lookup"><span data-stu-id="cfcf0-120">Example</span></span>  
 <span data-ttu-id="cfcf0-121">下面的示例使用 `-=` 运算符将一个 `Integer` 变量减去另一个，并将结果赋给后一个变量。</span><span class="sxs-lookup"><span data-stu-id="cfcf0-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="cfcf0-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfcf0-122">See also</span></span>

- [<span data-ttu-id="cfcf0-123">-Operator （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="cfcf0-123">- Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="cfcf0-124">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="cfcf0-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="cfcf0-125">算术运算符</span><span class="sxs-lookup"><span data-stu-id="cfcf0-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="cfcf0-126">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="cfcf0-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="cfcf0-127">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="cfcf0-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="cfcf0-128">语句</span><span class="sxs-lookup"><span data-stu-id="cfcf0-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
