---
title: "ULong 数据类型 (Visual Basic)"
ms.date: 01/31/2018
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 606e0ef87b209bb2e75e28223f27d081713c1b7e
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="f6259-102">ULong 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6259-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="f6259-103">包含无符号的 64 位 （8 字节） 整数，范围为 0 到 18446744073709551615 (多个 1.84 倍 10 ^19)。</span><span class="sxs-lookup"><span data-stu-id="f6259-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6259-104">备注</span><span class="sxs-lookup"><span data-stu-id="f6259-104">Remarks</span></span>

<span data-ttu-id="f6259-105">使用`ULong`数据类型包含二进制数据对于来说太大`UInteger`，或可能的最大无符号整数值。</span><span class="sxs-lookup"><span data-stu-id="f6259-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>  
  
<span data-ttu-id="f6259-106">`ULong` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="f6259-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="f6259-107">文本分配</span><span class="sxs-lookup"><span data-stu-id="f6259-107">Literal assignments</span></span>

<span data-ttu-id="f6259-108">你可以声明并初始化`ULong`变量中将其分配为十进制文本、 八进制文本中，为十六进制文本、 （开始或利用 Visual Basic 自 2017 年 1） 二进制文本。</span><span class="sxs-lookup"><span data-stu-id="f6259-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="f6259-109">如果整数文本在 `ULong` 范围之外（即，如果它小于 <xref:System.UInt64.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="f6259-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="f6259-110">在以下示例中，表示为十进制、十六进制和二进制文本且等于 7,934,076,125 的整数被分配给 `ULong` 值。</span><span class="sxs-lookup"><span data-stu-id="f6259-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> <span data-ttu-id="f6259-111">使用前缀`&h`或`&H`来表示为十六进制文本、 前缀`&b`或`&B`来表示二进制文字和前缀`&o`或`&O`来表示八进制文本。</span><span class="sxs-lookup"><span data-stu-id="f6259-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="f6259-112">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="f6259-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="f6259-113">从 Visual Basic 自 2017 年开始，你还可以使用下划线字符， `_`，作为数字分隔符以增强可读性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="f6259-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="f6259-114">从 Visual Basic 15.5 开始，你还可以使用下划线字符 (`_`) 为之间的前缀和十六进制、 二进制文件，或八进制数字的前导分隔符。</span><span class="sxs-lookup"><span data-stu-id="f6259-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="f6259-115">例如:</span><span class="sxs-lookup"><span data-stu-id="f6259-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="f6259-116">此外可以包括数值`UL`或`ul`[键入字符](../../programming-guide\language-features\data-types/type-characters.md)来表示`ULong`数据类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="f6259-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="f6259-117">编程提示</span><span class="sxs-lookup"><span data-stu-id="f6259-117">Programming tips</span></span>
  
-   <span data-ttu-id="f6259-118">**负数。**</span><span class="sxs-lookup"><span data-stu-id="f6259-118">**Negative Numbers.**</span></span> <span data-ttu-id="f6259-119">因为`ULong`是无符号的类型，它不能表示为负数。</span><span class="sxs-lookup"><span data-stu-id="f6259-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="f6259-120">如果你使用一元负 (`-`) 运算符的表达式的计算结果为键入`ULong`，Visual Basic 将转换为表达式`Decimal`第一个。</span><span class="sxs-lookup"><span data-stu-id="f6259-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>  
  
-   <span data-ttu-id="f6259-121">**CLS 遵从性。**</span><span class="sxs-lookup"><span data-stu-id="f6259-121">**CLS Compliance.**</span></span> <span data-ttu-id="f6259-122">`ULong`数据类型不是属于[公共语言规范](http://www.ecma-international.org/publications/standards/Ecma-335.htm)(CLS)，因此符合 cls 的代码不能使用的组件，使用它。</span><span class="sxs-lookup"><span data-stu-id="f6259-122">The `ULong` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>  
  
-   <span data-ttu-id="f6259-123">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="f6259-123">**Interop Considerations.**</span></span> <span data-ttu-id="f6259-124">如果你与不是为.NET Framework 中，如自动化或 COM 对象编写的组件交互请记住，类型，如`ulong`可以在其他环境中具有不同的数据宽度 （32 位）。</span><span class="sxs-lookup"><span data-stu-id="f6259-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="f6259-125">如果你的 32 位自变量传递给此类组件，将其声明为`UInteger`而不是`ULong`托管 Visual Basic 代码中。</span><span class="sxs-lookup"><span data-stu-id="f6259-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>  
  
     <span data-ttu-id="f6259-126">此外，自动化不支持 Windows 95、 Windows 98、 Windows ME，或 Windows 2000 上的 64 位整数。</span><span class="sxs-lookup"><span data-stu-id="f6259-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="f6259-127">不能将传递 Visual Basic`ULong`到自动化组件在这些平台上的自变量。</span><span class="sxs-lookup"><span data-stu-id="f6259-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>  
  
-   <span data-ttu-id="f6259-128">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="f6259-128">**Widening.**</span></span> <span data-ttu-id="f6259-129">`ULong`数据类型加宽到`Decimal`， `Single`，和`Double`。</span><span class="sxs-lookup"><span data-stu-id="f6259-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="f6259-130">这意味着你可以将转换`ULong`到而不会遇到这些类型的任何<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="f6259-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="f6259-131">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="f6259-131">**Type Characters.**</span></span> <span data-ttu-id="f6259-132">附加文本类型字符`UL`到文本将其强制转换到`ULong`数据类型。</span><span class="sxs-lookup"><span data-stu-id="f6259-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="f6259-133">`ULong`中有任何标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="f6259-133">`ULong` has no identifier type character.</span></span>
  
-   <span data-ttu-id="f6259-134">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="f6259-134">**Framework Type.**</span></span> <span data-ttu-id="f6259-135">.NET Framework 中的对应类型是 <xref:System.UInt64?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="f6259-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6259-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6259-136">See also</span></span>

 <xref:System.UInt64>  
 [<span data-ttu-id="f6259-137">数据类型</span><span class="sxs-lookup"><span data-stu-id="f6259-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="f6259-138">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="f6259-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="f6259-139">转换摘要</span><span class="sxs-lookup"><span data-stu-id="f6259-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="f6259-140">如何：调用采用无符号类型的 Windows 函数</span><span class="sxs-lookup"><span data-stu-id="f6259-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="f6259-141">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="f6259-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
