---
title: 文本 (F#)
description: '了解有关 F # 编程语言中的文本类型。'
ms.date: 05/16/2016
ms.openlocfilehash: e6d34acd928edce8447c793105b08085ab0757b9
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087620"
---
# <a name="literals"></a><span data-ttu-id="3ba29-103">文本</span><span class="sxs-lookup"><span data-stu-id="3ba29-103">Literals</span></span>

> [!NOTE]
<span data-ttu-id="3ba29-104">在本文中的 API 参考链接将转至 MSDN （适用于暂时）。</span><span class="sxs-lookup"><span data-stu-id="3ba29-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="3ba29-105">本主题提供了演示如何指定 F # 中的文本类型的表。</span><span class="sxs-lookup"><span data-stu-id="3ba29-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="3ba29-106">文本类型</span><span class="sxs-lookup"><span data-stu-id="3ba29-106">Literal Types</span></span>

<span data-ttu-id="3ba29-107">下表显示 F # 中的文本的类型。</span><span class="sxs-lookup"><span data-stu-id="3ba29-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="3ba29-108">表示以十六进制表示法表示的数字的字符不区分大小写;标识类型的字符是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="3ba29-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="3ba29-109">类型</span><span class="sxs-lookup"><span data-stu-id="3ba29-109">Type</span></span>|<span data-ttu-id="3ba29-110">描述</span><span class="sxs-lookup"><span data-stu-id="3ba29-110">Description</span></span>|<span data-ttu-id="3ba29-111">后缀或前缀</span><span class="sxs-lookup"><span data-stu-id="3ba29-111">Suffix or prefix</span></span>|<span data-ttu-id="3ba29-112">示例</span><span class="sxs-lookup"><span data-stu-id="3ba29-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="3ba29-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="3ba29-113">sbyte</span></span>|<span data-ttu-id="3ba29-114">8 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="3ba29-114">signed 8-bit integer</span></span>|<span data-ttu-id="3ba29-115">y</span><span class="sxs-lookup"><span data-stu-id="3ba29-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="3ba29-116">byte</span><span class="sxs-lookup"><span data-stu-id="3ba29-116">byte</span></span>|<span data-ttu-id="3ba29-117">无符号的 8 位自然数</span><span class="sxs-lookup"><span data-stu-id="3ba29-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="3ba29-118">uy</span><span class="sxs-lookup"><span data-stu-id="3ba29-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="3ba29-119">int16</span><span class="sxs-lookup"><span data-stu-id="3ba29-119">int16</span></span>|<span data-ttu-id="3ba29-120">16 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="3ba29-120">signed 16-bit integer</span></span>|<span data-ttu-id="3ba29-121">秒</span><span class="sxs-lookup"><span data-stu-id="3ba29-121">s</span></span>|`86s`|
|<span data-ttu-id="3ba29-122">uint16</span><span class="sxs-lookup"><span data-stu-id="3ba29-122">uint16</span></span>|<span data-ttu-id="3ba29-123">无符号的 16 位自然数</span><span class="sxs-lookup"><span data-stu-id="3ba29-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="3ba29-124">us</span><span class="sxs-lookup"><span data-stu-id="3ba29-124">us</span></span>|`86us`|
|<span data-ttu-id="3ba29-125">int</span><span class="sxs-lookup"><span data-stu-id="3ba29-125">int</span></span><br /><br /><span data-ttu-id="3ba29-126">int32</span><span class="sxs-lookup"><span data-stu-id="3ba29-126">int32</span></span>|<span data-ttu-id="3ba29-127">32 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="3ba29-127">signed 32-bit integer</span></span>|<span data-ttu-id="3ba29-128">l 或 none</span><span class="sxs-lookup"><span data-stu-id="3ba29-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="3ba29-129">uint</span><span class="sxs-lookup"><span data-stu-id="3ba29-129">uint</span></span><br /><br /><span data-ttu-id="3ba29-130">uint32</span><span class="sxs-lookup"><span data-stu-id="3ba29-130">uint32</span></span>|<span data-ttu-id="3ba29-131">无符号的 32 位自然数</span><span class="sxs-lookup"><span data-stu-id="3ba29-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="3ba29-132">u 或 ul</span><span class="sxs-lookup"><span data-stu-id="3ba29-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="3ba29-133">unativeint</span><span class="sxs-lookup"><span data-stu-id="3ba29-133">unativeint</span></span>|<span data-ttu-id="3ba29-134">无符号自然数形式的本机指针</span><span class="sxs-lookup"><span data-stu-id="3ba29-134">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="3ba29-135">取消</span><span class="sxs-lookup"><span data-stu-id="3ba29-135">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="3ba29-136">int64</span><span class="sxs-lookup"><span data-stu-id="3ba29-136">int64</span></span>|<span data-ttu-id="3ba29-137">64 位有符号整数</span><span class="sxs-lookup"><span data-stu-id="3ba29-137">signed 64-bit integer</span></span>|<span data-ttu-id="3ba29-138">L</span><span class="sxs-lookup"><span data-stu-id="3ba29-138">L</span></span>|`86L`|
|<span data-ttu-id="3ba29-139">uint64</span><span class="sxs-lookup"><span data-stu-id="3ba29-139">uint64</span></span>|<span data-ttu-id="3ba29-140">无符号的 64 位自然数</span><span class="sxs-lookup"><span data-stu-id="3ba29-140">unsigned 64-bit natural number</span></span>|<span data-ttu-id="3ba29-141">UL</span><span class="sxs-lookup"><span data-stu-id="3ba29-141">UL</span></span>|`86UL`|
|<span data-ttu-id="3ba29-142">单一的 float32</span><span class="sxs-lookup"><span data-stu-id="3ba29-142">single, float32</span></span>|<span data-ttu-id="3ba29-143">32 位浮点数</span><span class="sxs-lookup"><span data-stu-id="3ba29-143">32-bit floating point number</span></span>|<span data-ttu-id="3ba29-144">F 或 f</span><span class="sxs-lookup"><span data-stu-id="3ba29-144">F or f</span></span>|<span data-ttu-id="3ba29-145">`4.14F` 或 `4.14f`</span><span class="sxs-lookup"><span data-stu-id="3ba29-145">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="3ba29-146">lf</span><span class="sxs-lookup"><span data-stu-id="3ba29-146">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="3ba29-147">float;双精度</span><span class="sxs-lookup"><span data-stu-id="3ba29-147">float; double</span></span>|<span data-ttu-id="3ba29-148">64 位浮点数</span><span class="sxs-lookup"><span data-stu-id="3ba29-148">64-bit floating point number</span></span>|<span data-ttu-id="3ba29-149">无</span><span class="sxs-lookup"><span data-stu-id="3ba29-149">none</span></span>|<span data-ttu-id="3ba29-150">`4.14` 或 `2.3E+32` 或 `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="3ba29-150">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="3ba29-151">LF</span><span class="sxs-lookup"><span data-stu-id="3ba29-151">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="3ba29-152">bigint</span><span class="sxs-lookup"><span data-stu-id="3ba29-152">bigint</span></span>|<span data-ttu-id="3ba29-153">不限制为 64 位表示形式的整数</span><span class="sxs-lookup"><span data-stu-id="3ba29-153">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="3ba29-154">I</span><span class="sxs-lookup"><span data-stu-id="3ba29-154">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="3ba29-155">decimal</span><span class="sxs-lookup"><span data-stu-id="3ba29-155">decimal</span></span>|<span data-ttu-id="3ba29-156">表示为固定的点或有理数的小数</span><span class="sxs-lookup"><span data-stu-id="3ba29-156">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="3ba29-157">M 或 m</span><span class="sxs-lookup"><span data-stu-id="3ba29-157">M or m</span></span>|<span data-ttu-id="3ba29-158">`0.7833M` 或 `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="3ba29-158">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="3ba29-159">Char</span><span class="sxs-lookup"><span data-stu-id="3ba29-159">Char</span></span>|<span data-ttu-id="3ba29-160">Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="3ba29-160">Unicode character</span></span>|<span data-ttu-id="3ba29-161">无</span><span class="sxs-lookup"><span data-stu-id="3ba29-161">none</span></span>|`'a'`|
|<span data-ttu-id="3ba29-162">String</span><span class="sxs-lookup"><span data-stu-id="3ba29-162">String</span></span>|<span data-ttu-id="3ba29-163">Unicode 字符串</span><span class="sxs-lookup"><span data-stu-id="3ba29-163">Unicode string</span></span>|<span data-ttu-id="3ba29-164">无</span><span class="sxs-lookup"><span data-stu-id="3ba29-164">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="3ba29-165">或</span><span class="sxs-lookup"><span data-stu-id="3ba29-165">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="3ba29-166">或</span><span class="sxs-lookup"><span data-stu-id="3ba29-166">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="3ba29-167">或</span><span class="sxs-lookup"><span data-stu-id="3ba29-167">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="3ba29-168">另请参阅[字符串](Strings.md)。</span><span class="sxs-lookup"><span data-stu-id="3ba29-168">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="3ba29-169">byte</span><span class="sxs-lookup"><span data-stu-id="3ba29-169">byte</span></span>|<span data-ttu-id="3ba29-170">ASCII 字符</span><span class="sxs-lookup"><span data-stu-id="3ba29-170">ASCII character</span></span>|<span data-ttu-id="3ba29-171">B</span><span class="sxs-lookup"><span data-stu-id="3ba29-171">B</span></span>|`'a'B`|
|<span data-ttu-id="3ba29-172">byte[]</span><span class="sxs-lookup"><span data-stu-id="3ba29-172">byte[]</span></span>|<span data-ttu-id="3ba29-173">ASCII 字符串</span><span class="sxs-lookup"><span data-stu-id="3ba29-173">ASCII string</span></span>|<span data-ttu-id="3ba29-174">B</span><span class="sxs-lookup"><span data-stu-id="3ba29-174">B</span></span>|`"text"B`|
|<span data-ttu-id="3ba29-175">字符串或 byte]</span><span class="sxs-lookup"><span data-stu-id="3ba29-175">String or byte[]</span></span>|<span data-ttu-id="3ba29-176">逐字字符串</span><span class="sxs-lookup"><span data-stu-id="3ba29-176">verbatim string</span></span>|<span data-ttu-id="3ba29-177">@ 前缀</span><span class="sxs-lookup"><span data-stu-id="3ba29-177">@ prefix</span></span>|<span data-ttu-id="3ba29-178">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="3ba29-178">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="3ba29-179">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="3ba29-179">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="3ba29-180">备注</span><span class="sxs-lookup"><span data-stu-id="3ba29-180">Remarks</span></span>

<span data-ttu-id="3ba29-181">Unicode 字符串可包含可以通过使用指定的显式编码`\u`跟 16 位十六进制代码或可以通过使用指定的 UTF-32 编码`\U`跟表示 Unicode 的 32 位十六进制代码代理项对。</span><span class="sxs-lookup"><span data-stu-id="3ba29-181">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="3ba29-182">自 F # 3.1，您可以使用`+`符号合并字符串文本。</span><span class="sxs-lookup"><span data-stu-id="3ba29-182">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="3ba29-183">你还可以使用按位或 (`|||`) 运算符来组合枚举标志。</span><span class="sxs-lookup"><span data-stu-id="3ba29-183">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="3ba29-184">例如，下面的代码是在 F # 3.1 中合法的：</span><span class="sxs-lookup"><span data-stu-id="3ba29-184">For example, the following code is legal in F# 3.1:</span></span>

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

<span data-ttu-id="3ba29-185">不允许使用其他按位运算符。</span><span class="sxs-lookup"><span data-stu-id="3ba29-185">The use of other bitwise operators isn't allowed.</span></span>

## <a name="named-literals"></a><span data-ttu-id="3ba29-186">指定的文字</span><span class="sxs-lookup"><span data-stu-id="3ba29-186">Named Literals</span></span>

<span data-ttu-id="3ba29-187">可以使用标记值都应是常量[文字](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285)属性。</span><span class="sxs-lookup"><span data-stu-id="3ba29-187">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="3ba29-188">此属性具有导致被编译为一个常量值的效果。</span><span class="sxs-lookup"><span data-stu-id="3ba29-188">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="3ba29-189">在模式匹配表达式中，小写字母开头的标识符始终被当作变量绑定，而不是文字，因此通常应使用首字母大写定义文字。</span><span class="sxs-lookup"><span data-stu-id="3ba29-189">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="3ba29-190">在其他基数的整数</span><span class="sxs-lookup"><span data-stu-id="3ba29-190">Integers In Other Bases</span></span>

<span data-ttu-id="3ba29-191">有符号的 32 位整数，还可以指定在使用十六进制、 八进制或二进制`0x`，`0o`或`0b`分别前缀。</span><span class="sxs-lookup"><span data-stu-id="3ba29-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="3ba29-192">数值文字中的下划线</span><span class="sxs-lookup"><span data-stu-id="3ba29-192">Underscores in Numeric Literals</span></span>

<span data-ttu-id="3ba29-193">从 F # 4.1 开始，你可以分隔数字使用下划线字符 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="3ba29-193">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="3ba29-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ba29-194">See also</span></span>

- [<span data-ttu-id="3ba29-195">Core.LiteralAttribute 类</span><span class="sxs-lookup"><span data-stu-id="3ba29-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
