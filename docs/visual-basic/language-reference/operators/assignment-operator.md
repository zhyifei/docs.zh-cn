---
title: = 运算符 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 230005640b2b494e5413b14ba13a7cb82ee9f22b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ffd4a-102">= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffd4a-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="ffd4a-103">将值分配给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="ffd4a-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffd4a-104">语法</span><span class="sxs-lookup"><span data-stu-id="ffd4a-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="ffd4a-105">部件</span><span class="sxs-lookup"><span data-stu-id="ffd4a-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="ffd4a-106">任何可写的变量或任何属性。</span><span class="sxs-lookup"><span data-stu-id="ffd4a-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="ffd4a-107">任何文本、 常量或表达式。</span><span class="sxs-lookup"><span data-stu-id="ffd4a-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffd4a-108">备注</span><span class="sxs-lookup"><span data-stu-id="ffd4a-108">Remarks</span></span>  
 <span data-ttu-id="ffd4a-109">等号左侧的元素 (`=`) 可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="ffd4a-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="ffd4a-110">变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="ffd4a-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="ffd4a-111">`=`运算符将值赋给变量右侧的值或与其左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="ffd4a-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffd4a-112">`=`运算符也用作比较运算符。</span><span class="sxs-lookup"><span data-stu-id="ffd4a-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="ffd4a-113">有关详细信息，请参阅[比较运算符](../../../visual-basic/language-reference/operators/comparison-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="ffd4a-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ffd4a-114">重载</span><span class="sxs-lookup"><span data-stu-id="ffd4a-114">Overloading</span></span>  
 <span data-ttu-id="ffd4a-115">`=`仅为关系的比较运算符，而不是赋值运算符可以重载运算符。</span><span class="sxs-lookup"><span data-stu-id="ffd4a-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="ffd4a-116">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="ffd4a-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffd4a-117">示例</span><span class="sxs-lookup"><span data-stu-id="ffd4a-117">Example</span></span>  
 <span data-ttu-id="ffd4a-118">下面的示例演示赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="ffd4a-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="ffd4a-119">在右侧的值分配给左侧的变量。</span><span class="sxs-lookup"><span data-stu-id="ffd4a-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ffd4a-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffd4a-120">See Also</span></span>  
 [<span data-ttu-id="ffd4a-121">&= 运算符</span><span class="sxs-lookup"><span data-stu-id="ffd4a-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="ffd4a-122">\*= 运算符</span><span class="sxs-lookup"><span data-stu-id="ffd4a-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [<span data-ttu-id="ffd4a-123">+= 运算符</span><span class="sxs-lookup"><span data-stu-id="ffd4a-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [<span data-ttu-id="ffd4a-124">-= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffd4a-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)  
 [<span data-ttu-id="ffd4a-125">/ = 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffd4a-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="ffd4a-126">\\= 运算符</span><span class="sxs-lookup"><span data-stu-id="ffd4a-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="ffd4a-127">^= 运算符</span><span class="sxs-lookup"><span data-stu-id="ffd4a-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [<span data-ttu-id="ffd4a-128">语句</span><span class="sxs-lookup"><span data-stu-id="ffd4a-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="ffd4a-129">比较运算符</span><span class="sxs-lookup"><span data-stu-id="ffd4a-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="ffd4a-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="ffd4a-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [<span data-ttu-id="ffd4a-131">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="ffd4a-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
