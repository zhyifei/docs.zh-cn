---
title: "UShort 数据类型 (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ushort
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
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 513e8ce4694788d33c5aa14e34b95e88b6d37ff1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="da385-102">UShort 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da385-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="da385-103">包含无符号的 16 位 （2 个字节） 整数，范围为 0 到 65,535。</span><span class="sxs-lookup"><span data-stu-id="da385-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da385-104">备注</span><span class="sxs-lookup"><span data-stu-id="da385-104">Remarks</span></span>

 <span data-ttu-id="da385-105">使用`UShort`数据类型包含二进制数据对于来说太大`Byte`。</span><span class="sxs-lookup"><span data-stu-id="da385-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="da385-106">`UShort` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="da385-106">The default value of `UShort` is 0.</span></span>  

# <a name="literal-assignments"></a><span data-ttu-id="da385-107">文本分配</span><span class="sxs-lookup"><span data-stu-id="da385-107">Literal assignments</span></span>

<span data-ttu-id="da385-108">你可以声明并初始化`UShort`变量中将其分配为十进制文本、 八进制文本中，为十六进制文本、 （开始或利用 Visual Basic 自 2017 年 1） 二进制文本。</span><span class="sxs-lookup"><span data-stu-id="da385-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="da385-109">如果整数文本在 `UShort` 范围之外（即，如果它小于 <xref:System.UInt16.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt16.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="da385-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="da385-110">在下面的示例中，整数等于表示为十进制数字，十六进制，65,034 和二进制文本分配给`UShort`值。</span><span class="sxs-lookup"><span data-stu-id="da385-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="da385-111">使用前缀`&h`或`&H`来表示为十六进制文本、 前缀`&b`或`&B`来表示二进制文字和前缀`&o`或`&O`来表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="da385-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="da385-112">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="da385-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="da385-113">从 Visual Basic 自 2017 年开始，你还可以使用下划线字符， `_`，作为数字分隔符以增强可读性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="da385-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="da385-114">此外可以包括数值`US`或`us`[键入字符](../../programming-guide\language-features\data-types/type-characters.md)来表示`UShort`数据类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="da385-114">Numeric literals can also include the `US` or `us` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H035826us
```

## <a name="programming-tips"></a><span data-ttu-id="da385-115">编程提示</span><span class="sxs-lookup"><span data-stu-id="da385-115">Programming tips</span></span>
  
-   <span data-ttu-id="da385-116">**负数。**</span><span class="sxs-lookup"><span data-stu-id="da385-116">**Negative Numbers.**</span></span> <span data-ttu-id="da385-117">因为`UShort`是无符号的类型，它不能表示为负数。</span><span class="sxs-lookup"><span data-stu-id="da385-117">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="da385-118">如果你使用一元负 (`-`) 运算符的表达式的计算结果为键入`UShort`，Visual Basic 将转换为表达式`Integer`第一个。</span><span class="sxs-lookup"><span data-stu-id="da385-118">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
-   <span data-ttu-id="da385-119">**CLS 遵从性。**</span><span class="sxs-lookup"><span data-stu-id="da385-119">**CLS Compliance.**</span></span> <span data-ttu-id="da385-120">`UShort`数据类型不是属于[公共语言规范](http://www.ecma-international.org/publications/standards/Ecma-335.htm)(CLS)，因此符合 cls 的代码不能使用的组件，使用它。</span><span class="sxs-lookup"><span data-stu-id="da385-120">The `UShort` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="da385-121">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="da385-121">**Widening.**</span></span> <span data-ttu-id="da385-122">`UShort`数据类型加宽到`Integer`， `UInteger`， `Long`， `ULong`， `Decimal`， `Single`，和`Double`。</span><span class="sxs-lookup"><span data-stu-id="da385-122">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="da385-123">这意味着你可以将转换`UShort`到而不会遇到这些类型的任何<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="da385-123">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="da385-124">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="da385-124">**Type Characters.**</span></span> <span data-ttu-id="da385-125">附加文本类型字符`US`到文本将其强制转换到`UShort`数据类型。</span><span class="sxs-lookup"><span data-stu-id="da385-125">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="da385-126">`UShort`中有任何标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="da385-126">`UShort` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="da385-127">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="da385-127">**Framework Type.**</span></span> <span data-ttu-id="da385-128">.NET Framework 中的对应类型是 <xref:System.UInt16?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="da385-128">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da385-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da385-129">See Also</span></span>  
 <xref:System.UInt16>  
 [<span data-ttu-id="da385-130">数据类型</span><span class="sxs-lookup"><span data-stu-id="da385-130">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="da385-131">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="da385-131">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="da385-132">转换摘要</span><span class="sxs-lookup"><span data-stu-id="da385-132">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="da385-133">如何：调用采用无符号类型的 Windows 函数</span><span class="sxs-lookup"><span data-stu-id="da385-133">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="da385-134">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="da385-134">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
