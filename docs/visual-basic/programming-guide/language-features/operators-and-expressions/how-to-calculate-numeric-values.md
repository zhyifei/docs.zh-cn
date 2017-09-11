---
title: "如何︰ 计算数值 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations, numeric expressions
- precedence, of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fe781cca8f716c792d3af153b2004c716bc87f90
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="92ab3-102">如何：计算数值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92ab3-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="92ab3-103">您可以计算通过使用数值表达式的数值。</span><span class="sxs-lookup"><span data-stu-id="92ab3-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="92ab3-104">一个*数值表达式*一个表达式，包含文本、 常量和变量表示数值，以及处理这些值的运算符。</span><span class="sxs-lookup"><span data-stu-id="92ab3-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="92ab3-105">计算数值</span><span class="sxs-lookup"><span data-stu-id="92ab3-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="92ab3-106">若要计算的数字值</span><span class="sxs-lookup"><span data-stu-id="92ab3-106">To calculate a numeric value</span></span>  
  
-   <span data-ttu-id="92ab3-107">将一个或多个数字文本、 常量和变量组合到一个数值表达式。</span><span class="sxs-lookup"><span data-stu-id="92ab3-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="92ab3-108">下面的示例显示了一些有效的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="92ab3-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="92ab3-109">前三行显示文本、 常量和变量。</span><span class="sxs-lookup"><span data-stu-id="92ab3-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="92ab3-110">每个构成有效的数值表达式本身。</span><span class="sxs-lookup"><span data-stu-id="92ab3-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="92ab3-111">最后一行演示具有两个字符串的变量的组合。</span><span class="sxs-lookup"><span data-stu-id="92ab3-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="92ab3-112">请注意，并未数值表达式组成的完整[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]本身的语句。</span><span class="sxs-lookup"><span data-stu-id="92ab3-112">Note that a numeric expression does not form a complete [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statement by itself.</span></span> <span data-ttu-id="92ab3-113">作为一个完整的语句的一部分，必须使用表达式。</span><span class="sxs-lookup"><span data-stu-id="92ab3-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="92ab3-114">若要存储的数字值</span><span class="sxs-lookup"><span data-stu-id="92ab3-114">To store a numeric value</span></span>  
  
-   <span data-ttu-id="92ab3-115">赋值语句可用于将分配给一个变量，数值表达式所表示的值，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="92ab3-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     <span data-ttu-id="92ab3-116">[!code-vb[VbVbalrOperators #&82;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="92ab3-116">[!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]</span></span>  
  
     <span data-ttu-id="92ab3-117">在前面的示例中，相等运算符右侧的表达式的值 (`=`) 赋给变量`j`运算符，左侧以便`j`的计算结果为 276。</span><span class="sxs-lookup"><span data-stu-id="92ab3-117">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="92ab3-118">有关详细信息，请参阅[语句](../../../../visual-basic/language-reference/statements/index.md)。</span><span class="sxs-lookup"><span data-stu-id="92ab3-118">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="92ab3-119">多个运算符</span><span class="sxs-lookup"><span data-stu-id="92ab3-119">Multiple Operators</span></span>  
 <span data-ttu-id="92ab3-120">如果数值表达式包含多个运算符，它们的计算顺序由运算符优先级的规则确定。</span><span class="sxs-lookup"><span data-stu-id="92ab3-120">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="92ab3-121">若要覆盖的运算符优先顺序规则，则将表达式括在括号内，如上面的示例;首先计算括起来的表达式。</span><span class="sxs-lookup"><span data-stu-id="92ab3-121">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="92ab3-122">若要重写常规运算符优先级</span><span class="sxs-lookup"><span data-stu-id="92ab3-122">To override normal operator precedence</span></span>  
  
-   <span data-ttu-id="92ab3-123">使用括号括住您想要首先执行的操作。</span><span class="sxs-lookup"><span data-stu-id="92ab3-123">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="92ab3-124">下面的示例演示具有相同的操作数和运算符的两个不同的结果。</span><span class="sxs-lookup"><span data-stu-id="92ab3-124">The following example shows two different results with the same operands and operators.</span></span>  
  
     <span data-ttu-id="92ab3-125">[!code-vb[VbVbalrOperators #&83;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="92ab3-125">[!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]</span></span>  
  
     <span data-ttu-id="92ab3-126">在前面的示例中，用于计算`j`执行加法运算符 (`+`) 第一个因为两边的括号`(67 + i)`正常的优先级和赋予的值重写`j`为 276 (4 次 69)。</span><span class="sxs-lookup"><span data-stu-id="92ab3-126">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="92ab3-127">用于计算`k`按常规优先级执行运算符 (`*`之前`+`)，和赋予的值`k`为 270 （268 加 2）。</span><span class="sxs-lookup"><span data-stu-id="92ab3-127">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="92ab3-128">有关详细信息，请参阅[Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="92ab3-128">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ab3-129">请参见</span><span class="sxs-lookup"><span data-stu-id="92ab3-129">See Also</span></span>  
 <span data-ttu-id="92ab3-130">[运算符和表达式](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="92ab3-130">[Operators and Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span></span>  
<span data-ttu-id="92ab3-131"> [值的比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span><span class="sxs-lookup"><span data-stu-id="92ab3-131"> [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span></span>  
<span data-ttu-id="92ab3-132"> [语句](../../../../visual-basic/language-reference/statements/index.md) </span><span class="sxs-lookup"><span data-stu-id="92ab3-132"> [Statements](../../../../visual-basic/language-reference/statements/index.md) </span></span>  
<span data-ttu-id="92ab3-133"> [在 Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="92ab3-133"> [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="92ab3-134"> [算术运算符](../../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="92ab3-134"> [Arithmetic Operators](../../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="92ab3-135"> [运算符的有效组合](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)</span><span class="sxs-lookup"><span data-stu-id="92ab3-135"> [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)</span></span>
