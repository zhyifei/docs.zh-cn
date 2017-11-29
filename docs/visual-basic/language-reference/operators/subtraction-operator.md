---
title: "- 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ffb7c96fe95e73dc857a15608df94ed8468f9df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="db4f1-102">- 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db4f1-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="db4f1-103">返回两个数值表达式或数值表达式的负值之间的差异。</span><span class="sxs-lookup"><span data-stu-id="db4f1-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db4f1-104">语法</span><span class="sxs-lookup"><span data-stu-id="db4f1-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="db4f1-105">部件</span><span class="sxs-lookup"><span data-stu-id="db4f1-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="db4f1-106">必需。</span><span class="sxs-lookup"><span data-stu-id="db4f1-106">Required.</span></span> <span data-ttu-id="db4f1-107">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="db4f1-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="db4f1-108">必填，除非`–`运算符正在计算值为负。</span><span class="sxs-lookup"><span data-stu-id="db4f1-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="db4f1-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="db4f1-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="db4f1-110">结果</span><span class="sxs-lookup"><span data-stu-id="db4f1-110">Result</span></span>  
 <span data-ttu-id="db4f1-111">结果之间的区别是`expression1`和`expression2`，或的相反的值`expression1`。</span><span class="sxs-lookup"><span data-stu-id="db4f1-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="db4f1-112">结果数据类型为数值类型适用于数据类型的`expression1`和`expression2`。</span><span class="sxs-lookup"><span data-stu-id="db4f1-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="db4f1-113">请参阅中的"整数算法"表[运算符结果的数据类型的](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。</span><span class="sxs-lookup"><span data-stu-id="db4f1-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="db4f1-114">支持的类型</span><span class="sxs-lookup"><span data-stu-id="db4f1-114">Supported Types</span></span>  
 <span data-ttu-id="db4f1-115">所有数值类型。</span><span class="sxs-lookup"><span data-stu-id="db4f1-115">All numeric types.</span></span> <span data-ttu-id="db4f1-116">这包括的无符号和浮点类型和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="db4f1-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db4f1-117">备注</span><span class="sxs-lookup"><span data-stu-id="db4f1-117">Remarks</span></span>  
 <span data-ttu-id="db4f1-118">在以前，所示的语法中所示的第一个应用`–`运算符是*二进制*算术减法运算符，用于两个数值表达式之间的差异。</span><span class="sxs-lookup"><span data-stu-id="db4f1-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="db4f1-119">在中以前，所示的语法中所示的第二个应用`–`运算符是*一元*求反运算符的表达式的负值。</span><span class="sxs-lookup"><span data-stu-id="db4f1-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="db4f1-120">在这个意义上来说，该向量组成反转的符号`expression1`以便则结果为正如果`expression1`为负。</span><span class="sxs-lookup"><span data-stu-id="db4f1-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="db4f1-121">如果其中任何一个表达式的计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)、`–`运算符会将其视为零。</span><span class="sxs-lookup"><span data-stu-id="db4f1-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db4f1-122">`–`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="db4f1-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="db4f1-123">如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="db4f1-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="db4f1-124">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="db4f1-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="db4f1-125">示例</span><span class="sxs-lookup"><span data-stu-id="db4f1-125">Example</span></span>  
 <span data-ttu-id="db4f1-126">下面的示例使用`–`运算符计算并返回两个数字之间的差异，然后进行求反运算的一个数字。</span><span class="sxs-lookup"><span data-stu-id="db4f1-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 <span data-ttu-id="db4f1-127">这些语句执行后`binaryResult`包含 124.45 和`unaryResult`包含 –334.90。</span><span class="sxs-lookup"><span data-stu-id="db4f1-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db4f1-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db4f1-128">See Also</span></span>  
 <span data-ttu-id="db4f1-129">[-= 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md)</span><span class="sxs-lookup"><span data-stu-id="db4f1-129">[-= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)</span></span>  
 [<span data-ttu-id="db4f1-130">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="db4f1-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="db4f1-131">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="db4f1-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="db4f1-132">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="db4f1-132">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
