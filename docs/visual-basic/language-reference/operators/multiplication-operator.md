---
title: '* 运算符 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: e723667b6397fe758ae2f33babe27c0e41887aab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641169"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="f2b66-102">\* 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2b66-102">\* Operator (Visual Basic)</span></span>
<span data-ttu-id="f2b66-103">将两个数字相乘。</span><span class="sxs-lookup"><span data-stu-id="f2b66-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2b66-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2b66-104">Syntax</span></span>  
  
```  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="f2b66-105">部件</span><span class="sxs-lookup"><span data-stu-id="f2b66-105">Parts</span></span>  
  
|<span data-ttu-id="f2b66-106">术语</span><span class="sxs-lookup"><span data-stu-id="f2b66-106">Term</span></span>|<span data-ttu-id="f2b66-107">定义</span><span class="sxs-lookup"><span data-stu-id="f2b66-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="f2b66-108">必需。</span><span class="sxs-lookup"><span data-stu-id="f2b66-108">Required.</span></span> <span data-ttu-id="f2b66-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="f2b66-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="f2b66-110">必需。</span><span class="sxs-lookup"><span data-stu-id="f2b66-110">Required.</span></span> <span data-ttu-id="f2b66-111">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="f2b66-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="f2b66-112">结果</span><span class="sxs-lookup"><span data-stu-id="f2b66-112">Result</span></span>  
 <span data-ttu-id="f2b66-113">结果是乘积`number1`和`number2`。</span><span class="sxs-lookup"><span data-stu-id="f2b66-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="f2b66-114">支持的类型</span><span class="sxs-lookup"><span data-stu-id="f2b66-114">Supported Types</span></span>  
 <span data-ttu-id="f2b66-115">所有数值类型，包括未签名和浮点类型和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="f2b66-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2b66-116">备注</span><span class="sxs-lookup"><span data-stu-id="f2b66-116">Remarks</span></span>  
 <span data-ttu-id="f2b66-117">结果的数据类型取决于操作数的类型。</span><span class="sxs-lookup"><span data-stu-id="f2b66-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="f2b66-118">下表显示了如何确定结果的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f2b66-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="f2b66-119">操作数数据类型</span><span class="sxs-lookup"><span data-stu-id="f2b66-119">Operand data types</span></span>|<span data-ttu-id="f2b66-120">结果数据类型</span><span class="sxs-lookup"><span data-stu-id="f2b66-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="f2b66-121">这两个表达式是整数数据类型 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)，[字节](../../../visual-basic/language-reference/data-types/byte-data-type.md)，[短](../../../visual-basic/language-reference/data-types/short-data-type.md)， [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)，[整数](../../../visual-basic/language-reference/data-types/integer-data-type.md)，[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)，[长](../../../visual-basic/language-reference/data-types/long-data-type.md)， [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="f2b66-121">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="f2b66-122">适用于数据类型的数值数据类型`number1`和`number2`。</span><span class="sxs-lookup"><span data-stu-id="f2b66-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="f2b66-123">请参阅中的"整数运算"表[数据类型的运算符结果](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。</span><span class="sxs-lookup"><span data-stu-id="f2b66-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="f2b66-124">两个表达式均[十进制](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="f2b66-124">Both expressions are [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="f2b66-125">两个表达式均[单一](../../../visual-basic/language-reference/data-types/single-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="f2b66-125">Both expressions are [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="f2b66-126">其中任何一个表达式是浮点数据类型 (`Single`或[双](../../../visual-basic/language-reference/data-types/double-data-type.md))，但不是能同时`Single`(请注意`Decimal`不是浮点数据类型)</span><span class="sxs-lookup"><span data-stu-id="f2b66-126">Either expression is a floating-point data type (`Single` or [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="f2b66-127">如果表达式计算结果为[Nothing](../../../visual-basic/language-reference/nothing.md)，它将被视为零。</span><span class="sxs-lookup"><span data-stu-id="f2b66-127">If an expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f2b66-128">重载</span><span class="sxs-lookup"><span data-stu-id="f2b66-128">Overloading</span></span>  
 <span data-ttu-id="f2b66-129">`*`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="f2b66-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f2b66-130">如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="f2b66-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f2b66-131">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="f2b66-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2b66-132">示例</span><span class="sxs-lookup"><span data-stu-id="f2b66-132">Example</span></span>  
 <span data-ttu-id="f2b66-133">此示例使用`*`运算符将两个数相乘。</span><span class="sxs-lookup"><span data-stu-id="f2b66-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="f2b66-134">结果是两个操作数的乘积。</span><span class="sxs-lookup"><span data-stu-id="f2b66-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f2b66-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2b66-135">See also</span></span>
- [<span data-ttu-id="f2b66-136">\*= 运算符</span><span class="sxs-lookup"><span data-stu-id="f2b66-136">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="f2b66-137">算术运算符</span><span class="sxs-lookup"><span data-stu-id="f2b66-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="f2b66-138">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="f2b66-138">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f2b66-139">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="f2b66-139">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f2b66-140">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="f2b66-140">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
