---
title: 如何：计算数值 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: cf24d7259ac04f6901497c81558a4d59b340eec7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649781"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="8cfd0-102">如何：计算数值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8cfd0-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="8cfd0-103">您可以计算通过数值表达式使用的数字值。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="8cfd0-104">A*数值表达式*会包含文本、 常量和变量表示数字值的表达式并处理这些值的运算符。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="8cfd0-105">计算数值</span><span class="sxs-lookup"><span data-stu-id="8cfd0-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="8cfd0-106">若要计算的数字值</span><span class="sxs-lookup"><span data-stu-id="8cfd0-106">To calculate a numeric value</span></span>  
  
-   <span data-ttu-id="8cfd0-107">将一个或多个数值的文本、 常量和变量组合到一个数值表达式。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="8cfd0-108">下面的示例显示了一些有效的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="8cfd0-109">前三个行显示文本、 常量和变量。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="8cfd0-110">每个单独构成有效的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="8cfd0-111">最后一行显示了具有两个文本的变量的组合。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="8cfd0-112">请注意数值表达式本身并不构成一个完整的 Visual Basic 语句。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="8cfd0-113">作为一个完整的语句的一部分，必须使用表达式。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="8cfd0-114">若要存储的数字值</span><span class="sxs-lookup"><span data-stu-id="8cfd0-114">To store a numeric value</span></span>  
  
-   <span data-ttu-id="8cfd0-115">赋值语句可用于分配给一个变量，一个数值表达式所表示的值，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     <span data-ttu-id="8cfd0-116">在前面的示例中，相等运算符右侧的表达式的值 (`=`) 分配给变量`j`运算符，左侧以便`j`计算结果为 276。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="8cfd0-117">有关详细信息，请参阅[语句](../../../../visual-basic/language-reference/statements/index.md)。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-117">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="8cfd0-118">多个运算符</span><span class="sxs-lookup"><span data-stu-id="8cfd0-118">Multiple Operators</span></span>  
 <span data-ttu-id="8cfd0-119">如果数值的表达式包含多个运算符，将计算它们的顺序由运算符优先级规则确定。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="8cfd0-120">若要覆盖的运算符优先顺序规则，则将表达式括在括号，如下所示上面的示例;首先计算括起来的表达式。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="8cfd0-121">若要重写正常运算符优先级</span><span class="sxs-lookup"><span data-stu-id="8cfd0-121">To override normal operator precedence</span></span>  
  
-   <span data-ttu-id="8cfd0-122">使用括号括住你想要首先执行的操作。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="8cfd0-123">下面的示例演示具有相同的操作数和运算符的两个不同的结果。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     <span data-ttu-id="8cfd0-124">在前面的示例中，针对的计算`j`执行加法运算符 (`+`) 第一个因为两边的括号`(67 + i)`重写正常优先级和分配给值`j`为 276 (4 次 69)。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="8cfd0-125">对计算`k`执行运算符在其正常优先 (`*`之前`+`)，和的值分配给`k`为 270 （268 加 2）。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="8cfd0-126">有关详细信息，请参阅[Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="8cfd0-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cfd0-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="8cfd0-127">See Also</span></span>  
 [<span data-ttu-id="8cfd0-128">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="8cfd0-128">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="8cfd0-129">值的比较</span><span class="sxs-lookup"><span data-stu-id="8cfd0-129">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="8cfd0-130">语句</span><span class="sxs-lookup"><span data-stu-id="8cfd0-130">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)  
 [<span data-ttu-id="8cfd0-131">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="8cfd0-131">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="8cfd0-132">算术运算符</span><span class="sxs-lookup"><span data-stu-id="8cfd0-132">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="8cfd0-133">运算符的有效组合</span><span class="sxs-lookup"><span data-stu-id="8cfd0-133">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
