---
title: char 关键字 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 754c04bfc3b4090906420d55d55e51606b72f187
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605949"
---
# <a name="char-c-reference"></a><span data-ttu-id="305d4-102">char（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="305d4-102">char (C# Reference)</span></span>

<span data-ttu-id="305d4-103">`char` 关键字用于声明 <xref:System.Char?displayProperty=nameWithType> 结构的实例，.NET Framework 使用该结构来表示 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="305d4-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="305d4-104">`Char` 对象的值为 16 位的数字（序号）值。</span><span class="sxs-lookup"><span data-stu-id="305d4-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>

 <span data-ttu-id="305d4-105">Unicode 字符用于表示世界各地大多数的书面语言。</span><span class="sxs-lookup"><span data-stu-id="305d4-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>

|<span data-ttu-id="305d4-106">类型</span><span class="sxs-lookup"><span data-stu-id="305d4-106">Type</span></span>|<span data-ttu-id="305d4-107">范围</span><span class="sxs-lookup"><span data-stu-id="305d4-107">Range</span></span>|<span data-ttu-id="305d4-108">大小</span><span class="sxs-lookup"><span data-stu-id="305d4-108">Size</span></span>|<span data-ttu-id="305d4-109">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="305d4-109">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="305d4-110">U+0000 到 U+FFFF</span><span class="sxs-lookup"><span data-stu-id="305d4-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="305d4-111">Unicode 16 位字符</span><span class="sxs-lookup"><span data-stu-id="305d4-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="305d4-112">文本</span><span class="sxs-lookup"><span data-stu-id="305d4-112">Literals</span></span>

<span data-ttu-id="305d4-113">`char` 类型的常量可以编写为字符文本、十六进制转义序列或 Unicode 表示形式。</span><span class="sxs-lookup"><span data-stu-id="305d4-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="305d4-114">还可转换整型字符代码。</span><span class="sxs-lookup"><span data-stu-id="305d4-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="305d4-115">在下面的示例中，使用相同的字符 `X` 对四个 `char` 变量进行初始化：</span><span class="sxs-lookup"><span data-stu-id="305d4-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="305d4-116">转换</span><span class="sxs-lookup"><span data-stu-id="305d4-116">Conversions</span></span>

<span data-ttu-id="305d4-117">`char` 可隐式转换为 [ushort](../builtin-types/integral-numeric-types.md)、[int](../builtin-types/integral-numeric-types.md)、[uint](../builtin-types/integral-numeric-types.md)、[double](../builtin-types/floating-point-numeric-types.md) 或 [decimal](../builtin-types/floating-point-numeric-types.md)。</span><span class="sxs-lookup"><span data-stu-id="305d4-117">A `char` can be implicitly converted to [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md), or [decimal](../builtin-types/floating-point-numeric-types.md).</span></span> <span data-ttu-id="305d4-118">但是无法将其他类型隐式转换为 `char` 类型。</span><span class="sxs-lookup"><span data-stu-id="305d4-118">However, there are no implicit conversions from other types to the `char` type.</span></span>

<span data-ttu-id="305d4-119"><xref:System.Char?displayProperty=nameWithType> 类型提供多种适用于 `char` 值的静态方法。</span><span class="sxs-lookup"><span data-stu-id="305d4-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="305d4-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="305d4-120">C# language specification</span></span>  

<span data-ttu-id="305d4-121">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[整型类型](~/_csharplang/spec/types.md#integral-types)。</span><span class="sxs-lookup"><span data-stu-id="305d4-121">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="305d4-122">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="305d4-122">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="305d4-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="305d4-123">See also</span></span>

- <xref:System.Char>
- [<span data-ttu-id="305d4-124">C# 参考</span><span class="sxs-lookup"><span data-stu-id="305d4-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="305d4-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="305d4-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="305d4-126">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="305d4-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="305d4-127">整型类型</span><span class="sxs-lookup"><span data-stu-id="305d4-127">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="305d4-128">内置类型表</span><span class="sxs-lookup"><span data-stu-id="305d4-128">Built-In Types Table</span></span>](./built-in-types-table.md)
- [<span data-ttu-id="305d4-129">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="305d4-129">Implicit Numeric Conversions Table</span></span>](./implicit-numeric-conversions-table.md)
- [<span data-ttu-id="305d4-130">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="305d4-130">Explicit Numeric Conversions Table</span></span>](./explicit-numeric-conversions-table.md)
- [<span data-ttu-id="305d4-131">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="305d4-131">Nullable Types</span></span>](../../programming-guide/nullable-types/index.md)
- [<span data-ttu-id="305d4-132">字符串</span><span class="sxs-lookup"><span data-stu-id="305d4-132">Strings</span></span>](../../programming-guide/strings/index.md)
