---
title: UShort 数据类型 (Visual Basic)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 038aad2c41f655d0699dab33df276132a70e3ede
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46696668"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="ccd41-102">UShort 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ccd41-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="ccd41-103">包含无符号的 16 位 （2 个字节） 整数取值范围为 0 到 65,535。</span><span class="sxs-lookup"><span data-stu-id="ccd41-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccd41-104">备注</span><span class="sxs-lookup"><span data-stu-id="ccd41-104">Remarks</span></span>

 <span data-ttu-id="ccd41-105">使用`UShort`数据类型来包含二进制数据太大， `Byte`。</span><span class="sxs-lookup"><span data-stu-id="ccd41-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="ccd41-106">`UShort` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="ccd41-106">The default value of `UShort` is 0.</span></span>  

# <a name="literal-assignments"></a><span data-ttu-id="ccd41-107">文本分配</span><span class="sxs-lookup"><span data-stu-id="ccd41-107">Literal assignments</span></span>

<span data-ttu-id="ccd41-108">您可以声明并初始化`UShort`变量由将其分配十进制文本、 十六进制文本八进制文本，或 （Visual Basic 从 2017年开始） 二进制文本。</span><span class="sxs-lookup"><span data-stu-id="ccd41-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="ccd41-109">如果整数文本在 `UShort` 范围之外（即，如果它小于 <xref:System.UInt16.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt16.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="ccd41-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="ccd41-110">在以下示例中，整数等于 65034、 表示为十进制、 十六进制和二进制文本分配给`UShort`值。</span><span class="sxs-lookup"><span data-stu-id="ccd41-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="ccd41-111">使用前缀`&h`或`&H`来表示十六进制文本前缀`&b`或`&B`来表示二进制文本和前缀`&o`或`&O`来表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="ccd41-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="ccd41-112">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="ccd41-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="ccd41-113">从 Visual Basic 2017 开始，你还可以使用下划线字符， `_`，作为数字分隔符，以增强可读性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="ccd41-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="ccd41-114">从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 作为前缀和十六进制、 二进制或八进制数字之间的前导分隔符。</span><span class="sxs-lookup"><span data-stu-id="ccd41-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="ccd41-115">例如：</span><span class="sxs-lookup"><span data-stu-id="ccd41-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="ccd41-116">此外可以包含数值`US`或`us`[键入字符](../../programming-guide\language-features\data-types/type-characters.md)来表示`UShort`数据类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="ccd41-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="ccd41-117">编程提示</span><span class="sxs-lookup"><span data-stu-id="ccd41-117">Programming tips</span></span>
  
-   <span data-ttu-id="ccd41-118">**负号。**</span><span class="sxs-lookup"><span data-stu-id="ccd41-118">**Negative Numbers.**</span></span> <span data-ttu-id="ccd41-119">因为`UShort`是无符号的类型，它不能表示为负数。</span><span class="sxs-lookup"><span data-stu-id="ccd41-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="ccd41-120">如果使用一元负 (`-`) 运算符的表达式的计算结果为类型`UShort`，Visual Basic 将转换为表达式`Integer`第一个。</span><span class="sxs-lookup"><span data-stu-id="ccd41-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
-   <span data-ttu-id="ccd41-121">**CLS 遵从性。**</span><span class="sxs-lookup"><span data-stu-id="ccd41-121">**CLS Compliance.**</span></span> <span data-ttu-id="ccd41-122">`UShort`数据类型不属于[公共语言规范](http://www.ecma-international.org/publications/standards/Ecma-335.htm)(CLS)，因此符合 cls 的代码不能使用使用它的组件。</span><span class="sxs-lookup"><span data-stu-id="ccd41-122">The `UShort` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="ccd41-123">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="ccd41-123">**Widening.**</span></span> <span data-ttu-id="ccd41-124">`UShort`数据类型加宽到`Integer`， `UInteger`， `Long`， `ULong`， `Decimal`， `Single`，和`Double`。</span><span class="sxs-lookup"><span data-stu-id="ccd41-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="ccd41-125">这意味着可以将转换`UShort`而不会遇到这些类型的任何<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="ccd41-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="ccd41-126">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="ccd41-126">**Type Characters.**</span></span> <span data-ttu-id="ccd41-127">追加文本类型字符`US`为文本将其强制转换到`UShort`数据类型。</span><span class="sxs-lookup"><span data-stu-id="ccd41-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="ccd41-128">`UShort` 有没有标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="ccd41-128">`UShort` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="ccd41-129">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="ccd41-129">**Framework Type.**</span></span> <span data-ttu-id="ccd41-130">.NET Framework 中的对应类型是 <xref:System.UInt16?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="ccd41-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd41-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="ccd41-131">See Also</span></span>  
 <xref:System.UInt16>  
 [<span data-ttu-id="ccd41-132">数据类型</span><span class="sxs-lookup"><span data-stu-id="ccd41-132">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="ccd41-133">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="ccd41-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="ccd41-134">转换摘要</span><span class="sxs-lookup"><span data-stu-id="ccd41-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="ccd41-135">如何：调用采用无符号类型的 Windows 函数</span><span class="sxs-lookup"><span data-stu-id="ccd41-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="ccd41-136">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="ccd41-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
