---
title: 字符串
description: 了解 F# "字符串"类型如何表示不可变文本作为 Unicode 字符序列。
ms.date: 07/05/2019
ms.openlocfilehash: 242a2cefa1cce8995090dddd1d1fd7181e0f5e0c
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739569"
---
# <a name="strings"></a><span data-ttu-id="8d931-103">字符串</span><span class="sxs-lookup"><span data-stu-id="8d931-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="8d931-104">本文中的 API 参考链接将转至 MSDN。</span><span class="sxs-lookup"><span data-stu-id="8d931-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="8d931-105">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="8d931-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="8d931-106">该`string`类型表示不可变文本为 Unicode 字符序列。</span><span class="sxs-lookup"><span data-stu-id="8d931-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="8d931-107">`string` 是 .NET Framework 中 `System.String` 的别名。</span><span class="sxs-lookup"><span data-stu-id="8d931-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="8d931-108">备注</span><span class="sxs-lookup"><span data-stu-id="8d931-108">Remarks</span></span>

<span data-ttu-id="8d931-109">字符串文本由引号 （"） 字符分隔。</span><span class="sxs-lookup"><span data-stu-id="8d931-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="8d931-110">反斜杠字符\\（ ） 用于编码某些特殊字符。</span><span class="sxs-lookup"><span data-stu-id="8d931-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="8d931-111">反斜杠和下一个字符一起被称为*转义序列*。</span><span class="sxs-lookup"><span data-stu-id="8d931-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="8d931-112">F# 字符串文本中支持的转义序列显示在下表中。</span><span class="sxs-lookup"><span data-stu-id="8d931-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="8d931-113">字符</span><span class="sxs-lookup"><span data-stu-id="8d931-113">Character</span></span>|<span data-ttu-id="8d931-114">转义序列</span><span class="sxs-lookup"><span data-stu-id="8d931-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="8d931-115">警报</span><span class="sxs-lookup"><span data-stu-id="8d931-115">Alert</span></span>|`\a`|
|<span data-ttu-id="8d931-116">退格键</span><span class="sxs-lookup"><span data-stu-id="8d931-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="8d931-117">换页符</span><span class="sxs-lookup"><span data-stu-id="8d931-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="8d931-118">换行符</span><span class="sxs-lookup"><span data-stu-id="8d931-118">Newline</span></span>|`\n`|
|<span data-ttu-id="8d931-119">回车符</span><span class="sxs-lookup"><span data-stu-id="8d931-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="8d931-120">选项卡</span><span class="sxs-lookup"><span data-stu-id="8d931-120">Tab</span></span>|`\t`|
|<span data-ttu-id="8d931-121">垂直制表符</span><span class="sxs-lookup"><span data-stu-id="8d931-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="8d931-122">反斜杠</span><span class="sxs-lookup"><span data-stu-id="8d931-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="8d931-123">引号</span><span class="sxs-lookup"><span data-stu-id="8d931-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="8d931-124">撇号</span><span class="sxs-lookup"><span data-stu-id="8d931-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="8d931-125">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="8d931-125">Unicode character</span></span>|<span data-ttu-id="8d931-126">`\DDD`（其中`D`表示小数数字;范围为 000 - 255;`\231`例如，= "\*"）</span><span class="sxs-lookup"><span data-stu-id="8d931-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="8d931-127">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="8d931-127">Unicode character</span></span>|<span data-ttu-id="8d931-128">`\xHH`（其中`H`指示十六进制数字;范围为 00 - FF;例如，= `\xE7` "\*"）</span><span class="sxs-lookup"><span data-stu-id="8d931-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="8d931-129">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="8d931-129">Unicode character</span></span>|<span data-ttu-id="8d931-130">`\uHHHH`（UTF-16）（其中`H`表示十六进制数字;范围为 0000 - FFFF; 例如，= `\u00E7` "\*"）</span><span class="sxs-lookup"><span data-stu-id="8d931-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="8d931-131">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="8d931-131">Unicode character</span></span>|<span data-ttu-id="8d931-132">`\U00HHHHHH`（UTF-32）（其中`H`表示十六进制数字;范围为 000000 - 10FFFF; 例如，= `\U0001F47D` """）👽</span><span class="sxs-lookup"><span data-stu-id="8d931-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="8d931-133">`\DDD`转义序列是十进制表示法，不像大多数其他语言那样的八进制表示法。</span><span class="sxs-lookup"><span data-stu-id="8d931-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="8d931-134">因此，数字`8`和`9`有效，并且序列`\032`表示空格 （U+0020），而八进制表示法中的同一代码点将是`\040`。</span><span class="sxs-lookup"><span data-stu-id="8d931-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="8d931-135">被限制到 0 - 255 （0xFF） `\DDD` `\x`的范围， 和转义序列实际上是[ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout)字符集， 因为它匹配前 256 个 Unicode 点。</span><span class="sxs-lookup"><span data-stu-id="8d931-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="8d931-136">逐字字符串</span><span class="sxs-lookup"><span data-stu-id="8d931-136">Verbatim Strings</span></span>

<span data-ttu-id="8d931-137">如果前面有 + 符号，则文本是逐字字符串。</span><span class="sxs-lookup"><span data-stu-id="8d931-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="8d931-138">这意味着忽略任何转义序列，只不过两个引号字符被解释为一个引号字符。</span><span class="sxs-lookup"><span data-stu-id="8d931-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="8d931-139">三重报价字符串</span><span class="sxs-lookup"><span data-stu-id="8d931-139">Triple Quoted Strings</span></span>

<span data-ttu-id="8d931-140">此外，字符串可以用三重引号括起来。</span><span class="sxs-lookup"><span data-stu-id="8d931-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="8d931-141">在这种情况下，将忽略所有转义序列，包括双引号字符。</span><span class="sxs-lookup"><span data-stu-id="8d931-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="8d931-142">要指定包含嵌入引用字符串的字符串，可以使用逐字字符串或三重引号字符串。</span><span class="sxs-lookup"><span data-stu-id="8d931-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="8d931-143">如果使用逐字字符串，则必须指定两个引号字符以指示单个引号字符。</span><span class="sxs-lookup"><span data-stu-id="8d931-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="8d931-144">如果使用三重引号字符串，则可以使用单个引号字符，而无需将它们解析为字符串的末尾。</span><span class="sxs-lookup"><span data-stu-id="8d931-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="8d931-145">当您使用 XML 或其他包含嵌入引号的结构时，此方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="8d931-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="8d931-146">在代码中，接受具有换行符的字符串，并且换行符从字面上解释为换行符，除非反斜杠字符是换行符之前的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="8d931-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="8d931-147">使用反斜杠字符时，将忽略下一行的前导空格。</span><span class="sxs-lookup"><span data-stu-id="8d931-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="8d931-148">`str1`以下代码生成具有值`"abc\ndef"`的字符串和具有 值`str2``"abcdef"`的字符串。</span><span class="sxs-lookup"><span data-stu-id="8d931-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="8d931-149">字符串索引和切片</span><span class="sxs-lookup"><span data-stu-id="8d931-149">String Indexing and Slicing</span></span>

<span data-ttu-id="8d931-150">可以使用类似于数组的语法访问字符串中的单个字符，如下所示。</span><span class="sxs-lookup"><span data-stu-id="8d931-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="8d931-151">输出为 `b`。</span><span class="sxs-lookup"><span data-stu-id="8d931-151">The output is `b`.</span></span>

<span data-ttu-id="8d931-152">或者，您可以使用数组切片语法提取子字符串，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="8d931-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="8d931-153">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="8d931-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="8d931-154">您可以按未签名字节的数组表示 ASCII 字符串，类型`byte[]`为 。</span><span class="sxs-lookup"><span data-stu-id="8d931-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="8d931-155">将后缀`B`添加到字符串文本，以指示它是 ASCII 字符串。</span><span class="sxs-lookup"><span data-stu-id="8d931-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="8d931-156">与字节数组一起使用的 ASCII 字符串文本支持与 Unicode 字符串相同的转义序列，Unicode 转义序列除外。</span><span class="sxs-lookup"><span data-stu-id="8d931-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="8d931-157">字符串运算符</span><span class="sxs-lookup"><span data-stu-id="8d931-157">String Operators</span></span>

<span data-ttu-id="8d931-158">该`+`运算符可用于串联字符串，保持与 .NET 框架字符串处理功能的兼容性。</span><span class="sxs-lookup"><span data-stu-id="8d931-158">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="8d931-159">下面的示例演示了字符串串联。</span><span class="sxs-lookup"><span data-stu-id="8d931-159">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="8d931-160">字符串类</span><span class="sxs-lookup"><span data-stu-id="8d931-160">String Class</span></span>

<span data-ttu-id="8d931-161">由于 F# 中的字符串类型实际上是 .NET`System.String`框架类型，`System.String`因此所有成员都可用。</span><span class="sxs-lookup"><span data-stu-id="8d931-161">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="8d931-162">这包括`+`运算符，该运算符用于串联字符串、`Length`属性和`Chars`属性，后者将字符串作为 Unicode 字符的数组返回。</span><span class="sxs-lookup"><span data-stu-id="8d931-162">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="8d931-163">有关字符串的详细信息，请参阅`System.String`。</span><span class="sxs-lookup"><span data-stu-id="8d931-163">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="8d931-164">通过使用 属性`Chars``System.String`，可以通过指定索引来访问字符串中的单个字符，如下代码所示。</span><span class="sxs-lookup"><span data-stu-id="8d931-164">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="8d931-165">字符串模块</span><span class="sxs-lookup"><span data-stu-id="8d931-165">String Module</span></span>

<span data-ttu-id="8d931-166">`FSharp.Core`命名空间中的`String`模块中包括字符串处理的其他功能。</span><span class="sxs-lookup"><span data-stu-id="8d931-166">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="8d931-167">有关详细信息，请参阅[Core.String 模块](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="8d931-167">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="8d931-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d931-168">See also</span></span>

- [<span data-ttu-id="8d931-169">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="8d931-169">F# Language Reference</span></span>](index.md)
