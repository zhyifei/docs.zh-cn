---
title: = 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 5e6d34802f5f82373d0e8176f3b732a327c55d01
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56964989"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="41f63-102">= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41f63-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="41f63-103">将值分配给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="41f63-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41f63-104">语法</span><span class="sxs-lookup"><span data-stu-id="41f63-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="41f63-105">部件</span><span class="sxs-lookup"><span data-stu-id="41f63-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="41f63-106">任何可写的变量或任何属性。</span><span class="sxs-lookup"><span data-stu-id="41f63-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="41f63-107">任何文本、 常量或表达式。</span><span class="sxs-lookup"><span data-stu-id="41f63-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41f63-108">备注</span><span class="sxs-lookup"><span data-stu-id="41f63-108">Remarks</span></span>  
 <span data-ttu-id="41f63-109">在等号左侧的元素 (`=`) 可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="41f63-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="41f63-110">变量或属性不能[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="41f63-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="41f63-111">`=`运算符将值赋给变量其右侧的值或在其左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="41f63-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41f63-112">`=`运算符还用作比较运算符。</span><span class="sxs-lookup"><span data-stu-id="41f63-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="41f63-113">有关详细信息，请参阅[比较运算符](../../../visual-basic/language-reference/operators/comparison-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="41f63-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="41f63-114">重载</span><span class="sxs-lookup"><span data-stu-id="41f63-114">Overloading</span></span>  
 <span data-ttu-id="41f63-115">`=`仅作为关系比较运算符，而不是赋值运算符可重载运算符。</span><span class="sxs-lookup"><span data-stu-id="41f63-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="41f63-116">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="41f63-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="41f63-117">示例</span><span class="sxs-lookup"><span data-stu-id="41f63-117">Example</span></span>  
 <span data-ttu-id="41f63-118">下面的示例演示赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="41f63-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="41f63-119">在右侧的值分配给左侧变量。</span><span class="sxs-lookup"><span data-stu-id="41f63-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="41f63-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="41f63-120">See also</span></span>
- [<span data-ttu-id="41f63-121">&= 运算符</span><span class="sxs-lookup"><span data-stu-id="41f63-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="41f63-122">\*= 运算符</span><span class="sxs-lookup"><span data-stu-id="41f63-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="41f63-123">+= 运算符</span><span class="sxs-lookup"><span data-stu-id="41f63-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="41f63-124">-= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41f63-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="41f63-125">/ = 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41f63-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="41f63-126">\\= 运算符</span><span class="sxs-lookup"><span data-stu-id="41f63-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="41f63-127">^= 运算符</span><span class="sxs-lookup"><span data-stu-id="41f63-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="41f63-128">语句</span><span class="sxs-lookup"><span data-stu-id="41f63-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="41f63-129">比较运算符</span><span class="sxs-lookup"><span data-stu-id="41f63-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="41f63-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="41f63-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="41f63-131">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="41f63-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
