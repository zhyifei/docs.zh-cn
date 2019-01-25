---
title: Visual Basic 中的运算符和表达式
ms.date: 07/20/2015
helpviewer_keywords:
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands [Visual Basic], definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
ms.openlocfilehash: 9badc41a97043b6e32da4dd93834770f871261c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498526"
---
# <a name="operators-and-expressions-in-visual-basic"></a><span data-ttu-id="c239f-102">Visual Basic 中的运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="c239f-102">Operators and Expressions in Visual Basic</span></span>
<span data-ttu-id="c239f-103">运算符是对包含值的一个或多个代码元素执行运算的代码元素。</span><span class="sxs-lookup"><span data-stu-id="c239f-103">An *operator* is a code element that performs an operation on one or more code elements that hold values.</span></span> <span data-ttu-id="c239f-104">值元素包括变量、常量、文本、属性、`Function` 和 `Operator` 过程的返回结果以及表达式。</span><span class="sxs-lookup"><span data-stu-id="c239f-104">Value elements include variables, constants, literals, properties, returns from `Function` and `Operator` procedures, and expressions.</span></span>  
  
 <span data-ttu-id="c239f-105">表达式是一系列与运算符结合使用的值元素，将生成新值。</span><span class="sxs-lookup"><span data-stu-id="c239f-105">An *expression* is a series of value elements combined with operators, which yields a new value.</span></span> <span data-ttu-id="c239f-106">运算符通过执行计算、比较或其他运算来处理值元素。</span><span class="sxs-lookup"><span data-stu-id="c239f-106">The operators act on the value elements by performing calculations, comparisons, or other operations.</span></span>  
  
## <a name="types-of-operators"></a><span data-ttu-id="c239f-107">运算符类型</span><span class="sxs-lookup"><span data-stu-id="c239f-107">Types of Operators</span></span>  
 <span data-ttu-id="c239f-108">Visual Basic 提供了以下类型的运算符：</span><span class="sxs-lookup"><span data-stu-id="c239f-108">Visual Basic provides the following types of operators:</span></span>  
  
-   <span data-ttu-id="c239f-109">[算术运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)：对数字值执行常见计算，包括更改位模式。</span><span class="sxs-lookup"><span data-stu-id="c239f-109">[Arithmetic Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) perform familiar calculations on numeric values, including shifting their bit patterns.</span></span>  
  
-   <span data-ttu-id="c239f-110">[比较运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)：比较两个表达式，并返回 `Boolean` 值来表示比较结果。</span><span class="sxs-lookup"><span data-stu-id="c239f-110">[Comparison Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) compare two expressions and return a `Boolean` value representing the result of the comparison.</span></span>  
  
-   <span data-ttu-id="c239f-111">[串联运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)：将多个字符串联接为一个字符串。</span><span class="sxs-lookup"><span data-stu-id="c239f-111">[Concatenation Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) join multiple strings into a single string.</span></span>  
  
-   <span data-ttu-id="c239f-112">[Visual Basic 中的逻辑和位运算运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)：合并 `Boolean` 或数字值，并以值的形式返回数据类型相同的结果。</span><span class="sxs-lookup"><span data-stu-id="c239f-112">[Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) combine `Boolean` or numeric values and return a result of the same data type as the values.</span></span>  
  
 <span data-ttu-id="c239f-113">与运算符合并的值元素称为相应运算符的操作数。</span><span class="sxs-lookup"><span data-stu-id="c239f-113">The value elements that are combined with an operator are called *operands* of that operator.</span></span> <span data-ttu-id="c239f-114">运算符与值元素共同构成了表达式，构成语句的赋值运算符除外。</span><span class="sxs-lookup"><span data-stu-id="c239f-114">Operators combined with value elements form expressions, except for the assignment operator, which forms a *statement*.</span></span> <span data-ttu-id="c239f-115">有关详细信息，请参阅[语句](../../../../visual-basic/programming-guide/language-features/statements.md)。</span><span class="sxs-lookup"><span data-stu-id="c239f-115">For more information, see [Statements](../../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
## <a name="evaluation-of-expressions"></a><span data-ttu-id="c239f-116">表达式计算</span><span class="sxs-lookup"><span data-stu-id="c239f-116">Evaluation of Expressions</span></span>  
 <span data-ttu-id="c239f-117">表达式的最终结果表示采用常见数据类型（如 `Boolean`、`String` 或数字类型）的值。</span><span class="sxs-lookup"><span data-stu-id="c239f-117">The end result of an expression represents a value, which is typically of a familiar data type such as `Boolean`, `String`, or a numeric type.</span></span>  
  
 <span data-ttu-id="c239f-118">下面展示了表达式示例。</span><span class="sxs-lookup"><span data-stu-id="c239f-118">The following are examples of expressions.</span></span>  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 <span data-ttu-id="c239f-119">多个运算符可以在一个表达式或语句中执行运算，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="c239f-119">Several operators can perform actions in a single expression or statement, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#56](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/index_1.vb)]  
  
 <span data-ttu-id="c239f-120">在前面的示例中，Visual Basic 所执行的赋值运算符右侧的表达式中的操作 (`=`)，然后将生成的值分配给该变量`x`左侧。</span><span class="sxs-lookup"><span data-stu-id="c239f-120">In the preceding example, Visual Basic performs the operations in the expression on the right side of the assignment operator (`=`), then assigns the resulting value to the variable `x` on the left.</span></span> <span data-ttu-id="c239f-121">对于可以合并到表达式中的运算符数量没有实际限制，但需要了解 [Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)，以确保结果符合预期。</span><span class="sxs-lookup"><span data-stu-id="c239f-121">There is no practical limit to the number of operators that can be combined into an expression, but an understanding of [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) is necessary to ensure that you get the results you expect.</span></span>  
  
 <span data-ttu-id="c239f-122">有关详细信息和示例，请参阅 [Visual Basic 2005 中的运算符重载](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx)。</span><span class="sxs-lookup"><span data-stu-id="c239f-122">For more information and examples, see [Operator Overloading in Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c239f-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="c239f-123">See also</span></span>
- [<span data-ttu-id="c239f-124">运算符</span><span class="sxs-lookup"><span data-stu-id="c239f-124">Operators</span></span>](../../../../visual-basic/language-reference/operators/index.md)
- [<span data-ttu-id="c239f-125">运算符的有效组合</span><span class="sxs-lookup"><span data-stu-id="c239f-125">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [<span data-ttu-id="c239f-126">语句</span><span class="sxs-lookup"><span data-stu-id="c239f-126">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
