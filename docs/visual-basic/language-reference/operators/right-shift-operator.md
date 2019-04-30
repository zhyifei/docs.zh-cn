---
title: '>> 运算符 (Visual Basic)'
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
ms.openlocfilehash: 8803dc2e25edde756958a243d429dd30c5c78bcf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053283"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="c3d86-102">>> 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3d86-102">>> Operator (Visual Basic)</span></span>
<span data-ttu-id="c3d86-103">对位模式执行算术右移位运算。</span><span class="sxs-lookup"><span data-stu-id="c3d86-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3d86-104">语法</span><span class="sxs-lookup"><span data-stu-id="c3d86-104">Syntax</span></span>  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="c3d86-105">部件</span><span class="sxs-lookup"><span data-stu-id="c3d86-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c3d86-106">必需。</span><span class="sxs-lookup"><span data-stu-id="c3d86-106">Required.</span></span> <span data-ttu-id="c3d86-107">整型数值。</span><span class="sxs-lookup"><span data-stu-id="c3d86-107">Integral numeric value.</span></span> <span data-ttu-id="c3d86-108">移位的位模式的结果。</span><span class="sxs-lookup"><span data-stu-id="c3d86-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="c3d86-109">数据类型是相同的`pattern`。</span><span class="sxs-lookup"><span data-stu-id="c3d86-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="c3d86-110">必需。</span><span class="sxs-lookup"><span data-stu-id="c3d86-110">Required.</span></span> <span data-ttu-id="c3d86-111">整型数值表达式。</span><span class="sxs-lookup"><span data-stu-id="c3d86-111">Integral numeric expression.</span></span> <span data-ttu-id="c3d86-112">要移动的位模式。</span><span class="sxs-lookup"><span data-stu-id="c3d86-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="c3d86-113">数据类型必须为整型类型 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，或`ULong`)。</span><span class="sxs-lookup"><span data-stu-id="c3d86-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="c3d86-114">必需。</span><span class="sxs-lookup"><span data-stu-id="c3d86-114">Required.</span></span> <span data-ttu-id="c3d86-115">数值表达式。</span><span class="sxs-lookup"><span data-stu-id="c3d86-115">Numeric expression.</span></span> <span data-ttu-id="c3d86-116">要移位的位模式的比特数。</span><span class="sxs-lookup"><span data-stu-id="c3d86-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="c3d86-117">数据类型必须是`Integer`或扩大到`Integer`。</span><span class="sxs-lookup"><span data-stu-id="c3d86-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3d86-118">备注</span><span class="sxs-lookup"><span data-stu-id="c3d86-118">Remarks</span></span>  
 <span data-ttu-id="c3d86-119">算术移位不是循环，这意味着移出结果的一端的数位另一端不重新移入。</span><span class="sxs-lookup"><span data-stu-id="c3d86-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="c3d86-120">在算术右移位运算移出最右侧位位置的位将被丢弃，并最左侧 （符号） 位传播到左侧而空出的位位置。</span><span class="sxs-lookup"><span data-stu-id="c3d86-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="c3d86-121">这意味着，如果`pattern`为负值，空出的位置设置为 1; 否则设置为零。</span><span class="sxs-lookup"><span data-stu-id="c3d86-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="c3d86-122">请注意，数据类型`Byte`， `UShort`， `UInteger`，和`ULong`是无符号整数，因此没有任何符号位传播。</span><span class="sxs-lookup"><span data-stu-id="c3d86-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="c3d86-123">如果`pattern`的任何无符号类型，空出的位置始终设置为零。</span><span class="sxs-lookup"><span data-stu-id="c3d86-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="c3d86-124">若要防止移位的结果可以容纳超出的位数，Visual Basic 使用的值`amount`对应的数据类型大小掩码`pattern`。</span><span class="sxs-lookup"><span data-stu-id="c3d86-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="c3d86-125">这些值的二进制 AND 用于位移量。</span><span class="sxs-lookup"><span data-stu-id="c3d86-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="c3d86-126">大小掩码如下所示：</span><span class="sxs-lookup"><span data-stu-id="c3d86-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="c3d86-127">数据类型 `pattern`</span><span class="sxs-lookup"><span data-stu-id="c3d86-127">Data type of `pattern`</span></span>|<span data-ttu-id="c3d86-128">大小掩码 （十进制）</span><span class="sxs-lookup"><span data-stu-id="c3d86-128">Size mask (decimal)</span></span>|<span data-ttu-id="c3d86-129">大小掩码 （十六进制）</span><span class="sxs-lookup"><span data-stu-id="c3d86-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="c3d86-130">`SByte`， `Byte`</span><span class="sxs-lookup"><span data-stu-id="c3d86-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="c3d86-131">7</span><span class="sxs-lookup"><span data-stu-id="c3d86-131">7</span></span>|<span data-ttu-id="c3d86-132">&H00000007</span><span class="sxs-lookup"><span data-stu-id="c3d86-132">&H00000007</span></span>|  
|<span data-ttu-id="c3d86-133">`Short`， `UShort`</span><span class="sxs-lookup"><span data-stu-id="c3d86-133">`Short`, `UShort`</span></span>|<span data-ttu-id="c3d86-134">15</span><span class="sxs-lookup"><span data-stu-id="c3d86-134">15</span></span>|<span data-ttu-id="c3d86-135">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="c3d86-135">&H0000000F</span></span>|  
|<span data-ttu-id="c3d86-136">`Integer`， `UInteger`</span><span class="sxs-lookup"><span data-stu-id="c3d86-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="c3d86-137">31</span><span class="sxs-lookup"><span data-stu-id="c3d86-137">31</span></span>|<span data-ttu-id="c3d86-138">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="c3d86-138">&H0000001F</span></span>|  
|<span data-ttu-id="c3d86-139">`Long`， `ULong`</span><span class="sxs-lookup"><span data-stu-id="c3d86-139">`Long`, `ULong`</span></span>|<span data-ttu-id="c3d86-140">63</span><span class="sxs-lookup"><span data-stu-id="c3d86-140">63</span></span>|<span data-ttu-id="c3d86-141">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="c3d86-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="c3d86-142">如果`amount`为零的值`result`的值是否相同`pattern`。</span><span class="sxs-lookup"><span data-stu-id="c3d86-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="c3d86-143">如果`amount`是负数，它是作为无符号值，使用适当的大小掩码进行屏蔽。</span><span class="sxs-lookup"><span data-stu-id="c3d86-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="c3d86-144">算术移位永远不会产生溢出异常。</span><span class="sxs-lookup"><span data-stu-id="c3d86-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c3d86-145">重载</span><span class="sxs-lookup"><span data-stu-id="c3d86-145">Overloading</span></span>  
 <span data-ttu-id="c3d86-146">`>>`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="c3d86-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c3d86-147">如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="c3d86-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c3d86-148">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="c3d86-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3d86-149">示例</span><span class="sxs-lookup"><span data-stu-id="c3d86-149">Example</span></span>  
 <span data-ttu-id="c3d86-150">下面的示例使用`>>`要对整数值执行算术右移位运算符。</span><span class="sxs-lookup"><span data-stu-id="c3d86-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="c3d86-151">结果始终具有相同的数据类型的被移位的表达式。</span><span class="sxs-lookup"><span data-stu-id="c3d86-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 <span data-ttu-id="c3d86-152">前面的示例中的结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="c3d86-152">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="c3d86-153">`result1` 是 2560 (0000 0000 0000 1010年)。</span><span class="sxs-lookup"><span data-stu-id="c3d86-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
- <span data-ttu-id="c3d86-154">`result2` 为 160 (0000 0000 1010年 0000)。</span><span class="sxs-lookup"><span data-stu-id="c3d86-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
- <span data-ttu-id="c3d86-155">`result3` 为 2 (0000 0000 0000 0010)。</span><span class="sxs-lookup"><span data-stu-id="c3d86-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
- <span data-ttu-id="c3d86-156">`result4` 为 640 (0000 0010 1000年 0000)。</span><span class="sxs-lookup"><span data-stu-id="c3d86-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
- <span data-ttu-id="c3d86-157">`result5` 为 0 （向右移动 15 位）。</span><span class="sxs-lookup"><span data-stu-id="c3d86-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="c3d86-158">移位量`result4`计算为 18 和 15，等于 2。</span><span class="sxs-lookup"><span data-stu-id="c3d86-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="c3d86-159">下面的示例演示上一个负值数学移位。</span><span class="sxs-lookup"><span data-stu-id="c3d86-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 <span data-ttu-id="c3d86-160">前面的示例中的结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="c3d86-160">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="c3d86-161">`negresult1` 是-512 (1111年 1110年 0000 0000)。</span><span class="sxs-lookup"><span data-stu-id="c3d86-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
- <span data-ttu-id="c3d86-162">`negresult2` 为-1 （传播符号位）。</span><span class="sxs-lookup"><span data-stu-id="c3d86-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3d86-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3d86-163">See also</span></span>

- [<span data-ttu-id="c3d86-164">移位运算符</span><span class="sxs-lookup"><span data-stu-id="c3d86-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="c3d86-165">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="c3d86-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="c3d86-166">>>= 运算符</span><span class="sxs-lookup"><span data-stu-id="c3d86-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [<span data-ttu-id="c3d86-167">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="c3d86-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c3d86-168">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="c3d86-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="c3d86-169">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="c3d86-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
