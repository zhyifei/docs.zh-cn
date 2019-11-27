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
ms.openlocfilehash: 600acf9b41b63358da245fe602595fee4093b15b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330941"
---
# <a name="-operator"></a><span data-ttu-id="02086-102">\\= 运算符</span><span class="sxs-lookup"><span data-stu-id="02086-102">\\= Operator</span></span>
<span data-ttu-id="02086-103">将变量或属性的值除以表达式的值，并将整数结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="02086-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02086-104">语法</span><span class="sxs-lookup"><span data-stu-id="02086-104">Syntax</span></span>  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="02086-105">部件</span><span class="sxs-lookup"><span data-stu-id="02086-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="02086-106">必需。</span><span class="sxs-lookup"><span data-stu-id="02086-106">Required.</span></span> <span data-ttu-id="02086-107">任何数值变量或属性。</span><span class="sxs-lookup"><span data-stu-id="02086-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="02086-108">必需。</span><span class="sxs-lookup"><span data-stu-id="02086-108">Required.</span></span> <span data-ttu-id="02086-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="02086-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02086-110">备注</span><span class="sxs-lookup"><span data-stu-id="02086-110">Remarks</span></span>  
 <span data-ttu-id="02086-111">`\=` 运算符左侧的元素可以是简单的标量变量、属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="02086-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="02086-112">变量或属性不能是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的。</span><span class="sxs-lookup"><span data-stu-id="02086-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="02086-113">`\=` 运算符将变量或属性的值除以其右侧的值，并将整数结果分配给其左侧的变量或属性</span><span class="sxs-lookup"><span data-stu-id="02086-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="02086-114">有关整数除法的详细信息，请参阅[\ 运算符（Visual Basic）](../../../visual-basic/language-reference/operators/integer-division-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="02086-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="02086-115">重载</span><span class="sxs-lookup"><span data-stu-id="02086-115">Overloading</span></span>  
 <span data-ttu-id="02086-116">可以*重载*`\` 运算符，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="02086-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="02086-117">重载 `\` 运算符会影响 `\=` 运算符的行为。</span><span class="sxs-lookup"><span data-stu-id="02086-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="02086-118">如果你的代码在重载 `\`的类或结构上使用 `\=`，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="02086-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="02086-119">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="02086-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02086-120">示例</span><span class="sxs-lookup"><span data-stu-id="02086-120">Example</span></span>  
 <span data-ttu-id="02086-121">下面的示例使用 `\=` 运算符将一个 `Integer` 变量除以第二个变量，并将整数结果赋给第一个变量。</span><span class="sxs-lookup"><span data-stu-id="02086-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="02086-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02086-122">See also</span></span>

- [<span data-ttu-id="02086-123">\ 运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="02086-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="02086-124">/= 运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="02086-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="02086-125">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="02086-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="02086-126">算术运算符</span><span class="sxs-lookup"><span data-stu-id="02086-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="02086-127">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="02086-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="02086-128">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="02086-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="02086-129">语句</span><span class="sxs-lookup"><span data-stu-id="02086-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
