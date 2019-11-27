---
title: Decimal 数据类型
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
ms.openlocfilehash: 6d62bcc1d043b45c0fc30154d9dc633b998f97b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344032"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="01076-102">Decimal 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01076-102">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="01076-103">保存由表示 96 位（12 字节）整数按 10 的可变次幂缩放所得的 128 位（16 字节）值。</span><span class="sxs-lookup"><span data-stu-id="01076-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="01076-104">缩放系数指定小数点右侧的数字位数;范围为0到28。</span><span class="sxs-lookup"><span data-stu-id="01076-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="01076-105">当小数位数为0（没有小数位数）时，可能的最大值为 +/-79228162514264337593543950335 （+/-7.9228162514264337593543950335E + 28）。</span><span class="sxs-lookup"><span data-stu-id="01076-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="01076-106">如果有28个小数位数，则最大值为 +/-7.9228162514264337593543950335，最小非零值为 +/-0.0000000000000000000000000001 （+/-1E-28）。</span><span class="sxs-lookup"><span data-stu-id="01076-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="01076-107">备注</span><span class="sxs-lookup"><span data-stu-id="01076-107">Remarks</span></span>

<span data-ttu-id="01076-108">`Decimal` 数据类型为数字提供最大的有效位数。</span><span class="sxs-lookup"><span data-stu-id="01076-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="01076-109">它最多支持29个有效位数，并可表示超过 7.9228 x 10 ^ 28 的值。</span><span class="sxs-lookup"><span data-stu-id="01076-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="01076-110">它特别适用于需要大量数字但不允许舍入误差的计算（例如财务）。</span><span class="sxs-lookup"><span data-stu-id="01076-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="01076-111">`Decimal` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="01076-111">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="01076-112">编程提示</span><span class="sxs-lookup"><span data-stu-id="01076-112">Programming Tips</span></span>

- <span data-ttu-id="01076-113">**Precision.**</span><span class="sxs-lookup"><span data-stu-id="01076-113">**Precision.**</span></span> <span data-ttu-id="01076-114">`Decimal` 不是浮点数据类型。</span><span class="sxs-lookup"><span data-stu-id="01076-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="01076-115">`Decimal` 结构包含一个二进制整数值以及一个符号位和一个整数比例因子，用于指定值的哪一部分是小数部分。</span><span class="sxs-lookup"><span data-stu-id="01076-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="01076-116">因此，`Decimal` 数字在内存中的表示形式比浮点类型（`Single` 和 `Double`）更准确。</span><span class="sxs-lookup"><span data-stu-id="01076-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="01076-117">**性能。**</span><span class="sxs-lookup"><span data-stu-id="01076-117">**Performance.**</span></span> <span data-ttu-id="01076-118">`Decimal` 的数据类型是所有数值类型的最慢。</span><span class="sxs-lookup"><span data-stu-id="01076-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="01076-119">在选择数据类型之前，应权衡精度与性能的重要性。</span><span class="sxs-lookup"><span data-stu-id="01076-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="01076-120">**扩大.**</span><span class="sxs-lookup"><span data-stu-id="01076-120">**Widening.**</span></span> <span data-ttu-id="01076-121">`Decimal` 数据类型扩大到 `Single` 或 `Double`。</span><span class="sxs-lookup"><span data-stu-id="01076-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="01076-122">这意味着，可以将 `Decimal` 转换为这些类型中的任何一种，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。</span><span class="sxs-lookup"><span data-stu-id="01076-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="01076-123">**尾随零。**</span><span class="sxs-lookup"><span data-stu-id="01076-123">**Trailing Zeros.**</span></span> <span data-ttu-id="01076-124">Visual Basic 不会在 `Decimal` 文本中存储尾随零。</span><span class="sxs-lookup"><span data-stu-id="01076-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="01076-125">但是，`Decimal` 变量会保留任何尾随零获取计算。</span><span class="sxs-lookup"><span data-stu-id="01076-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="01076-126">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="01076-126">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="01076-127">上述示例中 `MsgBox` 的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="01076-127">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="01076-128">**键入字符。**</span><span class="sxs-lookup"><span data-stu-id="01076-128">**Type Characters.**</span></span> <span data-ttu-id="01076-129">将文本类型字符 `D` 追加到文本会将其强制转换为 `Decimal` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="01076-129">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="01076-130">将标识符类型字符 `@` 追加到任何标识符会将其强制转换为 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="01076-130">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="01076-131">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="01076-131">**Framework Type.**</span></span> <span data-ttu-id="01076-132">.NET Framework 中的对应类型是 <xref:System.Decimal?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="01076-132">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="01076-133">范围</span><span class="sxs-lookup"><span data-stu-id="01076-133">Range</span></span>

 <span data-ttu-id="01076-134">你可能需要使用 `D` 类型的字符向 `Decimal` 的变量或常量分配一个较大的值。</span><span class="sxs-lookup"><span data-stu-id="01076-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="01076-135">此要求是因为，除非文本类型字符跟随文本，否则编译器会将文本解释为 `Long`，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="01076-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="01076-136">`bigDec1` 的声明不会产生溢出，因为赋给它的值落在 `Long`的范围内。</span><span class="sxs-lookup"><span data-stu-id="01076-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="01076-137">可以将 `Long` 值分配给 `Decimal` 变量。</span><span class="sxs-lookup"><span data-stu-id="01076-137">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="01076-138">`bigDec2` 的声明会生成溢出错误，因为赋给它的值太大，无法用于 `Long`。</span><span class="sxs-lookup"><span data-stu-id="01076-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="01076-139">因为数值不能首先解释为 `Long`，所以不能将其分配给 `Decimal` 变量。</span><span class="sxs-lookup"><span data-stu-id="01076-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="01076-140">对于 `bigDec3`，文本类型字符 `D` 通过强制编译器将文本解释为 `Decimal` 而不是作为 `Long`来解决该问题。</span><span class="sxs-lookup"><span data-stu-id="01076-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="01076-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01076-141">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="01076-142">数据类型</span><span class="sxs-lookup"><span data-stu-id="01076-142">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="01076-143">Single 数据类型</span><span class="sxs-lookup"><span data-stu-id="01076-143">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="01076-144">Double 数据类型</span><span class="sxs-lookup"><span data-stu-id="01076-144">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="01076-145">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="01076-145">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="01076-146">转换摘要</span><span class="sxs-lookup"><span data-stu-id="01076-146">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="01076-147">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="01076-147">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
