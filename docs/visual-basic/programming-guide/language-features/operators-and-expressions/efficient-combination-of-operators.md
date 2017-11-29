---
title: "运算符的有效组合 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b0f1d637bc1757515cf271a8c70d62effab0843
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="ede54-102">运算符的有效组合 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ede54-102">Efficient Combination of Operators (Visual Basic)</span></span>
<span data-ttu-id="ede54-103">复杂表达式可以包含许多不同的运算符。</span><span class="sxs-lookup"><span data-stu-id="ede54-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="ede54-104">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="ede54-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="ede54-105">创建复杂表达式，例如前面示例中需要的运算符优先顺序规则的全面了解。</span><span class="sxs-lookup"><span data-stu-id="ede54-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="ede54-106">有关详细信息，请参阅[Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="ede54-106">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="ede54-107">带括号的表达式</span><span class="sxs-lookup"><span data-stu-id="ede54-107">Parenthetical Expressions</span></span>  
 <span data-ttu-id="ede54-108">通常，你想以不同的由运算符优先级确定顺序来执行运算。</span><span class="sxs-lookup"><span data-stu-id="ede54-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="ede54-109">请看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="ede54-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="ede54-110">前面的示例乘以`z`通过`y`，然后将添加到结果`4`。</span><span class="sxs-lookup"><span data-stu-id="ede54-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="ede54-111">但是，如果你想要添加`y`和`4`之前将由结果乘以`z`，你可以使用括号来覆盖正常运算符优先级。</span><span class="sxs-lookup"><span data-stu-id="ede54-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="ede54-112">通过表达式括在括号中，你可以强制而不考虑运算符优先级首先，计算该表达式。</span><span class="sxs-lookup"><span data-stu-id="ede54-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="ede54-113">若要强制前面的示例先计算加法，你无法重写如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="ede54-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="ede54-114">前面的示例将`y`和`4`，然后乘以由其总和`z`。</span><span class="sxs-lookup"><span data-stu-id="ede54-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="ede54-115">嵌套的括号表达式</span><span class="sxs-lookup"><span data-stu-id="ede54-115">Nested Parenthetical Expressions</span></span>  
 <span data-ttu-id="ede54-116">你可以嵌套的括号以进一步重写优先级的多个级别中的表达式。</span><span class="sxs-lookup"><span data-stu-id="ede54-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="ede54-117">最深嵌套在括号中的表达式都将先评估跟嵌套最深的依次类推至少深度嵌套的并最后外部括号的表达式到下一步。</span><span class="sxs-lookup"><span data-stu-id="ede54-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="ede54-118">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="ede54-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="ede54-119">在前面的示例中，`z + 2`为首先进行评估，则其他带括号的表达式。</span><span class="sxs-lookup"><span data-stu-id="ede54-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="ede54-120">求幂，通常具有优先权要高于加法或乘法，是在此示例中上次评估，因为其他表达式括在括号中。</span><span class="sxs-lookup"><span data-stu-id="ede54-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede54-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ede54-121">See Also</span></span>  
 [<span data-ttu-id="ede54-122">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="ede54-122">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="ede54-123">在 Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="ede54-123">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="ede54-124">在 Visual Basic 中的逻辑和按位运算符</span><span class="sxs-lookup"><span data-stu-id="ede54-124">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="ede54-125">逻辑/按位运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ede54-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="ede54-126">布尔表达式</span><span class="sxs-lookup"><span data-stu-id="ede54-126">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="ede54-127">值的比较</span><span class="sxs-lookup"><span data-stu-id="ede54-127">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="ede54-128">如何：计算数值</span><span class="sxs-lookup"><span data-stu-id="ede54-128">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [<span data-ttu-id="ede54-129">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="ede54-129">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
