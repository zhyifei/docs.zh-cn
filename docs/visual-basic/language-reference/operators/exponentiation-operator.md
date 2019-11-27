---
title: ^ 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponentiation
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: b9860b7b6e076fc9c0288818aa9e4f2c0fc4c356
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331108"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="fef97-102">^ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fef97-102">^ Operator (Visual Basic)</span></span>

<span data-ttu-id="fef97-103">计算一个数字的另一个数字的幂。</span><span class="sxs-lookup"><span data-stu-id="fef97-103">Raises a number to the power of another number.</span></span>

## <a name="syntax"></a><span data-ttu-id="fef97-104">语法</span><span class="sxs-lookup"><span data-stu-id="fef97-104">Syntax</span></span>

```vb
number ^ exponent
```

## <a name="parts"></a><span data-ttu-id="fef97-105">部件</span><span class="sxs-lookup"><span data-stu-id="fef97-105">Parts</span></span>

`number`\
<span data-ttu-id="fef97-106">必需。</span><span class="sxs-lookup"><span data-stu-id="fef97-106">Required.</span></span> <span data-ttu-id="fef97-107">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="fef97-107">Any numeric expression.</span></span>

`exponent`\
<span data-ttu-id="fef97-108">必需。</span><span class="sxs-lookup"><span data-stu-id="fef97-108">Required.</span></span> <span data-ttu-id="fef97-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="fef97-109">Any numeric expression.</span></span>

## <a name="result"></a><span data-ttu-id="fef97-110">结果</span><span class="sxs-lookup"><span data-stu-id="fef97-110">Result</span></span>

<span data-ttu-id="fef97-111">结果 `number` `exponent`的次幂，并始终作为 `Double` 值。</span><span class="sxs-lookup"><span data-stu-id="fef97-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>

## <a name="supported-types"></a><span data-ttu-id="fef97-112">支持的类型</span><span class="sxs-lookup"><span data-stu-id="fef97-112">Supported Types</span></span>

<span data-ttu-id="fef97-113">`Double`。</span><span class="sxs-lookup"><span data-stu-id="fef97-113">`Double`.</span></span> <span data-ttu-id="fef97-114">任何不同类型的操作数都转换为 `Double`。</span><span class="sxs-lookup"><span data-stu-id="fef97-114">Operands of any different type are converted to `Double`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fef97-115">备注</span><span class="sxs-lookup"><span data-stu-id="fef97-115">Remarks</span></span>

<span data-ttu-id="fef97-116">Visual Basic 总是对[Double 数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)执行幂运算。</span><span class="sxs-lookup"><span data-stu-id="fef97-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>

<span data-ttu-id="fef97-117">`exponent` 的值可以是小数、负数或同时为两者。</span><span class="sxs-lookup"><span data-stu-id="fef97-117">The value of `exponent` can be fractional, negative, or both.</span></span>

<span data-ttu-id="fef97-118">如果在单个表达式中执行了多个幂运算，将计算 `^` 运算符，因为它是从左到右发生的。</span><span class="sxs-lookup"><span data-stu-id="fef97-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>

> [!NOTE]
> <span data-ttu-id="fef97-119">可以*重载*`^` 运算符，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="fef97-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fef97-120">如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="fef97-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="fef97-121">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="fef97-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="fef97-122">示例</span><span class="sxs-lookup"><span data-stu-id="fef97-122">Example</span></span>

<span data-ttu-id="fef97-123">下面的示例使用 `^` 运算符对某个数字进行幂运算。</span><span class="sxs-lookup"><span data-stu-id="fef97-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="fef97-124">结果是第一个操作数的次幂。</span><span class="sxs-lookup"><span data-stu-id="fef97-124">The result is the first operand raised to the power of the second.</span></span>

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

<span data-ttu-id="fef97-125">前面的示例生成了以下结果：</span><span class="sxs-lookup"><span data-stu-id="fef97-125">The preceding example produces the following results:</span></span>

<span data-ttu-id="fef97-126">`exp1` 设置为4（2平方）。</span><span class="sxs-lookup"><span data-stu-id="fef97-126">`exp1` is set to 4 (2 squared).</span></span>

<span data-ttu-id="fef97-127">`exp2` 设置为19683（3个立方，然后是该值的立方）。</span><span class="sxs-lookup"><span data-stu-id="fef97-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>

<span data-ttu-id="fef97-128">`exp3` 设置为-125 （-5 立方）。</span><span class="sxs-lookup"><span data-stu-id="fef97-128">`exp3` is set to -125 (-5 cubed).</span></span>

<span data-ttu-id="fef97-129">`exp4` 设置为625（-5 到第四次幂）。</span><span class="sxs-lookup"><span data-stu-id="fef97-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>

<span data-ttu-id="fef97-130">`exp5` 设置为2（多维数据集的第8级）。</span><span class="sxs-lookup"><span data-stu-id="fef97-130">`exp5` is set to 2 (cube root of 8).</span></span>

<span data-ttu-id="fef97-131">`exp6` 设置为0.5 （1.0 除以8的 cube 根）。</span><span class="sxs-lookup"><span data-stu-id="fef97-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>

<span data-ttu-id="fef97-132">请注意前面示例的表达式中的括号的重要性。</span><span class="sxs-lookup"><span data-stu-id="fef97-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="fef97-133">由于*运算符优先级*，Visual Basic 通常在任何其他运算符（甚至一元 `–` 运算符）之前执行 `^` 运算符。</span><span class="sxs-lookup"><span data-stu-id="fef97-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="fef97-134">如果未使用括号计算 `exp4` 和 `exp6`，则会生成以下结果：</span><span class="sxs-lookup"><span data-stu-id="fef97-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>

<span data-ttu-id="fef97-135">`exp4 = -5 ^ 4` 将计算为–（5到第四次幂），这会导致-625。</span><span class="sxs-lookup"><span data-stu-id="fef97-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>

<span data-ttu-id="fef97-136">`exp6 = 8 ^ -1.0 / 3.0` 将计算为（8到1个幂，即0.125）除以3.0，这将导致0.041666666666666666666666666666667。</span><span class="sxs-lookup"><span data-stu-id="fef97-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>

## <a name="see-also"></a><span data-ttu-id="fef97-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fef97-137">See also</span></span>

- [<span data-ttu-id="fef97-138">^= 运算符</span><span class="sxs-lookup"><span data-stu-id="fef97-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="fef97-139">算术运算符</span><span class="sxs-lookup"><span data-stu-id="fef97-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="fef97-140">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="fef97-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="fef97-141">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="fef97-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="fef97-142">Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="fef97-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
