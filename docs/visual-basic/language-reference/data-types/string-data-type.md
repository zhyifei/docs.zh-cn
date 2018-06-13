---
title: String 数据类型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.String
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings [Visual Basic], string data type
- literals [Visual Basic], string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals [Visual Basic]
- data types [Visual Basic], assigning
- String literals [Visual Basic]
- identifier type characters [Visual Basic], $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
ms.openlocfilehash: 894638bbe50dad2cae1f74a2f7b7fe006f029d1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33592114"
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="0e31f-102">String 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e31f-102">String Data Type (Visual Basic)</span></span>
<span data-ttu-id="0e31f-103">包含从 0 到 65535 之间的值中的无符号的 16 位 （2 个字节） 码位的序列该范围。</span><span class="sxs-lookup"><span data-stu-id="0e31f-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="0e31f-104">每个*代码点*，或字符代码，表示单个 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="0e31f-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="0e31f-105">一个字符串可以包含从 0 到二十亿 (2 ^31) Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="0e31f-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e31f-106">备注</span><span class="sxs-lookup"><span data-stu-id="0e31f-106">Remarks</span></span>  
 <span data-ttu-id="0e31f-107">使用`String`数据类型以保存多个字符，而无需数组管理开销`Char()`，数组`Char`元素。</span><span class="sxs-lookup"><span data-stu-id="0e31f-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="0e31f-108">默认值`String`是`Nothing`（空引用）。</span><span class="sxs-lookup"><span data-stu-id="0e31f-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="0e31f-109">请注意，这并不相同，则为空字符串 (值`""`)。</span><span class="sxs-lookup"><span data-stu-id="0e31f-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="0e31f-110">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="0e31f-110">Unicode Characters</span></span>  
 <span data-ttu-id="0e31f-111">Unicode 的第一个 128 个码位 (0-127) 对应的字母和标准的美国键盘上的符号。</span><span class="sxs-lookup"><span data-stu-id="0e31f-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="0e31f-112">这些第一个 128 个码位都与 ASCII 字符集定义相同。</span><span class="sxs-lookup"><span data-stu-id="0e31f-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="0e31f-113">第二个 128 个码位 (128 到 255) 表示特殊字符，例如拉丁字母字母、 重音符号、 货币符号和分数 （竖式）。</span><span class="sxs-lookup"><span data-stu-id="0e31f-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="0e31f-114">Unicode 用于各种符号的其余代码点 (256-65535)。</span><span class="sxs-lookup"><span data-stu-id="0e31f-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="0e31f-115">这包括全球范围内的文本字符、 标注字符，以及数学和技术的符号。</span><span class="sxs-lookup"><span data-stu-id="0e31f-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="0e31f-116">你可以使用方法，如<xref:System.Char.IsDigit%2A>和<xref:System.Char.IsPunctuation%2A>上中的单个字符`String`变量以确定其 Unicode 分类。</span><span class="sxs-lookup"><span data-stu-id="0e31f-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="0e31f-117">格式要求</span><span class="sxs-lookup"><span data-stu-id="0e31f-117">Format Requirements</span></span>  
 <span data-ttu-id="0e31f-118">必须将括`String`引号内的文本 (`" "`)。</span><span class="sxs-lookup"><span data-stu-id="0e31f-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="0e31f-119">如果你必须包括一个引号作为一个字符串中字符，则使用两个连续的引号 (`""`)。</span><span class="sxs-lookup"><span data-stu-id="0e31f-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="0e31f-120">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="0e31f-120">The following example illustrates this.</span></span>  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="0e31f-121">请注意，连续的引号表示字符串中的引号是独立的引号开始和结束`String`文本。</span><span class="sxs-lookup"><span data-stu-id="0e31f-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="0e31f-122">字符串操作</span><span class="sxs-lookup"><span data-stu-id="0e31f-122">String Manipulations</span></span>  
 <span data-ttu-id="0e31f-123">一旦分配的字符串`String`变量，该字符串是*不可变*，这意味着你无法更改它的长度或内容。</span><span class="sxs-lookup"><span data-stu-id="0e31f-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="0e31f-124">在修改以任何方式的字符串时，Visual Basic 创建一个新字符串和放弃上一个。</span><span class="sxs-lookup"><span data-stu-id="0e31f-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="0e31f-125">`String`变量然后指向新的字符串。</span><span class="sxs-lookup"><span data-stu-id="0e31f-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="0e31f-126">你可以操作的内容`String`变量中使用各种字符串函数。</span><span class="sxs-lookup"><span data-stu-id="0e31f-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="0e31f-127">下面的示例演示<xref:Microsoft.VisualBasic.Strings.Left%2A>函数</span><span class="sxs-lookup"><span data-stu-id="0e31f-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="0e31f-128">可能会用前导空格或尾随空格填充通过另一个组件创建的字符串。</span><span class="sxs-lookup"><span data-stu-id="0e31f-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="0e31f-129">如果你收到此类字符串，则可以使用<xref:Microsoft.VisualBasic.Strings.Trim%2A>， <xref:Microsoft.VisualBasic.Strings.LTrim%2A>，和<xref:Microsoft.VisualBasic.Strings.RTrim%2A>函数来删除这些空格。</span><span class="sxs-lookup"><span data-stu-id="0e31f-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="0e31f-130">有关字符串操作的详细信息，请参阅[字符串](../../../visual-basic/programming-guide/language-features/strings/index.md)。</span><span class="sxs-lookup"><span data-stu-id="0e31f-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="0e31f-131">编程提示</span><span class="sxs-lookup"><span data-stu-id="0e31f-131">Programming Tips</span></span>  
  
-   <span data-ttu-id="0e31f-132">**负数。**</span><span class="sxs-lookup"><span data-stu-id="0e31f-132">**Negative Numbers.**</span></span> <span data-ttu-id="0e31f-133">请记住持有字符`String`是无符号，并且不能表示负值。</span><span class="sxs-lookup"><span data-stu-id="0e31f-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="0e31f-134">在任何情况下，不应使用`String`来保存数值。</span><span class="sxs-lookup"><span data-stu-id="0e31f-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="0e31f-135">**互操作注意事项。**</span><span class="sxs-lookup"><span data-stu-id="0e31f-135">**Interop Considerations.**</span></span> <span data-ttu-id="0e31f-136">如果你与不是为.NET Framework 中，编写的组件交互如自动化或 COM 对象，请记住字符串字符具有不同的数据宽度 （8 位） 在其他环境中。</span><span class="sxs-lookup"><span data-stu-id="0e31f-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="0e31f-137">如果你的 8 位字符的字符串自变量传递给此类组件，将其声明为`Byte()`，数组`Byte`元素，而不是`String`在新的 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="0e31f-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="0e31f-138">**类型字符。**</span><span class="sxs-lookup"><span data-stu-id="0e31f-138">**Type Characters.**</span></span> <span data-ttu-id="0e31f-139">后追加一个标识符类型字符`$`到任何标识符将其强制转换到`String`数据类型。</span><span class="sxs-lookup"><span data-stu-id="0e31f-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="0e31f-140">`String` 有没有文本类型字符。</span><span class="sxs-lookup"><span data-stu-id="0e31f-140">`String` has no literal type character.</span></span> <span data-ttu-id="0e31f-141">但是，编译器将用引号引起来的文本 (`" "`) 作为`String`。</span><span class="sxs-lookup"><span data-stu-id="0e31f-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
-   <span data-ttu-id="0e31f-142">**Framework 类型。**</span><span class="sxs-lookup"><span data-stu-id="0e31f-142">**Framework Type.**</span></span> <span data-ttu-id="0e31f-143">.NET Framework 中的对应类型是<xref:System.String?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="0e31f-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e31f-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e31f-144">See Also</span></span>  
 <xref:System.String?displayProperty=nameWithType>  
 [<span data-ttu-id="0e31f-145">数据类型</span><span class="sxs-lookup"><span data-stu-id="0e31f-145">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="0e31f-146">Char 数据类型</span><span class="sxs-lookup"><span data-stu-id="0e31f-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [<span data-ttu-id="0e31f-147">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="0e31f-147">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="0e31f-148">转换摘要</span><span class="sxs-lookup"><span data-stu-id="0e31f-148">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="0e31f-149">如何：调用采用无符号类型的 Windows 函数</span><span class="sxs-lookup"><span data-stu-id="0e31f-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="0e31f-150">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="0e31f-150">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
