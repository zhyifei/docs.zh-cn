---
title: Short 数据类型 (Visual Basic)
ms.date: 01/31/2018
author: rpetrusha
ms.author: ronpet
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
ms.openlocfilehash: eb218a9b72208b13700ebd18dbf588066839203d
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46532764"
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="1f7d9-102">Short 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f7d9-102">Short data type (Visual Basic)</span></span>
<span data-ttu-id="1f7d9-103">保存有符号 16 位 （2 个字节） 整数，值的范围从-32,768 到 32767 之间。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f7d9-104">备注</span><span class="sxs-lookup"><span data-stu-id="1f7d9-104">Remarks</span></span>  
 <span data-ttu-id="1f7d9-105">使用`Short`数据类型包含不需要的完整数据宽度的整数值`Integer`。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="1f7d9-106">在某些情况下，公共语言运行时能够打包你`Short`变量紧密合作，以节省内存消耗。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="1f7d9-107">`Short` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="1f7d9-108">文本分配</span><span class="sxs-lookup"><span data-stu-id="1f7d9-108">Literal assignments</span></span>

<span data-ttu-id="1f7d9-109">您可以声明并初始化`Short`变量由将其分配十进制文本、 十六进制文本八进制文本，或 （Visual Basic 从 2017年开始） 二进制文本。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="1f7d9-110">如果整数文本在 `Short` 范围之外（即，如果它小于 <xref:System.Int16.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Int16.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="1f7d9-111">在以下示例中，整数等于 1034、 表示为十进制、 十六进制和二进制文本隐式转换从[整数](integer-data-type.md)到`Short`值。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="1f7d9-112">使用前缀`&h`或`&H`来表示十六进制文本前缀`&b`或`&B`来表示二进制文本和前缀`&o`或`&O`来表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="1f7d9-113">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="1f7d9-114">从 Visual Basic 2017 开始，你还可以使用下划线字符， `_`，作为数字分隔符，以增强可读性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="1f7d9-115">从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 作为前缀和十六进制、 二进制或八进制数字之间的前导分隔符。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="1f7d9-116">例如：</span><span class="sxs-lookup"><span data-stu-id="1f7d9-116">For example:</span></span>

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="1f7d9-117">此外可以包含数值`S`[键入字符](../../programming-guide\language-features\data-types/type-characters.md)来表示`Short`数据类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-117">Numeric literals can also include the `S` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a><span data-ttu-id="1f7d9-118">编程提示</span><span class="sxs-lookup"><span data-stu-id="1f7d9-118">Programming tips</span></span>

-   <span data-ttu-id="1f7d9-119">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="1f7d9-119">**Widening.**</span></span> <span data-ttu-id="1f7d9-120">`Short`数据类型加宽到`Integer`， `Long`， `Decimal`， `Single`，或`Double`。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-120">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="1f7d9-121">这意味着，你可以将 `Short` 转换为这些类型中的任意类型，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-121">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="1f7d9-122">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="1f7d9-122">**Type Characters.**</span></span> <span data-ttu-id="1f7d9-123">将文本类型字符 `S` 追加到文本会将其强制转换为 `Short` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-123">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="1f7d9-124">`Short` 有没有标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-124">`Short` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="1f7d9-125">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="1f7d9-125">**Framework Type.**</span></span> <span data-ttu-id="1f7d9-126">.NET Framework 中的对应类型是 <xref:System.Int16?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="1f7d9-126">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f7d9-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f7d9-127">See also</span></span>

 <xref:System.Int16?displayProperty=nameWithType>  
 [<span data-ttu-id="1f7d9-128">数据类型</span><span class="sxs-lookup"><span data-stu-id="1f7d9-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="1f7d9-129">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="1f7d9-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="1f7d9-130">转换摘要</span><span class="sxs-lookup"><span data-stu-id="1f7d9-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="1f7d9-131">Integer 数据类型</span><span class="sxs-lookup"><span data-stu-id="1f7d9-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="1f7d9-132">Long 数据类型</span><span class="sxs-lookup"><span data-stu-id="1f7d9-132">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="1f7d9-133">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="1f7d9-133">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
