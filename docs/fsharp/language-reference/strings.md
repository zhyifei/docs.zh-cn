---
title: 字符串
description: 了解F# "string" 类型如何将不可变文本表示为 Unicode 字符序列。
ms.date: 07/05/2019
ms.openlocfilehash: 284de939c90c4d9d4ea064fb4db1fb90a37038e2
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627102"
---
# <a name="strings"></a><span data-ttu-id="e4778-103">字符串</span><span class="sxs-lookup"><span data-stu-id="e4778-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="e4778-104">本文中的 API 参考链接将转至 MSDN。</span><span class="sxs-lookup"><span data-stu-id="e4778-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="e4778-105">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="e4778-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="e4778-106">`string`类型将不可变文本表示为 Unicode 字符序列。</span><span class="sxs-lookup"><span data-stu-id="e4778-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="e4778-107">`string` 是 .NET Framework 中 `System.String` 的别名。</span><span class="sxs-lookup"><span data-stu-id="e4778-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4778-108">备注</span><span class="sxs-lookup"><span data-stu-id="e4778-108">Remarks</span></span>

<span data-ttu-id="e4778-109">字符串文本用引号 (") 字符分隔。</span><span class="sxs-lookup"><span data-stu-id="e4778-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="e4778-110">反斜杠字符 ( \\ ) 用于对某些特殊字符进行编码。</span><span class="sxs-lookup"><span data-stu-id="e4778-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="e4778-111">反斜杠和下一个字符共同称为*转义序列*。</span><span class="sxs-lookup"><span data-stu-id="e4778-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="e4778-112">下表显示了F#字符串文本中支持的转义序列。</span><span class="sxs-lookup"><span data-stu-id="e4778-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="e4778-113">字符</span><span class="sxs-lookup"><span data-stu-id="e4778-113">Character</span></span>|<span data-ttu-id="e4778-114">转义序列</span><span class="sxs-lookup"><span data-stu-id="e4778-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="e4778-115">警报</span><span class="sxs-lookup"><span data-stu-id="e4778-115">Alert</span></span>|`\a`|
|<span data-ttu-id="e4778-116">Backspace</span><span class="sxs-lookup"><span data-stu-id="e4778-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="e4778-117">换页</span><span class="sxs-lookup"><span data-stu-id="e4778-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="e4778-118">换行符</span><span class="sxs-lookup"><span data-stu-id="e4778-118">Newline</span></span>|`\n`|
|<span data-ttu-id="e4778-119">回车</span><span class="sxs-lookup"><span data-stu-id="e4778-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="e4778-120">Tab</span><span class="sxs-lookup"><span data-stu-id="e4778-120">Tab</span></span>|`\t`|
|<span data-ttu-id="e4778-121">垂直制表符</span><span class="sxs-lookup"><span data-stu-id="e4778-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="e4778-122">反斜杠</span><span class="sxs-lookup"><span data-stu-id="e4778-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="e4778-123">引号</span><span class="sxs-lookup"><span data-stu-id="e4778-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="e4778-124">撇号</span><span class="sxs-lookup"><span data-stu-id="e4778-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="e4778-125">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="e4778-125">Unicode character</span></span>|<span data-ttu-id="e4778-126">`\DDD`(其中`D`指示十进制数字; 范围为 000-255; 例如, `\231` = "ç")</span><span class="sxs-lookup"><span data-stu-id="e4778-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="e4778-127">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="e4778-127">Unicode character</span></span>|<span data-ttu-id="e4778-128">`\xHH`(其中`H`指示十六进制数字; 00-FF 的范围; 例如, `\xE7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="e4778-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="e4778-129">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="e4778-129">Unicode character</span></span>|<span data-ttu-id="e4778-130">`\uHHHH`(UTF-16)(其中`H`指示十六进制数字; 0000-FFFF 范围; 例如, `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="e4778-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="e4778-131">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="e4778-131">Unicode character</span></span>|<span data-ttu-id="e4778-132">`\U00HHHHHH`(UTF-32)(其中`H`指示十六进制数字; 10FFFF 的范围; 例如, `\U0001F47D` = "👽")</span><span class="sxs-lookup"><span data-stu-id="e4778-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="e4778-133">`\DDD`转义序列是十进制符号, 而不是八进制表示法, 这与大多数其他语言类似。</span><span class="sxs-lookup"><span data-stu-id="e4778-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="e4778-134">因此, 数字`8`和`9`是有效的`\032` , 序列表示空格 (U + 0020), 而八进制表示法中的码位就是`\040`。</span><span class="sxs-lookup"><span data-stu-id="e4778-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="e4778-135">约束为 0-255 (0xff) 的范围, `\DDD`并且`\x`转义序列实际上是[ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout)字符集, 因为它与第一个 256 Unicode 码位匹配。</span><span class="sxs-lookup"><span data-stu-id="e4778-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

<span data-ttu-id="e4778-136">如果前面带有 @ 符号, 则文本为逐字字符串。</span><span class="sxs-lookup"><span data-stu-id="e4778-136">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="e4778-137">这意味着将忽略任何转义序列, 只不过两个引号字符被解释为一个引号字符。</span><span class="sxs-lookup"><span data-stu-id="e4778-137">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="e4778-138">此外, 字符串可以用三个引号括起来。</span><span class="sxs-lookup"><span data-stu-id="e4778-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="e4778-139">在这种情况下, 将忽略所有转义序列, 包括双引号字符。</span><span class="sxs-lookup"><span data-stu-id="e4778-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="e4778-140">若要指定包含嵌入的带引号的字符串的字符串, 可以使用逐字字符串或带三个引号的字符串。</span><span class="sxs-lookup"><span data-stu-id="e4778-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="e4778-141">如果使用逐字字符串, 则必须指定两个引号字符来指示单引号字符。</span><span class="sxs-lookup"><span data-stu-id="e4778-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="e4778-142">如果使用三个带引号的字符串, 则可以使用单引号字符, 而不会将它们分析为字符串的末尾。</span><span class="sxs-lookup"><span data-stu-id="e4778-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="e4778-143">当使用包含嵌入引号的 XML 或其他结构时, 此方法会很有用。</span><span class="sxs-lookup"><span data-stu-id="e4778-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="e4778-144">在代码中, 将接受带有分行符的字符串, 分行符将按原义解释为换行符, 除非反斜杠字符为换行符前的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="e4778-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="e4778-145">使用反斜杠字符时, 将忽略下一行的前导空格。</span><span class="sxs-lookup"><span data-stu-id="e4778-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="e4778-146">下面的代码将生成一个`str1`字符串, 该`"abc\ndef"`字符串具有值`str2`和具有值`"abcdef"`的字符串。</span><span class="sxs-lookup"><span data-stu-id="e4778-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="e4778-147">您可以使用类似数组的语法来访问字符串中的单个字符, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="e4778-147">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="e4778-148">输出为 `b`。</span><span class="sxs-lookup"><span data-stu-id="e4778-148">The output is `b`.</span></span>

<span data-ttu-id="e4778-149">或者, 您可以使用数组切片语法来提取子字符串, 如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="e4778-149">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="e4778-150">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="e4778-150">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="e4778-151">可以按无符号字节的数组 (类型`byte[]`) 表示 ASCII 字符串。</span><span class="sxs-lookup"><span data-stu-id="e4778-151">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="e4778-152">将后缀`B`添加到字符串文字, 以指示它是 ASCII 字符串。</span><span class="sxs-lookup"><span data-stu-id="e4778-152">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="e4778-153">与 byte 数组一起使用的 ASCII 字符串文本除了 Unicode 转义序列外, 与 Unicode 字符串支持相同的转义序列。</span><span class="sxs-lookup"><span data-stu-id="e4778-153">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="e4778-154">字符串运算符</span><span class="sxs-lookup"><span data-stu-id="e4778-154">String Operators</span></span>

<span data-ttu-id="e4778-155">可以通过两种方式连接字符串: 通过使用`+`运算符或`^`使用运算符。</span><span class="sxs-lookup"><span data-stu-id="e4778-155">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="e4778-156">`+`运算符保持与 .NET Framework 字符串处理功能的兼容性。</span><span class="sxs-lookup"><span data-stu-id="e4778-156">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="e4778-157">下面的示例演示字符串串联。</span><span class="sxs-lookup"><span data-stu-id="e4778-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="e4778-158">String 类</span><span class="sxs-lookup"><span data-stu-id="e4778-158">String Class</span></span>

<span data-ttu-id="e4778-159">因为中F#的字符串类型实际上是 .NET Framework `System.String` `System.String`类型, 所以所有成员都可用。</span><span class="sxs-lookup"><span data-stu-id="e4778-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="e4778-160">这包括`+`用于连接字符串`Length` 、属性和`Chars`属性的运算符, 该运算符将字符串作为 Unicode 字符数组返回。</span><span class="sxs-lookup"><span data-stu-id="e4778-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="e4778-161">有关字符串的详细信息, 请`System.String`参阅。</span><span class="sxs-lookup"><span data-stu-id="e4778-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="e4778-162">通过使用`Chars`的`System.String`属性, 可以通过指定索引来访问字符串中的各个字符, 如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="e4778-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="e4778-163">字符串模块</span><span class="sxs-lookup"><span data-stu-id="e4778-163">String Module</span></span>

<span data-ttu-id="e4778-164">命名`FSharp.Core`空间中的`String`模块包含了用于字符串处理的其他功能。</span><span class="sxs-lookup"><span data-stu-id="e4778-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="e4778-165">有关详细信息, 请参阅[Core 模块](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="e4778-165">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4778-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4778-166">See also</span></span>

- [<span data-ttu-id="e4778-167">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="e4778-167">F# Language Reference</span></span>](index.md)
