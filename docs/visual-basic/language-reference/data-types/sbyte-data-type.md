---
title: "SByte 数据类型 (Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d391d7eea27ec7696dbb4c28da8916c744712f32
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="ecdaf-102">SByte 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecdaf-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="ecdaf-103">存储带符号的 8 位 （1 个字节） 整数，值的范围从-128 到 127。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecdaf-104">备注</span><span class="sxs-lookup"><span data-stu-id="ecdaf-104">Remarks</span></span>

<span data-ttu-id="ecdaf-105">使用`SByte`数据类型包含不需要的完整数据宽度的整数值`Integer`甚至数据长度的一半的`Short`。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="ecdaf-106">在某些情况下，公共语言运行时可能能够包你`SByte`紧密合作，以节省内存消耗的变量。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="ecdaf-107">`SByte` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="ecdaf-108">文本分配</span><span class="sxs-lookup"><span data-stu-id="ecdaf-108">Literal assignments</span></span>
  
<span data-ttu-id="ecdaf-109">你可以声明并初始化`SByte`变量中将其分配为十进制文本、 八进制文本中，为十六进制文本、 （开始或利用 Visual Basic 自 2017 年 1） 二进制文本。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="ecdaf-110">在下面的示例中，整数等于表示为十进制数字，十六进制，-102 和二进制文本分配给`SByte`值。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="ecdaf-111">此示例需要使用编译`/removeintchecks`编译器开关。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> <span data-ttu-id="ecdaf-112">使用前缀`&h`或`&H`来表示为十六进制文本、 前缀`&b`或`&B`来表示二进制文字和前缀`&o`或`&O`来表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="ecdaf-113">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="ecdaf-114">从 Visual Basic 自 2017 年开始，你还可以使用下划线字符， `_`，作为数字分隔符以增强可读性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

<span data-ttu-id="ecdaf-115">从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 为之间的前缀和十六进制、 二进制文件，或八进制数字的前导分隔符。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="ecdaf-116">例如:</span><span class="sxs-lookup"><span data-stu-id="ecdaf-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="ecdaf-117">如果整数文本在 `SByte` 范围之外（即，如果它小于 <xref:System.SByte.MinValue?displayProperty=nameWithType> 或大于 <xref:System.SByte.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="ecdaf-118">当一个整数文本具有无后缀[整数](integer-data-type.md)这方面的推断。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="ecdaf-119">如果整数文本之外的范围，则`Integer`类型，[长](long-data-type.md)这方面的推断。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="ecdaf-120">这意味着，在前面的示例中，数字文本`0x9A`和`0b10011010`都会被解释为 32 位有符号整数值为 156，这超出<xref:System.SByte.MaxValue?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ecdaf-121">若要成功编译代码如下将分配到一个非十进制整数`SByte`，你可以执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="ecdaf-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="ecdaf-122">通过使用编译禁用整数边界检查`/removeintchecks`编译器开关。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="ecdaf-123">使用[键入字符](../../programming-guide\language-features\data-types/type-characters.md)明确地定义你想要分配到的文本值`SByte`。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-123">Use a [type character](../../programming-guide\language-features\data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="ecdaf-124">下面的示例将负文本`Short`值赋给`SByte`。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="ecdaf-125">请注意，负数，必须设置数值的高序位字的高顺序位。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="ecdaf-126">对于本示例中，这位的文本的 15`Short`值。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="ecdaf-127">编程提示</span><span class="sxs-lookup"><span data-stu-id="ecdaf-127">Programming tips</span></span>
  
-   <span data-ttu-id="ecdaf-128">**CLS 遵从性。**</span><span class="sxs-lookup"><span data-stu-id="ecdaf-128">**CLS Compliance.**</span></span> <span data-ttu-id="ecdaf-129">`SByte`数据类型不是属于[公共语言规范](http://www.ecma-international.org/publications/standards/Ecma-335.htm)(CLS)，因此符合 cls 的代码不能使用的组件，使用它。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-129">The `SByte` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

-   <span data-ttu-id="ecdaf-130">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="ecdaf-130">**Widening.**</span></span> <span data-ttu-id="ecdaf-131">`SByte`数据类型加宽到`Short`， `Integer`， `Long`， `Decimal`， `Single`，和`Double`。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="ecdaf-132">这意味着你可以将转换`SByte`到而不会遇到这些类型的任何<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="ecdaf-133">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="ecdaf-133">**Type Characters.**</span></span> <span data-ttu-id="ecdaf-134">`SByte`不包含文本类型字符或标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-134">`SByte` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="ecdaf-135">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="ecdaf-135">**Framework Type.**</span></span> <span data-ttu-id="ecdaf-136">.NET Framework 中的对应类型是 <xref:System.SByte?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="ecdaf-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ecdaf-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecdaf-137">See also</span></span>

 <xref:System.SByte?displayProperty=nameWithType>  
 [<span data-ttu-id="ecdaf-138">数据类型</span><span class="sxs-lookup"><span data-stu-id="ecdaf-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="ecdaf-139">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="ecdaf-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="ecdaf-140">转换摘要</span><span class="sxs-lookup"><span data-stu-id="ecdaf-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="ecdaf-141">Short 数据类型</span><span class="sxs-lookup"><span data-stu-id="ecdaf-141">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [<span data-ttu-id="ecdaf-142">Integer 数据类型</span><span class="sxs-lookup"><span data-stu-id="ecdaf-142">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="ecdaf-143">Long 数据类型</span><span class="sxs-lookup"><span data-stu-id="ecdaf-143">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="ecdaf-144">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="ecdaf-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
