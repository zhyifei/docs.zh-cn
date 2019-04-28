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
ms.openlocfilehash: 33184d9be275f5e777ffd79c6dd4e3182d865de7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864670"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="063d2-102">如何：计算数值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="063d2-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="063d2-103">您可以计算通过使用数值表达式的数字值。</span><span class="sxs-lookup"><span data-stu-id="063d2-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="063d2-104">一个*数值表达式*会包含文本、 常量和变量表示数字值的表达式并处理这些值的运算符。</span><span class="sxs-lookup"><span data-stu-id="063d2-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="063d2-105">计算数值</span><span class="sxs-lookup"><span data-stu-id="063d2-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="063d2-106">若要计算的数字值</span><span class="sxs-lookup"><span data-stu-id="063d2-106">To calculate a numeric value</span></span>  
  
- <span data-ttu-id="063d2-107">将一个或多个数字文本、 常量和变量组合到一个数值表达式。</span><span class="sxs-lookup"><span data-stu-id="063d2-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="063d2-108">下面的示例显示了一些有效的数值表达式。</span><span class="sxs-lookup"><span data-stu-id="063d2-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="063d2-109">前三行显示文本、 常量和变量。</span><span class="sxs-lookup"><span data-stu-id="063d2-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="063d2-110">每个单独窗体的有效数值表达式。</span><span class="sxs-lookup"><span data-stu-id="063d2-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="063d2-111">最后一行显示了具有两个文本的变量的组合。</span><span class="sxs-lookup"><span data-stu-id="063d2-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="063d2-112">请注意，数值表达式不会不完整的 Visual Basic 语句本身组成。</span><span class="sxs-lookup"><span data-stu-id="063d2-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="063d2-113">作为一个完整的语句的一部分，必须使用表达式。</span><span class="sxs-lookup"><span data-stu-id="063d2-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="063d2-114">若要存储的数字值</span><span class="sxs-lookup"><span data-stu-id="063d2-114">To store a numeric value</span></span>  
  
- <span data-ttu-id="063d2-115">赋值语句可用于将分配给一个变量，数值表达式所表示的值，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="063d2-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     <span data-ttu-id="063d2-116">在前面的示例中，相等运算符右侧的表达式的值 (`=`) 分配给变量`j`上左侧和右侧的运算符，因此`j`的计算结果为 276。</span><span class="sxs-lookup"><span data-stu-id="063d2-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="063d2-117">有关详细信息，请参阅[语句](../../../../visual-basic/language-reference/statements/index.md)。</span><span class="sxs-lookup"><span data-stu-id="063d2-117">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="063d2-118">多个运算符</span><span class="sxs-lookup"><span data-stu-id="063d2-118">Multiple Operators</span></span>  
 <span data-ttu-id="063d2-119">如果数值表达式包含多个运算符，计算它们的顺序由运算符优先级的规则确定。</span><span class="sxs-lookup"><span data-stu-id="063d2-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="063d2-120">若要替代的运算符优先顺序规则，则将表达式括在括号内，如上面的示例; 中所示首先计算括住的表达式。</span><span class="sxs-lookup"><span data-stu-id="063d2-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="063d2-121">若要重写常规运算符优先级</span><span class="sxs-lookup"><span data-stu-id="063d2-121">To override normal operator precedence</span></span>  
  
- <span data-ttu-id="063d2-122">使用括号括住您想要首先执行的操作。</span><span class="sxs-lookup"><span data-stu-id="063d2-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="063d2-123">下面的示例显示了具有相同的操作数和运算符的两个不同的结果。</span><span class="sxs-lookup"><span data-stu-id="063d2-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     <span data-ttu-id="063d2-124">在前面的示例的计算`j`执行加法运算符 (`+`) 第一个因为两边的括号`(67 + i)`重写常规优先级和分配给的值`j`为 276 (4 次 69)。</span><span class="sxs-lookup"><span data-stu-id="063d2-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="063d2-125">计算`k`按正常优先级执行运算符 (`*`之前`+`)，并分配给的值`k`为 270 （268 加 2）。</span><span class="sxs-lookup"><span data-stu-id="063d2-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="063d2-126">有关详细信息，请参阅[在 Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="063d2-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="063d2-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="063d2-127">See also</span></span>

- [<span data-ttu-id="063d2-128">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="063d2-128">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="063d2-129">值的比较</span><span class="sxs-lookup"><span data-stu-id="063d2-129">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="063d2-130">语句</span><span class="sxs-lookup"><span data-stu-id="063d2-130">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="063d2-131">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="063d2-131">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="063d2-132">算术运算符</span><span class="sxs-lookup"><span data-stu-id="063d2-132">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="063d2-133">运算符的有效组合</span><span class="sxs-lookup"><span data-stu-id="063d2-133">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
