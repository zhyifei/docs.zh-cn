---
title: "文本 (F#)"
description: "了解有关在 F # 编程语言的文本类型。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4b1d6e9d-f933-4cd4-966d-d643152c27e4
ms.openlocfilehash: 6bb1f233b6846e226c4e73aee00b8cf77735fe2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="literals"></a><span data-ttu-id="43dd7-104">文本</span><span class="sxs-lookup"><span data-stu-id="43dd7-104">Literals</span></span>

> [!NOTE]
<span data-ttu-id="43dd7-105">这篇文章中的 API 引用链接将转到 MSDN （对于暂时）。</span><span class="sxs-lookup"><span data-stu-id="43dd7-105">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="43dd7-106">本主题提供演示如何在 F # 中指定文本的类型的表。</span><span class="sxs-lookup"><span data-stu-id="43dd7-106">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="43dd7-107">文本类型</span><span class="sxs-lookup"><span data-stu-id="43dd7-107">Literal Types</span></span>
<span data-ttu-id="43dd7-108">下表显示 F # 中的文本的类型。</span><span class="sxs-lookup"><span data-stu-id="43dd7-108">The following table shows the literal types in F#.</span></span> <span data-ttu-id="43dd7-109">表示以十六进制表示的数字的字符不区分大小写;标识类型的字符是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="43dd7-109">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="43dd7-110">类型</span><span class="sxs-lookup"><span data-stu-id="43dd7-110">Type</span></span>|<span data-ttu-id="43dd7-111">描述</span><span class="sxs-lookup"><span data-stu-id="43dd7-111">Description</span></span>|<span data-ttu-id="43dd7-112">后缀或前缀</span><span class="sxs-lookup"><span data-stu-id="43dd7-112">Suffix or prefix</span></span>|<span data-ttu-id="43dd7-113">示例</span><span class="sxs-lookup"><span data-stu-id="43dd7-113">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="43dd7-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="43dd7-114">sbyte</span></span>|<span data-ttu-id="43dd7-115">8 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="43dd7-115">signed 8-bit integer</span></span>|<span data-ttu-id="43dd7-116">y</span><span class="sxs-lookup"><span data-stu-id="43dd7-116">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="43dd7-117">byte</span><span class="sxs-lookup"><span data-stu-id="43dd7-117">byte</span></span>|<span data-ttu-id="43dd7-118">无符号的 8 位自然数</span><span class="sxs-lookup"><span data-stu-id="43dd7-118">unsigned 8-bit natural number</span></span>|<span data-ttu-id="43dd7-119">uy</span><span class="sxs-lookup"><span data-stu-id="43dd7-119">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="43dd7-120">int16</span><span class="sxs-lookup"><span data-stu-id="43dd7-120">int16</span></span>|<span data-ttu-id="43dd7-121">16 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="43dd7-121">signed 16-bit integer</span></span>|<span data-ttu-id="43dd7-122">秒</span><span class="sxs-lookup"><span data-stu-id="43dd7-122">s</span></span>|`86s`|
|<span data-ttu-id="43dd7-123">uint16</span><span class="sxs-lookup"><span data-stu-id="43dd7-123">uint16</span></span>|<span data-ttu-id="43dd7-124">无符号的 16 位自然数</span><span class="sxs-lookup"><span data-stu-id="43dd7-124">unsigned 16-bit natural number</span></span>|<span data-ttu-id="43dd7-125">us</span><span class="sxs-lookup"><span data-stu-id="43dd7-125">us</span></span>|`86us`|
|<span data-ttu-id="43dd7-126">int</span><span class="sxs-lookup"><span data-stu-id="43dd7-126">int</span></span><br /><br /><span data-ttu-id="43dd7-127">int32</span><span class="sxs-lookup"><span data-stu-id="43dd7-127">int32</span></span>|<span data-ttu-id="43dd7-128">32 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="43dd7-128">signed 32-bit integer</span></span>|<span data-ttu-id="43dd7-129">l 或无</span><span class="sxs-lookup"><span data-stu-id="43dd7-129">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="43dd7-130">uint</span><span class="sxs-lookup"><span data-stu-id="43dd7-130">uint</span></span><br /><br /><span data-ttu-id="43dd7-131">uint32</span><span class="sxs-lookup"><span data-stu-id="43dd7-131">uint32</span></span>|<span data-ttu-id="43dd7-132">无符号的 32 位自然数字</span><span class="sxs-lookup"><span data-stu-id="43dd7-132">unsigned 32-bit natural number</span></span>|<span data-ttu-id="43dd7-133">u 或 u l</span><span class="sxs-lookup"><span data-stu-id="43dd7-133">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="43dd7-134">unativeint</span><span class="sxs-lookup"><span data-stu-id="43dd7-134">unativeint</span></span>|<span data-ttu-id="43dd7-135">本机指针作为无符号的自然数字</span><span class="sxs-lookup"><span data-stu-id="43dd7-135">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="43dd7-136">取消</span><span class="sxs-lookup"><span data-stu-id="43dd7-136">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="43dd7-137">int64</span><span class="sxs-lookup"><span data-stu-id="43dd7-137">int64</span></span>|<span data-ttu-id="43dd7-138">64 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="43dd7-138">signed 64-bit integer</span></span>|<span data-ttu-id="43dd7-139">L</span><span class="sxs-lookup"><span data-stu-id="43dd7-139">L</span></span>|`86L`|
|<span data-ttu-id="43dd7-140">uint64</span><span class="sxs-lookup"><span data-stu-id="43dd7-140">uint64</span></span>|<span data-ttu-id="43dd7-141">无符号的 64 位自然数</span><span class="sxs-lookup"><span data-stu-id="43dd7-141">unsigned 64-bit natural number</span></span>|<span data-ttu-id="43dd7-142">UL</span><span class="sxs-lookup"><span data-stu-id="43dd7-142">UL</span></span>|`86UL`|
|<span data-ttu-id="43dd7-143">单个，float32</span><span class="sxs-lookup"><span data-stu-id="43dd7-143">single, float32</span></span>|<span data-ttu-id="43dd7-144">32 位浮点数字</span><span class="sxs-lookup"><span data-stu-id="43dd7-144">32-bit floating point number</span></span>|<span data-ttu-id="43dd7-145">F 或 f</span><span class="sxs-lookup"><span data-stu-id="43dd7-145">F or f</span></span>|<span data-ttu-id="43dd7-146">`4.14F` 或 `4.14f`</span><span class="sxs-lookup"><span data-stu-id="43dd7-146">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="43dd7-147">lf</span><span class="sxs-lookup"><span data-stu-id="43dd7-147">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="43dd7-148">float;双精度</span><span class="sxs-lookup"><span data-stu-id="43dd7-148">float; double</span></span>|<span data-ttu-id="43dd7-149">64 位浮点数</span><span class="sxs-lookup"><span data-stu-id="43dd7-149">64-bit floating point number</span></span>|<span data-ttu-id="43dd7-150">无</span><span class="sxs-lookup"><span data-stu-id="43dd7-150">none</span></span>|<span data-ttu-id="43dd7-151">`4.14` 或 `2.3E+32` 或 `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="43dd7-151">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="43dd7-152">LF</span><span class="sxs-lookup"><span data-stu-id="43dd7-152">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="43dd7-153">bigint</span><span class="sxs-lookup"><span data-stu-id="43dd7-153">bigint</span></span>|<span data-ttu-id="43dd7-154">不受限制为 64 位表示形式的整数</span><span class="sxs-lookup"><span data-stu-id="43dd7-154">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="43dd7-155">I</span><span class="sxs-lookup"><span data-stu-id="43dd7-155">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="43dd7-156">decimal</span><span class="sxs-lookup"><span data-stu-id="43dd7-156">decimal</span></span>|<span data-ttu-id="43dd7-157">小数表示为固定的点或有理数</span><span class="sxs-lookup"><span data-stu-id="43dd7-157">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="43dd7-158">M 或 m</span><span class="sxs-lookup"><span data-stu-id="43dd7-158">M or m</span></span>|<span data-ttu-id="43dd7-159">`0.7833M` 或 `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="43dd7-159">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="43dd7-160">Char</span><span class="sxs-lookup"><span data-stu-id="43dd7-160">Char</span></span>|<span data-ttu-id="43dd7-161">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="43dd7-161">Unicode character</span></span>|<span data-ttu-id="43dd7-162">无</span><span class="sxs-lookup"><span data-stu-id="43dd7-162">none</span></span>|`'a'`|
|<span data-ttu-id="43dd7-163">字符串</span><span class="sxs-lookup"><span data-stu-id="43dd7-163">String</span></span>|<span data-ttu-id="43dd7-164">Unicode 字符串</span><span class="sxs-lookup"><span data-stu-id="43dd7-164">Unicode string</span></span>|<span data-ttu-id="43dd7-165">无</span><span class="sxs-lookup"><span data-stu-id="43dd7-165">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="43dd7-166">或</span><span class="sxs-lookup"><span data-stu-id="43dd7-166">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="43dd7-167">或</span><span class="sxs-lookup"><span data-stu-id="43dd7-167">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="43dd7-168">或</span><span class="sxs-lookup"><span data-stu-id="43dd7-168">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="43dd7-169">另请参阅[字符串](Strings.md)。</span><span class="sxs-lookup"><span data-stu-id="43dd7-169">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="43dd7-170">byte</span><span class="sxs-lookup"><span data-stu-id="43dd7-170">byte</span></span>|<span data-ttu-id="43dd7-171">ASCII 字符</span><span class="sxs-lookup"><span data-stu-id="43dd7-171">ASCII character</span></span>|<span data-ttu-id="43dd7-172">B</span><span class="sxs-lookup"><span data-stu-id="43dd7-172">B</span></span>|`'a'B`|
|<span data-ttu-id="43dd7-173">byte[]</span><span class="sxs-lookup"><span data-stu-id="43dd7-173">byte[]</span></span>|<span data-ttu-id="43dd7-174">ASCII 字符串</span><span class="sxs-lookup"><span data-stu-id="43dd7-174">ASCII string</span></span>|<span data-ttu-id="43dd7-175">B</span><span class="sxs-lookup"><span data-stu-id="43dd7-175">B</span></span>|`"text"B`|
|<span data-ttu-id="43dd7-176">字符串或字节]</span><span class="sxs-lookup"><span data-stu-id="43dd7-176">String or byte[]</span></span>|<span data-ttu-id="43dd7-177">逐字字符串</span><span class="sxs-lookup"><span data-stu-id="43dd7-177">verbatim string</span></span>|<span data-ttu-id="43dd7-178">@ 前缀</span><span class="sxs-lookup"><span data-stu-id="43dd7-178">@ prefix</span></span>|<span data-ttu-id="43dd7-179">`@"\\server\share"`(Unicode)</span><span class="sxs-lookup"><span data-stu-id="43dd7-179">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="43dd7-180">`@"\\server\share"B`(ASCII)</span><span class="sxs-lookup"><span data-stu-id="43dd7-180">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="43dd7-181">备注</span><span class="sxs-lookup"><span data-stu-id="43dd7-181">Remarks</span></span>
<span data-ttu-id="43dd7-182">Unicode 字符串可以包含你可以通过使用指定的显式编码`\u`跟一个 16 位十六进制代码或可以通过使用指定的 utf-32 编码`\U`跟 32 位十六进制表示的代码的 Unicode代理项对。</span><span class="sxs-lookup"><span data-stu-id="43dd7-182">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="43dd7-183">截至 F # 3.1 中，你可以使用`+`登录，以合并字符串文本。</span><span class="sxs-lookup"><span data-stu-id="43dd7-183">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="43dd7-184">你还可以使用的按位或 (`|||`) 运算符来组合枚举标志。</span><span class="sxs-lookup"><span data-stu-id="43dd7-184">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="43dd7-185">例如，下面的代码是在 F # 3.1 中合法的：</span><span class="sxs-lookup"><span data-stu-id="43dd7-185">For example, the following code is legal in F# 3.1:</span></span>

```fsharp
[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

<span data-ttu-id="43dd7-186">不允许其他按位运算符的使用。</span><span class="sxs-lookup"><span data-stu-id="43dd7-186">The use of other bitwise operators isn't allowed.</span></span>


## <a name="named-literals"></a><span data-ttu-id="43dd7-187">命名的文本</span><span class="sxs-lookup"><span data-stu-id="43dd7-187">Named Literals</span></span>
<span data-ttu-id="43dd7-188">都应是常量的值可标记为[文本](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285)属性。</span><span class="sxs-lookup"><span data-stu-id="43dd7-188">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="43dd7-189">此属性的效果的导致要编译为常量的值。</span><span class="sxs-lookup"><span data-stu-id="43dd7-189">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="43dd7-190">在匹配表达式的模式中，小写字符开头的标识符始终被视为变量绑定，而不是原义字符，因此你通常应使用首字母大写时定义的文本。</span><span class="sxs-lookup"><span data-stu-id="43dd7-190">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="43dd7-191">在其他基整数</span><span class="sxs-lookup"><span data-stu-id="43dd7-191">Integers In Other Bases</span></span>

<span data-ttu-id="43dd7-192">32 位有符号的整数，还可以指定在十六进制、 八进制或二进制使用`0x`，`0o`或`0b`分别前缀。</span><span class="sxs-lookup"><span data-stu-id="43dd7-192">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="43dd7-193">数值中包含下划线</span><span class="sxs-lookup"><span data-stu-id="43dd7-193">Underscores in Numeric Literals</span></span>

<span data-ttu-id="43dd7-194">F # 4.1 开始，你可以分隔数字下划线字符开头 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="43dd7-194">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="43dd7-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43dd7-195">See Also</span></span>

[<span data-ttu-id="43dd7-196">Core.LiteralAttribute 类</span><span class="sxs-lookup"><span data-stu-id="43dd7-196">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
