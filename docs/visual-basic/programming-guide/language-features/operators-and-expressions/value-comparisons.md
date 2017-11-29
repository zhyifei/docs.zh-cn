---
title: "值的比较 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c11f12bbaf261c0853e96802f03322c5e7fdc706
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="04ac4-102">值的比较 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04ac4-102">Value Comparisons (Visual Basic)</span></span>
<span data-ttu-id="04ac4-103">比较运算符可以用于构造比较数值变量的值的表达式。</span><span class="sxs-lookup"><span data-stu-id="04ac4-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="04ac4-104">这些表达式返回`Boolean`值基于比较是否为 true 或 false。</span><span class="sxs-lookup"><span data-stu-id="04ac4-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="04ac4-105">此类表达式的示例如下所示。</span><span class="sxs-lookup"><span data-stu-id="04ac4-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="04ac4-106">第一个表达式的计算结果为`True`，这是因为 45 大于 26。</span><span class="sxs-lookup"><span data-stu-id="04ac4-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="04ac4-107">第二个示例的计算结果为`False`，这是因为 26 不大于 45。</span><span class="sxs-lookup"><span data-stu-id="04ac4-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="04ac4-108">你还可以比较数值表达式以这种方式。</span><span class="sxs-lookup"><span data-stu-id="04ac4-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="04ac4-109">要比较的表达式本身可以是复杂表达式，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="04ac4-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="04ac4-110">前面的复杂表达式包括文本、 变量和函数调用。</span><span class="sxs-lookup"><span data-stu-id="04ac4-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="04ac4-111">两端的比较运算符对表达式进行计算，并且将生成的值会然后比较使用`>=`比较运算符。</span><span class="sxs-lookup"><span data-stu-id="04ac4-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="04ac4-112">如果左侧表达式的值大于或等于右侧表达式的值，则整个表达式的计算结果为`True`; 否则为其计算结果为`False`。</span><span class="sxs-lookup"><span data-stu-id="04ac4-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="04ac4-113">比较值的表达式最常用于`If...Then`构造，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="04ac4-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 <span data-ttu-id="04ac4-114">`=`符号是比较运算符也是赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="04ac4-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="04ac4-115">当用作比较运算符，它会在下面的示例中所示，在左侧的值是否等于右侧，值评估。</span><span class="sxs-lookup"><span data-stu-id="04ac4-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 <span data-ttu-id="04ac4-116">你还可以使用比较表达式任意位置`Boolean`值是所需，例如，在`If`， `While`， `Loop`，或`ElseIf`语句，或者当将分配到或将值传递给`Boolean`变量。</span><span class="sxs-lookup"><span data-stu-id="04ac4-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="04ac4-117">在下面的示例中，比较表达式返回的值分配给`Boolean`变量。</span><span class="sxs-lookup"><span data-stu-id="04ac4-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="04ac4-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04ac4-118">See Also</span></span>  
 [<span data-ttu-id="04ac4-119">布尔表达式</span><span class="sxs-lookup"><span data-stu-id="04ac4-119">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="04ac4-120">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="04ac4-120">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="04ac4-121">在 Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="04ac4-121">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="04ac4-122">如何：计算数值</span><span class="sxs-lookup"><span data-stu-id="04ac4-122">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [<span data-ttu-id="04ac4-123">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="04ac4-123">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
