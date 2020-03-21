---
title: Byte 数据类型
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401351"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="2d45c-102">字节数据类型（可视基本）</span><span class="sxs-lookup"><span data-stu-id="2d45c-102">Byte data type (Visual Basic)</span></span>

<span data-ttu-id="2d45c-103">保存未签名的 8 位（1 字节）整数，其值范围为 0 到 255。</span><span class="sxs-lookup"><span data-stu-id="2d45c-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d45c-104">备注</span><span class="sxs-lookup"><span data-stu-id="2d45c-104">Remarks</span></span>

<span data-ttu-id="2d45c-105">使用`Byte`数据类型包含二进制数据。</span><span class="sxs-lookup"><span data-stu-id="2d45c-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="2d45c-106">`Byte` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="2d45c-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="2d45c-107">文本分配</span><span class="sxs-lookup"><span data-stu-id="2d45c-107">Literal assignments</span></span>

<span data-ttu-id="2d45c-108">您可以通过为其分配十进制文本、`Byte`十六进制文本、八进制文本或（从 Visual Basic 2017 开头）二进制文本来声明和初始化变量。</span><span class="sxs-lookup"><span data-stu-id="2d45c-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="2d45c-109">如果积分文本超出 的范围`Byte`（即，如果它小于<xref:System.Byte.MinValue?displayProperty=nameWithType>或大于<xref:System.Byte.MaxValue?displayProperty=nameWithType>），则会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="2d45c-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="2d45c-110">在下面的示例中，等于 201 的整数表示为十进制、十六进制和二进制文本，从[整数](integer-data-type.md)隐式转换为`byte`值。</span><span class="sxs-lookup"><span data-stu-id="2d45c-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="2d45c-111">`&h`您可以使用前缀或`&H`表示十六进制文本、前缀`&b`或`&B`表示二进制文本和前缀`&o`或`&O`表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="2d45c-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="2d45c-112">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="2d45c-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="2d45c-113">从 Visual Basic 2017 开始，您还可以使用下划线`_`字符 ，作为数字分隔符来增强可读性，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="2d45c-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="2d45c-114">从 Visual Basic 15.5 开始，您还可以使用下划线`_`字符 （ ） 作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。</span><span class="sxs-lookup"><span data-stu-id="2d45c-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="2d45c-115">例如：</span><span class="sxs-lookup"><span data-stu-id="2d45c-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="2d45c-116">编程提示</span><span class="sxs-lookup"><span data-stu-id="2d45c-116">Programming tips</span></span>

- <span data-ttu-id="2d45c-117">**负数。**</span><span class="sxs-lookup"><span data-stu-id="2d45c-117">**Negative Numbers.**</span></span> <span data-ttu-id="2d45c-118">因为它是`Byte`无符号类型，它不能表示负数。</span><span class="sxs-lookup"><span data-stu-id="2d45c-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="2d45c-119">如果在计算为键入`-``Byte`的表达式上使用一元减号 （ ） 运算符，Visual Basic 将表达式转换为`Short`第一个表达式。</span><span class="sxs-lookup"><span data-stu-id="2d45c-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="2d45c-120">**格式转换。**</span><span class="sxs-lookup"><span data-stu-id="2d45c-120">**Format Conversions.**</span></span> <span data-ttu-id="2d45c-121">当 Visual Basic 读取或写入文件时，或者当它调用 DLL、方法和属性时，它可以在数据格式之间自动转换。</span><span class="sxs-lookup"><span data-stu-id="2d45c-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="2d45c-122">存储在变量和数组`Byte`中的二进制数据在此类格式转换期间保留。</span><span class="sxs-lookup"><span data-stu-id="2d45c-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="2d45c-123">不应将`String`变量用于二进制数据，因为其内容在 ANSI 和 Unicode 格式之间的转换过程中可能会损坏。</span><span class="sxs-lookup"><span data-stu-id="2d45c-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="2d45c-124">**扩大。**</span><span class="sxs-lookup"><span data-stu-id="2d45c-124">**Widening.**</span></span> <span data-ttu-id="2d45c-125">数据类型`Byte``Short`扩展到 、 `UShort` `Integer`、 、 `UInteger`、 `Long` `ULong`、 `Decimal` `Single`、 `Double`、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、 、</span><span class="sxs-lookup"><span data-stu-id="2d45c-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="2d45c-126">这意味着您可以转换为`Byte`任何这些类型的，而不会遇到<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="2d45c-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="2d45c-127">**键入字符。**</span><span class="sxs-lookup"><span data-stu-id="2d45c-127">**Type Characters.**</span></span> <span data-ttu-id="2d45c-128">`Byte`没有文本类型字符或标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="2d45c-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="2d45c-129">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="2d45c-129">**Framework Type.**</span></span> <span data-ttu-id="2d45c-130">.NET Framework 中的对应类型是 <xref:System.Byte?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="2d45c-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="2d45c-131">示例</span><span class="sxs-lookup"><span data-stu-id="2d45c-131">Example</span></span>

 <span data-ttu-id="2d45c-132">在下面的示例中，`b`是一个`Byte`变量。</span><span class="sxs-lookup"><span data-stu-id="2d45c-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="2d45c-133">这些语句演示了变量的范围以及位移位运算符对变量的应用。</span><span class="sxs-lookup"><span data-stu-id="2d45c-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="2d45c-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d45c-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="2d45c-135">数据类型</span><span class="sxs-lookup"><span data-stu-id="2d45c-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="2d45c-136">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="2d45c-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="2d45c-137">转换摘要</span><span class="sxs-lookup"><span data-stu-id="2d45c-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="2d45c-138">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="2d45c-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
