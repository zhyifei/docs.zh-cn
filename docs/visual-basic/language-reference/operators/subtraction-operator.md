---
title: '- 运算符（Visual Basic）'
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
ms.openlocfilehash: eb34b34986613f36b624c43c04f98390ffba4fe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965868"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="10b8e-102">- 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10b8e-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="10b8e-103">返回数值表达式的两个数值表达式或负值之间的差。</span><span class="sxs-lookup"><span data-stu-id="10b8e-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10b8e-104">语法</span><span class="sxs-lookup"><span data-stu-id="10b8e-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="10b8e-105">部件</span><span class="sxs-lookup"><span data-stu-id="10b8e-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="10b8e-106">必需。</span><span class="sxs-lookup"><span data-stu-id="10b8e-106">Required.</span></span> <span data-ttu-id="10b8e-107">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="10b8e-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="10b8e-108">必需， `–`除非操作员计算负值。</span><span class="sxs-lookup"><span data-stu-id="10b8e-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="10b8e-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="10b8e-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="10b8e-110">结果</span><span class="sxs-lookup"><span data-stu-id="10b8e-110">Result</span></span>  
 <span data-ttu-id="10b8e-111">结果是`expression1`与`expression2`的差`expression1`或的求反值。</span><span class="sxs-lookup"><span data-stu-id="10b8e-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="10b8e-112">Result 数据类型是适用于`expression1`和`expression2`的数据类型的数值类型。</span><span class="sxs-lookup"><span data-stu-id="10b8e-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="10b8e-113">请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "整数算法" 表。</span><span class="sxs-lookup"><span data-stu-id="10b8e-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="10b8e-114">支持的类型</span><span class="sxs-lookup"><span data-stu-id="10b8e-114">Supported Types</span></span>  
 <span data-ttu-id="10b8e-115">所有数值类型。</span><span class="sxs-lookup"><span data-stu-id="10b8e-115">All numeric types.</span></span> <span data-ttu-id="10b8e-116">这包括无符号和浮点类型和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="10b8e-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10b8e-117">备注</span><span class="sxs-lookup"><span data-stu-id="10b8e-117">Remarks</span></span>  
 <span data-ttu-id="10b8e-118">在前面所示的语法中所示的第一个`–`用法中，运算符是两个数值表达式之差的*二进制*算术减法运算符。</span><span class="sxs-lookup"><span data-stu-id="10b8e-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="10b8e-119">在前面所示的语法中所示的第二`–`个用法中，运算符是表达式的负值的*一元*求反运算符。</span><span class="sxs-lookup"><span data-stu-id="10b8e-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="10b8e-120">在这种意义上，否定包含反转的符号`expression1` ，因此如果`expression1`为负，则结果为正。</span><span class="sxs-lookup"><span data-stu-id="10b8e-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="10b8e-121">如果其中一个表达式的计算结果为 [Nothing](../../../visual-basic/language-reference/nothing.md)，则 `–` 运算符将其视为零。</span><span class="sxs-lookup"><span data-stu-id="10b8e-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10b8e-122">运算符可以重载，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 `–`</span><span class="sxs-lookup"><span data-stu-id="10b8e-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="10b8e-123">如果代码对这样的类或结构使用此运算符，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="10b8e-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="10b8e-124">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="10b8e-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10b8e-125">示例</span><span class="sxs-lookup"><span data-stu-id="10b8e-125">Example</span></span>  
 <span data-ttu-id="10b8e-126">下面的示例使用`–`运算符计算并返回两个数字之间的差，然后对数字求反。</span><span class="sxs-lookup"><span data-stu-id="10b8e-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="10b8e-127">执行这些语句后， `binaryResult`包含124.45， `unaryResult`包含–334.90。</span><span class="sxs-lookup"><span data-stu-id="10b8e-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10b8e-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="10b8e-128">See also</span></span>

- [<span data-ttu-id="10b8e-129">-= 运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="10b8e-129">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="10b8e-130">算术运算符</span><span class="sxs-lookup"><span data-stu-id="10b8e-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="10b8e-131">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="10b8e-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="10b8e-132">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="10b8e-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="10b8e-133">Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="10b8e-133">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
