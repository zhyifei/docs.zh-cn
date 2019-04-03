---
title: Decimal 数据类型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: 4d530a8c1f85d2f0045184c05df63849047a8204
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834096"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="5ee0b-102">Decimal 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ee0b-102">Decimal Data Type (Visual Basic)</span></span>
<span data-ttu-id="5ee0b-103">保存有符号表示 96 位 （12 字节） 整数数字 10 的可变次幂缩放的 128 位 （16 字节） 值。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="5ee0b-104">比例因子指定小数点; 右侧的位数其范围从 0 到 28。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="5ee0b-105">小数位数为 0 （没有小数位），最大值为 + /-79228162514264337593543950335 (+ /-7.9228162514264337593543950335E + 28)。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="5ee0b-106">具有 28 位小数，最大值为 + /-7.9228162514264337593543950335，并最小的非零值为 + /-0.0000000000000000000000000001 （+ /-1E 28)。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ee0b-107">备注</span><span class="sxs-lookup"><span data-stu-id="5ee0b-107">Remarks</span></span>  
 <span data-ttu-id="5ee0b-108">`Decimal`数据类型提供了许多的最大有效位数。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="5ee0b-109">它支持最多 29 个有效位数，并可表示值超出 7.9228 x 10 ^28。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="5ee0b-110">它是特别适用于计算，例如财务，这需要大量的数字但不能容忍舍入误差。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>  
  
 <span data-ttu-id="5ee0b-111">`Decimal` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-111">The default value of `Decimal` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="5ee0b-112">编程提示</span><span class="sxs-lookup"><span data-stu-id="5ee0b-112">Programming Tips</span></span>  
  
-   <span data-ttu-id="5ee0b-113">**精度。**</span><span class="sxs-lookup"><span data-stu-id="5ee0b-113">**Precision.**</span></span> <span data-ttu-id="5ee0b-114">`Decimal` 不是浮点数据类型。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="5ee0b-115">`Decimal`结构保存的二进制整数值，以及符号位和缩放因子，指定了值的哪些部分是小数部分的整数。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="5ee0b-116">因此，`Decimal`数字在浮点类型相比，内存中具有更精确的表示形式 (`Single`和`Double`)。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>  
  
-   <span data-ttu-id="5ee0b-117">**性能。**</span><span class="sxs-lookup"><span data-stu-id="5ee0b-117">**Performance.**</span></span> <span data-ttu-id="5ee0b-118">`Decimal`数据类型是最慢的所有数字类型。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="5ee0b-119">应权衡针对性能，而不选择数据类型的精度的重要性。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>  
  
-   <span data-ttu-id="5ee0b-120">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="5ee0b-120">**Widening.**</span></span> <span data-ttu-id="5ee0b-121">`Decimal`数据类型加宽到`Single`或`Double`。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="5ee0b-122">这意味着可以将转换`Decimal`而不会遇到这些类型的任一<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="5ee0b-123">**尾随零。**</span><span class="sxs-lookup"><span data-stu-id="5ee0b-123">**Trailing Zeros.**</span></span> <span data-ttu-id="5ee0b-124">Visual Basic 不存储中的尾随零`Decimal`文本。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="5ee0b-125">但是，`Decimal`变量将保留任何计算所得的尾随零。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="5ee0b-126">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-126">The following example illustrates this.</span></span>  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     <span data-ttu-id="5ee0b-127">输出`MsgBox`在前面的示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="5ee0b-127">The output of `MsgBox` in the preceding example is as follows:</span></span>  
  
     <span data-ttu-id="5ee0b-128">d1 = 2.375，d2 = 1.625，d3 = 4.000，d4 = 4</span><span class="sxs-lookup"><span data-stu-id="5ee0b-128">d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4</span></span>  
  
-   <span data-ttu-id="5ee0b-129">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="5ee0b-129">**Type Characters.**</span></span> <span data-ttu-id="5ee0b-130">将文本类型字符 `D` 追加到文本会将其强制转换为 `Decimal` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-130">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="5ee0b-131">将标识符类型字符 `@` 追加到任何标识符会将其强制转换为 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-131">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>  
  
-   <span data-ttu-id="5ee0b-132">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="5ee0b-132">**Framework Type.**</span></span> <span data-ttu-id="5ee0b-133">.NET Framework 中的对应类型是 <xref:System.Decimal?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-133">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="range"></a><span data-ttu-id="5ee0b-134">范围</span><span class="sxs-lookup"><span data-stu-id="5ee0b-134">Range</span></span>  
 <span data-ttu-id="5ee0b-135">可能需要使用`D`键入要分配到较大的值的字符`Decimal`变量或常量。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-135">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="5ee0b-136">此要求是因为编译器将解释为文字`Long`除非文本类型字符遵循文本，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-136">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 <span data-ttu-id="5ee0b-137">声明`bigDec1`不会产生溢出，因为分配给它的值是否在范围内`Long`。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-137">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="5ee0b-138">`Long`可以将值分配给`Decimal`变量。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-138">The `Long` value can be assigned to the `Decimal` variable.</span></span>  
  
 <span data-ttu-id="5ee0b-139">声明`bigDec2`生成溢出错误，因为分配给它的值是太大， `Long`。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-139">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="5ee0b-140">由于数字文本不能首先解释为`Long`，它不能分配给`Decimal`变量。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-140">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>  
  
 <span data-ttu-id="5ee0b-141">有关`bigDec3`，文本类型字符`D`解决了问题，通过强制编译器将解释为文字`Decimal`而不是作为`Long`。</span><span class="sxs-lookup"><span data-stu-id="5ee0b-141">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee0b-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ee0b-142">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5ee0b-143">数据类型</span><span class="sxs-lookup"><span data-stu-id="5ee0b-143">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="5ee0b-144">Single 数据类型</span><span class="sxs-lookup"><span data-stu-id="5ee0b-144">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="5ee0b-145">Double 数据类型</span><span class="sxs-lookup"><span data-stu-id="5ee0b-145">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="5ee0b-146">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="5ee0b-146">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="5ee0b-147">转换摘要</span><span class="sxs-lookup"><span data-stu-id="5ee0b-147">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="5ee0b-148">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="5ee0b-148">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
