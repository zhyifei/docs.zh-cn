---
title: ^ 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponention
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: 2fb52a57a9d96f93c31ab1419e81e7f05967f831
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659697"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="7daa1-102">^ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7daa1-102">^ Operator (Visual Basic)</span></span>
<span data-ttu-id="7daa1-103">引发到另一个数字的幂的数字。</span><span class="sxs-lookup"><span data-stu-id="7daa1-103">Raises a number to the power of another number.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7daa1-104">语法</span><span class="sxs-lookup"><span data-stu-id="7daa1-104">Syntax</span></span>  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a><span data-ttu-id="7daa1-105">部件</span><span class="sxs-lookup"><span data-stu-id="7daa1-105">Parts</span></span>  
 `number`  
 <span data-ttu-id="7daa1-106">必需。</span><span class="sxs-lookup"><span data-stu-id="7daa1-106">Required.</span></span> <span data-ttu-id="7daa1-107">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="7daa1-107">Any numeric expression.</span></span>  
  
 `exponent`  
 <span data-ttu-id="7daa1-108">必需。</span><span class="sxs-lookup"><span data-stu-id="7daa1-108">Required.</span></span> <span data-ttu-id="7daa1-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="7daa1-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="7daa1-110">结果</span><span class="sxs-lookup"><span data-stu-id="7daa1-110">Result</span></span>  
 <span data-ttu-id="7daa1-111">结果是`number`次的幂`exponent`，始终为`Double`值。</span><span class="sxs-lookup"><span data-stu-id="7daa1-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="7daa1-112">支持的类型</span><span class="sxs-lookup"><span data-stu-id="7daa1-112">Supported Types</span></span>  
 <span data-ttu-id="7daa1-113">`Double`。</span><span class="sxs-lookup"><span data-stu-id="7daa1-113">`Double`.</span></span> <span data-ttu-id="7daa1-114">任何其他类型的操作数将转换为`Double`。</span><span class="sxs-lookup"><span data-stu-id="7daa1-114">Operands of any different type are converted to `Double`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7daa1-115">备注</span><span class="sxs-lookup"><span data-stu-id="7daa1-115">Remarks</span></span>  
 <span data-ttu-id="7daa1-116">Visual Basic 始终执行中的求幂[双精度数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="7daa1-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>  
  
 <span data-ttu-id="7daa1-117">值`exponent`可以是小数，负号，或两者。</span><span class="sxs-lookup"><span data-stu-id="7daa1-117">The value of `exponent` can be fractional, negative, or both.</span></span>  
  
 <span data-ttu-id="7daa1-118">当在单个表达式中执行多个求幂`^`运算符从左到右出现的顺序进行计算。</span><span class="sxs-lookup"><span data-stu-id="7daa1-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7daa1-119">`^`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="7daa1-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7daa1-120">如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="7daa1-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7daa1-121">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="7daa1-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7daa1-122">示例</span><span class="sxs-lookup"><span data-stu-id="7daa1-122">Example</span></span>  
 <span data-ttu-id="7daa1-123">下面的示例使用`^`运算符为指数的幂数。</span><span class="sxs-lookup"><span data-stu-id="7daa1-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="7daa1-124">结果是第一个操作数的次幂的第二个。</span><span class="sxs-lookup"><span data-stu-id="7daa1-124">The result is the first operand raised to the power of the second.</span></span>  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 <span data-ttu-id="7daa1-125">前面的示例生成以下结果：</span><span class="sxs-lookup"><span data-stu-id="7daa1-125">The preceding example produces the following results:</span></span>  
  
 <span data-ttu-id="7daa1-126">`exp1` 设置为 4 (平方的 2)。</span><span class="sxs-lookup"><span data-stu-id="7daa1-126">`exp1` is set to 4 (2 squared).</span></span>  
  
 <span data-ttu-id="7daa1-127">`exp2` 设置为 19683 (3 立方，然后立方值)。</span><span class="sxs-lookup"><span data-stu-id="7daa1-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>  
  
 <span data-ttu-id="7daa1-128">`exp3` 设置为-125 (-5 的立方)。</span><span class="sxs-lookup"><span data-stu-id="7daa1-128">`exp3` is set to -125 (-5 cubed).</span></span>  
  
 <span data-ttu-id="7daa1-129">`exp4` 设置为 625 (-5 的四次幂)。</span><span class="sxs-lookup"><span data-stu-id="7daa1-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>  
  
 <span data-ttu-id="7daa1-130">`exp5` 设置为 2 （8 的立方根）。</span><span class="sxs-lookup"><span data-stu-id="7daa1-130">`exp5` is set to 2 (cube root of 8).</span></span>  
  
 <span data-ttu-id="7daa1-131">`exp6` 设置为 0.5 (1.0 除以 8 的立方根)。</span><span class="sxs-lookup"><span data-stu-id="7daa1-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>  
  
 <span data-ttu-id="7daa1-132">请注意前面示例中的表达式中的括号的重要性。</span><span class="sxs-lookup"><span data-stu-id="7daa1-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="7daa1-133">由于*运算符优先级*，通常情况下，Visual Basic 执行`^`运算符先于任何其他，甚至是一元`–`运算符。</span><span class="sxs-lookup"><span data-stu-id="7daa1-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="7daa1-134">如果`exp4`和`exp6`计算时不带括号，将会产生以下结果：</span><span class="sxs-lookup"><span data-stu-id="7daa1-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>  
  
 <span data-ttu-id="7daa1-135">`exp4 = -5 ^ 4` 将计算为 – (5 四次幂)，这会导致-625。</span><span class="sxs-lookup"><span data-stu-id="7daa1-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>  
  
 <span data-ttu-id="7daa1-136">`exp6 = 8 ^ -1.0 / 3.0` 将计算为 (8 – 1 电源或 0.125) 除以 3.0，这将导致 0.041666666666666666666666666666667。</span><span class="sxs-lookup"><span data-stu-id="7daa1-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7daa1-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="7daa1-137">See also</span></span>
- [<span data-ttu-id="7daa1-138">^= 运算符</span><span class="sxs-lookup"><span data-stu-id="7daa1-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="7daa1-139">算术运算符</span><span class="sxs-lookup"><span data-stu-id="7daa1-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="7daa1-140">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="7daa1-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7daa1-141">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="7daa1-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7daa1-142">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="7daa1-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
