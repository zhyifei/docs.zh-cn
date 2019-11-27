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
# <a name="-operator-visual-basic"></a><span data-ttu-id="f50f0-102">\<\< 运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="f50f0-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="f50f0-103">对位模式执行算术左移位运算。</span><span class="sxs-lookup"><span data-stu-id="f50f0-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f50f0-104">语法</span><span class="sxs-lookup"><span data-stu-id="f50f0-104">Syntax</span></span>  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="f50f0-105">部件</span><span class="sxs-lookup"><span data-stu-id="f50f0-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="f50f0-106">必需。</span><span class="sxs-lookup"><span data-stu-id="f50f0-106">Required.</span></span> <span data-ttu-id="f50f0-107">整数数值。</span><span class="sxs-lookup"><span data-stu-id="f50f0-107">Integral numeric value.</span></span> <span data-ttu-id="f50f0-108">移位位模式的结果。</span><span class="sxs-lookup"><span data-stu-id="f50f0-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="f50f0-109">数据类型与 `pattern`的数据类型相同。</span><span class="sxs-lookup"><span data-stu-id="f50f0-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="f50f0-110">必需。</span><span class="sxs-lookup"><span data-stu-id="f50f0-110">Required.</span></span> <span data-ttu-id="f50f0-111">整数数值表达式。</span><span class="sxs-lookup"><span data-stu-id="f50f0-111">Integral numeric expression.</span></span> <span data-ttu-id="f50f0-112">要移动的位模式。</span><span class="sxs-lookup"><span data-stu-id="f50f0-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="f50f0-113">数据类型必须是整型（`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`或 `ULong`）。</span><span class="sxs-lookup"><span data-stu-id="f50f0-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="f50f0-114">必需。</span><span class="sxs-lookup"><span data-stu-id="f50f0-114">Required.</span></span> <span data-ttu-id="f50f0-115">数值表达式。</span><span class="sxs-lookup"><span data-stu-id="f50f0-115">Numeric expression.</span></span> <span data-ttu-id="f50f0-116">要移位位模式的位数。</span><span class="sxs-lookup"><span data-stu-id="f50f0-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="f50f0-117">数据类型必须 `Integer` 或扩大到 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="f50f0-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f50f0-118">备注</span><span class="sxs-lookup"><span data-stu-id="f50f0-118">Remarks</span></span>  
 <span data-ttu-id="f50f0-119">算术移位不是循环的，这意味着，不会在另一端重新引入结果的末尾以外的位。</span><span class="sxs-lookup"><span data-stu-id="f50f0-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="f50f0-120">在算术左移位中，将丢弃超出结果数据类型范围的位，并将在右侧空出的位位置设置为零。</span><span class="sxs-lookup"><span data-stu-id="f50f0-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="f50f0-121">若要防止移位比结果可以容纳的位数多，Visual Basic 用与 `pattern`的数据类型对应的大小掩码屏蔽 `amount` 的值。</span><span class="sxs-lookup"><span data-stu-id="f50f0-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="f50f0-122">这些值的二进制和均用于移位量。</span><span class="sxs-lookup"><span data-stu-id="f50f0-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="f50f0-123">大小掩码如下：</span><span class="sxs-lookup"><span data-stu-id="f50f0-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="f50f0-124">`pattern` 的数据类型</span><span class="sxs-lookup"><span data-stu-id="f50f0-124">Data type of `pattern`</span></span>|<span data-ttu-id="f50f0-125">大小掩码（十进制）</span><span class="sxs-lookup"><span data-stu-id="f50f0-125">Size mask (decimal)</span></span>|<span data-ttu-id="f50f0-126">大小掩码（十六进制）</span><span class="sxs-lookup"><span data-stu-id="f50f0-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="f50f0-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="f50f0-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="f50f0-128">7</span><span class="sxs-lookup"><span data-stu-id="f50f0-128">7</span></span>|<span data-ttu-id="f50f0-129">& H00000007</span><span class="sxs-lookup"><span data-stu-id="f50f0-129">&H00000007</span></span>|  
|<span data-ttu-id="f50f0-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="f50f0-130">`Short`, `UShort`</span></span>|<span data-ttu-id="f50f0-131">15</span><span class="sxs-lookup"><span data-stu-id="f50f0-131">15</span></span>|<span data-ttu-id="f50f0-132">& H0000000F</span><span class="sxs-lookup"><span data-stu-id="f50f0-132">&H0000000F</span></span>|  
|<span data-ttu-id="f50f0-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="f50f0-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="f50f0-134">31</span><span class="sxs-lookup"><span data-stu-id="f50f0-134">31</span></span>|<span data-ttu-id="f50f0-135">& H0000001F</span><span class="sxs-lookup"><span data-stu-id="f50f0-135">&H0000001F</span></span>|  
|<span data-ttu-id="f50f0-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="f50f0-136">`Long`, `ULong`</span></span>|<span data-ttu-id="f50f0-137">63</span><span class="sxs-lookup"><span data-stu-id="f50f0-137">63</span></span>|<span data-ttu-id="f50f0-138">& H0000003F</span><span class="sxs-lookup"><span data-stu-id="f50f0-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="f50f0-139">如果 `amount` 为零，则 `result` 的值与 `pattern`的值相同。</span><span class="sxs-lookup"><span data-stu-id="f50f0-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="f50f0-140">如果 `amount` 为负数，则将它作为无符号值，并使用适当的大小掩码屏蔽。</span><span class="sxs-lookup"><span data-stu-id="f50f0-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="f50f0-141">算术移位从不产生溢出异常。</span><span class="sxs-lookup"><span data-stu-id="f50f0-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f50f0-142">可以*重载*`<<` 运算符，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="f50f0-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f50f0-143">如果代码对这样的类或结构使用此运算符，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="f50f0-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="f50f0-144">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="f50f0-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f50f0-145">示例</span><span class="sxs-lookup"><span data-stu-id="f50f0-145">Example</span></span>  
 <span data-ttu-id="f50f0-146">下面的示例使用 `<<` 运算符对整数值执行算术左移位。</span><span class="sxs-lookup"><span data-stu-id="f50f0-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="f50f0-147">结果始终与要移动的表达式的数据类型相同。</span><span class="sxs-lookup"><span data-stu-id="f50f0-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="f50f0-148">上述示例的结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="f50f0-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="f50f0-149">`result1` 为192（0000 0000 1100 0000）。</span><span class="sxs-lookup"><span data-stu-id="f50f0-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="f50f0-150">`result2` 为3072（0000 1100 0000 0000）。</span><span class="sxs-lookup"><span data-stu-id="f50f0-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="f50f0-151">`result3` 为-32768 （1000 0000 0000 0000）。</span><span class="sxs-lookup"><span data-stu-id="f50f0-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="f50f0-152">`result4` 为384（0000 0001 1000 0000）。</span><span class="sxs-lookup"><span data-stu-id="f50f0-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="f50f0-153">`result5` 为0（向左移动15个位置）。</span><span class="sxs-lookup"><span data-stu-id="f50f0-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="f50f0-154">`result4` 的移位量计算为17和15，这等于1。</span><span class="sxs-lookup"><span data-stu-id="f50f0-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f50f0-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f50f0-155">See also</span></span>

- [<span data-ttu-id="f50f0-156">移位运算符</span><span class="sxs-lookup"><span data-stu-id="f50f0-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="f50f0-157">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="f50f0-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="f50f0-158"><<= 运算符</span><span class="sxs-lookup"><span data-stu-id="f50f0-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="f50f0-159">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="f50f0-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f50f0-160">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="f50f0-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f50f0-161">Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="f50f0-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
