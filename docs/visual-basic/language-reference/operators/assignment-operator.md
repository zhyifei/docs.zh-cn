---
title: "= 运算符 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assign
- vb.=
dev_langs:
- VB
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
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
ms.openlocfilehash: 46dc9e6018cf2ae71f1fc6dc2b8f19c2f0aadb62
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---
# <a name="-operator-visual-basic"></a><span data-ttu-id="2cbb7-102">= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cbb7-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="2cbb7-103">将值分配给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="2cbb7-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cbb7-104">语法</span><span class="sxs-lookup"><span data-stu-id="2cbb7-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="2cbb7-105">部件</span><span class="sxs-lookup"><span data-stu-id="2cbb7-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="2cbb7-106">任何可写的变量或任何属性。</span><span class="sxs-lookup"><span data-stu-id="2cbb7-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="2cbb7-107">任何文本、 常量或表达式。</span><span class="sxs-lookup"><span data-stu-id="2cbb7-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cbb7-108">备注</span><span class="sxs-lookup"><span data-stu-id="2cbb7-108">Remarks</span></span>  
 <span data-ttu-id="2cbb7-109">等号左侧元素 (`=`) 可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="2cbb7-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="2cbb7-110">该变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="2cbb7-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="2cbb7-111">`=`运算符将值赋给变量右侧的值或在其左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="2cbb7-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cbb7-112">`=`运算符也用作比较运算符。</span><span class="sxs-lookup"><span data-stu-id="2cbb7-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="2cbb7-113">有关详细信息，请参阅[比较运算符](../../../visual-basic/language-reference/operators/comparison-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="2cbb7-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="2cbb7-114">重载</span><span class="sxs-lookup"><span data-stu-id="2cbb7-114">Overloading</span></span>  
 <span data-ttu-id="2cbb7-115">`=`只能作为关系比较运算符，而不是赋值运算符可以重载运算符。</span><span class="sxs-lookup"><span data-stu-id="2cbb7-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="2cbb7-116">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="2cbb7-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cbb7-117">示例</span><span class="sxs-lookup"><span data-stu-id="2cbb7-117">Example</span></span>  
 <span data-ttu-id="2cbb7-118">下面的示例演示使用赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="2cbb7-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="2cbb7-119">在右侧的值分配给左侧变量。</span><span class="sxs-lookup"><span data-stu-id="2cbb7-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 <span data-ttu-id="2cbb7-120">[!code-vb[VbVbalrOperators #&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2cbb7-120">[!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cbb7-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cbb7-121">See Also</span></span>  
 <span data-ttu-id="2cbb7-122">[< = 运算符](../../../visual-basic/language-reference/operators/and-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="2cbb7-122">[&= Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md) </span></span>  
<span data-ttu-id="2cbb7-123"> [* = 运算符](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="2cbb7-123"> [*= Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md) </span></span>  
<span data-ttu-id="2cbb7-124"> [+ = 运算符](../../../visual-basic/language-reference/operators/addition-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="2cbb7-124"> [+= Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md) </span></span>  
<span data-ttu-id="2cbb7-125"> [-= 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="2cbb7-125"> [-= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) </span></span>  
<span data-ttu-id="2cbb7-126"> [/ = 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="2cbb7-126"> [/= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span></span>  
<span data-ttu-id="2cbb7-127"> [\\= 运算符](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="2cbb7-127"> [\\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span></span>  
<span data-ttu-id="2cbb7-128"> [^ = 运算符](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="2cbb7-128"> [^= Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md) </span></span>  
<span data-ttu-id="2cbb7-129"> [语句](../../../visual-basic/programming-guide/language-features/statements.md) </span><span class="sxs-lookup"><span data-stu-id="2cbb7-129"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md) </span></span>  
<span data-ttu-id="2cbb7-130"> [比较运算符](../../../visual-basic/language-reference/operators/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="2cbb7-130"> [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md) </span></span>  
<span data-ttu-id="2cbb7-131"> [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) </span><span class="sxs-lookup"><span data-stu-id="2cbb7-131"> [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) </span></span>  
<span data-ttu-id="2cbb7-132"> [局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span><span class="sxs-lookup"><span data-stu-id="2cbb7-132"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span></span>

