---
title: Short 数据类型
ms.date: 01/31/2018
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: 8dfdfb56de32e4b3a96729b09ccf46a6fee9a424
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343939"
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="155f2-102">Short data type (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="155f2-102">Short data type (Visual Basic)</span></span>

<span data-ttu-id="155f2-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span><span class="sxs-lookup"><span data-stu-id="155f2-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="155f2-104">备注</span><span class="sxs-lookup"><span data-stu-id="155f2-104">Remarks</span></span>  

 <span data-ttu-id="155f2-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span><span class="sxs-lookup"><span data-stu-id="155f2-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="155f2-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span><span class="sxs-lookup"><span data-stu-id="155f2-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="155f2-107">`Short` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="155f2-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="155f2-108">Literal assignments</span><span class="sxs-lookup"><span data-stu-id="155f2-108">Literal assignments</span></span>

<span data-ttu-id="155f2-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span><span class="sxs-lookup"><span data-stu-id="155f2-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="155f2-110">如果整数文本在 `Short` 范围之外（即，如果它小于 <xref:System.Int16.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Int16.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="155f2-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="155f2-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span><span class="sxs-lookup"><span data-stu-id="155f2-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="155f2-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span><span class="sxs-lookup"><span data-stu-id="155f2-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="155f2-113">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="155f2-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="155f2-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span><span class="sxs-lookup"><span data-stu-id="155f2-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="155f2-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span><span class="sxs-lookup"><span data-stu-id="155f2-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="155f2-116">例如:</span><span class="sxs-lookup"><span data-stu-id="155f2-116">For example:</span></span>

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="155f2-117">Numeric literals can also include the `S` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span><span class="sxs-lookup"><span data-stu-id="155f2-117">Numeric literals can also include the `S` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a><span data-ttu-id="155f2-118">编程提示</span><span class="sxs-lookup"><span data-stu-id="155f2-118">Programming tips</span></span>

- <span data-ttu-id="155f2-119">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="155f2-119">**Widening.**</span></span> <span data-ttu-id="155f2-120">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span><span class="sxs-lookup"><span data-stu-id="155f2-120">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="155f2-121">这意味着，你可以将 `Short` 转换为这些类型中的任意类型，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。</span><span class="sxs-lookup"><span data-stu-id="155f2-121">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="155f2-122">**Type Characters.**</span><span class="sxs-lookup"><span data-stu-id="155f2-122">**Type Characters.**</span></span> <span data-ttu-id="155f2-123">将文本类型字符 `S` 追加到文本会将其强制转换为 `Short` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="155f2-123">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="155f2-124">`Short` has no identifier type character.</span><span class="sxs-lookup"><span data-stu-id="155f2-124">`Short` has no identifier type character.</span></span>  
  
- <span data-ttu-id="155f2-125">**Framework Type.**</span><span class="sxs-lookup"><span data-stu-id="155f2-125">**Framework Type.**</span></span> <span data-ttu-id="155f2-126">.NET Framework 中的对应类型是 <xref:System.Int16?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="155f2-126">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="155f2-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="155f2-127">See also</span></span>

- <xref:System.Int16?displayProperty=nameWithType>
- [<span data-ttu-id="155f2-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="155f2-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="155f2-129">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="155f2-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="155f2-130">转换摘要</span><span class="sxs-lookup"><span data-stu-id="155f2-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="155f2-131">Integer 数据类型</span><span class="sxs-lookup"><span data-stu-id="155f2-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="155f2-132">Long 数据类型</span><span class="sxs-lookup"><span data-stu-id="155f2-132">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="155f2-133">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="155f2-133">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
