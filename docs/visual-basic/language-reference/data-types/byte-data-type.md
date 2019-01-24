---
title: Byte 数据类型 (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 8c9787d52667dc026d3fe62ac7f4b3de7e838a93
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519783"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="15356-102">Byte 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15356-102">Byte data type (Visual Basic)</span></span>
<span data-ttu-id="15356-103">保留范围在 0 到 255 的无符号的 8 位 （1 个字节） 整数。</span><span class="sxs-lookup"><span data-stu-id="15356-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="15356-104">备注</span><span class="sxs-lookup"><span data-stu-id="15356-104">Remarks</span></span>

<span data-ttu-id="15356-105">使用`Byte`数据类型来包含二进制数据。</span><span class="sxs-lookup"><span data-stu-id="15356-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="15356-106">`Byte` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="15356-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="15356-107">文本分配</span><span class="sxs-lookup"><span data-stu-id="15356-107">Literal assignments</span></span>

<span data-ttu-id="15356-108">您可以声明并初始化`Byte`变量由将其分配十进制文本、 十六进制文本八进制文本，或 （Visual Basic 从 2017年开始） 二进制文本。</span><span class="sxs-lookup"><span data-stu-id="15356-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="15356-109">如果整型文本之外的范围，则`Byte`(即，如果它是小于<xref:System.Byte.MinValue?displayProperty=nameWithType>或大于<xref:System.Byte.MaxValue?displayProperty=nameWithType>)，将出现编译错误。</span><span class="sxs-lookup"><span data-stu-id="15356-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="15356-110">在以下示例中，整数等于 201 表示为十进制、 十六进制和二进制文本隐式转换从[整数](integer-data-type.md)到`byte`值。</span><span class="sxs-lookup"><span data-stu-id="15356-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="15356-111">使用前缀`&h`或`&H`来表示十六进制文本前缀`&b`或`&B`来表示二进制文本和前缀`&o`或`&O`来表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="15356-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="15356-112">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="15356-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="15356-113">从 Visual Basic 2017 开始，你还可以使用下划线字符， `_`，作为数字分隔符，以增强可读性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="15356-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="15356-114">从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 作为前缀和十六进制、 二进制或八进制数字之间的前导分隔符。</span><span class="sxs-lookup"><span data-stu-id="15356-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="15356-115">例如：</span><span class="sxs-lookup"><span data-stu-id="15356-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="15356-116">编程提示</span><span class="sxs-lookup"><span data-stu-id="15356-116">Programming tips</span></span>

-   <span data-ttu-id="15356-117">**负号。**</span><span class="sxs-lookup"><span data-stu-id="15356-117">**Negative Numbers.**</span></span> <span data-ttu-id="15356-118">因为`Byte`是无符号的类型，它不能表示为负数。</span><span class="sxs-lookup"><span data-stu-id="15356-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="15356-119">如果使用一元负 (`-`) 运算符的表达式的计算结果为类型`Byte`，Visual Basic 将转换为表达式`Short`第一个。</span><span class="sxs-lookup"><span data-stu-id="15356-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
-   <span data-ttu-id="15356-120">**格式转换。**</span><span class="sxs-lookup"><span data-stu-id="15356-120">**Format Conversions.**</span></span> <span data-ttu-id="15356-121">当 Visual Basic 中读取或写入文件，或调用 Dll、 方法和属性时，它可以自动将数据格式之间转换。</span><span class="sxs-lookup"><span data-stu-id="15356-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="15356-122">二进制数据存储在`Byte`这种格式转换过程中会保留变量和数组。</span><span class="sxs-lookup"><span data-stu-id="15356-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="15356-123">不应使用`String`变量对于二进制数据，因为其内容在 ANSI 和 Unicode 格式之间转换过程可能会损坏。</span><span class="sxs-lookup"><span data-stu-id="15356-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

-   <span data-ttu-id="15356-124">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="15356-124">**Widening.**</span></span> <span data-ttu-id="15356-125">`Byte`数据类型加宽到`Short`， `UShort`， `Integer`， `UInteger`， `Long`， `ULong`， `Decimal`， `Single`，或`Double`。</span><span class="sxs-lookup"><span data-stu-id="15356-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="15356-126">这意味着可以将转换`Byte`而不会遇到这些类型的任何<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="15356-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="15356-127">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="15356-127">**Type Characters.**</span></span> <span data-ttu-id="15356-128">`Byte` 不包含文本类型字符或标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="15356-128">`Byte` has no literal type character or identifier type character.</span></span>

-   <span data-ttu-id="15356-129">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="15356-129">**Framework Type.**</span></span> <span data-ttu-id="15356-130">.NET Framework 中的对应类型是 <xref:System.Byte?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="15356-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="15356-131">示例</span><span class="sxs-lookup"><span data-stu-id="15356-131">Example</span></span>

 <span data-ttu-id="15356-132">在以下示例中，`b`是`Byte`变量。</span><span class="sxs-lookup"><span data-stu-id="15356-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="15356-133">语句演示变量的范围和移位运算符应用于它。</span><span class="sxs-lookup"><span data-stu-id="15356-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a><span data-ttu-id="15356-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="15356-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="15356-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="15356-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="15356-136">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="15356-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="15356-137">转换摘要</span><span class="sxs-lookup"><span data-stu-id="15356-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="15356-138">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="15356-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
