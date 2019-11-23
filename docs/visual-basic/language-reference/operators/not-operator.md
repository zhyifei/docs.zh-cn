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
ms.openlocfilehash: 5ebc5f9dbf674a9a6560bd96b3e8c9edcae08a81
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701081"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="8f484-102">Not 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f484-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="8f484-103">对 `Boolean` 表达式执行逻辑非运算，或对数值表达式执行位求反运算。</span><span class="sxs-lookup"><span data-stu-id="8f484-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f484-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f484-104">Syntax</span></span>  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="8f484-105">部件</span><span class="sxs-lookup"><span data-stu-id="8f484-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="8f484-106">必需。</span><span class="sxs-lookup"><span data-stu-id="8f484-106">Required.</span></span> <span data-ttu-id="8f484-107">任何 `Boolean` 或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="8f484-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="8f484-108">必需。</span><span class="sxs-lookup"><span data-stu-id="8f484-108">Required.</span></span> <span data-ttu-id="8f484-109">任何 `Boolean` 或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="8f484-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f484-110">备注</span><span class="sxs-lookup"><span data-stu-id="8f484-110">Remarks</span></span>  
 <span data-ttu-id="8f484-111">对于 `Boolean` 表达式，下表说明了如何确定 `result`。</span><span class="sxs-lookup"><span data-stu-id="8f484-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="8f484-112">如果 `expression` 为</span><span class="sxs-lookup"><span data-stu-id="8f484-112">If `expression` is</span></span>|<span data-ttu-id="8f484-113">`result` 的值是</span><span class="sxs-lookup"><span data-stu-id="8f484-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="8f484-114">对于数值表达式，`Not` 运算符会反转任何数值表达式的位值，并根据下表设置 `result` 中的相应位。</span><span class="sxs-lookup"><span data-stu-id="8f484-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="8f484-115">如果 `expression` 中有位</span><span class="sxs-lookup"><span data-stu-id="8f484-115">If bit in `expression` is</span></span>|<span data-ttu-id="8f484-116">`result` 中的位是</span><span class="sxs-lookup"><span data-stu-id="8f484-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="8f484-117">1</span><span class="sxs-lookup"><span data-stu-id="8f484-117">1</span></span>|<span data-ttu-id="8f484-118">0</span><span class="sxs-lookup"><span data-stu-id="8f484-118">0</span></span>|  
|<span data-ttu-id="8f484-119">0</span><span class="sxs-lookup"><span data-stu-id="8f484-119">0</span></span>|<span data-ttu-id="8f484-120">1</span><span class="sxs-lookup"><span data-stu-id="8f484-120">1</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="8f484-121">由于逻辑 and 位运算符的优先级低于其他算术运算符和关系运算符，因此应将任何按位运算括在括号中，以确保准确执行。</span><span class="sxs-lookup"><span data-stu-id="8f484-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="8f484-122">数据类型</span><span class="sxs-lookup"><span data-stu-id="8f484-122">Data Types</span></span>  
 <span data-ttu-id="8f484-123">对于布尔求反，结果的数据类型为 `Boolean`。</span><span class="sxs-lookup"><span data-stu-id="8f484-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="8f484-124">对于按位求反，结果数据类型与 `expression`的数据类型相同。</span><span class="sxs-lookup"><span data-stu-id="8f484-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="8f484-125">但是，如果 `Decimal`expression，则结果将 `Long`。</span><span class="sxs-lookup"><span data-stu-id="8f484-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8f484-126">重载</span><span class="sxs-lookup"><span data-stu-id="8f484-126">Overloading</span></span>  
 <span data-ttu-id="8f484-127">可以*重载*`Not` 运算符，这意味着当类或结构的操作数具有该类或结构的类型时，它可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="8f484-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="8f484-128">如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="8f484-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8f484-129">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="8f484-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f484-130">示例</span><span class="sxs-lookup"><span data-stu-id="8f484-130">Example</span></span>  
 <span data-ttu-id="8f484-131">下面的示例使用 `Not` 运算符对 `Boolean` 表达式执行逻辑非运算。</span><span class="sxs-lookup"><span data-stu-id="8f484-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="8f484-132">结果是一个 `Boolean` 值，该值表示表达式的值的逆值。</span><span class="sxs-lookup"><span data-stu-id="8f484-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="8f484-133">前面的示例分别产生 `False` 和 `True`的结果。</span><span class="sxs-lookup"><span data-stu-id="8f484-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f484-134">示例</span><span class="sxs-lookup"><span data-stu-id="8f484-134">Example</span></span>  
 <span data-ttu-id="8f484-135">下面的示例使用 `Not` 运算符对数值表达式的各个位执行逻辑求反运算。</span><span class="sxs-lookup"><span data-stu-id="8f484-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="8f484-136">结果模式中的位设置为操作数模式中相应位的反向，其中包括符号位。</span><span class="sxs-lookup"><span data-stu-id="8f484-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="8f484-137">前面的示例分别产生–11、–9和–7的结果。</span><span class="sxs-lookup"><span data-stu-id="8f484-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f484-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f484-138">See also</span></span>

- [<span data-ttu-id="8f484-139">逻辑/按位运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="8f484-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="8f484-140">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="8f484-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="8f484-141">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="8f484-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="8f484-142">Visual Basic 中的逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="8f484-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
