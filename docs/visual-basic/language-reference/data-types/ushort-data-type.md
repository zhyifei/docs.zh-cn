---
title: UShort 数据类型
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
ms.openlocfilehash: 7cdbd5fb192fd5cc1be6260dcdcdb1f30cf3f865
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401309"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="92ab2-102">UShort 数据类型（可视基本）</span><span class="sxs-lookup"><span data-stu-id="92ab2-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="92ab2-103">保存未签名的 16 位（2 字节）整数，其值范围为 0 到 65，535。</span><span class="sxs-lookup"><span data-stu-id="92ab2-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92ab2-104">备注</span><span class="sxs-lookup"><span data-stu-id="92ab2-104">Remarks</span></span>

 <span data-ttu-id="92ab2-105">使用`UShort`数据类型包含的二进制数据太大。 `Byte`</span><span class="sxs-lookup"><span data-stu-id="92ab2-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="92ab2-106">`UShort` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="92ab2-106">The default value of `UShort` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="92ab2-107">文本分配</span><span class="sxs-lookup"><span data-stu-id="92ab2-107">Literal assignments</span></span>

<span data-ttu-id="92ab2-108">您可以通过为其分配十进制文本、`UShort`十六进制文本、八进制文本或（从 Visual Basic 2017 开头）二进制文本来声明和初始化变量。</span><span class="sxs-lookup"><span data-stu-id="92ab2-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="92ab2-109">如果整数文本在 `UShort` 范围之外（即，如果它小于 <xref:System.UInt16.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt16.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="92ab2-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="92ab2-110">在下面的示例中，等于 65，034 的整数，表示为十进制、十六进制和二进制文本`UShort`。</span><span class="sxs-lookup"><span data-stu-id="92ab2-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="92ab2-111">`&h`您可以使用前缀或`&H`表示十六进制文本、前缀`&b`或`&B`表示二进制文本和前缀`&o`或`&O`表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="92ab2-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="92ab2-112">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="92ab2-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="92ab2-113">从 Visual Basic 2017 开始，您还可以使用下划线`_`字符 ，作为数字分隔符来增强可读性，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="92ab2-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="92ab2-114">从 Visual Basic 15.5 开始，您还可以使用下划线`_`字符 （ ） 作为前缀和十六进制、二进制或八进制数字之间的前导分隔符。</span><span class="sxs-lookup"><span data-stu-id="92ab2-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="92ab2-115">例如：</span><span class="sxs-lookup"><span data-stu-id="92ab2-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="92ab2-116">数字文本还可以包括`US`或`us`[类型字符](../../programming-guide/language-features/data-types/type-characters.md)来表示`UShort`数据类型，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="92ab2-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="92ab2-117">编程提示</span><span class="sxs-lookup"><span data-stu-id="92ab2-117">Programming tips</span></span>
  
- <span data-ttu-id="92ab2-118">**负数。**</span><span class="sxs-lookup"><span data-stu-id="92ab2-118">**Negative Numbers.**</span></span> <span data-ttu-id="92ab2-119">因为它是`UShort`无符号类型，它不能表示负数。</span><span class="sxs-lookup"><span data-stu-id="92ab2-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="92ab2-120">如果在计算为键入`-``UShort`的表达式上使用一元减号 （ ） 运算符，Visual Basic 将表达式转换为`Integer`第一个表达式。</span><span class="sxs-lookup"><span data-stu-id="92ab2-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
- <span data-ttu-id="92ab2-121">**CLS 合规性。**</span><span class="sxs-lookup"><span data-stu-id="92ab2-121">**CLS Compliance.**</span></span> <span data-ttu-id="92ab2-122">数据类型`UShort`不是[通用语言规范](https://www.ecma-international.org/publications/standards/Ecma-335.htm)（CLS） 的一部分，因此符合 CLS 的代码不能使用使用它的组件。</span><span class="sxs-lookup"><span data-stu-id="92ab2-122">The `UShort` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
- <span data-ttu-id="92ab2-123">**扩大。**</span><span class="sxs-lookup"><span data-stu-id="92ab2-123">**Widening.**</span></span> <span data-ttu-id="92ab2-124">数据类型`UShort`扩展到`Integer`、、、、、、、、`Single``Double``UInteger``Long``ULong``Decimal`和 。</span><span class="sxs-lookup"><span data-stu-id="92ab2-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="92ab2-125">这意味着您可以转换为`UShort`任何这些类型的，而不会遇到<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="92ab2-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="92ab2-126">**键入字符。**</span><span class="sxs-lookup"><span data-stu-id="92ab2-126">**Type Characters.**</span></span> <span data-ttu-id="92ab2-127">将文本类型字符`US`追加到文本强制它到`UShort`数据类型。</span><span class="sxs-lookup"><span data-stu-id="92ab2-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="92ab2-128">`UShort`没有标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="92ab2-128">`UShort` has no identifier type character.</span></span>  
  
- <span data-ttu-id="92ab2-129">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="92ab2-129">**Framework Type.**</span></span> <span data-ttu-id="92ab2-130">.NET Framework 中的对应类型是 <xref:System.UInt16?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="92ab2-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ab2-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92ab2-131">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="92ab2-132">数据类型</span><span class="sxs-lookup"><span data-stu-id="92ab2-132">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="92ab2-133">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="92ab2-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="92ab2-134">转换摘要</span><span class="sxs-lookup"><span data-stu-id="92ab2-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="92ab2-135">如何：调用采用无符号类型的 Windows 函数</span><span class="sxs-lookup"><span data-stu-id="92ab2-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="92ab2-136">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="92ab2-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
