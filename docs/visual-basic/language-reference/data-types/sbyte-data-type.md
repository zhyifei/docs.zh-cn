---
title: SByte 数据类型
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
ms.openlocfilehash: 01a0a4a261213d7e6e2016bf49128092e5b22308
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401381"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="2e175-102">SByte 数据类型（可视基本）</span><span class="sxs-lookup"><span data-stu-id="2e175-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="2e175-103">保留在 -128 到 127 之间的值范围的已签名 8 位（1 字节）整数。</span><span class="sxs-lookup"><span data-stu-id="2e175-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e175-104">备注</span><span class="sxs-lookup"><span data-stu-id="2e175-104">Remarks</span></span>

<span data-ttu-id="2e175-105">使用`SByte`数据类型包含不需要 的完整数据宽度`Integer`甚至一半数据宽度的`Short`整数值。</span><span class="sxs-lookup"><span data-stu-id="2e175-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="2e175-106">在某些情况下，通用语言运行时可能能够将`SByte`变量紧密打包在一起并节省内存消耗。</span><span class="sxs-lookup"><span data-stu-id="2e175-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="2e175-107">`SByte` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="2e175-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="2e175-108">文本分配</span><span class="sxs-lookup"><span data-stu-id="2e175-108">Literal assignments</span></span>

<span data-ttu-id="2e175-109">您可以通过为其分配十进制文本、`SByte`十六进制文本、八进制文本或（从 Visual Basic 2017 开头）二进制文本来声明和初始化变量。</span><span class="sxs-lookup"><span data-stu-id="2e175-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="2e175-110">在下面的示例中，等于 -102 的整数，表示为十进制、十六进制和二进制文本`SByte`。</span><span class="sxs-lookup"><span data-stu-id="2e175-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="2e175-111">此示例要求您使用`/removeintchecks`编译器开关进行编译。</span><span class="sxs-lookup"><span data-stu-id="2e175-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> <span data-ttu-id="2e175-112">`&h`您可以使用前缀或`&H`表示十六进制文本、前缀`&b`或`&B`表示二进制文本和前缀`&o`或`&O`表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="2e175-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="2e175-113">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="2e175-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="2e175-114">从 Visual Basic 2017 开始，您还可以使用下划线`_`字符 ，作为数字分隔符来增强可读性，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="2e175-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

<span data-ttu-id="2e175-115">从 Visual Basic 15.5 开始，您还可以使用下划线`_`字符 （ ） 作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。</span><span class="sxs-lookup"><span data-stu-id="2e175-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="2e175-116">例如：</span><span class="sxs-lookup"><span data-stu-id="2e175-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="2e175-117">如果整数文本在 `SByte` 范围之外（即，如果它小于 <xref:System.SByte.MinValue?displayProperty=nameWithType> 或大于 <xref:System.SByte.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="2e175-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="2e175-118">当整数文本没有后缀时，将推断出[整数](integer-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="2e175-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="2e175-119">如果整数文本超出`Integer`类型的范围，则推断为[Long。](long-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="2e175-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="2e175-120">这意味着，在前面的示例中，数字文本`0x9A`和`0b10011010`转换为 32 位签名整数，值为 156，超过<xref:System.SByte.MaxValue?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2e175-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2e175-121">要成功编译像这样将非十进制整数分配给 的代码`SByte`，可以执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="2e175-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="2e175-122">通过编译`/removeintchecks`编译器开关禁用整数边界检查。</span><span class="sxs-lookup"><span data-stu-id="2e175-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="2e175-123">使用[类型字符](../../programming-guide/language-features/data-types/type-characters.md)显式定义要分配给 的文本`SByte`值。</span><span class="sxs-lookup"><span data-stu-id="2e175-123">Use a [type character](../../programming-guide/language-features/data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="2e175-124">下面的示例将负文本`Short`值分配给 。 `SByte`</span><span class="sxs-lookup"><span data-stu-id="2e175-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="2e175-125">请注意，对于负数，必须设置数字文本的高阶字的高阶位。</span><span class="sxs-lookup"><span data-stu-id="2e175-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="2e175-126">在我们的示例中，这是文本`Short`值的第 15 位。</span><span class="sxs-lookup"><span data-stu-id="2e175-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="2e175-127">编程提示</span><span class="sxs-lookup"><span data-stu-id="2e175-127">Programming tips</span></span>

- <span data-ttu-id="2e175-128">**CLS 合规性。**</span><span class="sxs-lookup"><span data-stu-id="2e175-128">**CLS Compliance.**</span></span> <span data-ttu-id="2e175-129">数据类型`SByte`不是[通用语言规范](https://www.ecma-international.org/publications/standards/Ecma-335.htm)（CLS） 的一部分，因此符合 CLS 的代码不能使用使用它的组件。</span><span class="sxs-lookup"><span data-stu-id="2e175-129">The `SByte` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="2e175-130">**扩大。**</span><span class="sxs-lookup"><span data-stu-id="2e175-130">**Widening.**</span></span> <span data-ttu-id="2e175-131">数据类型`SByte`扩展到`Short`、、、、、、、`Integer``Long``Decimal``Single`和`Double`。</span><span class="sxs-lookup"><span data-stu-id="2e175-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="2e175-132">这意味着您可以转换为`SByte`任何这些类型的，而不会遇到<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="2e175-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="2e175-133">**键入字符。**</span><span class="sxs-lookup"><span data-stu-id="2e175-133">**Type Characters.**</span></span> <span data-ttu-id="2e175-134">`SByte`没有文本类型字符或标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="2e175-134">`SByte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="2e175-135">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="2e175-135">**Framework Type.**</span></span> <span data-ttu-id="2e175-136">.NET Framework 中的对应类型是 <xref:System.SByte?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="2e175-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e175-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e175-137">See also</span></span>

- <xref:System.SByte?displayProperty=nameWithType>
- [<span data-ttu-id="2e175-138">数据类型</span><span class="sxs-lookup"><span data-stu-id="2e175-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="2e175-139">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="2e175-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="2e175-140">转换摘要</span><span class="sxs-lookup"><span data-stu-id="2e175-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="2e175-141">Short 数据类型</span><span class="sxs-lookup"><span data-stu-id="2e175-141">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="2e175-142">整数数据类型</span><span class="sxs-lookup"><span data-stu-id="2e175-142">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="2e175-143">Long 数据类型</span><span class="sxs-lookup"><span data-stu-id="2e175-143">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="2e175-144">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="2e175-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
