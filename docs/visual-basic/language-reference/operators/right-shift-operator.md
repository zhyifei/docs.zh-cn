---
title: '>> 运算符（Visual Basic）'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: 337d651e831dc2ab132056f6e9a1f2b5300bf7f8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701332"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="acb00-102">> > 运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="acb00-102">>> Operator (Visual Basic)</span></span>
<span data-ttu-id="acb00-103">对位模式执行算术右移位运算。</span><span class="sxs-lookup"><span data-stu-id="acb00-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb00-104">语法</span><span class="sxs-lookup"><span data-stu-id="acb00-104">Syntax</span></span>  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="acb00-105">部件</span><span class="sxs-lookup"><span data-stu-id="acb00-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="acb00-106">必需。</span><span class="sxs-lookup"><span data-stu-id="acb00-106">Required.</span></span> <span data-ttu-id="acb00-107">整数数值。</span><span class="sxs-lookup"><span data-stu-id="acb00-107">Integral numeric value.</span></span> <span data-ttu-id="acb00-108">移位位模式的结果。</span><span class="sxs-lookup"><span data-stu-id="acb00-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="acb00-109">数据类型与的数据类型相同`pattern`。</span><span class="sxs-lookup"><span data-stu-id="acb00-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="acb00-110">必需。</span><span class="sxs-lookup"><span data-stu-id="acb00-110">Required.</span></span> <span data-ttu-id="acb00-111">整数数值表达式。</span><span class="sxs-lookup"><span data-stu-id="acb00-111">Integral numeric expression.</span></span> <span data-ttu-id="acb00-112">要移动的位模式。</span><span class="sxs-lookup"><span data-stu-id="acb00-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="acb00-113">数据类型`SByte`必须为整型类型（、 `UShort` `Integer` `Short` 、、`ULong`、、 `UInteger` 、或）。`Long` `Byte`</span><span class="sxs-lookup"><span data-stu-id="acb00-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="acb00-114">必需。</span><span class="sxs-lookup"><span data-stu-id="acb00-114">Required.</span></span> <span data-ttu-id="acb00-115">数值表达式。</span><span class="sxs-lookup"><span data-stu-id="acb00-115">Numeric expression.</span></span> <span data-ttu-id="acb00-116">要移位位模式的位数。</span><span class="sxs-lookup"><span data-stu-id="acb00-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="acb00-117">数据类型必须`Integer`为或扩大到`Integer`。</span><span class="sxs-lookup"><span data-stu-id="acb00-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acb00-118">备注</span><span class="sxs-lookup"><span data-stu-id="acb00-118">Remarks</span></span>  
 <span data-ttu-id="acb00-119">算术移位不是循环的，这意味着，不会在另一端重新引入结果的末尾以外的位。</span><span class="sxs-lookup"><span data-stu-id="acb00-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="acb00-120">在算术右移位中，将丢弃超出最右位位置的位，并将最左侧的（符号）位传播到左端空出的位位置。</span><span class="sxs-lookup"><span data-stu-id="acb00-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="acb00-121">这意味着，如果 `pattern` 的值为负值，则空出的位置设置为 1;否则，它们会被设置为零。</span><span class="sxs-lookup"><span data-stu-id="acb00-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="acb00-122">请注意，数据类型 `Byte`、`UShort`、`UInteger` 和 `ULong` 是无符号的，因此没有要传播的符号位。</span><span class="sxs-lookup"><span data-stu-id="acb00-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="acb00-123">如果 @no__t 为任何无符号类型，则空出的位置始终设置为零。</span><span class="sxs-lookup"><span data-stu-id="acb00-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="acb00-124">若要防止超过结果的移位量，请 Visual Basic 使用与 @no__t 的数据类型相对应的大小掩码来屏蔽 @no__t 的值。</span><span class="sxs-lookup"><span data-stu-id="acb00-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="acb00-125">这些值的二进制和均用于移位量。</span><span class="sxs-lookup"><span data-stu-id="acb00-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="acb00-126">大小掩码如下：</span><span class="sxs-lookup"><span data-stu-id="acb00-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="acb00-127">@No__t 的数据类型-0</span><span class="sxs-lookup"><span data-stu-id="acb00-127">Data type of `pattern`</span></span>|<span data-ttu-id="acb00-128">大小掩码（十进制）</span><span class="sxs-lookup"><span data-stu-id="acb00-128">Size mask (decimal)</span></span>|<span data-ttu-id="acb00-129">大小掩码（十六进制）</span><span class="sxs-lookup"><span data-stu-id="acb00-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="acb00-130">`SByte`， `Byte`</span><span class="sxs-lookup"><span data-stu-id="acb00-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="acb00-131">7</span><span class="sxs-lookup"><span data-stu-id="acb00-131">7</span></span>|<span data-ttu-id="acb00-132">& H00000007</span><span class="sxs-lookup"><span data-stu-id="acb00-132">&H00000007</span></span>|  
|<span data-ttu-id="acb00-133">`Short`， `UShort`</span><span class="sxs-lookup"><span data-stu-id="acb00-133">`Short`, `UShort`</span></span>|<span data-ttu-id="acb00-134">15</span><span class="sxs-lookup"><span data-stu-id="acb00-134">15</span></span>|<span data-ttu-id="acb00-135">& H0000000F</span><span class="sxs-lookup"><span data-stu-id="acb00-135">&H0000000F</span></span>|  
|<span data-ttu-id="acb00-136">`Integer`， `UInteger`</span><span class="sxs-lookup"><span data-stu-id="acb00-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="acb00-137">31</span><span class="sxs-lookup"><span data-stu-id="acb00-137">31</span></span>|<span data-ttu-id="acb00-138">& H0000001F</span><span class="sxs-lookup"><span data-stu-id="acb00-138">&H0000001F</span></span>|  
|<span data-ttu-id="acb00-139">`Long`， `ULong`</span><span class="sxs-lookup"><span data-stu-id="acb00-139">`Long`, `ULong`</span></span>|<span data-ttu-id="acb00-140">63</span><span class="sxs-lookup"><span data-stu-id="acb00-140">63</span></span>|<span data-ttu-id="acb00-141">& H0000003F</span><span class="sxs-lookup"><span data-stu-id="acb00-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="acb00-142">如果 @no__t 为零，`result` 的值与 @no__t 的值相同。</span><span class="sxs-lookup"><span data-stu-id="acb00-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="acb00-143">如果 `amount` 为负数，则将其视为无符号值，并使用适当的大小掩码掩码。</span><span class="sxs-lookup"><span data-stu-id="acb00-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="acb00-144">算术移位从不产生溢出异常。</span><span class="sxs-lookup"><span data-stu-id="acb00-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="acb00-145">重载</span><span class="sxs-lookup"><span data-stu-id="acb00-145">Overloading</span></span>  
 <span data-ttu-id="acb00-146">@No__t-0 运算符可*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="acb00-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="acb00-147">如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="acb00-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="acb00-148">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="acb00-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="acb00-149">示例</span><span class="sxs-lookup"><span data-stu-id="acb00-149">Example</span></span>  
 <span data-ttu-id="acb00-150">下面的示例使用 `>>` 运算符对整数值执行算术右移位运算。</span><span class="sxs-lookup"><span data-stu-id="acb00-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="acb00-151">结果始终与要移动的表达式的数据类型相同。</span><span class="sxs-lookup"><span data-stu-id="acb00-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 <span data-ttu-id="acb00-152">上述示例的结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="acb00-152">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="acb00-153">@no__t 为2560（0000 1010 0000 0000）。</span><span class="sxs-lookup"><span data-stu-id="acb00-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
- <span data-ttu-id="acb00-154">@no__t 为160（0000 0000 1010 0000）。</span><span class="sxs-lookup"><span data-stu-id="acb00-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
- <span data-ttu-id="acb00-155">@no__t 为2（0000 0000 0000 0010）。</span><span class="sxs-lookup"><span data-stu-id="acb00-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
- <span data-ttu-id="acb00-156">@no__t 为640（0000 0010 1000 0000）。</span><span class="sxs-lookup"><span data-stu-id="acb00-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
- <span data-ttu-id="acb00-157">@no__t 为0（向右移动15个位置）。</span><span class="sxs-lookup"><span data-stu-id="acb00-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="acb00-158">@No__t 的移位量计算为18和15，这等于2。</span><span class="sxs-lookup"><span data-stu-id="acb00-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="acb00-159">下面的示例演示如何对负值进行算术移位运算。</span><span class="sxs-lookup"><span data-stu-id="acb00-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 <span data-ttu-id="acb00-160">上述示例的结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="acb00-160">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="acb00-161">`negresult1` 为-512 （1111 1110 0000 0000）。</span><span class="sxs-lookup"><span data-stu-id="acb00-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
- <span data-ttu-id="acb00-162">`negresult2` 为-1 （传播符号位）。</span><span class="sxs-lookup"><span data-stu-id="acb00-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb00-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="acb00-163">See also</span></span>

- [<span data-ttu-id="acb00-164">移位运算符</span><span class="sxs-lookup"><span data-stu-id="acb00-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="acb00-165">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="acb00-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="acb00-166">>>= 运算符</span><span class="sxs-lookup"><span data-stu-id="acb00-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [<span data-ttu-id="acb00-167">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="acb00-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="acb00-168">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="acb00-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="acb00-169">Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="acb00-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
