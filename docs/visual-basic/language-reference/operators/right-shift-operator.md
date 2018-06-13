---
title: '&gt;&gt; 运算符 (Visual Basic)'
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
ms.openlocfilehash: 9bb8e82b3f5451417fe1867d08b7601ee1acb036
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605402"
---
# <a name="gtgt-operator-visual-basic"></a><span data-ttu-id="68b74-102">&gt;&gt; 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68b74-102">&gt;&gt; Operator (Visual Basic)</span></span>
<span data-ttu-id="68b74-103">对位模式执行算术右移位运算。</span><span class="sxs-lookup"><span data-stu-id="68b74-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68b74-104">语法</span><span class="sxs-lookup"><span data-stu-id="68b74-104">Syntax</span></span>  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="68b74-105">部件</span><span class="sxs-lookup"><span data-stu-id="68b74-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="68b74-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="68b74-106">Required.</span></span> <span data-ttu-id="68b74-107">整型数值。</span><span class="sxs-lookup"><span data-stu-id="68b74-107">Integral numeric value.</span></span> <span data-ttu-id="68b74-108">移位位模式的结果。</span><span class="sxs-lookup"><span data-stu-id="68b74-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="68b74-109">数据类型是相同的`pattern`。</span><span class="sxs-lookup"><span data-stu-id="68b74-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="68b74-110">必须的。</span><span class="sxs-lookup"><span data-stu-id="68b74-110">Required.</span></span> <span data-ttu-id="68b74-111">整型数值表达式。</span><span class="sxs-lookup"><span data-stu-id="68b74-111">Integral numeric expression.</span></span> <span data-ttu-id="68b74-112">要移动的位模式。</span><span class="sxs-lookup"><span data-stu-id="68b74-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="68b74-113">数据类型必须为整数类型 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，或`ULong`)。</span><span class="sxs-lookup"><span data-stu-id="68b74-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="68b74-114">必须的。</span><span class="sxs-lookup"><span data-stu-id="68b74-114">Required.</span></span> <span data-ttu-id="68b74-115">数值表达式。</span><span class="sxs-lookup"><span data-stu-id="68b74-115">Numeric expression.</span></span> <span data-ttu-id="68b74-116">要位移位模式的位数数。</span><span class="sxs-lookup"><span data-stu-id="68b74-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="68b74-117">数据类型必须为`Integer`或扩大到`Integer`。</span><span class="sxs-lookup"><span data-stu-id="68b74-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68b74-118">备注</span><span class="sxs-lookup"><span data-stu-id="68b74-118">Remarks</span></span>  
 <span data-ttu-id="68b74-119">算术移位不是循环，这意味着移出结果的一个 end 的数位另一端不重新移入。</span><span class="sxs-lookup"><span data-stu-id="68b74-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="68b74-120">在算术右移位运算移出最右边的位位置的位将被丢弃，并最左侧 （符号） 位传播到左侧空出的位位置。</span><span class="sxs-lookup"><span data-stu-id="68b74-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="68b74-121">这意味着，如果`pattern`具有负值，空出的位置将设置为一个; 否则设置为零。</span><span class="sxs-lookup"><span data-stu-id="68b74-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="68b74-122">请注意，数据类型`Byte`， `UShort`， `UInteger`，和`ULong`是无符号整数，因此没有任何符号位传播。</span><span class="sxs-lookup"><span data-stu-id="68b74-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="68b74-123">如果`pattern`的任何无符号类型，空出的位置将始终设置为零。</span><span class="sxs-lookup"><span data-stu-id="68b74-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="68b74-124">若要防止移位的更多位数超过结果所能容纳，Visual Basic 使用的值`amount`使用对应的数据类型的大小掩码`pattern`。</span><span class="sxs-lookup"><span data-stu-id="68b74-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="68b74-125">这些值的二进制 AND 用于位移量。</span><span class="sxs-lookup"><span data-stu-id="68b74-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="68b74-126">大小掩码如下所示：</span><span class="sxs-lookup"><span data-stu-id="68b74-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="68b74-127">数据类型 `pattern`</span><span class="sxs-lookup"><span data-stu-id="68b74-127">Data type of `pattern`</span></span>|<span data-ttu-id="68b74-128">大小掩码 （十进制）</span><span class="sxs-lookup"><span data-stu-id="68b74-128">Size mask (decimal)</span></span>|<span data-ttu-id="68b74-129">大小掩码 （十六进制）</span><span class="sxs-lookup"><span data-stu-id="68b74-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="68b74-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="68b74-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="68b74-131">7</span><span class="sxs-lookup"><span data-stu-id="68b74-131">7</span></span>|<span data-ttu-id="68b74-132">&AMP; H00000007</span><span class="sxs-lookup"><span data-stu-id="68b74-132">&H00000007</span></span>|  
|<span data-ttu-id="68b74-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="68b74-133">`Short`, `UShort`</span></span>|<span data-ttu-id="68b74-134">15</span><span class="sxs-lookup"><span data-stu-id="68b74-134">15</span></span>|<span data-ttu-id="68b74-135">&AMP; H0000000F</span><span class="sxs-lookup"><span data-stu-id="68b74-135">&H0000000F</span></span>|  
|<span data-ttu-id="68b74-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="68b74-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="68b74-137">31</span><span class="sxs-lookup"><span data-stu-id="68b74-137">31</span></span>|<span data-ttu-id="68b74-138">&AMP; H0000001F</span><span class="sxs-lookup"><span data-stu-id="68b74-138">&H0000001F</span></span>|  
|<span data-ttu-id="68b74-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="68b74-139">`Long`, `ULong`</span></span>|<span data-ttu-id="68b74-140">63</span><span class="sxs-lookup"><span data-stu-id="68b74-140">63</span></span>|<span data-ttu-id="68b74-141">&AMP; H0000003F</span><span class="sxs-lookup"><span data-stu-id="68b74-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="68b74-142">如果`amount`为零的值`result`的值是否相同`pattern`。</span><span class="sxs-lookup"><span data-stu-id="68b74-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="68b74-143">如果`amount`是负数，它采用无符号值并使用适当的大小掩码进行屏蔽。</span><span class="sxs-lookup"><span data-stu-id="68b74-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="68b74-144">算术移位永远不会生成溢出异常。</span><span class="sxs-lookup"><span data-stu-id="68b74-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="68b74-145">重载</span><span class="sxs-lookup"><span data-stu-id="68b74-145">Overloading</span></span>  
 <span data-ttu-id="68b74-146">`>>`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="68b74-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="68b74-147">如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="68b74-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="68b74-148">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="68b74-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="68b74-149">示例</span><span class="sxs-lookup"><span data-stu-id="68b74-149">Example</span></span>  
 <span data-ttu-id="68b74-150">下面的示例使用`>>`运算符对整型值执行算术右移位。</span><span class="sxs-lookup"><span data-stu-id="68b74-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="68b74-151">结果始终具有相同的数据被移位的表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="68b74-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 <span data-ttu-id="68b74-152">上述示例的结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="68b74-152">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="68b74-153">`result1` 为 2560 (0000 1010年 0000 0000)。</span><span class="sxs-lookup"><span data-stu-id="68b74-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
-   <span data-ttu-id="68b74-154">`result2` 为 160 (0000 0000 1010年 0000)。</span><span class="sxs-lookup"><span data-stu-id="68b74-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
-   <span data-ttu-id="68b74-155">`result3` 为 2 (0000 0000 0000 0010)。</span><span class="sxs-lookup"><span data-stu-id="68b74-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
-   <span data-ttu-id="68b74-156">`result4` 为 640 (0000 0010 1000年 0000)。</span><span class="sxs-lookup"><span data-stu-id="68b74-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
-   <span data-ttu-id="68b74-157">`result5` 为 0 （向右移位 15 位数）。</span><span class="sxs-lookup"><span data-stu-id="68b74-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="68b74-158">移位量`result4`的计算方法为 18 和 15，等于 2。</span><span class="sxs-lookup"><span data-stu-id="68b74-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="68b74-159">下面的示例演示上一个负数值的算术移位。</span><span class="sxs-lookup"><span data-stu-id="68b74-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 <span data-ttu-id="68b74-160">上述示例的结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="68b74-160">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="68b74-161">`negresult1` 是-512 (1111年 1110年 0000 0000)。</span><span class="sxs-lookup"><span data-stu-id="68b74-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
-   <span data-ttu-id="68b74-162">`negresult2` 为-1 （传播符号位）。</span><span class="sxs-lookup"><span data-stu-id="68b74-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68b74-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="68b74-163">See Also</span></span>  
 [<span data-ttu-id="68b74-164">移位运算符</span><span class="sxs-lookup"><span data-stu-id="68b74-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="68b74-165">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="68b74-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="68b74-166">>>= 运算符</span><span class="sxs-lookup"><span data-stu-id="68b74-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)  
 [<span data-ttu-id="68b74-167">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="68b74-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="68b74-168">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="68b74-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="68b74-169">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="68b74-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
