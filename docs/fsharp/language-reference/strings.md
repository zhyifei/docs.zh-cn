---
title: 字符串 (F#)
description: "了解 F # 'string' 类型如何表示为一系列 Unicode 字符的不可变的文本。"
ms.date: 05/16/2016
ms.openlocfilehash: 21971602093bc84b0df47d4ae46a14fb936c28bb
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "43799338"
---
# <a name="strings"></a><span data-ttu-id="2fcde-103">字符串</span><span class="sxs-lookup"><span data-stu-id="2fcde-103">Strings</span></span>

> [!NOTE]
<span data-ttu-id="2fcde-104">本文中的 API 参考链接将转至 MSDN。</span><span class="sxs-lookup"><span data-stu-id="2fcde-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="2fcde-105">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="2fcde-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="2fcde-106">`string`类型将不可变的文本表示为一系列 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="2fcde-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="2fcde-107">`string` 是 .NET Framework 中 `System.String` 的别名。</span><span class="sxs-lookup"><span data-stu-id="2fcde-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="2fcde-108">备注</span><span class="sxs-lookup"><span data-stu-id="2fcde-108">Remarks</span></span>

<span data-ttu-id="2fcde-109">字符串文本用引号 （"） 字符分隔。</span><span class="sxs-lookup"><span data-stu-id="2fcde-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="2fcde-110">反斜杠字符 ( \\ ) 使用某些特殊字符进行编码。</span><span class="sxs-lookup"><span data-stu-id="2fcde-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="2fcde-111">反斜杠和组合在一起的下一个字符被称为*转义序列*。</span><span class="sxs-lookup"><span data-stu-id="2fcde-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="2fcde-112">转义序列在 F # 字符串文本会显示下表中受支持。</span><span class="sxs-lookup"><span data-stu-id="2fcde-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="2fcde-113">字符</span><span class="sxs-lookup"><span data-stu-id="2fcde-113">Character</span></span>|<span data-ttu-id="2fcde-114">转义序列</span><span class="sxs-lookup"><span data-stu-id="2fcde-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="2fcde-115">Backspace</span><span class="sxs-lookup"><span data-stu-id="2fcde-115">Backspace</span></span>|`\b`|
|<span data-ttu-id="2fcde-116">换行符</span><span class="sxs-lookup"><span data-stu-id="2fcde-116">Newline</span></span>|`\n`|
|<span data-ttu-id="2fcde-117">回车</span><span class="sxs-lookup"><span data-stu-id="2fcde-117">Carriage return</span></span>|`\r`|
|<span data-ttu-id="2fcde-118">Tab</span><span class="sxs-lookup"><span data-stu-id="2fcde-118">Tab</span></span>|`\t`|
|<span data-ttu-id="2fcde-119">反斜杠</span><span class="sxs-lookup"><span data-stu-id="2fcde-119">Backslash</span></span>|`\\`|
|<span data-ttu-id="2fcde-120">引号</span><span class="sxs-lookup"><span data-stu-id="2fcde-120">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="2fcde-121">撇号</span><span class="sxs-lookup"><span data-stu-id="2fcde-121">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="2fcde-122">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="2fcde-122">Unicode character</span></span>|<span data-ttu-id="2fcde-123">`\uXXXX` 或`\UXXXX`(其中`X`表示一个十六进制数字)</span><span class="sxs-lookup"><span data-stu-id="2fcde-123">`\uXXXX` or `\UXXXX` (where `X` indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="2fcde-124">如果前面有 @ 符号，则该文本是原义字符串。</span><span class="sxs-lookup"><span data-stu-id="2fcde-124">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="2fcde-125">这意味着，将忽略任何转义序列，但两个引号字符解释为一个引号字符。</span><span class="sxs-lookup"><span data-stu-id="2fcde-125">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="2fcde-126">此外，字符串可能包含三个引号引起来。</span><span class="sxs-lookup"><span data-stu-id="2fcde-126">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="2fcde-127">在这种情况下，将忽略所有转义序列，包括双引号字符。</span><span class="sxs-lookup"><span data-stu-id="2fcde-127">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="2fcde-128">若要指定包含嵌入的带引号的字符串的字符串，您可以使用原义字符串或三引号字符串。</span><span class="sxs-lookup"><span data-stu-id="2fcde-128">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="2fcde-129">如果使用原义字符串，则必须指定两个引号字符来表示单引号字符。</span><span class="sxs-lookup"><span data-stu-id="2fcde-129">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="2fcde-130">如果使用三引号字符串时，您可以使用单引号字符没有它们解析为字符串的末尾。</span><span class="sxs-lookup"><span data-stu-id="2fcde-130">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="2fcde-131">当您使用 XML 或其他结构包含嵌入的引号时，此技术很有用。</span><span class="sxs-lookup"><span data-stu-id="2fcde-131">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="2fcde-132">在代码中，接受有换行符的字符串的和换行是按字面解释为换行符，除非反斜杠字符为换行符之前的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="2fcde-132">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="2fcde-133">使用反斜杠字符时，将忽略在下一行中前导空白字符。</span><span class="sxs-lookup"><span data-stu-id="2fcde-133">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="2fcde-134">下面的代码生成一个字符串`str1`具有值`"abc\ndef"`和一个字符串`str2`具有值`"abcdef"`。</span><span class="sxs-lookup"><span data-stu-id="2fcde-134">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="2fcde-135">可以按以下方式使用的类似数组的语法来访问字符串中的单个字符。</span><span class="sxs-lookup"><span data-stu-id="2fcde-135">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="2fcde-136">输出为 `b`。</span><span class="sxs-lookup"><span data-stu-id="2fcde-136">The output is `b`.</span></span>

<span data-ttu-id="2fcde-137">或者，可以通过使用数组切片语法提取子字符串，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="2fcde-137">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="2fcde-138">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="2fcde-138">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="2fcde-139">您可以通过无符号字节，类型的数组表示 ASCII 字符串`byte[]`。</span><span class="sxs-lookup"><span data-stu-id="2fcde-139">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="2fcde-140">添加后缀`B`到字符串文本以指示它是一个 ASCII 字符串。</span><span class="sxs-lookup"><span data-stu-id="2fcde-140">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="2fcde-141">ASCII 字符串文本使用的字节数组支持相同的转义序列作为 Unicode 字符串，除了 Unicode 转义序列。</span><span class="sxs-lookup"><span data-stu-id="2fcde-141">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="2fcde-142">字符串运算符</span><span class="sxs-lookup"><span data-stu-id="2fcde-142">String Operators</span></span>

<span data-ttu-id="2fcde-143">有两种方法来连接字符串： 通过使用`+`运算符或通过使用`^`运算符。</span><span class="sxs-lookup"><span data-stu-id="2fcde-143">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="2fcde-144">`+`运算符维护与.NET Framework 字符串处理功能的兼容性。</span><span class="sxs-lookup"><span data-stu-id="2fcde-144">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="2fcde-145">下面的示例说明了字符串串联。</span><span class="sxs-lookup"><span data-stu-id="2fcde-145">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="2fcde-146">字符串类</span><span class="sxs-lookup"><span data-stu-id="2fcde-146">String Class</span></span>

<span data-ttu-id="2fcde-147">因为 F # 中的字符串类型是实际.NET Framework`System.String`类型，所有`System.String`成员均可。</span><span class="sxs-lookup"><span data-stu-id="2fcde-147">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="2fcde-148">这包括`+`运算符，用来连接字符串`Length`属性，并`Chars`Unicode 字符数组的形式返回字符串的属性。</span><span class="sxs-lookup"><span data-stu-id="2fcde-148">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="2fcde-149">有关字符串的详细信息，请参阅`System.String`。</span><span class="sxs-lookup"><span data-stu-id="2fcde-149">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="2fcde-150">通过使用`Chars`属性的`System.String`，可以通过指定一个索引，如下面的代码中所示访问字符串中的单个字符。</span><span class="sxs-lookup"><span data-stu-id="2fcde-150">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="2fcde-151">字符串模块</span><span class="sxs-lookup"><span data-stu-id="2fcde-151">String Module</span></span>

<span data-ttu-id="2fcde-152">字符串处理的附加功能包含在`String`中的模块`FSharp.Core`命名空间。</span><span class="sxs-lookup"><span data-stu-id="2fcde-152">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="2fcde-153">有关详细信息，请参阅[Core.String 模块](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="2fcde-153">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="2fcde-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fcde-154">See also</span></span>

- [<span data-ttu-id="2fcde-155">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="2fcde-155">F# Language Reference</span></span>](index.md)
