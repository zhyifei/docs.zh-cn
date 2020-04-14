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
ms.openlocfilehash: d4d868ba7c05cf3c2d538de1217231df91d4f43d
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243318"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="adca2-102">Decimal 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adca2-102">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="adca2-103">保存由表示 96 位（12 字节）整数按 10 的可变次幂缩放所得的 128 位（16 字节）值。</span><span class="sxs-lookup"><span data-stu-id="adca2-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="adca2-104">缩放因子指定小数点右侧的数字数;范围从 0 到 28。</span><span class="sxs-lookup"><span data-stu-id="adca2-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="adca2-105">其刻度为 0（无小数位数），最大可能值为 +/-79，228，162，514，264，337，593，543，950，335 （+/-7.922816251423355353535535553355+28）。</span><span class="sxs-lookup"><span data-stu-id="adca2-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="adca2-106">对于 28 位小数，最大值为 +//922816251426433759355439555555555555303335，最小非零值为 +//00000000000000000000000001（+//-1E-28）。</span><span class="sxs-lookup"><span data-stu-id="adca2-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="adca2-107">备注</span><span class="sxs-lookup"><span data-stu-id="adca2-107">Remarks</span></span>

<span data-ttu-id="adca2-108">数据类型`Decimal`为数字提供最多数量的重要数字。</span><span class="sxs-lookup"><span data-stu-id="adca2-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="adca2-109">它最多支持 29 位有效数字，可以表示大于 7.9228 x 10^28 的值。</span><span class="sxs-lookup"><span data-stu-id="adca2-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="adca2-110">它特别适用于需要大量数字但不能容忍舍入错误的计算（如财务）。</span><span class="sxs-lookup"><span data-stu-id="adca2-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="adca2-111">`Decimal` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="adca2-111">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="adca2-112">编程提示</span><span class="sxs-lookup"><span data-stu-id="adca2-112">Programming Tips</span></span>

- <span data-ttu-id="adca2-113">**精度。**</span><span class="sxs-lookup"><span data-stu-id="adca2-113">**Precision.**</span></span> <span data-ttu-id="adca2-114">`Decimal`不是浮点数据类型。</span><span class="sxs-lookup"><span data-stu-id="adca2-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="adca2-115">结构`Decimal`包含二进制整数值，以及符号位和整数缩放因子，指定值的哪一部分是十进制分数。</span><span class="sxs-lookup"><span data-stu-id="adca2-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="adca2-116">因此，与浮`Decimal`点类型 （和`Single``Double`） 相比，数字在内存中的表示法更精确。</span><span class="sxs-lookup"><span data-stu-id="adca2-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="adca2-117">**性能。**</span><span class="sxs-lookup"><span data-stu-id="adca2-117">**Performance.**</span></span> <span data-ttu-id="adca2-118">数据类型`Decimal`是所有数值类型中最慢的。</span><span class="sxs-lookup"><span data-stu-id="adca2-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="adca2-119">在选择数据类型之前，应权衡精度与性能的重要性。</span><span class="sxs-lookup"><span data-stu-id="adca2-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="adca2-120">**扩大。**</span><span class="sxs-lookup"><span data-stu-id="adca2-120">**Widening.**</span></span> <span data-ttu-id="adca2-121">数据类型`Decimal`扩展到`Single`或`Double`。</span><span class="sxs-lookup"><span data-stu-id="adca2-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="adca2-122">这意味着您可以转换为`Decimal`其中任一<xref:System.OverflowException?displayProperty=nameWithType>类型，而不会遇到错误。</span><span class="sxs-lookup"><span data-stu-id="adca2-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="adca2-123">**尾随零。**</span><span class="sxs-lookup"><span data-stu-id="adca2-123">**Trailing Zeros.**</span></span> <span data-ttu-id="adca2-124">视觉基础不会在`Decimal`文本中存储尾随零。</span><span class="sxs-lookup"><span data-stu-id="adca2-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="adca2-125">但是，`Decimal`变量保留在计算中获取的任何尾随零。</span><span class="sxs-lookup"><span data-stu-id="adca2-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="adca2-126">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="adca2-126">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="adca2-127">上`MsgBox`例中的输出如下：</span><span class="sxs-lookup"><span data-stu-id="adca2-127">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="adca2-128">**键入字符。**</span><span class="sxs-lookup"><span data-stu-id="adca2-128">**Type Characters.**</span></span> <span data-ttu-id="adca2-129">将文本类型字符 `D` 追加到文本会将其强制转换为 `Decimal` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="adca2-129">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="adca2-130">将标识符类型字符 `@` 追加到任何标识符会将其强制转换为 `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="adca2-130">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="adca2-131">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="adca2-131">**Framework Type.**</span></span> <span data-ttu-id="adca2-132">.NET Framework 中的对应类型是 <xref:System.Decimal?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="adca2-132">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="adca2-133">范围</span><span class="sxs-lookup"><span data-stu-id="adca2-133">Range</span></span>

 <span data-ttu-id="adca2-134">您可能需要使用`D`类型字符将大值分配给`Decimal`变量或常量。</span><span class="sxs-lookup"><span data-stu-id="adca2-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="adca2-135">此要求是因为编译器将文本解释为`Long`除非文本类型字符遵循文本，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="adca2-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="adca2-136">的声明`bigDec1`不会生成溢出，因为分配给它的值在`Long`</span><span class="sxs-lookup"><span data-stu-id="adca2-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="adca2-137">可以将`Long`该值分配给`Decimal`变量。</span><span class="sxs-lookup"><span data-stu-id="adca2-137">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="adca2-138">的声明`bigDec2`生成溢出错误，因为分配给它的值对于`Long`来说太大。</span><span class="sxs-lookup"><span data-stu-id="adca2-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="adca2-139">由于数字文本不能首先解释为 ，`Long`无法将其分配给`Decimal`变量。</span><span class="sxs-lookup"><span data-stu-id="adca2-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="adca2-140">对于`bigDec3`，文本类型字符`D`通过强制编译器将文本解释为`Decimal`而不是 解说，从而解决了问题。 `Long`</span><span class="sxs-lookup"><span data-stu-id="adca2-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="adca2-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="adca2-141">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="adca2-142">数据类型</span><span class="sxs-lookup"><span data-stu-id="adca2-142">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="adca2-143">Single 数据类型</span><span class="sxs-lookup"><span data-stu-id="adca2-143">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="adca2-144">Double 数据类型</span><span class="sxs-lookup"><span data-stu-id="adca2-144">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="adca2-145">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="adca2-145">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="adca2-146">转换摘要</span><span class="sxs-lookup"><span data-stu-id="adca2-146">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="adca2-147">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="adca2-147">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
