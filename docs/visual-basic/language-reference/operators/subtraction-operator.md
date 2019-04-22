---
title: '- 运算符 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 1a5c47a2f1bc8a8b9e1b0263b90006a0e58e17bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830664"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="1bc24-102">- 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1bc24-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="1bc24-103">返回两个数值表达式或数值表达式的负值之间的差异。</span><span class="sxs-lookup"><span data-stu-id="1bc24-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bc24-104">语法</span><span class="sxs-lookup"><span data-stu-id="1bc24-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="1bc24-105">部件</span><span class="sxs-lookup"><span data-stu-id="1bc24-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="1bc24-106">必需。</span><span class="sxs-lookup"><span data-stu-id="1bc24-106">Required.</span></span> <span data-ttu-id="1bc24-107">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="1bc24-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="1bc24-108">必填，除非`–`运算符正在计算值为负。</span><span class="sxs-lookup"><span data-stu-id="1bc24-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="1bc24-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="1bc24-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="1bc24-110">结果</span><span class="sxs-lookup"><span data-stu-id="1bc24-110">Result</span></span>  
 <span data-ttu-id="1bc24-111">结果是之间的差异`expression1`并`expression2`，或的相反的值`expression1`。</span><span class="sxs-lookup"><span data-stu-id="1bc24-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="1bc24-112">结果数据类型为数值类型的数据类型的相应`expression1`和`expression2`。</span><span class="sxs-lookup"><span data-stu-id="1bc24-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="1bc24-113">请参阅中的"整数运算"表[数据类型的运算符结果](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。</span><span class="sxs-lookup"><span data-stu-id="1bc24-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="1bc24-114">支持的类型</span><span class="sxs-lookup"><span data-stu-id="1bc24-114">Supported Types</span></span>  
 <span data-ttu-id="1bc24-115">所有数值类型。</span><span class="sxs-lookup"><span data-stu-id="1bc24-115">All numeric types.</span></span> <span data-ttu-id="1bc24-116">这包括未签名和浮点类型和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="1bc24-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bc24-117">备注</span><span class="sxs-lookup"><span data-stu-id="1bc24-117">Remarks</span></span>  
 <span data-ttu-id="1bc24-118">以前，所示的语法中所示的第一个应用中`–`运算符是*二进制*减法算术运算符的两个数值表达式之间的差异。</span><span class="sxs-lookup"><span data-stu-id="1bc24-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="1bc24-119">在以前，所示的语法中所示的第二个使用情况`–`运算符是*一元*求反运算符的表达式的负值。</span><span class="sxs-lookup"><span data-stu-id="1bc24-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="1bc24-120">在这种情况下，求反运算组成反转的符号`expression1`，以便结果为正如果`expression1`为负。</span><span class="sxs-lookup"><span data-stu-id="1bc24-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="1bc24-121">如果任一表达式计算结果为[Nothing](../../../visual-basic/language-reference/nothing.md)，则`–`运算符将其视为零。</span><span class="sxs-lookup"><span data-stu-id="1bc24-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bc24-122">`–`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="1bc24-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1bc24-123">如果你的代码对此类的类或结构使用此运算符，请确保您了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="1bc24-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="1bc24-124">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="1bc24-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bc24-125">示例</span><span class="sxs-lookup"><span data-stu-id="1bc24-125">Example</span></span>  
 <span data-ttu-id="1bc24-126">下面的示例使用`–`运算符以计算并返回两个数字之间的差异，然后以对数字求反。</span><span class="sxs-lookup"><span data-stu-id="1bc24-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="1bc24-127">这些语句执行后`binaryResult`包含 124.45 和`unaryResult`包含 –334.90。</span><span class="sxs-lookup"><span data-stu-id="1bc24-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bc24-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="1bc24-128">See also</span></span>

- [<span data-ttu-id="1bc24-129">-= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1bc24-129">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="1bc24-130">算术运算符</span><span class="sxs-lookup"><span data-stu-id="1bc24-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="1bc24-131">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="1bc24-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="1bc24-132">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="1bc24-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="1bc24-133">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="1bc24-133">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
