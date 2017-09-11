---
title: "- 运算符 (Visual Basic) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Negate
- vb.-
dev_langs:
- VB
helpviewer_keywords:
- '- operator [Visual Basic]'
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator
- operators [Visual Basic], arithmetic
- subtraction operator, syntax
- arithmetic operators, subtraction
- difference operator
- math operators
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
caps.latest.revision: 14
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: eb9b8e94877cce9aacde69c5f555f4a7f4a9ad7c
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---
# <a name="--operator-visual-basic"></a><span data-ttu-id="2aef8-102">- 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2aef8-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="2aef8-103">返回两个数值表达式或数值表达式的负值之间的差异。</span><span class="sxs-lookup"><span data-stu-id="2aef8-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aef8-104">语法</span><span class="sxs-lookup"><span data-stu-id="2aef8-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="2aef8-105">部件</span><span class="sxs-lookup"><span data-stu-id="2aef8-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="2aef8-106">必需。</span><span class="sxs-lookup"><span data-stu-id="2aef8-106">Required.</span></span> <span data-ttu-id="2aef8-107">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="2aef8-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="2aef8-108">必需，除非`–`运算符正在计算值为负。</span><span class="sxs-lookup"><span data-stu-id="2aef8-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="2aef8-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="2aef8-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="2aef8-110">结果</span><span class="sxs-lookup"><span data-stu-id="2aef8-110">Result</span></span>  
 <span data-ttu-id="2aef8-111">结果之间的区别是`expression1`和`expression2`，或的相反的值`expression1`。</span><span class="sxs-lookup"><span data-stu-id="2aef8-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="2aef8-112">结果数据类型为数值类型适用于数据类型的`expression1`和`expression2`。</span><span class="sxs-lookup"><span data-stu-id="2aef8-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="2aef8-113">请参阅中的"整数算法"表[运算符结果的数据类型的](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。</span><span class="sxs-lookup"><span data-stu-id="2aef8-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="2aef8-114">支持的类型</span><span class="sxs-lookup"><span data-stu-id="2aef8-114">Supported Types</span></span>  
 <span data-ttu-id="2aef8-115">所有数值类型。</span><span class="sxs-lookup"><span data-stu-id="2aef8-115">All numeric types.</span></span> <span data-ttu-id="2aef8-116">这包括未签名和浮点类型和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="2aef8-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2aef8-117">备注</span><span class="sxs-lookup"><span data-stu-id="2aef8-117">Remarks</span></span>  
 <span data-ttu-id="2aef8-118">在以前，所示的语法中所示的第一个应用`–`运算符是*二进制*算术减法运算符，用于两个数值表达式之间的差异。</span><span class="sxs-lookup"><span data-stu-id="2aef8-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="2aef8-119">在第二个用法中以前，所示的语法中所示`–`运算符是*一元*求反运算符用于计算表达式的负值。</span><span class="sxs-lookup"><span data-stu-id="2aef8-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="2aef8-120">在这个意义上来说，该向量组成反转的符号`expression1`以便则结果为正如果`expression1`为负。</span><span class="sxs-lookup"><span data-stu-id="2aef8-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="2aef8-121">如果其中任何一个表达式的计算结果为[Nothing](../../../visual-basic/language-reference/nothing.md)、`–`运算符将其视为零。</span><span class="sxs-lookup"><span data-stu-id="2aef8-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2aef8-122">`–`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="2aef8-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="2aef8-123">如果您的代码对这样的类或结构中使用此运算符，请确保您了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="2aef8-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="2aef8-124">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="2aef8-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aef8-125">示例</span><span class="sxs-lookup"><span data-stu-id="2aef8-125">Example</span></span>  
 <span data-ttu-id="2aef8-126">下面的示例使用`–`运算符计算并返回两个数字之间的差，然后进行求反运算的一个数字。</span><span class="sxs-lookup"><span data-stu-id="2aef8-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 <span data-ttu-id="2aef8-127">[!code-vb[VbVbalrOperators #&10;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2aef8-127">[!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="2aef8-128">这些语句执行后`binaryResult`包含 124.45 和`unaryResult`包含 –334.90。</span><span class="sxs-lookup"><span data-stu-id="2aef8-128">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aef8-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2aef8-129">See Also</span></span>  
 <span data-ttu-id="2aef8-130">[-= 运算符 (Visual Basic 中)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
 [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="2aef8-130">[-= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="2aef8-131"> [在 Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="2aef8-131"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="2aef8-132"> [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="2aef8-132"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="2aef8-133"> [在 Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)</span><span class="sxs-lookup"><span data-stu-id="2aef8-133"> [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)</span></span>

