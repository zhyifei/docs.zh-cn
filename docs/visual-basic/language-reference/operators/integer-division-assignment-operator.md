---
title: '\= 运算符 (Visual Basic)'
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
ms.openlocfilehash: 377a14a76f67e938f24c973b5946abd63f851bfd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842533"
---
# <a name="-operator"></a><span data-ttu-id="2fd2b-102">\\= 运算符</span><span class="sxs-lookup"><span data-stu-id="2fd2b-102">\\= Operator</span></span>
<span data-ttu-id="2fd2b-103">将表达式的值的变量或属性的值除以并将整数结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="2fd2b-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fd2b-104">语法</span><span class="sxs-lookup"><span data-stu-id="2fd2b-104">Syntax</span></span>  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="2fd2b-105">部件</span><span class="sxs-lookup"><span data-stu-id="2fd2b-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="2fd2b-106">必需。</span><span class="sxs-lookup"><span data-stu-id="2fd2b-106">Required.</span></span> <span data-ttu-id="2fd2b-107">任何数值变量或属性。</span><span class="sxs-lookup"><span data-stu-id="2fd2b-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="2fd2b-108">必需。</span><span class="sxs-lookup"><span data-stu-id="2fd2b-108">Required.</span></span> <span data-ttu-id="2fd2b-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="2fd2b-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fd2b-110">备注</span><span class="sxs-lookup"><span data-stu-id="2fd2b-110">Remarks</span></span>  
 <span data-ttu-id="2fd2b-111">在左侧和右侧的元素`\=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="2fd2b-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="2fd2b-112">变量或属性不能[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd2b-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="2fd2b-113">`\=`运算符将在其右侧的值的变量或在其左侧的属性值除以并将整数结果赋给变量或在其左侧的属性</span><span class="sxs-lookup"><span data-stu-id="2fd2b-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="2fd2b-114">整数除法的详细信息，请参阅[\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd2b-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="2fd2b-115">重载</span><span class="sxs-lookup"><span data-stu-id="2fd2b-115">Overloading</span></span>  
 <span data-ttu-id="2fd2b-116">`\`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="2fd2b-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="2fd2b-117">重载`\`运算符会影响的行为`\=`运算符。</span><span class="sxs-lookup"><span data-stu-id="2fd2b-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="2fd2b-118">如果你的代码使用`\=`上类或结构的重载`\`，确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="2fd2b-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="2fd2b-119">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd2b-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fd2b-120">示例</span><span class="sxs-lookup"><span data-stu-id="2fd2b-120">Example</span></span>  
 <span data-ttu-id="2fd2b-121">下面的示例使用`\=`运算符将一个`Integer`通过第二个和整数结果到第一个变量分配变量。</span><span class="sxs-lookup"><span data-stu-id="2fd2b-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="2fd2b-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fd2b-122">See also</span></span>

- [<span data-ttu-id="2fd2b-123">\ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="2fd2b-124">/ = 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="2fd2b-125">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="2fd2b-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="2fd2b-126">算术运算符</span><span class="sxs-lookup"><span data-stu-id="2fd2b-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="2fd2b-127">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="2fd2b-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="2fd2b-128">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="2fd2b-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="2fd2b-129">语句</span><span class="sxs-lookup"><span data-stu-id="2fd2b-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
