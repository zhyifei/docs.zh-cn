---
title: '*= 运算符 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 7c009a6b3acfe1528a2c34ed1e10735ac86507e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032125"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="aa577-102">\*= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa577-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="aa577-103">将表达式的值的变量或属性的值相乘并将结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="aa577-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa577-104">语法</span><span class="sxs-lookup"><span data-stu-id="aa577-104">Syntax</span></span>  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="aa577-105">部件</span><span class="sxs-lookup"><span data-stu-id="aa577-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="aa577-106">必需。</span><span class="sxs-lookup"><span data-stu-id="aa577-106">Required.</span></span> <span data-ttu-id="aa577-107">任何数值变量或属性。</span><span class="sxs-lookup"><span data-stu-id="aa577-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="aa577-108">必需。</span><span class="sxs-lookup"><span data-stu-id="aa577-108">Required.</span></span> <span data-ttu-id="aa577-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="aa577-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa577-110">备注</span><span class="sxs-lookup"><span data-stu-id="aa577-110">Remarks</span></span>  
 <span data-ttu-id="aa577-111">在左侧和右侧的元素`*=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="aa577-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="aa577-112">变量或属性不能[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="aa577-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="aa577-113">`*=`运算符首先用变量或属性 （在运算符的左侧） 的值乘以 （运算符右侧） 的表达式的值。</span><span class="sxs-lookup"><span data-stu-id="aa577-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="aa577-114">然后，运算符将该操作的结果分配给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="aa577-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="aa577-115">重载</span><span class="sxs-lookup"><span data-stu-id="aa577-115">Overloading</span></span>  
 <span data-ttu-id="aa577-116">[\* 运算符](../../../visual-basic/language-reference/operators/multiplication-operator.md)可以是*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="aa577-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="aa577-117">重载`*`运算符会影响的行为`*=`运算符。</span><span class="sxs-lookup"><span data-stu-id="aa577-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="aa577-118">如果你的代码使用`*=`上类或结构的重载`*`，确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="aa577-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="aa577-119">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="aa577-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa577-120">示例</span><span class="sxs-lookup"><span data-stu-id="aa577-120">Example</span></span>  
 <span data-ttu-id="aa577-121">下面的示例使用`*=`运算符将一个`Integer`变量通过第二个并将结果赋给第一个变量。</span><span class="sxs-lookup"><span data-stu-id="aa577-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="aa577-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa577-122">See also</span></span>

- [<span data-ttu-id="aa577-123">\* 运算符</span><span class="sxs-lookup"><span data-stu-id="aa577-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [<span data-ttu-id="aa577-124">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="aa577-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="aa577-125">算术运算符</span><span class="sxs-lookup"><span data-stu-id="aa577-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="aa577-126">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="aa577-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="aa577-127">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="aa577-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="aa577-128">语句</span><span class="sxs-lookup"><span data-stu-id="aa577-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
