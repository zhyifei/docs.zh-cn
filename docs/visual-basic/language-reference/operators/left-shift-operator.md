---
title: << 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 327d0e5cbd1ebcc43bd47fb068f4513940c2165a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350984"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ae778-102">\<\< Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae778-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="ae778-103">Performs an arithmetic left shift on a bit pattern.</span><span class="sxs-lookup"><span data-stu-id="ae778-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae778-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae778-104">Syntax</span></span>  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="ae778-105">部件</span><span class="sxs-lookup"><span data-stu-id="ae778-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="ae778-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="ae778-106">Required.</span></span> <span data-ttu-id="ae778-107">Integral numeric value.</span><span class="sxs-lookup"><span data-stu-id="ae778-107">Integral numeric value.</span></span> <span data-ttu-id="ae778-108">The result of shifting the bit pattern.</span><span class="sxs-lookup"><span data-stu-id="ae778-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="ae778-109">The data type is the same as that of `pattern`.</span><span class="sxs-lookup"><span data-stu-id="ae778-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="ae778-110">必须的。</span><span class="sxs-lookup"><span data-stu-id="ae778-110">Required.</span></span> <span data-ttu-id="ae778-111">Integral numeric expression.</span><span class="sxs-lookup"><span data-stu-id="ae778-111">Integral numeric expression.</span></span> <span data-ttu-id="ae778-112">The bit pattern to be shifted.</span><span class="sxs-lookup"><span data-stu-id="ae778-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="ae778-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span><span class="sxs-lookup"><span data-stu-id="ae778-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="ae778-114">必须的。</span><span class="sxs-lookup"><span data-stu-id="ae778-114">Required.</span></span> <span data-ttu-id="ae778-115">Numeric expression.</span><span class="sxs-lookup"><span data-stu-id="ae778-115">Numeric expression.</span></span> <span data-ttu-id="ae778-116">The number of bits to shift the bit pattern.</span><span class="sxs-lookup"><span data-stu-id="ae778-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="ae778-117">The data type must be `Integer` or widen to `Integer`.</span><span class="sxs-lookup"><span data-stu-id="ae778-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae778-118">备注</span><span class="sxs-lookup"><span data-stu-id="ae778-118">Remarks</span></span>  
 <span data-ttu-id="ae778-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span><span class="sxs-lookup"><span data-stu-id="ae778-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="ae778-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span><span class="sxs-lookup"><span data-stu-id="ae778-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="ae778-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span><span class="sxs-lookup"><span data-stu-id="ae778-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="ae778-122">The binary AND of these values is used for the shift amount.</span><span class="sxs-lookup"><span data-stu-id="ae778-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="ae778-123">The size masks are as follows:</span><span class="sxs-lookup"><span data-stu-id="ae778-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="ae778-124">Data type of `pattern`</span><span class="sxs-lookup"><span data-stu-id="ae778-124">Data type of `pattern`</span></span>|<span data-ttu-id="ae778-125">Size mask (decimal)</span><span class="sxs-lookup"><span data-stu-id="ae778-125">Size mask (decimal)</span></span>|<span data-ttu-id="ae778-126">Size mask (hexadecimal)</span><span class="sxs-lookup"><span data-stu-id="ae778-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="ae778-127">`SByte`，`Byte`</span><span class="sxs-lookup"><span data-stu-id="ae778-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="ae778-128">7</span><span class="sxs-lookup"><span data-stu-id="ae778-128">7</span></span>|<span data-ttu-id="ae778-129">&H00000007</span><span class="sxs-lookup"><span data-stu-id="ae778-129">&H00000007</span></span>|  
|<span data-ttu-id="ae778-130">`Short`，`UShort`</span><span class="sxs-lookup"><span data-stu-id="ae778-130">`Short`, `UShort`</span></span>|<span data-ttu-id="ae778-131">15</span><span class="sxs-lookup"><span data-stu-id="ae778-131">15</span></span>|<span data-ttu-id="ae778-132">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="ae778-132">&H0000000F</span></span>|  
|<span data-ttu-id="ae778-133">`Integer`，`UInteger`</span><span class="sxs-lookup"><span data-stu-id="ae778-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="ae778-134">31</span><span class="sxs-lookup"><span data-stu-id="ae778-134">31</span></span>|<span data-ttu-id="ae778-135">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="ae778-135">&H0000001F</span></span>|  
|<span data-ttu-id="ae778-136">`Long`，`ULong`</span><span class="sxs-lookup"><span data-stu-id="ae778-136">`Long`, `ULong`</span></span>|<span data-ttu-id="ae778-137">63</span><span class="sxs-lookup"><span data-stu-id="ae778-137">63</span></span>|<span data-ttu-id="ae778-138">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="ae778-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="ae778-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span><span class="sxs-lookup"><span data-stu-id="ae778-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="ae778-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span><span class="sxs-lookup"><span data-stu-id="ae778-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="ae778-141">Arithmetic shifts never generate overflow exceptions.</span><span class="sxs-lookup"><span data-stu-id="ae778-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae778-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span><span class="sxs-lookup"><span data-stu-id="ae778-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ae778-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span><span class="sxs-lookup"><span data-stu-id="ae778-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="ae778-144">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="ae778-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae778-145">示例</span><span class="sxs-lookup"><span data-stu-id="ae778-145">Example</span></span>  
 <span data-ttu-id="ae778-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span><span class="sxs-lookup"><span data-stu-id="ae778-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="ae778-147">The result always has the same data type as that of the expression being shifted.</span><span class="sxs-lookup"><span data-stu-id="ae778-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="ae778-148">The results of the previous example are as follows:</span><span class="sxs-lookup"><span data-stu-id="ae778-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="ae778-149">`result1` is 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="ae778-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="ae778-150">`result2` is 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="ae778-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="ae778-151">`result3` is -32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="ae778-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="ae778-152">`result4` is 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="ae778-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="ae778-153">`result5` is 0 (shifted 15 places to the left).</span><span class="sxs-lookup"><span data-stu-id="ae778-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="ae778-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span><span class="sxs-lookup"><span data-stu-id="ae778-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae778-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae778-155">See also</span></span>

- [<span data-ttu-id="ae778-156">移位运算符</span><span class="sxs-lookup"><span data-stu-id="ae778-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="ae778-157">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="ae778-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="ae778-158"><<= 运算符</span><span class="sxs-lookup"><span data-stu-id="ae778-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="ae778-159">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="ae778-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="ae778-160">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="ae778-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="ae778-161">Arithmetic Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae778-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
