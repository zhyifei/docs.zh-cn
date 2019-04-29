---
title: << 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 75c16c27dc919ba365cbe3c28c61a1e46496b0ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768285"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="23742-102">\<\< 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23742-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="23742-103">对位模式执行算术左的移位运算。</span><span class="sxs-lookup"><span data-stu-id="23742-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23742-104">语法</span><span class="sxs-lookup"><span data-stu-id="23742-104">Syntax</span></span>  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="23742-105">部件</span><span class="sxs-lookup"><span data-stu-id="23742-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="23742-106">必需。</span><span class="sxs-lookup"><span data-stu-id="23742-106">Required.</span></span> <span data-ttu-id="23742-107">整型数值。</span><span class="sxs-lookup"><span data-stu-id="23742-107">Integral numeric value.</span></span> <span data-ttu-id="23742-108">移位的位模式的结果。</span><span class="sxs-lookup"><span data-stu-id="23742-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="23742-109">数据类型是相同的`pattern`。</span><span class="sxs-lookup"><span data-stu-id="23742-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="23742-110">必需。</span><span class="sxs-lookup"><span data-stu-id="23742-110">Required.</span></span> <span data-ttu-id="23742-111">整型数值表达式。</span><span class="sxs-lookup"><span data-stu-id="23742-111">Integral numeric expression.</span></span> <span data-ttu-id="23742-112">要移动的位模式。</span><span class="sxs-lookup"><span data-stu-id="23742-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="23742-113">数据类型必须为整型类型 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，或`ULong`)。</span><span class="sxs-lookup"><span data-stu-id="23742-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="23742-114">必需。</span><span class="sxs-lookup"><span data-stu-id="23742-114">Required.</span></span> <span data-ttu-id="23742-115">数值表达式。</span><span class="sxs-lookup"><span data-stu-id="23742-115">Numeric expression.</span></span> <span data-ttu-id="23742-116">要移位的位模式的比特数。</span><span class="sxs-lookup"><span data-stu-id="23742-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="23742-117">数据类型必须是`Integer`或扩大到`Integer`。</span><span class="sxs-lookup"><span data-stu-id="23742-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23742-118">备注</span><span class="sxs-lookup"><span data-stu-id="23742-118">Remarks</span></span>  
 <span data-ttu-id="23742-119">算术移位不是循环，这意味着移出结果的一端的数位另一端不重新移入。</span><span class="sxs-lookup"><span data-stu-id="23742-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="23742-120">在算术左移位运算移出的结果数据类型范围的位将被丢弃，并在右侧而空出的位设置为零。</span><span class="sxs-lookup"><span data-stu-id="23742-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="23742-121">若要防止移位的结果可以容纳超出的位数，Visual Basic 使用的值`amount`具有对应的数据类型大小掩码`pattern`。</span><span class="sxs-lookup"><span data-stu-id="23742-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="23742-122">这些值的二进制 AND 用于位移量。</span><span class="sxs-lookup"><span data-stu-id="23742-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="23742-123">大小掩码如下所示：</span><span class="sxs-lookup"><span data-stu-id="23742-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="23742-124">数据类型 `pattern`</span><span class="sxs-lookup"><span data-stu-id="23742-124">Data type of `pattern`</span></span>|<span data-ttu-id="23742-125">大小掩码 （十进制）</span><span class="sxs-lookup"><span data-stu-id="23742-125">Size mask (decimal)</span></span>|<span data-ttu-id="23742-126">大小掩码 （十六进制）</span><span class="sxs-lookup"><span data-stu-id="23742-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="23742-127">`SByte`， `Byte`</span><span class="sxs-lookup"><span data-stu-id="23742-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="23742-128">7</span><span class="sxs-lookup"><span data-stu-id="23742-128">7</span></span>|<span data-ttu-id="23742-129">&H00000007</span><span class="sxs-lookup"><span data-stu-id="23742-129">&H00000007</span></span>|  
|<span data-ttu-id="23742-130">`Short`， `UShort`</span><span class="sxs-lookup"><span data-stu-id="23742-130">`Short`, `UShort`</span></span>|<span data-ttu-id="23742-131">15</span><span class="sxs-lookup"><span data-stu-id="23742-131">15</span></span>|<span data-ttu-id="23742-132">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="23742-132">&H0000000F</span></span>|  
|<span data-ttu-id="23742-133">`Integer`， `UInteger`</span><span class="sxs-lookup"><span data-stu-id="23742-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="23742-134">31</span><span class="sxs-lookup"><span data-stu-id="23742-134">31</span></span>|<span data-ttu-id="23742-135">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="23742-135">&H0000001F</span></span>|  
|<span data-ttu-id="23742-136">`Long`， `ULong`</span><span class="sxs-lookup"><span data-stu-id="23742-136">`Long`, `ULong`</span></span>|<span data-ttu-id="23742-137">63</span><span class="sxs-lookup"><span data-stu-id="23742-137">63</span></span>|<span data-ttu-id="23742-138">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="23742-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="23742-139">如果`amount`为零的值`result`的值是否相同`pattern`。</span><span class="sxs-lookup"><span data-stu-id="23742-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="23742-140">如果`amount`是负数，它是作为无符号值，使用适当的大小掩码进行屏蔽。</span><span class="sxs-lookup"><span data-stu-id="23742-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="23742-141">算术移位永远不会产生溢出异常。</span><span class="sxs-lookup"><span data-stu-id="23742-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23742-142">`<<`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="23742-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="23742-143">如果你的代码对此类的类或结构使用此运算符，请确保您了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="23742-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="23742-144">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="23742-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23742-145">示例</span><span class="sxs-lookup"><span data-stu-id="23742-145">Example</span></span>  
 <span data-ttu-id="23742-146">下面的示例使用`<<`运算符执行算术左移位对整数值。</span><span class="sxs-lookup"><span data-stu-id="23742-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="23742-147">结果始终具有相同的数据类型的被移位的表达式。</span><span class="sxs-lookup"><span data-stu-id="23742-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="23742-148">前一示例的结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="23742-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="23742-149">`result1` 为 192 (0000 0000 0000 1100年)。</span><span class="sxs-lookup"><span data-stu-id="23742-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="23742-150">`result2` 为 3072 (0000 0000 0000 1100年)。</span><span class="sxs-lookup"><span data-stu-id="23742-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="23742-151">`result3` 是-32768 (1000年 0000 0000 0000)。</span><span class="sxs-lookup"><span data-stu-id="23742-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="23742-152">`result4` 是 384 (0000 0001 1000年 0000)。</span><span class="sxs-lookup"><span data-stu-id="23742-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="23742-153">`result5` 为 0 （向左移动 15 位）。</span><span class="sxs-lookup"><span data-stu-id="23742-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="23742-154">移位量`result4`计算为 17 和 15，等于 1。</span><span class="sxs-lookup"><span data-stu-id="23742-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23742-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="23742-155">See also</span></span>

- [<span data-ttu-id="23742-156">移位运算符</span><span class="sxs-lookup"><span data-stu-id="23742-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="23742-157">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="23742-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="23742-158"><<= 运算符</span><span class="sxs-lookup"><span data-stu-id="23742-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="23742-159">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="23742-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="23742-160">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="23742-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="23742-161">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="23742-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
