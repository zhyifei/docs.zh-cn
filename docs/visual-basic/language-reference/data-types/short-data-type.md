---
title: "Short 数据类型 (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
f1_keywords: vb.Short
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
ms.openlocfilehash: fef948debed69cf9fb7b0e6bb65eb0ddbe497a92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="1f1b3-102">Short 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f1b3-102">Short data type (Visual Basic)</span></span>
<span data-ttu-id="1f1b3-103">保存有符号 16 位 （2 个字节） 整数，值的范围从-32768 到 32767。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f1b3-104">备注</span><span class="sxs-lookup"><span data-stu-id="1f1b3-104">Remarks</span></span>  
 <span data-ttu-id="1f1b3-105">使用`Short`数据类型包含不需要的完整数据宽度的整数值`Integer`。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="1f1b3-106">在某些情况下，公共语言运行时可以 pack 你`Short`紧密合作，以节省内存消耗的变量。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="1f1b3-107">`Short` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="1f1b3-108">文本分配</span><span class="sxs-lookup"><span data-stu-id="1f1b3-108">Literal assignments</span></span>

<span data-ttu-id="1f1b3-109">你可以声明并初始化`Short`变量中将其分配为十进制文本、 八进制文本中，为十六进制文本、 （开始或利用 Visual Basic 自 2017 年 1） 二进制文本。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="1f1b3-110">如果整数文本在 `Short` 范围之外（即，如果它小于 <xref:System.Int16.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Int16.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="1f1b3-111">在下面的示例中，整数等于 1,034，表示为十进制数字，十六进制，和从隐式转换二进制文本[整数](integer-data-type.md)到`Short`值。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="1f1b3-112">使用前缀`&h`或`&H`来表示为十六进制文本、 前缀`&b`或`&B`来表示二进制文字和前缀`&o`或`&O`来表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="1f1b3-113">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="1f1b3-114">从 Visual Basic 自 2017 年开始，你还可以使用下划线字符， `_`，作为数字分隔符以增强可读性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="1f1b3-115">此外可以包括数值`S`[键入字符](../../programming-guide\language-features\data-types/type-characters.md)来表示`Short`数据类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-115">Numeric literals can also include the `S` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H0326S
```

## <a name="programming-tips"></a><span data-ttu-id="1f1b3-116">编程提示</span><span class="sxs-lookup"><span data-stu-id="1f1b3-116">Programming tips</span></span>

-   <span data-ttu-id="1f1b3-117">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="1f1b3-117">**Widening.**</span></span> <span data-ttu-id="1f1b3-118">`Short`数据类型加宽到`Integer`， `Long`， `Decimal`， `Single`，或`Double`。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-118">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="1f1b3-119">这意味着，你可以将 `Short` 转换为这些类型中的任意类型，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType> 错误。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-119">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="1f1b3-120">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="1f1b3-120">**Type Characters.**</span></span> <span data-ttu-id="1f1b3-121">将文本类型字符 `S` 追加到文本会将其强制转换为 `Short` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-121">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="1f1b3-122">`Short`中有任何标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-122">`Short` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="1f1b3-123">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="1f1b3-123">**Framework Type.**</span></span> <span data-ttu-id="1f1b3-124">.NET Framework 中的对应类型是 <xref:System.Int16?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="1f1b3-124">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f1b3-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f1b3-125">See also</span></span>

 <xref:System.Int16?displayProperty=nameWithType>  
 [<span data-ttu-id="1f1b3-126">数据类型</span><span class="sxs-lookup"><span data-stu-id="1f1b3-126">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="1f1b3-127">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="1f1b3-127">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="1f1b3-128">转换摘要</span><span class="sxs-lookup"><span data-stu-id="1f1b3-128">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="1f1b3-129">Integer 数据类型</span><span class="sxs-lookup"><span data-stu-id="1f1b3-129">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="1f1b3-130">Long 数据类型</span><span class="sxs-lookup"><span data-stu-id="1f1b3-130">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="1f1b3-131">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="1f1b3-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
