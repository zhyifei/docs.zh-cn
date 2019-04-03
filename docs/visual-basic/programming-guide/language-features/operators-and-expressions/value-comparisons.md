---
title: 值的比较 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: 270b226d0a1aa7d08721e6f9ed36d68492685af3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818600"
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="41cba-102">值的比较 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41cba-102">Value Comparisons (Visual Basic)</span></span>
<span data-ttu-id="41cba-103">比较运算符可以用于构造比较数值变量的值的表达式。</span><span class="sxs-lookup"><span data-stu-id="41cba-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="41cba-104">两个表达式返回`Boolean`值根据比较是 true 或 false。</span><span class="sxs-lookup"><span data-stu-id="41cba-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="41cba-105">此类表达式的示例如下所示。</span><span class="sxs-lookup"><span data-stu-id="41cba-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="41cba-106">第一个表达式的计算结果为`True`，这是因为 45 大于 26。</span><span class="sxs-lookup"><span data-stu-id="41cba-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="41cba-107">第二个示例的计算结果为`False`，这是因为 26 不超过 45。</span><span class="sxs-lookup"><span data-stu-id="41cba-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="41cba-108">此外可以比较这种方式中的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="41cba-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="41cba-109">要比较的表达式本身可以是复杂表达式，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="41cba-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="41cba-110">在前面的复杂表达式包括文本、 变量和函数调用。</span><span class="sxs-lookup"><span data-stu-id="41cba-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="41cba-111">比较运算符两侧的表达式计算，，然后使用比较结果值`>=`比较运算符。</span><span class="sxs-lookup"><span data-stu-id="41cba-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="41cba-112">如果左侧和右侧表达式的值是否大于或等于右侧表达式的值，整个表达式的计算结果`True`; 否则为为其计算结果为`False`。</span><span class="sxs-lookup"><span data-stu-id="41cba-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="41cba-113">比较值的表达式最常用于`If...Then`构造，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="41cba-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 <span data-ttu-id="41cba-114">`=`符号是比较运算符和赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="41cba-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="41cba-115">当用作比较运算符，它计算左侧的值是否等于右侧的值，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="41cba-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 <span data-ttu-id="41cba-116">此外可以任意位置使用比较表达式`Boolean`值是所需，例如，在`If`， `While`， `Loop`，或`ElseIf`语句中，或者当将分配到或将值传递给`Boolean`变量。</span><span class="sxs-lookup"><span data-stu-id="41cba-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="41cba-117">在以下示例中，通过比较表达式返回的值分配给`Boolean`变量。</span><span class="sxs-lookup"><span data-stu-id="41cba-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a><span data-ttu-id="41cba-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="41cba-118">See also</span></span>

- [<span data-ttu-id="41cba-119">布尔表达式</span><span class="sxs-lookup"><span data-stu-id="41cba-119">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="41cba-120">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="41cba-120">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="41cba-121">在 Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="41cba-121">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="41cba-122">如何：计算数值</span><span class="sxs-lookup"><span data-stu-id="41cba-122">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [<span data-ttu-id="41cba-123">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="41cba-123">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
