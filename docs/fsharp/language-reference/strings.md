---
title: 字符串
description: 了解如何F#'string' 类型不可变的文本表示为一系列 Unicode 字符。
ms.date: 07/05/2019
ms.openlocfilehash: b252aef7d7e6e299df8282407198714971e80cd5
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610163"
---
# <a name="strings"></a><span data-ttu-id="ff368-103">字符串</span><span class="sxs-lookup"><span data-stu-id="ff368-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="ff368-104">本文中的 API 参考链接将转至 MSDN。</span><span class="sxs-lookup"><span data-stu-id="ff368-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="ff368-105">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="ff368-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="ff368-106">`string`类型将不可变的文本表示为一系列 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="ff368-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="ff368-107">`string` 是 .NET Framework 中 `System.String` 的别名。</span><span class="sxs-lookup"><span data-stu-id="ff368-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff368-108">备注</span><span class="sxs-lookup"><span data-stu-id="ff368-108">Remarks</span></span>

<span data-ttu-id="ff368-109">字符串文本用引号 （"） 字符分隔。</span><span class="sxs-lookup"><span data-stu-id="ff368-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="ff368-110">反斜杠字符 ( \\ ) 使用某些特殊字符进行编码。</span><span class="sxs-lookup"><span data-stu-id="ff368-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="ff368-111">反斜杠和组合在一起的下一个字符被称为*转义序列*。</span><span class="sxs-lookup"><span data-stu-id="ff368-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="ff368-112">转义序列中支持F#字符串文本下表中所示。</span><span class="sxs-lookup"><span data-stu-id="ff368-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="ff368-113">字符</span><span class="sxs-lookup"><span data-stu-id="ff368-113">Character</span></span>|<span data-ttu-id="ff368-114">转义序列</span><span class="sxs-lookup"><span data-stu-id="ff368-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="ff368-115">警报</span><span class="sxs-lookup"><span data-stu-id="ff368-115">Alert</span></span>|`\a`|
|<span data-ttu-id="ff368-116">Backspace</span><span class="sxs-lookup"><span data-stu-id="ff368-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="ff368-117">换页</span><span class="sxs-lookup"><span data-stu-id="ff368-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="ff368-118">换行符</span><span class="sxs-lookup"><span data-stu-id="ff368-118">Newline</span></span>|`\n`|
|<span data-ttu-id="ff368-119">回车</span><span class="sxs-lookup"><span data-stu-id="ff368-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="ff368-120">Tab</span><span class="sxs-lookup"><span data-stu-id="ff368-120">Tab</span></span>|`\t`|
|<span data-ttu-id="ff368-121">垂直制表符</span><span class="sxs-lookup"><span data-stu-id="ff368-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="ff368-122">反斜杠</span><span class="sxs-lookup"><span data-stu-id="ff368-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="ff368-123">引号</span><span class="sxs-lookup"><span data-stu-id="ff368-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="ff368-124">撇号</span><span class="sxs-lookup"><span data-stu-id="ff368-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="ff368-125">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="ff368-125">Unicode character</span></span>|<span data-ttu-id="ff368-126">`\DDD` (其中`D`指示十进制数字; 范围 000-255; 例如`\231`="ç")</span><span class="sxs-lookup"><span data-stu-id="ff368-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; e.g. `\231` = "ç")</span></span>|
|<span data-ttu-id="ff368-127">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="ff368-127">Unicode character</span></span>|<span data-ttu-id="ff368-128">`\xHH` (其中`H`指示的十六进制数字，范围 00-FF; 例如`\xE7`="ç")</span><span class="sxs-lookup"><span data-stu-id="ff368-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; e.g. `\xE7` = "ç")</span></span>|
|<span data-ttu-id="ff368-129">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="ff368-129">Unicode character</span></span>|<span data-ttu-id="ff368-130">`\uHHHH` (UTF-16)(其中`H`指示的十六进制数字，范围 0000-FFFF; 例如`\u00E7`="ç")</span><span class="sxs-lookup"><span data-stu-id="ff368-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  e.g. `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="ff368-131">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="ff368-131">Unicode character</span></span>|<span data-ttu-id="ff368-132">`\U00HHHHHH` (UTF-32)(其中`H`指示的十六进制数字，范围为 000000-10FFFF; 例如`\U0001F47D`="👽")</span><span class="sxs-lookup"><span data-stu-id="ff368-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  e.g. `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="ff368-133">`\DDD`转义序列是十进制表示法，不是八进制表示法如大多数其他语言中。</span><span class="sxs-lookup"><span data-stu-id="ff368-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="ff368-134">因此，数字`8`并`9`是否有效和一系列`\032`表示空格 (U + 0020)，而是将相同的码位八进制表示法`\040`。</span><span class="sxs-lookup"><span data-stu-id="ff368-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="ff368-135">受约束，以一系列 0-255 (0xFF)`\DDD`并`\x`实际上是转义序列[ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout)字符集，因为匹配的前 256 个 Unicode 码位。</span><span class="sxs-lookup"><span data-stu-id="ff368-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

<span data-ttu-id="ff368-136">如果前面有 @ 符号，则该文本是原义字符串。</span><span class="sxs-lookup"><span data-stu-id="ff368-136">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="ff368-137">这意味着，将忽略任何转义序列，但两个引号字符解释为一个引号字符。</span><span class="sxs-lookup"><span data-stu-id="ff368-137">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="ff368-138">此外，字符串可能包含三个引号引起来。</span><span class="sxs-lookup"><span data-stu-id="ff368-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="ff368-139">在这种情况下，将忽略所有转义序列，包括双引号字符。</span><span class="sxs-lookup"><span data-stu-id="ff368-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="ff368-140">若要指定包含嵌入的带引号的字符串的字符串，您可以使用原义字符串或三引号字符串。</span><span class="sxs-lookup"><span data-stu-id="ff368-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="ff368-141">如果使用原义字符串，则必须指定两个引号字符来表示单引号字符。</span><span class="sxs-lookup"><span data-stu-id="ff368-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="ff368-142">如果使用三引号字符串时，您可以使用单引号字符没有它们解析为字符串的末尾。</span><span class="sxs-lookup"><span data-stu-id="ff368-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="ff368-143">当您使用 XML 或其他结构包含嵌入的引号时，此技术很有用。</span><span class="sxs-lookup"><span data-stu-id="ff368-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="ff368-144">在代码中，接受有换行符的字符串的和换行是按字面解释为换行符，除非反斜杠字符为换行符之前的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="ff368-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="ff368-145">使用反斜杠字符时，将忽略在下一行中前导空白字符。</span><span class="sxs-lookup"><span data-stu-id="ff368-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="ff368-146">下面的代码生成一个字符串`str1`具有值`"abc\ndef"`和一个字符串`str2`具有值`"abcdef"`。</span><span class="sxs-lookup"><span data-stu-id="ff368-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="ff368-147">可以按以下方式使用的类似数组的语法来访问字符串中的单个字符。</span><span class="sxs-lookup"><span data-stu-id="ff368-147">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="ff368-148">输出为 `b`。</span><span class="sxs-lookup"><span data-stu-id="ff368-148">The output is `b`.</span></span>

<span data-ttu-id="ff368-149">或者，可以通过使用数组切片语法提取子字符串，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="ff368-149">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="ff368-150">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="ff368-150">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="ff368-151">您可以通过无符号字节，类型的数组表示 ASCII 字符串`byte[]`。</span><span class="sxs-lookup"><span data-stu-id="ff368-151">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="ff368-152">添加后缀`B`到字符串文本以指示它是一个 ASCII 字符串。</span><span class="sxs-lookup"><span data-stu-id="ff368-152">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="ff368-153">ASCII 字符串文本使用的字节数组支持相同的转义序列作为 Unicode 字符串，除了 Unicode 转义序列。</span><span class="sxs-lookup"><span data-stu-id="ff368-153">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="ff368-154">字符串运算符</span><span class="sxs-lookup"><span data-stu-id="ff368-154">String Operators</span></span>

<span data-ttu-id="ff368-155">有两种方法来连接字符串： 通过使用`+`运算符或通过使用`^`运算符。</span><span class="sxs-lookup"><span data-stu-id="ff368-155">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="ff368-156">`+`运算符维护与.NET Framework 字符串处理功能的兼容性。</span><span class="sxs-lookup"><span data-stu-id="ff368-156">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="ff368-157">下面的示例说明了字符串串联。</span><span class="sxs-lookup"><span data-stu-id="ff368-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="ff368-158">字符串类</span><span class="sxs-lookup"><span data-stu-id="ff368-158">String Class</span></span>

<span data-ttu-id="ff368-159">因为字符串类型在F#是实际.NET Framework`System.String`键入所有`System.String`成员均可。</span><span class="sxs-lookup"><span data-stu-id="ff368-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="ff368-160">这包括`+`运算符，用来连接字符串`Length`属性，并`Chars`Unicode 字符数组的形式返回字符串的属性。</span><span class="sxs-lookup"><span data-stu-id="ff368-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="ff368-161">有关字符串的详细信息，请参阅`System.String`。</span><span class="sxs-lookup"><span data-stu-id="ff368-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="ff368-162">通过使用`Chars`属性的`System.String`，可以通过指定一个索引，如下面的代码中所示访问字符串中的单个字符。</span><span class="sxs-lookup"><span data-stu-id="ff368-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="ff368-163">字符串模块</span><span class="sxs-lookup"><span data-stu-id="ff368-163">String Module</span></span>

<span data-ttu-id="ff368-164">字符串处理的附加功能包含在`String`中的模块`FSharp.Core`命名空间。</span><span class="sxs-lookup"><span data-stu-id="ff368-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="ff368-165">有关详细信息，请参阅[Core.String 模块](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="ff368-165">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="ff368-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff368-166">See also</span></span>

- [<span data-ttu-id="ff368-167">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="ff368-167">F# Language Reference</span></span>](index.md)
