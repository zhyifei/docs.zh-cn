---
title: Char 数据类型
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: 1ed5b19a307d094fc1d5a6bb0251c57052dc9bc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344052"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="d5d81-102">Char 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5d81-102">Char Data Type (Visual Basic)</span></span>

<span data-ttu-id="d5d81-103">保存16位（2字节）无符号码位，范围介于0到65535之间。</span><span class="sxs-lookup"><span data-stu-id="d5d81-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="d5d81-104">每个*码位*或字符代码都表示一个 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="d5d81-104">Each *code point*, or character code, represents a single Unicode character.</span></span>

## <a name="remarks"></a><span data-ttu-id="d5d81-105">备注</span><span class="sxs-lookup"><span data-stu-id="d5d81-105">Remarks</span></span>

<span data-ttu-id="d5d81-106">如果只需要保存单个字符，而不需要 `String`开销，请使用 `Char` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="d5d81-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="d5d81-107">在某些情况下，可以使用 `Char()`，`Char` 元素的数组来保存多个字符。</span><span class="sxs-lookup"><span data-stu-id="d5d81-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>

<span data-ttu-id="d5d81-108">`Char` 的默认值为码位为0的字符。</span><span class="sxs-lookup"><span data-stu-id="d5d81-108">The default value of `Char` is the character with a code point of 0.</span></span>

## <a name="unicode-characters"></a><span data-ttu-id="d5d81-109">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="d5d81-109">Unicode Characters</span></span>

<span data-ttu-id="d5d81-110">Unicode 的第一个128码位（0–127）对应于标准美式键盘上的字母和符号。</span><span class="sxs-lookup"><span data-stu-id="d5d81-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="d5d81-111">这前128码位与 ASCII 字符集定义的代码点相同。</span><span class="sxs-lookup"><span data-stu-id="d5d81-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="d5d81-112">第二个128码位（128–255）表示特殊字符，例如基于拉丁语的字母表号、重音、货币符号和分数。</span><span class="sxs-lookup"><span data-stu-id="d5d81-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="d5d81-113">Unicode 对各种符号（包括全球文本字符、音调符号和数学符号和技术符号）使用剩余的代码点（256-65535）。</span><span class="sxs-lookup"><span data-stu-id="d5d81-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>

<span data-ttu-id="d5d81-114">您可以使用 `Char` 变量上 <xref:System.Char.IsDigit%2A> 和 <xref:System.Char.IsPunctuation%2A> 等方法来确定其 Unicode 分类。</span><span class="sxs-lookup"><span data-stu-id="d5d81-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>

## <a name="type-conversions"></a><span data-ttu-id="d5d81-115">类型转换</span><span class="sxs-lookup"><span data-stu-id="d5d81-115">Type Conversions</span></span>

<span data-ttu-id="d5d81-116">Visual Basic 不会直接在 `Char` 与数值类型之间转换。</span><span class="sxs-lookup"><span data-stu-id="d5d81-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="d5d81-117">您可以使用 <xref:Microsoft.VisualBasic.Strings.Asc%2A> 或 <xref:Microsoft.VisualBasic.Strings.AscW%2A> 函数将 `Char` 值转换为表示其码位的 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="d5d81-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="d5d81-118">您可以使用 <xref:Microsoft.VisualBasic.Strings.Chr%2A> 或 <xref:Microsoft.VisualBasic.Strings.ChrW%2A> 函数将 `Integer` 值转换为具有该码位的 `Char`。</span><span class="sxs-lookup"><span data-stu-id="d5d81-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>

<span data-ttu-id="d5d81-119">如果类型检查开关（ [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)）为 on，则必须将文本类型字符追加到单字符字符串文本，才能将其标识为 `Char` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="d5d81-119">If the type checking switch (the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="d5d81-120">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="d5d81-120">The following example illustrates this.</span></span> <span data-ttu-id="d5d81-121">第一次分配给 `charVar` 变量会生成编译器错误[BC30512](../../misc/bc30512.md) ，因为 `Option Strict` 为 on。</span><span class="sxs-lookup"><span data-stu-id="d5d81-121">The first assignment to the `charVar` variable generates compiler error [BC30512](../../misc/bc30512.md) because `Option Strict` is on.</span></span> <span data-ttu-id="d5d81-122">第二个编译成功，因为 `c` 文本类型字符将文本标识为 `Char` 值。</span><span class="sxs-lookup"><span data-stu-id="d5d81-122">The second compiles successfully because the `c` literal type character identifies the literal as a `Char` value.</span></span>

```vb
Option Strict On

Module CharType
    Public Sub Main()
        Dim charVar As Char

        ' This statement generates compiler error BC30512 because Option Strict is On.  
        charVar = "Z"  

        ' The following statement succeeds because it specifies a Char literal.  
        charVar = "Z"c
    End Sub
End Module
```

## <a name="programming-tips"></a><span data-ttu-id="d5d81-123">编程提示</span><span class="sxs-lookup"><span data-stu-id="d5d81-123">Programming Tips</span></span>

- <span data-ttu-id="d5d81-124">**负数。**</span><span class="sxs-lookup"><span data-stu-id="d5d81-124">**Negative Numbers.**</span></span> <span data-ttu-id="d5d81-125">`Char` 是一种无符号类型，不能表示负值。</span><span class="sxs-lookup"><span data-stu-id="d5d81-125">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="d5d81-126">在任何情况下，不应使用 `Char` 来保存数值。</span><span class="sxs-lookup"><span data-stu-id="d5d81-126">In any case, you should not use `Char` to hold numeric values.</span></span>

- <span data-ttu-id="d5d81-127">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="d5d81-127">**Interop Considerations.**</span></span> <span data-ttu-id="d5d81-128">如果你使用不是为 .NET Framework 编写的组件（如自动化或 COM 对象）进行交互，请记住，在其他环境中字符类型具有不同的数据宽度（8位）。</span><span class="sxs-lookup"><span data-stu-id="d5d81-128">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="d5d81-129">如果将一个8位参数传递给此类组件，请在新的 Visual Basic 代码中将其声明为 `Byte` 而不是 `Char`。</span><span class="sxs-lookup"><span data-stu-id="d5d81-129">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>

- <span data-ttu-id="d5d81-130">**扩大.**</span><span class="sxs-lookup"><span data-stu-id="d5d81-130">**Widening.**</span></span> <span data-ttu-id="d5d81-131">`Char` 的数据类型扩大到 `String`。</span><span class="sxs-lookup"><span data-stu-id="d5d81-131">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="d5d81-132">这意味着你可以将 `Char` 转换为 `String`，而不会遇到 <xref:System.OverflowException?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="d5d81-132">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="d5d81-133">**键入字符。**</span><span class="sxs-lookup"><span data-stu-id="d5d81-133">**Type Characters.**</span></span> <span data-ttu-id="d5d81-134">将文本类型字符追加 `C` 为单字符字符串会将其强制转换为 `Char` 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="d5d81-134">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="d5d81-135">`Char` 没有标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="d5d81-135">`Char` has no identifier type character.</span></span>

- <span data-ttu-id="d5d81-136">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="d5d81-136">**Framework Type.**</span></span> <span data-ttu-id="d5d81-137">.NET Framework 中的对应类型是 <xref:System.Char?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="d5d81-137">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5d81-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5d81-138">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="d5d81-139">数据类型</span><span class="sxs-lookup"><span data-stu-id="d5d81-139">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="d5d81-140">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="d5d81-140">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="d5d81-141">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="d5d81-141">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="d5d81-142">转换摘要</span><span class="sxs-lookup"><span data-stu-id="d5d81-142">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="d5d81-143">如何：调用采用无符号类型的 Windows 函数</span><span class="sxs-lookup"><span data-stu-id="d5d81-143">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="d5d81-144">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="d5d81-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
