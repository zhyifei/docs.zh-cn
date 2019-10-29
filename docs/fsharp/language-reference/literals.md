---
title: 文本
description: 了解F#编程语言中的文本类型。
ms.date: 06/28/2019
ms.openlocfilehash: 9792a24ac28eb402e35e78574cd6a2bf9526734d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041031"
---
# <a name="literals"></a><span data-ttu-id="afd90-103">文本</span><span class="sxs-lookup"><span data-stu-id="afd90-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="afd90-104">本文中的 API 参考链接将转到 MSDN （目前为）。</span><span class="sxs-lookup"><span data-stu-id="afd90-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="afd90-105">本主题提供了一个表，其中显示了如何在中F#指定文本的类型。</span><span class="sxs-lookup"><span data-stu-id="afd90-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="afd90-106">文本类型</span><span class="sxs-lookup"><span data-stu-id="afd90-106">Literal Types</span></span>

<span data-ttu-id="afd90-107">下表显示了中F#的文本类型。</span><span class="sxs-lookup"><span data-stu-id="afd90-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="afd90-108">用十六进制表示法表示数字的字符不区分大小写;标识该类型的字符区分大小写。</span><span class="sxs-lookup"><span data-stu-id="afd90-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="afd90-109">键入</span><span class="sxs-lookup"><span data-stu-id="afd90-109">Type</span></span>|<span data-ttu-id="afd90-110">描述</span><span class="sxs-lookup"><span data-stu-id="afd90-110">Description</span></span>|<span data-ttu-id="afd90-111">后缀或前缀</span><span class="sxs-lookup"><span data-stu-id="afd90-111">Suffix or prefix</span></span>|<span data-ttu-id="afd90-112">示例</span><span class="sxs-lookup"><span data-stu-id="afd90-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="afd90-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="afd90-113">sbyte</span></span>|<span data-ttu-id="afd90-114">8位有符号整数</span><span class="sxs-lookup"><span data-stu-id="afd90-114">signed 8-bit integer</span></span>|<span data-ttu-id="afd90-115">y</span><span class="sxs-lookup"><span data-stu-id="afd90-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="afd90-116">byte</span><span class="sxs-lookup"><span data-stu-id="afd90-116">byte</span></span>|<span data-ttu-id="afd90-117">无符号8位自然数</span><span class="sxs-lookup"><span data-stu-id="afd90-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="afd90-118">uy</span><span class="sxs-lookup"><span data-stu-id="afd90-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="afd90-119">int16</span><span class="sxs-lookup"><span data-stu-id="afd90-119">int16</span></span>|<span data-ttu-id="afd90-120">16位带符号整数</span><span class="sxs-lookup"><span data-stu-id="afd90-120">signed 16-bit integer</span></span>|<span data-ttu-id="afd90-121">秒</span><span class="sxs-lookup"><span data-stu-id="afd90-121">s</span></span>|`86s`|
|<span data-ttu-id="afd90-122">uint16</span><span class="sxs-lookup"><span data-stu-id="afd90-122">uint16</span></span>|<span data-ttu-id="afd90-123">无符号16位自然数</span><span class="sxs-lookup"><span data-stu-id="afd90-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="afd90-124">us</span><span class="sxs-lookup"><span data-stu-id="afd90-124">us</span></span>|`86us`|
|<span data-ttu-id="afd90-125">int</span><span class="sxs-lookup"><span data-stu-id="afd90-125">int</span></span><br /><br /><span data-ttu-id="afd90-126">int32</span><span class="sxs-lookup"><span data-stu-id="afd90-126">int32</span></span>|<span data-ttu-id="afd90-127">已签名32位整数</span><span class="sxs-lookup"><span data-stu-id="afd90-127">signed 32-bit integer</span></span>|<span data-ttu-id="afd90-128">l 或无</span><span class="sxs-lookup"><span data-stu-id="afd90-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="afd90-129">uint</span><span class="sxs-lookup"><span data-stu-id="afd90-129">uint</span></span><br /><br /><span data-ttu-id="afd90-130">uint32</span><span class="sxs-lookup"><span data-stu-id="afd90-130">uint32</span></span>|<span data-ttu-id="afd90-131">无符号32位自然数</span><span class="sxs-lookup"><span data-stu-id="afd90-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="afd90-132">u 或 ul</span><span class="sxs-lookup"><span data-stu-id="afd90-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="afd90-133">nativeint</span><span class="sxs-lookup"><span data-stu-id="afd90-133">nativeint</span></span>|<span data-ttu-id="afd90-134">指向有符号自然数的本机指针</span><span class="sxs-lookup"><span data-stu-id="afd90-134">native pointer to a signed natural number</span></span>|<span data-ttu-id="afd90-135">n</span><span class="sxs-lookup"><span data-stu-id="afd90-135">n</span></span>|`123n`|
|<span data-ttu-id="afd90-136">unativeint</span><span class="sxs-lookup"><span data-stu-id="afd90-136">unativeint</span></span>|<span data-ttu-id="afd90-137">作为无符号自然数的本机指针</span><span class="sxs-lookup"><span data-stu-id="afd90-137">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="afd90-138">&</span><span class="sxs-lookup"><span data-stu-id="afd90-138">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="afd90-139">int64</span><span class="sxs-lookup"><span data-stu-id="afd90-139">int64</span></span>|<span data-ttu-id="afd90-140">已签名64位整数</span><span class="sxs-lookup"><span data-stu-id="afd90-140">signed 64-bit integer</span></span>|<span data-ttu-id="afd90-141">L</span><span class="sxs-lookup"><span data-stu-id="afd90-141">L</span></span>|`86L`|
|<span data-ttu-id="afd90-142">uint64</span><span class="sxs-lookup"><span data-stu-id="afd90-142">uint64</span></span>|<span data-ttu-id="afd90-143">无符号64位自然数</span><span class="sxs-lookup"><span data-stu-id="afd90-143">unsigned 64-bit natural number</span></span>|<span data-ttu-id="afd90-144">UL</span><span class="sxs-lookup"><span data-stu-id="afd90-144">UL</span></span>|`86UL`|
|<span data-ttu-id="afd90-145">单个，float32</span><span class="sxs-lookup"><span data-stu-id="afd90-145">single, float32</span></span>|<span data-ttu-id="afd90-146">32位浮点数</span><span class="sxs-lookup"><span data-stu-id="afd90-146">32-bit floating point number</span></span>|<span data-ttu-id="afd90-147">F 或 f</span><span class="sxs-lookup"><span data-stu-id="afd90-147">F or f</span></span>|<span data-ttu-id="afd90-148">`4.14F` 或 `4.14f`</span><span class="sxs-lookup"><span data-stu-id="afd90-148">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="afd90-149">换行符</span><span class="sxs-lookup"><span data-stu-id="afd90-149">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="afd90-150">float仔细</span><span class="sxs-lookup"><span data-stu-id="afd90-150">float; double</span></span>|<span data-ttu-id="afd90-151">64位浮点数</span><span class="sxs-lookup"><span data-stu-id="afd90-151">64-bit floating point number</span></span>|<span data-ttu-id="afd90-152">无</span><span class="sxs-lookup"><span data-stu-id="afd90-152">none</span></span>|<span data-ttu-id="afd90-153">`4.14` 或 `2.3E+32` 或 `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="afd90-153">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="afd90-154">换行符</span><span class="sxs-lookup"><span data-stu-id="afd90-154">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="afd90-155">bigint</span><span class="sxs-lookup"><span data-stu-id="afd90-155">bigint</span></span>|<span data-ttu-id="afd90-156">不限于64位表示形式的整数</span><span class="sxs-lookup"><span data-stu-id="afd90-156">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="afd90-157">I</span><span class="sxs-lookup"><span data-stu-id="afd90-157">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="afd90-158">decimal</span><span class="sxs-lookup"><span data-stu-id="afd90-158">decimal</span></span>|<span data-ttu-id="afd90-159">表示为固定点或有理数的小数</span><span class="sxs-lookup"><span data-stu-id="afd90-159">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="afd90-160">M 或 m</span><span class="sxs-lookup"><span data-stu-id="afd90-160">M or m</span></span>|<span data-ttu-id="afd90-161">`0.7833M` 或 `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="afd90-161">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="afd90-162">Char</span><span class="sxs-lookup"><span data-stu-id="afd90-162">Char</span></span>|<span data-ttu-id="afd90-163">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="afd90-163">Unicode character</span></span>|<span data-ttu-id="afd90-164">无</span><span class="sxs-lookup"><span data-stu-id="afd90-164">none</span></span>|<span data-ttu-id="afd90-165">`'a'` 或 `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="afd90-165">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="afd90-166">字符串</span><span class="sxs-lookup"><span data-stu-id="afd90-166">String</span></span>|<span data-ttu-id="afd90-167">Unicode 字符串</span><span class="sxs-lookup"><span data-stu-id="afd90-167">Unicode string</span></span>|<span data-ttu-id="afd90-168">无</span><span class="sxs-lookup"><span data-stu-id="afd90-168">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="afd90-169">或</span><span class="sxs-lookup"><span data-stu-id="afd90-169">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="afd90-170">或</span><span class="sxs-lookup"><span data-stu-id="afd90-170">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="afd90-171">或</span><span class="sxs-lookup"><span data-stu-id="afd90-171">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="afd90-172">另请参阅[字符串](Strings.md)。</span><span class="sxs-lookup"><span data-stu-id="afd90-172">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="afd90-173">byte</span><span class="sxs-lookup"><span data-stu-id="afd90-173">byte</span></span>|<span data-ttu-id="afd90-174">ASCII 字符</span><span class="sxs-lookup"><span data-stu-id="afd90-174">ASCII character</span></span>|<span data-ttu-id="afd90-175">B</span><span class="sxs-lookup"><span data-stu-id="afd90-175">B</span></span>|`'a'B`|
|<span data-ttu-id="afd90-176">byte[]</span><span class="sxs-lookup"><span data-stu-id="afd90-176">byte[]</span></span>|<span data-ttu-id="afd90-177">ASCII 字符串</span><span class="sxs-lookup"><span data-stu-id="afd90-177">ASCII string</span></span>|<span data-ttu-id="afd90-178">B</span><span class="sxs-lookup"><span data-stu-id="afd90-178">B</span></span>|`"text"B`|
|<span data-ttu-id="afd90-179">String 或 byte []</span><span class="sxs-lookup"><span data-stu-id="afd90-179">String or byte[]</span></span>|<span data-ttu-id="afd90-180">原义字符串</span><span class="sxs-lookup"><span data-stu-id="afd90-180">verbatim string</span></span>|<span data-ttu-id="afd90-181">@ prefix</span><span class="sxs-lookup"><span data-stu-id="afd90-181">@ prefix</span></span>|<span data-ttu-id="afd90-182">`@"\\server\share"` （Unicode）</span><span class="sxs-lookup"><span data-stu-id="afd90-182">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="afd90-183">`@"\\server\share"B` （ASCII）</span><span class="sxs-lookup"><span data-stu-id="afd90-183">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="afd90-184">命名文本</span><span class="sxs-lookup"><span data-stu-id="afd90-184">Named literals</span></span>

<span data-ttu-id="afd90-185">应为常量的值可以用[文本](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285)属性进行标记。</span><span class="sxs-lookup"><span data-stu-id="afd90-185">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="afd90-186">此属性的作用是使值编译为常量。</span><span class="sxs-lookup"><span data-stu-id="afd90-186">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="afd90-187">在模式匹配表达式中，以小写字符开头的标识符始终被视为要绑定的变量而不是文本，因此在定义文本时通常应使用首字母大写。</span><span class="sxs-lookup"><span data-stu-id="afd90-187">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="afd90-188">备注</span><span class="sxs-lookup"><span data-stu-id="afd90-188">Remarks</span></span>

<span data-ttu-id="afd90-189">Unicode 字符串可以包含通过使用 `\u` 后跟16位十六进制代码（0000-FFFF）或32编码（可通过使用 `\U` 后跟表示任何 Unicode 的32位十六进制代码）来指定的显式编码码位（00000000-0010FFFF 之间）。</span><span class="sxs-lookup"><span data-stu-id="afd90-189">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="afd90-190">不允许使用除 `|||` 以外的其他位运算符。</span><span class="sxs-lookup"><span data-stu-id="afd90-190">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="afd90-191">其他基中的整数</span><span class="sxs-lookup"><span data-stu-id="afd90-191">Integers in other bases</span></span>

<span data-ttu-id="afd90-192">还可以使用 `0x`、`0o` 或 `0b` 前缀分别以十六进制、八进制或二进制格式指定已签名的32位整数。</span><span class="sxs-lookup"><span data-stu-id="afd90-192">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="afd90-193">数值文本中的下划线</span><span class="sxs-lookup"><span data-stu-id="afd90-193">Underscores in numeric literals</span></span>

<span data-ttu-id="afd90-194">可以用下划线字符（`_`）分隔数字。</span><span class="sxs-lookup"><span data-stu-id="afd90-194">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="afd90-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="afd90-195">See also</span></span>

- [<span data-ttu-id="afd90-196">LiteralAttribute 类</span><span class="sxs-lookup"><span data-stu-id="afd90-196">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
