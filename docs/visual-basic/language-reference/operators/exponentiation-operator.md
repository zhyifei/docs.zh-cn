---
title: "^ 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.^
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e7159f289b687055c7d75cc8da58d6f76607a83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="49965-102">^ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49965-102">^ Operator (Visual Basic)</span></span>
<span data-ttu-id="49965-103">引发到另一个数字的幂的数字。</span><span class="sxs-lookup"><span data-stu-id="49965-103">Raises a number to the power of another number.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49965-104">语法</span><span class="sxs-lookup"><span data-stu-id="49965-104">Syntax</span></span>  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a><span data-ttu-id="49965-105">部件</span><span class="sxs-lookup"><span data-stu-id="49965-105">Parts</span></span>  
 `number`  
 <span data-ttu-id="49965-106">必需。</span><span class="sxs-lookup"><span data-stu-id="49965-106">Required.</span></span> <span data-ttu-id="49965-107">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="49965-107">Any numeric expression.</span></span>  
  
 `exponent`  
 <span data-ttu-id="49965-108">必需。</span><span class="sxs-lookup"><span data-stu-id="49965-108">Required.</span></span> <span data-ttu-id="49965-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="49965-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="49965-110">结果</span><span class="sxs-lookup"><span data-stu-id="49965-110">Result</span></span>  
 <span data-ttu-id="49965-111">结果是`number`的幂`exponent`，始终为`Double`值。</span><span class="sxs-lookup"><span data-stu-id="49965-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="49965-112">支持的类型</span><span class="sxs-lookup"><span data-stu-id="49965-112">Supported Types</span></span>  
 <span data-ttu-id="49965-113">`Double`。</span><span class="sxs-lookup"><span data-stu-id="49965-113">`Double`.</span></span> <span data-ttu-id="49965-114">任何其他类型的操作数将转换为`Double`。</span><span class="sxs-lookup"><span data-stu-id="49965-114">Operands of any different type are converted to `Double`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49965-115">备注</span><span class="sxs-lookup"><span data-stu-id="49965-115">Remarks</span></span>  
 <span data-ttu-id="49965-116">Visual Basic 始终执行求幂中的[Double 数据类型](../../../visual-basic/language-reference/data-types/double-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="49965-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>  
  
 <span data-ttu-id="49965-117">值`exponent`可以是小数，负的、 和/或文件名。</span><span class="sxs-lookup"><span data-stu-id="49965-117">The value of `exponent` can be fractional, negative, or both.</span></span>  
  
 <span data-ttu-id="49965-118">在单个表达式中执行多个求幂时`^`运算符从左到右出现的顺序进行计算。</span><span class="sxs-lookup"><span data-stu-id="49965-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49965-119">`^`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="49965-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="49965-120">如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="49965-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="49965-121">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="49965-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="49965-122">示例</span><span class="sxs-lookup"><span data-stu-id="49965-122">Example</span></span>  
 <span data-ttu-id="49965-123">下面的示例使用`^`运算符的指数次幂数。</span><span class="sxs-lookup"><span data-stu-id="49965-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="49965-124">结果是第一个操作数的第二个次幂。</span><span class="sxs-lookup"><span data-stu-id="49965-124">The result is the first operand raised to the power of the second.</span></span>  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 <span data-ttu-id="49965-125">前面的示例将生成下列结果：</span><span class="sxs-lookup"><span data-stu-id="49965-125">The preceding example produces the following results:</span></span>  
  
 <span data-ttu-id="49965-126">`exp1`设置为 4 (2 平方值)。</span><span class="sxs-lookup"><span data-stu-id="49965-126">`exp1` is set to 4 (2 squared).</span></span>  
  
 <span data-ttu-id="49965-127">`exp2`设置为 19683 (3 立方，然后的值求立方)。</span><span class="sxs-lookup"><span data-stu-id="49965-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>  
  
 <span data-ttu-id="49965-128">`exp3`设置为-125 (-5 的立方)。</span><span class="sxs-lookup"><span data-stu-id="49965-128">`exp3` is set to -125 (-5 cubed).</span></span>  
  
 <span data-ttu-id="49965-129">`exp4`设置为 625 (-5 的四次幂)。</span><span class="sxs-lookup"><span data-stu-id="49965-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>  
  
 <span data-ttu-id="49965-130">`exp5`设置为 2 （8 的立方根）。</span><span class="sxs-lookup"><span data-stu-id="49965-130">`exp5` is set to 2 (cube root of 8).</span></span>  
  
 <span data-ttu-id="49965-131">`exp6`设置为 0.5 (1.0 除以 8 的立方根)。</span><span class="sxs-lookup"><span data-stu-id="49965-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>  
  
 <span data-ttu-id="49965-132">请注意在前面的示例中的表达式中的括号的重要性。</span><span class="sxs-lookup"><span data-stu-id="49965-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="49965-133">由于*运算符优先级*，通常情况下，Visual Basic 执行`^`运算符之前的任何其他，即使一元`–`运算符。</span><span class="sxs-lookup"><span data-stu-id="49965-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="49965-134">如果`exp4`和`exp6`计算时不带括号，将会产生以下结果：</span><span class="sxs-lookup"><span data-stu-id="49965-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>  
  
 <span data-ttu-id="49965-135">`exp4 = -5 ^ 4`将计算为 – (5 四次幂)，这将导致-625。</span><span class="sxs-lookup"><span data-stu-id="49965-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>  
  
 <span data-ttu-id="49965-136">`exp6 = 8 ^ -1.0 / 3.0`将计算方式 (8 到为-1 电源中或从 0.125) 除以 3.0，它的结果为 0.041666666666666666666666666666667。</span><span class="sxs-lookup"><span data-stu-id="49965-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49965-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49965-137">See Also</span></span>  
 [<span data-ttu-id="49965-138">^= 运算符</span><span class="sxs-lookup"><span data-stu-id="49965-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [<span data-ttu-id="49965-139">算术运算符</span><span class="sxs-lookup"><span data-stu-id="49965-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="49965-140">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="49965-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="49965-141">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="49965-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="49965-142">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="49965-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
