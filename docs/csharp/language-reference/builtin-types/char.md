---
title: char 类型 - C# 引用
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 8727e47e13082e8550fb174c92139dfd5c17ec36
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134331"
---
# <a name="char-c-reference"></a><span data-ttu-id="179cc-102">char（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="179cc-102">char (C# reference)</span></span>

<span data-ttu-id="179cc-103">`char` 类型关键字是 .NET <xref:System.Char?displayProperty=nameWithType> 结构类型的别名，它表示 Unicode UTF-16 字符。</span><span class="sxs-lookup"><span data-stu-id="179cc-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="179cc-104">类型</span><span class="sxs-lookup"><span data-stu-id="179cc-104">Type</span></span>|<span data-ttu-id="179cc-105">范围</span><span class="sxs-lookup"><span data-stu-id="179cc-105">Range</span></span>|<span data-ttu-id="179cc-106">大小</span><span class="sxs-lookup"><span data-stu-id="179cc-106">Size</span></span>|<span data-ttu-id="179cc-107">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="179cc-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="179cc-108">U+0000 到 U+FFFF</span><span class="sxs-lookup"><span data-stu-id="179cc-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="179cc-109">16 位</span><span class="sxs-lookup"><span data-stu-id="179cc-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="179cc-110">`char` 类型的默认值为 `\0`，即 U+0000。</span><span class="sxs-lookup"><span data-stu-id="179cc-110">The default value of the `char` type is `\0`, that is, U+0000.</span></span>

<span data-ttu-id="179cc-111">[字符串](reference-types.md#the-string-type)类型将文本表示为 `char` 值的序列。</span><span class="sxs-lookup"><span data-stu-id="179cc-111">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="179cc-112">文本</span><span class="sxs-lookup"><span data-stu-id="179cc-112">Literals</span></span>

<span data-ttu-id="179cc-113">可以使用以下命令指定 `char` 值：</span><span class="sxs-lookup"><span data-stu-id="179cc-113">You can specify a `char` value with:</span></span>

- <span data-ttu-id="179cc-114">字符文本。</span><span class="sxs-lookup"><span data-stu-id="179cc-114">a character literal.</span></span>
- <span data-ttu-id="179cc-115">Unicode 转义序列，它是 `\u` 后跟字符代码的十六进制表示形式（四个符号）。</span><span class="sxs-lookup"><span data-stu-id="179cc-115">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="179cc-116">十六进制转义序列，它是 `\x` 后跟字符代码的十六进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="179cc-116">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](snippets/CharType.cs#Literals)]

<span data-ttu-id="179cc-117">如前面的示例所示，你还可以将字符代码的值转换为相应的 `char` 值。</span><span class="sxs-lookup"><span data-stu-id="179cc-117">As the preceding example shows, you also can cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="179cc-118">对于 Unicode 转义序列，必须指定全部四位十六进制值。</span><span class="sxs-lookup"><span data-stu-id="179cc-118">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="179cc-119">也就是说，`\u006A` 是一个有效的转义序列，而 `\u06A` 和 `\u6A` 是无效的。</span><span class="sxs-lookup"><span data-stu-id="179cc-119">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="179cc-120">对于十六进制转义序列，可以省略前导零。</span><span class="sxs-lookup"><span data-stu-id="179cc-120">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="179cc-121">也就是说，`\x006A`、`\x06A` 和 `\x6A` 转义序列是有效的，并且对应于同一个字符。</span><span class="sxs-lookup"><span data-stu-id="179cc-121">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="179cc-122">转换</span><span class="sxs-lookup"><span data-stu-id="179cc-122">Conversions</span></span>

<span data-ttu-id="179cc-123">`char` 类型可隐式转换为以下[整型](integral-numeric-types.md)类型：`ushort`、`int`、`uint`、`long` 和 `ulong`。</span><span class="sxs-lookup"><span data-stu-id="179cc-123">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="179cc-124">它也可以隐式转换为内置[浮点](floating-point-numeric-types.md)数值类型：`float`、`double` 和 `decimal`。</span><span class="sxs-lookup"><span data-stu-id="179cc-124">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="179cc-125">它可以显式转换为 `sbyte`、`byte` 和 `short` 整型类型。</span><span class="sxs-lookup"><span data-stu-id="179cc-125">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="179cc-126">无法将其他类型隐式转换为 `char` 类型。</span><span class="sxs-lookup"><span data-stu-id="179cc-126">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="179cc-127">但是，任何[整型](integral-numeric-types.md)或[浮点](floating-point-numeric-types.md)数值类型都可显式转换为 `char`。</span><span class="sxs-lookup"><span data-stu-id="179cc-127">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="179cc-128">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="179cc-128">C# language specification</span></span>

<span data-ttu-id="179cc-129">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[整型类型](~/_csharplang/spec/types.md#integral-types)部分。</span><span class="sxs-lookup"><span data-stu-id="179cc-129">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="179cc-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="179cc-130">See also</span></span>

- [<span data-ttu-id="179cc-131">C# 参考</span><span class="sxs-lookup"><span data-stu-id="179cc-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="179cc-132">值类型</span><span class="sxs-lookup"><span data-stu-id="179cc-132">Value types</span></span>](value-types.md)
- [<span data-ttu-id="179cc-133">字符串</span><span class="sxs-lookup"><span data-stu-id="179cc-133">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
- [<span data-ttu-id="179cc-134">.NET 中的字符编码</span><span class="sxs-lookup"><span data-stu-id="179cc-134">Character encoding in .NET</span></span>](../../../standard/base-types/character-encoding-introduction.md)
