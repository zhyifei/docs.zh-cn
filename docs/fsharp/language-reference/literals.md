---
title: 文本
description: 了解有关在中的文本类型F#编程语言。
ms.date: 06/28/2019
ms.openlocfilehash: 0c9ced0b505817a161ca39c6c9f853f94cedf410
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610158"
---
# <a name="literals"></a><span data-ttu-id="77382-103">文本</span><span class="sxs-lookup"><span data-stu-id="77382-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="77382-104">在本文中的 API 参考链接将转至 MSDN （适用于暂时）。</span><span class="sxs-lookup"><span data-stu-id="77382-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="77382-105">本主题提供了表显示了如何指定的类型中的文本F#。</span><span class="sxs-lookup"><span data-stu-id="77382-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="77382-106">文本类型</span><span class="sxs-lookup"><span data-stu-id="77382-106">Literal Types</span></span>

<span data-ttu-id="77382-107">下表显示了中的文本类型F#。</span><span class="sxs-lookup"><span data-stu-id="77382-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="77382-108">表示以十六进制表示法表示的数字的字符不区分大小写;标识类型的字符是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="77382-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="77382-109">类型</span><span class="sxs-lookup"><span data-stu-id="77382-109">Type</span></span>|<span data-ttu-id="77382-110">描述</span><span class="sxs-lookup"><span data-stu-id="77382-110">Description</span></span>|<span data-ttu-id="77382-111">后缀或前缀</span><span class="sxs-lookup"><span data-stu-id="77382-111">Suffix or prefix</span></span>|<span data-ttu-id="77382-112">示例</span><span class="sxs-lookup"><span data-stu-id="77382-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="77382-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="77382-113">sbyte</span></span>|<span data-ttu-id="77382-114">8 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="77382-114">signed 8-bit integer</span></span>|<span data-ttu-id="77382-115">y</span><span class="sxs-lookup"><span data-stu-id="77382-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="77382-116">byte</span><span class="sxs-lookup"><span data-stu-id="77382-116">byte</span></span>|<span data-ttu-id="77382-117">无符号的 8 位自然数</span><span class="sxs-lookup"><span data-stu-id="77382-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="77382-118">uy</span><span class="sxs-lookup"><span data-stu-id="77382-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="77382-119">int16</span><span class="sxs-lookup"><span data-stu-id="77382-119">int16</span></span>|<span data-ttu-id="77382-120">16 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="77382-120">signed 16-bit integer</span></span>|<span data-ttu-id="77382-121">秒</span><span class="sxs-lookup"><span data-stu-id="77382-121">s</span></span>|`86s`|
|<span data-ttu-id="77382-122">uint16</span><span class="sxs-lookup"><span data-stu-id="77382-122">uint16</span></span>|<span data-ttu-id="77382-123">无符号的 16 位自然数</span><span class="sxs-lookup"><span data-stu-id="77382-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="77382-124">us</span><span class="sxs-lookup"><span data-stu-id="77382-124">us</span></span>|`86us`|
|<span data-ttu-id="77382-125">int</span><span class="sxs-lookup"><span data-stu-id="77382-125">int</span></span><br /><br /><span data-ttu-id="77382-126">int32</span><span class="sxs-lookup"><span data-stu-id="77382-126">int32</span></span>|<span data-ttu-id="77382-127">32 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="77382-127">signed 32-bit integer</span></span>|<span data-ttu-id="77382-128">l 或 none</span><span class="sxs-lookup"><span data-stu-id="77382-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="77382-129">uint</span><span class="sxs-lookup"><span data-stu-id="77382-129">uint</span></span><br /><br /><span data-ttu-id="77382-130">uint32</span><span class="sxs-lookup"><span data-stu-id="77382-130">uint32</span></span>|<span data-ttu-id="77382-131">无符号的 32 位自然数</span><span class="sxs-lookup"><span data-stu-id="77382-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="77382-132">u 或 ul</span><span class="sxs-lookup"><span data-stu-id="77382-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="77382-133">nativeint</span><span class="sxs-lookup"><span data-stu-id="77382-133">nativeint</span></span>|<span data-ttu-id="77382-134">为有符号数字，自然的本机指针</span><span class="sxs-lookup"><span data-stu-id="77382-134">native pointer to a signed natural number</span></span>|<span data-ttu-id="77382-135">n</span><span class="sxs-lookup"><span data-stu-id="77382-135">n</span></span>|`123n`|
|<span data-ttu-id="77382-136">unativeint</span><span class="sxs-lookup"><span data-stu-id="77382-136">unativeint</span></span>|<span data-ttu-id="77382-137">无符号自然数形式的本机指针</span><span class="sxs-lookup"><span data-stu-id="77382-137">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="77382-138">取消</span><span class="sxs-lookup"><span data-stu-id="77382-138">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="77382-139">int64</span><span class="sxs-lookup"><span data-stu-id="77382-139">int64</span></span>|<span data-ttu-id="77382-140">64 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="77382-140">signed 64-bit integer</span></span>|<span data-ttu-id="77382-141">L</span><span class="sxs-lookup"><span data-stu-id="77382-141">L</span></span>|`86L`|
|<span data-ttu-id="77382-142">uint64</span><span class="sxs-lookup"><span data-stu-id="77382-142">uint64</span></span>|<span data-ttu-id="77382-143">无符号的 64 位自然数</span><span class="sxs-lookup"><span data-stu-id="77382-143">unsigned 64-bit natural number</span></span>|<span data-ttu-id="77382-144">UL</span><span class="sxs-lookup"><span data-stu-id="77382-144">UL</span></span>|`86UL`|
|<span data-ttu-id="77382-145">单一的 float32</span><span class="sxs-lookup"><span data-stu-id="77382-145">single, float32</span></span>|<span data-ttu-id="77382-146">32 位浮点数</span><span class="sxs-lookup"><span data-stu-id="77382-146">32-bit floating point number</span></span>|<span data-ttu-id="77382-147">F 或 f</span><span class="sxs-lookup"><span data-stu-id="77382-147">F or f</span></span>|<span data-ttu-id="77382-148">`4.14F` 或 `4.14f`</span><span class="sxs-lookup"><span data-stu-id="77382-148">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="77382-149">lf</span><span class="sxs-lookup"><span data-stu-id="77382-149">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="77382-150">float;双精度</span><span class="sxs-lookup"><span data-stu-id="77382-150">float; double</span></span>|<span data-ttu-id="77382-151">64 位浮点数</span><span class="sxs-lookup"><span data-stu-id="77382-151">64-bit floating point number</span></span>|<span data-ttu-id="77382-152">无</span><span class="sxs-lookup"><span data-stu-id="77382-152">none</span></span>|<span data-ttu-id="77382-153">`4.14` 或 `2.3E+32` 或 `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="77382-153">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="77382-154">LF</span><span class="sxs-lookup"><span data-stu-id="77382-154">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="77382-155">bigint</span><span class="sxs-lookup"><span data-stu-id="77382-155">bigint</span></span>|<span data-ttu-id="77382-156">不限制为 64 位表示形式的整数</span><span class="sxs-lookup"><span data-stu-id="77382-156">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="77382-157">I</span><span class="sxs-lookup"><span data-stu-id="77382-157">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="77382-158">decimal</span><span class="sxs-lookup"><span data-stu-id="77382-158">decimal</span></span>|<span data-ttu-id="77382-159">表示为固定的点或有理数的小数</span><span class="sxs-lookup"><span data-stu-id="77382-159">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="77382-160">M 或 m</span><span class="sxs-lookup"><span data-stu-id="77382-160">M or m</span></span>|<span data-ttu-id="77382-161">`0.7833M` 或 `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="77382-161">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="77382-162">Char</span><span class="sxs-lookup"><span data-stu-id="77382-162">Char</span></span>|<span data-ttu-id="77382-163">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="77382-163">Unicode character</span></span>|<span data-ttu-id="77382-164">无</span><span class="sxs-lookup"><span data-stu-id="77382-164">none</span></span>|`'a'`|
|<span data-ttu-id="77382-165">String</span><span class="sxs-lookup"><span data-stu-id="77382-165">String</span></span>|<span data-ttu-id="77382-166">Unicode 字符串</span><span class="sxs-lookup"><span data-stu-id="77382-166">Unicode string</span></span>|<span data-ttu-id="77382-167">无</span><span class="sxs-lookup"><span data-stu-id="77382-167">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="77382-168">或</span><span class="sxs-lookup"><span data-stu-id="77382-168">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="77382-169">或</span><span class="sxs-lookup"><span data-stu-id="77382-169">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="77382-170">或</span><span class="sxs-lookup"><span data-stu-id="77382-170">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="77382-171">另请参阅[字符串](Strings.md)。</span><span class="sxs-lookup"><span data-stu-id="77382-171">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="77382-172">byte</span><span class="sxs-lookup"><span data-stu-id="77382-172">byte</span></span>|<span data-ttu-id="77382-173">ASCII 字符</span><span class="sxs-lookup"><span data-stu-id="77382-173">ASCII character</span></span>|<span data-ttu-id="77382-174">B</span><span class="sxs-lookup"><span data-stu-id="77382-174">B</span></span>|`'a'B`|
|<span data-ttu-id="77382-175">byte[]</span><span class="sxs-lookup"><span data-stu-id="77382-175">byte[]</span></span>|<span data-ttu-id="77382-176">ASCII 字符串</span><span class="sxs-lookup"><span data-stu-id="77382-176">ASCII string</span></span>|<span data-ttu-id="77382-177">B</span><span class="sxs-lookup"><span data-stu-id="77382-177">B</span></span>|`"text"B`|
|<span data-ttu-id="77382-178">字符串或 byte]</span><span class="sxs-lookup"><span data-stu-id="77382-178">String or byte[]</span></span>|<span data-ttu-id="77382-179">逐字字符串</span><span class="sxs-lookup"><span data-stu-id="77382-179">verbatim string</span></span>|<span data-ttu-id="77382-180">@ prefix</span><span class="sxs-lookup"><span data-stu-id="77382-180">@ prefix</span></span>|<span data-ttu-id="77382-181">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="77382-181">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="77382-182">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="77382-182">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="77382-183">指定的文字</span><span class="sxs-lookup"><span data-stu-id="77382-183">Named literals</span></span>

<span data-ttu-id="77382-184">可以使用标记值都应是常量[文字](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285)属性。</span><span class="sxs-lookup"><span data-stu-id="77382-184">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="77382-185">此属性具有导致被编译为一个常量值的效果。</span><span class="sxs-lookup"><span data-stu-id="77382-185">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="77382-186">在模式匹配表达式中，小写字母开头的标识符始终被当作变量绑定，而不是文字，因此通常应使用首字母大写定义文字。</span><span class="sxs-lookup"><span data-stu-id="77382-186">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a><span data-ttu-id="77382-187">备注</span><span class="sxs-lookup"><span data-stu-id="77382-187">Remarks</span></span>

<span data-ttu-id="77382-188">Unicode 字符串可包含可以通过使用指定的显式编码`\u`跟 16 位十六进制代码 (0000-FFFF) 或可以通过使用指定的 UTF-32 编码`\U`跟表示 32 位十六进制代码任何 Unicode 码位 (00000000-0010FFFF)。</span><span class="sxs-lookup"><span data-stu-id="77382-188">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="77382-189">使用其他按位运算符以外的其他`|||`不允许使用。</span><span class="sxs-lookup"><span data-stu-id="77382-189">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="77382-190">在其他基数的整数</span><span class="sxs-lookup"><span data-stu-id="77382-190">Integers in other bases</span></span>

<span data-ttu-id="77382-191">有符号的 32 位整数，还可以指定在使用十六进制、 八进制或二进制`0x`，`0o`或`0b`分别前缀。</span><span class="sxs-lookup"><span data-stu-id="77382-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="77382-192">数值文字中的下划线</span><span class="sxs-lookup"><span data-stu-id="77382-192">Underscores in numeric literals</span></span>

<span data-ttu-id="77382-193">可以使用下划线字符分隔数字 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="77382-193">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="77382-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="77382-194">See also</span></span>

- [<span data-ttu-id="77382-195">Core.LiteralAttribute 类</span><span class="sxs-lookup"><span data-stu-id="77382-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
