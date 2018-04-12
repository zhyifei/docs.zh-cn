---
title: Char 数据类型 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16ff547fccbf4481d31ca79537962cc7090fc9b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="f71d2-102">Char 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f71d2-102">Char Data Type (Visual Basic)</span></span>
<span data-ttu-id="f71d2-103">取值范围为 0 到 65535 的保存无符号的 16 位 （2 个字节） 码位。</span><span class="sxs-lookup"><span data-stu-id="f71d2-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="f71d2-104">每个*代码点*，或字符代码，表示单个 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="f71d2-104">Each *code point*, or character code, represents a single Unicode character.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f71d2-105">备注</span><span class="sxs-lookup"><span data-stu-id="f71d2-105">Remarks</span></span>  
 <span data-ttu-id="f71d2-106">使用`Char`数据类型时你需要保存只有一个字符，且不需要的开销`String`。</span><span class="sxs-lookup"><span data-stu-id="f71d2-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="f71d2-107">在某些情况下可以使用`Char()`，数组`Char`元素，来保存多个字符。</span><span class="sxs-lookup"><span data-stu-id="f71d2-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>  
  
 <span data-ttu-id="f71d2-108">默认值`Char`是与 0 的码位的字符。</span><span class="sxs-lookup"><span data-stu-id="f71d2-108">The default value of `Char` is the character with a code point of 0.</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="f71d2-109">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="f71d2-109">Unicode Characters</span></span>  
 <span data-ttu-id="f71d2-110">Unicode 的第一个 128 个码位 (0-127) 对应的字母和标准的美国键盘上的符号。</span><span class="sxs-lookup"><span data-stu-id="f71d2-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="f71d2-111">这些第一个 128 个码位都与 ASCII 字符集定义相同。</span><span class="sxs-lookup"><span data-stu-id="f71d2-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="f71d2-112">第二个 128 个码位 (128 到 255) 表示特殊字符，例如拉丁字母字母、 重音符号、 货币符号和分数 （竖式）。</span><span class="sxs-lookup"><span data-stu-id="f71d2-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="f71d2-113">Unicode 用于各种符号，包括全球范围内的文本字符、 标注字符，以及数学和技术的符号的其余代码点 (256-65535)。</span><span class="sxs-lookup"><span data-stu-id="f71d2-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="f71d2-114">你可以使用类似的方法<xref:System.Char.IsDigit%2A>和<xref:System.Char.IsPunctuation%2A>上`Char`变量以确定其 Unicode 分类。</span><span class="sxs-lookup"><span data-stu-id="f71d2-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="f71d2-115">类型转换</span><span class="sxs-lookup"><span data-stu-id="f71d2-115">Type Conversions</span></span>  
 <span data-ttu-id="f71d2-116">Visual Basic 不直接之间转换`Char`与数值类型。</span><span class="sxs-lookup"><span data-stu-id="f71d2-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="f71d2-117">你可以使用<xref:Microsoft.VisualBasic.Strings.Asc%2A>或<xref:Microsoft.VisualBasic.Strings.AscW%2A>函数将转换`Char`值赋给`Integer`表示其码位。</span><span class="sxs-lookup"><span data-stu-id="f71d2-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="f71d2-118">你可以使用<xref:Microsoft.VisualBasic.Strings.Chr%2A>或<xref:Microsoft.VisualBasic.Strings.ChrW%2A>函数将转换`Integer`值赋给`Char`，其将码位。</span><span class="sxs-lookup"><span data-stu-id="f71d2-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>  
  
 <span data-ttu-id="f71d2-119">如果类型检查开关 ([Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)) 处于打开状态，必须将文本类型字符追加到单字符的字符串文本以标识为`Char`数据类型。</span><span class="sxs-lookup"><span data-stu-id="f71d2-119">If the type checking switch ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="f71d2-120">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="f71d2-120">The following example illustrates this.</span></span>  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a><span data-ttu-id="f71d2-121">编程提示</span><span class="sxs-lookup"><span data-stu-id="f71d2-121">Programming Tips</span></span>  
  
-   <span data-ttu-id="f71d2-122">**负数。**</span><span class="sxs-lookup"><span data-stu-id="f71d2-122">**Negative Numbers.**</span></span> <span data-ttu-id="f71d2-123">`Char`是无符号的类型且不能表示为负值。</span><span class="sxs-lookup"><span data-stu-id="f71d2-123">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="f71d2-124">在任何情况下，不应使用`Char`来保存数值。</span><span class="sxs-lookup"><span data-stu-id="f71d2-124">In any case, you should not use `Char` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="f71d2-125">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="f71d2-125">**Interop Considerations.**</span></span> <span data-ttu-id="f71d2-126">如果接口与组件不是为.NET Framework 中，编写如自动化或 COM 对象，请记住，字符类型具有不同的数据宽度 （8 位） 在其他环境中。</span><span class="sxs-lookup"><span data-stu-id="f71d2-126">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="f71d2-127">如果将 8 位自变量传递到此类组件时，将其声明为`Byte`而不是`Char`在新的 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="f71d2-127">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="f71d2-128">**扩大转换。**</span><span class="sxs-lookup"><span data-stu-id="f71d2-128">**Widening.**</span></span> <span data-ttu-id="f71d2-129">`Char`数据类型加宽到`String`。</span><span class="sxs-lookup"><span data-stu-id="f71d2-129">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="f71d2-130">这意味着你可以将转换`Char`到`String`而不会遇到<xref:System.OverflowException?displayProperty=nameWithType>错误。</span><span class="sxs-lookup"><span data-stu-id="f71d2-130">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="f71d2-131">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="f71d2-131">**Type Characters.**</span></span> <span data-ttu-id="f71d2-132">追加文本类型字符`C`到单字符字符串文本将其强制转换到`Char`数据类型。</span><span class="sxs-lookup"><span data-stu-id="f71d2-132">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="f71d2-133">`Char`中有任何标识符类型字符。</span><span class="sxs-lookup"><span data-stu-id="f71d2-133">`Char` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="f71d2-134">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="f71d2-134">**Framework Type.**</span></span> <span data-ttu-id="f71d2-135">.NET Framework 中的对应类型是 <xref:System.Char?displayProperty=nameWithType> 结构。</span><span class="sxs-lookup"><span data-stu-id="f71d2-135">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f71d2-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f71d2-136">See Also</span></span>  
 <xref:System.Char?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [<span data-ttu-id="f71d2-137">数据类型</span><span class="sxs-lookup"><span data-stu-id="f71d2-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="f71d2-138">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="f71d2-138">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [<span data-ttu-id="f71d2-139">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="f71d2-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="f71d2-140">转换摘要</span><span class="sxs-lookup"><span data-stu-id="f71d2-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="f71d2-141">如何：调用采用无符号类型的 Windows 函数</span><span class="sxs-lookup"><span data-stu-id="f71d2-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="f71d2-142">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="f71d2-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
