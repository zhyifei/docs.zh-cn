---
title: Not 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 332cee57c8d25d7f51737e01e70ba515d50bd6e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604388"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="7a45c-102">Not 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a45c-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="7a45c-103">在执行逻辑求反`Boolean`表达式或对数值表达式的按位求反运算。</span><span class="sxs-lookup"><span data-stu-id="7a45c-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a45c-104">语法</span><span class="sxs-lookup"><span data-stu-id="7a45c-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="7a45c-105">部件</span><span class="sxs-lookup"><span data-stu-id="7a45c-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="7a45c-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="7a45c-106">Required.</span></span> <span data-ttu-id="7a45c-107">任何`Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="7a45c-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="7a45c-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="7a45c-108">Required.</span></span> <span data-ttu-id="7a45c-109">任何`Boolean`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="7a45c-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a45c-110">备注</span><span class="sxs-lookup"><span data-stu-id="7a45c-110">Remarks</span></span>  
 <span data-ttu-id="7a45c-111">有关`Boolean`表达式下, 表说明了如何`result`确定。</span><span class="sxs-lookup"><span data-stu-id="7a45c-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="7a45c-112">如果`expression`是</span><span class="sxs-lookup"><span data-stu-id="7a45c-112">If `expression` is</span></span>|<span data-ttu-id="7a45c-113">值`result`是</span><span class="sxs-lookup"><span data-stu-id="7a45c-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="7a45c-114">对于数值表达式，`Not`运算符反转任何数值表达式的位值，并设置相应的中位`result`根据下表。</span><span class="sxs-lookup"><span data-stu-id="7a45c-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="7a45c-115">如果在位`expression`是</span><span class="sxs-lookup"><span data-stu-id="7a45c-115">If bit in `expression` is</span></span>|<span data-ttu-id="7a45c-116">中的位`result`是</span><span class="sxs-lookup"><span data-stu-id="7a45c-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="7a45c-117">1</span><span class="sxs-lookup"><span data-stu-id="7a45c-117">1</span></span>|<span data-ttu-id="7a45c-118">0</span><span class="sxs-lookup"><span data-stu-id="7a45c-118">0</span></span>|  
|<span data-ttu-id="7a45c-119">0</span><span class="sxs-lookup"><span data-stu-id="7a45c-119">0</span></span>|<span data-ttu-id="7a45c-120">1</span><span class="sxs-lookup"><span data-stu-id="7a45c-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="7a45c-121">因为逻辑和按位运算符的优先级低于其他算术和关系运算符，所以应将任何按位运算括在圆括号中以确保准确的执行。</span><span class="sxs-lookup"><span data-stu-id="7a45c-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="7a45c-122">数据类型</span><span class="sxs-lookup"><span data-stu-id="7a45c-122">Data Types</span></span>  
 <span data-ttu-id="7a45c-123">对于布尔求反，结果的数据类型是`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="7a45c-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="7a45c-124">对于按位求反，结果数据类型是相同的`expression`。</span><span class="sxs-lookup"><span data-stu-id="7a45c-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="7a45c-125">但是，如果表达式为`Decimal`，结果是`Long`。</span><span class="sxs-lookup"><span data-stu-id="7a45c-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7a45c-126">重载</span><span class="sxs-lookup"><span data-stu-id="7a45c-126">Overloading</span></span>  
 <span data-ttu-id="7a45c-127">`Not`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，其操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="7a45c-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="7a45c-128">如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="7a45c-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7a45c-129">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="7a45c-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a45c-130">示例</span><span class="sxs-lookup"><span data-stu-id="7a45c-130">Example</span></span>  
 <span data-ttu-id="7a45c-131">下面的示例使用`Not`运算符对执行逻辑求反`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="7a45c-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="7a45c-132">结果是`Boolean`值，该值表示表达式的值的相反值。</span><span class="sxs-lookup"><span data-stu-id="7a45c-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 <span data-ttu-id="7a45c-133">前面的示例将生成的结果`False`和`True`分别。</span><span class="sxs-lookup"><span data-stu-id="7a45c-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a45c-134">示例</span><span class="sxs-lookup"><span data-stu-id="7a45c-134">Example</span></span>  
 <span data-ttu-id="7a45c-135">下面的示例使用`Not`运算符执行的单个位进行运算的数值表达式的逻辑求反。</span><span class="sxs-lookup"><span data-stu-id="7a45c-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="7a45c-136">结果模式中的位设置为在操作数模式中，包括符号位的相应位的相反值。</span><span class="sxs-lookup"><span data-stu-id="7a45c-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 <span data-ttu-id="7a45c-137">上面的示例分别产生结果 – 11、-9 和-7。</span><span class="sxs-lookup"><span data-stu-id="7a45c-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a45c-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a45c-138">See Also</span></span>  
 [<span data-ttu-id="7a45c-139">逻辑/按位运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a45c-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="7a45c-140">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="7a45c-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="7a45c-141">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="7a45c-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="7a45c-142">在 Visual Basic 中的逻辑和按位运算符</span><span class="sxs-lookup"><span data-stu-id="7a45c-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
