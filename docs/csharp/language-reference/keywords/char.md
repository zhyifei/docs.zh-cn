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
ms.openlocfilehash: 0b4f04a1ba6244373e36cc6a6188edabe33ec453
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424342"
---
# <a name="char-c-reference"></a><span data-ttu-id="be41e-102">char（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="be41e-102">char (C# Reference)</span></span>

<span data-ttu-id="be41e-103">`char` 关键字用于声明 <xref:System.Char?displayProperty=nameWithType> 结构的实例，.NET Framework 使用该结构来表示 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="be41e-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="be41e-104">`Char` 对象的值为 16 位的数字（序号）值。</span><span class="sxs-lookup"><span data-stu-id="be41e-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>

 <span data-ttu-id="be41e-105">Unicode 字符用于表示世界各地大多数的书面语言。</span><span class="sxs-lookup"><span data-stu-id="be41e-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>

|<span data-ttu-id="be41e-106">类型</span><span class="sxs-lookup"><span data-stu-id="be41e-106">Type</span></span>|<span data-ttu-id="be41e-107">范围</span><span class="sxs-lookup"><span data-stu-id="be41e-107">Range</span></span>|<span data-ttu-id="be41e-108">大小</span><span class="sxs-lookup"><span data-stu-id="be41e-108">Size</span></span>|<span data-ttu-id="be41e-109">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="be41e-109">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="be41e-110">U+0000 到 U+FFFF</span><span class="sxs-lookup"><span data-stu-id="be41e-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="be41e-111">Unicode 16 位字符</span><span class="sxs-lookup"><span data-stu-id="be41e-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="be41e-112">文本</span><span class="sxs-lookup"><span data-stu-id="be41e-112">Literals</span></span>

<span data-ttu-id="be41e-113">`char` 类型的常量可以编写为字符文本、十六进制转义序列或 Unicode 表示形式。</span><span class="sxs-lookup"><span data-stu-id="be41e-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="be41e-114">还可转换整型字符代码。</span><span class="sxs-lookup"><span data-stu-id="be41e-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="be41e-115">在下面的示例中，使用相同的字符 `X` 对四个 `char` 变量进行初始化：</span><span class="sxs-lookup"><span data-stu-id="be41e-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="be41e-116">转换</span><span class="sxs-lookup"><span data-stu-id="be41e-116">Conversions</span></span>

<span data-ttu-id="be41e-117">`char` 可隐式转换为 [ushort](../builtin-types/integral-numeric-types.md)、[int](../builtin-types/integral-numeric-types.md)、[uint](../builtin-types/integral-numeric-types.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md)。</span><span class="sxs-lookup"><span data-stu-id="be41e-117">A `char` can be implicitly converted to [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="be41e-118">但是无法将其他类型隐式转换为 `char` 类型。</span><span class="sxs-lookup"><span data-stu-id="be41e-118">However, there are no implicit conversions from other types to the `char` type.</span></span>

<span data-ttu-id="be41e-119"><xref:System.Char?displayProperty=nameWithType> 类型提供多种适用于 `char` 值的静态方法。</span><span class="sxs-lookup"><span data-stu-id="be41e-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="be41e-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="be41e-120">C# language specification</span></span>  

<span data-ttu-id="be41e-121">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[整型类型](~/_csharplang/spec/types.md#integral-types)。</span><span class="sxs-lookup"><span data-stu-id="be41e-121">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="be41e-122">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="be41e-122">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="be41e-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="be41e-123">See also</span></span>

- <xref:System.Char>
- [<span data-ttu-id="be41e-124">C# 参考</span><span class="sxs-lookup"><span data-stu-id="be41e-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="be41e-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="be41e-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="be41e-126">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="be41e-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="be41e-127">整型类型</span><span class="sxs-lookup"><span data-stu-id="be41e-127">Integral types</span></span>](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="be41e-128">内置类型表</span><span class="sxs-lookup"><span data-stu-id="be41e-128">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="be41e-129">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="be41e-129">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="be41e-130">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="be41e-130">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
- [<span data-ttu-id="be41e-131">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="be41e-131">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)
- [<span data-ttu-id="be41e-132">字符串</span><span class="sxs-lookup"><span data-stu-id="be41e-132">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
