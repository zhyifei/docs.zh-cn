---
title: 文本 (F#)
description: '了解有关在 F # 编程语言的文本类型。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 961d6a10122c5d5c691d394efa8d2b7b31a80453
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="literals"></a><span data-ttu-id="bc743-103">文本</span><span class="sxs-lookup"><span data-stu-id="bc743-103">Literals</span></span>

> [!NOTE]
<span data-ttu-id="bc743-104">这篇文章中的 API 引用链接将转到 MSDN （对于暂时）。</span><span class="sxs-lookup"><span data-stu-id="bc743-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="bc743-105">本主题提供演示如何在 F # 中指定文本的类型的表。</span><span class="sxs-lookup"><span data-stu-id="bc743-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="bc743-106">文本类型</span><span class="sxs-lookup"><span data-stu-id="bc743-106">Literal Types</span></span>
<span data-ttu-id="bc743-107">下表显示 F # 中的文本的类型。</span><span class="sxs-lookup"><span data-stu-id="bc743-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="bc743-108">表示以十六进制表示的数字的字符不区分大小写;标识类型的字符是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="bc743-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="bc743-109">类型</span><span class="sxs-lookup"><span data-stu-id="bc743-109">Type</span></span>|<span data-ttu-id="bc743-110">描述</span><span class="sxs-lookup"><span data-stu-id="bc743-110">Description</span></span>|<span data-ttu-id="bc743-111">后缀或前缀</span><span class="sxs-lookup"><span data-stu-id="bc743-111">Suffix or prefix</span></span>|<span data-ttu-id="bc743-112">示例</span><span class="sxs-lookup"><span data-stu-id="bc743-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="bc743-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="bc743-113">sbyte</span></span>|<span data-ttu-id="bc743-114">8 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="bc743-114">signed 8-bit integer</span></span>|<span data-ttu-id="bc743-115">y</span><span class="sxs-lookup"><span data-stu-id="bc743-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="bc743-116">byte</span><span class="sxs-lookup"><span data-stu-id="bc743-116">byte</span></span>|<span data-ttu-id="bc743-117">无符号的 8 位自然数</span><span class="sxs-lookup"><span data-stu-id="bc743-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="bc743-118">uy</span><span class="sxs-lookup"><span data-stu-id="bc743-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="bc743-119">int16</span><span class="sxs-lookup"><span data-stu-id="bc743-119">int16</span></span>|<span data-ttu-id="bc743-120">16 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="bc743-120">signed 16-bit integer</span></span>|<span data-ttu-id="bc743-121">秒</span><span class="sxs-lookup"><span data-stu-id="bc743-121">s</span></span>|`86s`|
|<span data-ttu-id="bc743-122">uint16</span><span class="sxs-lookup"><span data-stu-id="bc743-122">uint16</span></span>|<span data-ttu-id="bc743-123">无符号的 16 位自然数</span><span class="sxs-lookup"><span data-stu-id="bc743-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="bc743-124">us</span><span class="sxs-lookup"><span data-stu-id="bc743-124">us</span></span>|`86us`|
|<span data-ttu-id="bc743-125">int</span><span class="sxs-lookup"><span data-stu-id="bc743-125">int</span></span><br /><br /><span data-ttu-id="bc743-126">int32</span><span class="sxs-lookup"><span data-stu-id="bc743-126">int32</span></span>|<span data-ttu-id="bc743-127">32 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="bc743-127">signed 32-bit integer</span></span>|<span data-ttu-id="bc743-128">l 或无</span><span class="sxs-lookup"><span data-stu-id="bc743-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="bc743-129">uint</span><span class="sxs-lookup"><span data-stu-id="bc743-129">uint</span></span><br /><br /><span data-ttu-id="bc743-130">uint32</span><span class="sxs-lookup"><span data-stu-id="bc743-130">uint32</span></span>|<span data-ttu-id="bc743-131">无符号的 32 位自然数字</span><span class="sxs-lookup"><span data-stu-id="bc743-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="bc743-132">u 或 u l</span><span class="sxs-lookup"><span data-stu-id="bc743-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="bc743-133">unativeint</span><span class="sxs-lookup"><span data-stu-id="bc743-133">unativeint</span></span>|<span data-ttu-id="bc743-134">本机指针作为无符号的自然数字</span><span class="sxs-lookup"><span data-stu-id="bc743-134">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="bc743-135">取消</span><span class="sxs-lookup"><span data-stu-id="bc743-135">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="bc743-136">int64</span><span class="sxs-lookup"><span data-stu-id="bc743-136">int64</span></span>|<span data-ttu-id="bc743-137">64 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="bc743-137">signed 64-bit integer</span></span>|<span data-ttu-id="bc743-138">L</span><span class="sxs-lookup"><span data-stu-id="bc743-138">L</span></span>|`86L`|
|<span data-ttu-id="bc743-139">uint64</span><span class="sxs-lookup"><span data-stu-id="bc743-139">uint64</span></span>|<span data-ttu-id="bc743-140">无符号的 64 位自然数</span><span class="sxs-lookup"><span data-stu-id="bc743-140">unsigned 64-bit natural number</span></span>|<span data-ttu-id="bc743-141">UL</span><span class="sxs-lookup"><span data-stu-id="bc743-141">UL</span></span>|`86UL`|
|<span data-ttu-id="bc743-142">单个，float32</span><span class="sxs-lookup"><span data-stu-id="bc743-142">single, float32</span></span>|<span data-ttu-id="bc743-143">32 位浮点数字</span><span class="sxs-lookup"><span data-stu-id="bc743-143">32-bit floating point number</span></span>|<span data-ttu-id="bc743-144">F 或 f</span><span class="sxs-lookup"><span data-stu-id="bc743-144">F or f</span></span>|<span data-ttu-id="bc743-145">`4.14F` 或 `4.14f`</span><span class="sxs-lookup"><span data-stu-id="bc743-145">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="bc743-146">lf</span><span class="sxs-lookup"><span data-stu-id="bc743-146">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="bc743-147">float;双精度</span><span class="sxs-lookup"><span data-stu-id="bc743-147">float; double</span></span>|<span data-ttu-id="bc743-148">64 位浮点数</span><span class="sxs-lookup"><span data-stu-id="bc743-148">64-bit floating point number</span></span>|<span data-ttu-id="bc743-149">无</span><span class="sxs-lookup"><span data-stu-id="bc743-149">none</span></span>|<span data-ttu-id="bc743-150">`4.14` 或 `2.3E+32` 或 `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="bc743-150">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="bc743-151">LF</span><span class="sxs-lookup"><span data-stu-id="bc743-151">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="bc743-152">bigint</span><span class="sxs-lookup"><span data-stu-id="bc743-152">bigint</span></span>|<span data-ttu-id="bc743-153">不受限制为 64 位表示形式的整数</span><span class="sxs-lookup"><span data-stu-id="bc743-153">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="bc743-154">I</span><span class="sxs-lookup"><span data-stu-id="bc743-154">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="bc743-155">decimal</span><span class="sxs-lookup"><span data-stu-id="bc743-155">decimal</span></span>|<span data-ttu-id="bc743-156">小数表示为固定的点或有理数</span><span class="sxs-lookup"><span data-stu-id="bc743-156">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="bc743-157">M 或 m</span><span class="sxs-lookup"><span data-stu-id="bc743-157">M or m</span></span>|<span data-ttu-id="bc743-158">`0.7833M` 或 `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="bc743-158">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="bc743-159">Char</span><span class="sxs-lookup"><span data-stu-id="bc743-159">Char</span></span>|<span data-ttu-id="bc743-160">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="bc743-160">Unicode character</span></span>|<span data-ttu-id="bc743-161">无</span><span class="sxs-lookup"><span data-stu-id="bc743-161">none</span></span>|`'a'`|
|<span data-ttu-id="bc743-162">String</span><span class="sxs-lookup"><span data-stu-id="bc743-162">String</span></span>|<span data-ttu-id="bc743-163">Unicode 字符串</span><span class="sxs-lookup"><span data-stu-id="bc743-163">Unicode string</span></span>|<span data-ttu-id="bc743-164">无</span><span class="sxs-lookup"><span data-stu-id="bc743-164">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="bc743-165">或</span><span class="sxs-lookup"><span data-stu-id="bc743-165">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="bc743-166">或</span><span class="sxs-lookup"><span data-stu-id="bc743-166">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="bc743-167">或</span><span class="sxs-lookup"><span data-stu-id="bc743-167">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="bc743-168">另请参阅[字符串](Strings.md)。</span><span class="sxs-lookup"><span data-stu-id="bc743-168">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="bc743-169">byte</span><span class="sxs-lookup"><span data-stu-id="bc743-169">byte</span></span>|<span data-ttu-id="bc743-170">ASCII 字符</span><span class="sxs-lookup"><span data-stu-id="bc743-170">ASCII character</span></span>|<span data-ttu-id="bc743-171">B</span><span class="sxs-lookup"><span data-stu-id="bc743-171">B</span></span>|`'a'B`|
|<span data-ttu-id="bc743-172">byte[]</span><span class="sxs-lookup"><span data-stu-id="bc743-172">byte[]</span></span>|<span data-ttu-id="bc743-173">ASCII 字符串</span><span class="sxs-lookup"><span data-stu-id="bc743-173">ASCII string</span></span>|<span data-ttu-id="bc743-174">B</span><span class="sxs-lookup"><span data-stu-id="bc743-174">B</span></span>|`"text"B`|
|<span data-ttu-id="bc743-175">字符串或字节]</span><span class="sxs-lookup"><span data-stu-id="bc743-175">String or byte[]</span></span>|<span data-ttu-id="bc743-176">逐字字符串</span><span class="sxs-lookup"><span data-stu-id="bc743-176">verbatim string</span></span>|<span data-ttu-id="bc743-177">@ 前缀</span><span class="sxs-lookup"><span data-stu-id="bc743-177">@ prefix</span></span>|<span data-ttu-id="bc743-178">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="bc743-178">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="bc743-179">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="bc743-179">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="bc743-180">备注</span><span class="sxs-lookup"><span data-stu-id="bc743-180">Remarks</span></span>
<span data-ttu-id="bc743-181">Unicode 字符串可以包含你可以通过使用指定的显式编码`\u`跟一个 16 位十六进制代码或可以通过使用指定的 utf-32 编码`\U`跟 32 位十六进制表示的代码的 Unicode代理项对。</span><span class="sxs-lookup"><span data-stu-id="bc743-181">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="bc743-182">截至 F # 3.1 中，你可以使用`+`登录，以合并字符串文本。</span><span class="sxs-lookup"><span data-stu-id="bc743-182">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="bc743-183">你还可以使用的按位或 (`|||`) 运算符来组合枚举标志。</span><span class="sxs-lookup"><span data-stu-id="bc743-183">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="bc743-184">例如，下面的代码是在 F # 3.1 中合法的：</span><span class="sxs-lookup"><span data-stu-id="bc743-184">For example, the following code is legal in F# 3.1:</span></span>

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

<span data-ttu-id="bc743-185">不允许其他按位运算符的使用。</span><span class="sxs-lookup"><span data-stu-id="bc743-185">The use of other bitwise operators isn't allowed.</span></span>


## <a name="named-literals"></a><span data-ttu-id="bc743-186">命名的文本</span><span class="sxs-lookup"><span data-stu-id="bc743-186">Named Literals</span></span>
<span data-ttu-id="bc743-187">都应是常量的值可标记为[文本](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285)属性。</span><span class="sxs-lookup"><span data-stu-id="bc743-187">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="bc743-188">此属性的效果的导致要编译为常量的值。</span><span class="sxs-lookup"><span data-stu-id="bc743-188">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="bc743-189">在匹配表达式的模式中，小写字符开头的标识符始终被视为变量绑定，而不是原义字符，因此你通常应使用首字母大写时定义的文本。</span><span class="sxs-lookup"><span data-stu-id="bc743-189">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="bc743-190">在其他基整数</span><span class="sxs-lookup"><span data-stu-id="bc743-190">Integers In Other Bases</span></span>

<span data-ttu-id="bc743-191">32 位有符号的整数，还可以指定在十六进制、 八进制或二进制使用`0x`，`0o`或`0b`分别前缀。</span><span class="sxs-lookup"><span data-stu-id="bc743-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="bc743-192">数值中包含下划线</span><span class="sxs-lookup"><span data-stu-id="bc743-192">Underscores in Numeric Literals</span></span>

<span data-ttu-id="bc743-193">F # 4.1 开始，你可以分隔数字下划线字符开头 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="bc743-193">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="bc743-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc743-194">See Also</span></span>

[<span data-ttu-id="bc743-195">Core.LiteralAttribute 类</span><span class="sxs-lookup"><span data-stu-id="bc743-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
