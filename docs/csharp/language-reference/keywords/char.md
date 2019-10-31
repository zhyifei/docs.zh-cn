---
title: char 关键字 - C# 参考
ms.custom: seodec18
ms.date: 10/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 1b9f8d1bb205a6cbfe521830a11bd8878ccde991
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771799"
---
# <a name="char-c-reference"></a><span data-ttu-id="49d19-102">char（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="49d19-102">char (C# reference)</span></span>

<span data-ttu-id="49d19-103">`char` 类型关键字是 .NET <xref:System.Char?displayProperty=nameWithType> 结构类型的别名，它表示 Unicode UTF-16 字符：</span><span class="sxs-lookup"><span data-stu-id="49d19-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character:</span></span>

|<span data-ttu-id="49d19-104">类型</span><span class="sxs-lookup"><span data-stu-id="49d19-104">Type</span></span>|<span data-ttu-id="49d19-105">范围</span><span class="sxs-lookup"><span data-stu-id="49d19-105">Range</span></span>|<span data-ttu-id="49d19-106">大小</span><span class="sxs-lookup"><span data-stu-id="49d19-106">Size</span></span>|<span data-ttu-id="49d19-107">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="49d19-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="49d19-108">U+0000 到 U+FFFF</span><span class="sxs-lookup"><span data-stu-id="49d19-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="49d19-109">16 位</span><span class="sxs-lookup"><span data-stu-id="49d19-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="49d19-110">文本</span><span class="sxs-lookup"><span data-stu-id="49d19-110">Literals</span></span>

<span data-ttu-id="49d19-111">`char` 类型的常量可以编写为字符文本、十六进制转义序列或 Unicode 表示形式。</span><span class="sxs-lookup"><span data-stu-id="49d19-111">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="49d19-112">也可以将整型字符代码强制转换为相应的 `char` 值。</span><span class="sxs-lookup"><span data-stu-id="49d19-112">You can also cast an integral character code into the corresponding `char` value.</span></span> <span data-ttu-id="49d19-113">在下面的示例中，使用相同的字符 `X` 对 `char` 数组的四个元素进行初始化：</span><span class="sxs-lookup"><span data-stu-id="49d19-113">In the following example, the four elements of an array of `char` are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="49d19-114">转换</span><span class="sxs-lookup"><span data-stu-id="49d19-114">Conversions</span></span>

<span data-ttu-id="49d19-115">`char` 类型可隐式转换为以下[整型](../builtin-types/integral-numeric-types.md)类型：`ushort`、`int`、`uint`、`long` 和 `ulong`。</span><span class="sxs-lookup"><span data-stu-id="49d19-115">The `char` type is implicitly convertible to the following [integral](../builtin-types/integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="49d19-116">它也可以隐式转换为内置[浮点](../builtin-types/floating-point-numeric-types.md)数值类型：`float`、`double` 和 `decimal`。</span><span class="sxs-lookup"><span data-stu-id="49d19-116">It's also implicitly convertible to the built-in [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="49d19-117">它可以显式转换为 `sbyte`、`byte` 和 `short` 整型类型。</span><span class="sxs-lookup"><span data-stu-id="49d19-117">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="49d19-118">无法将其他类型隐式转换为 `char` 类型。</span><span class="sxs-lookup"><span data-stu-id="49d19-118">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="49d19-119">但是，任何[整型](../builtin-types/integral-numeric-types.md)或[浮点](../builtin-types/floating-point-numeric-types.md)数值类型都可显式转换为 `char`。</span><span class="sxs-lookup"><span data-stu-id="49d19-119">However, any [integral](../builtin-types/integral-numeric-types.md) or [floating-point](../builtin-types/floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="49d19-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="49d19-120">C# language specification</span></span>

<span data-ttu-id="49d19-121">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[整型类型](~/_csharplang/spec/types.md#integral-types)部分。</span><span class="sxs-lookup"><span data-stu-id="49d19-121">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="49d19-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="49d19-122">See also</span></span>

- [<span data-ttu-id="49d19-123">C# 参考</span><span class="sxs-lookup"><span data-stu-id="49d19-123">C# reference</span></span>](../index.md)
- [<span data-ttu-id="49d19-124">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="49d19-124">C# keywords</span></span>](./index.md)
- [<span data-ttu-id="49d19-125">内置类型表</span><span class="sxs-lookup"><span data-stu-id="49d19-125">Built-in types table</span></span>](./built-in-types-table.md)
- [<span data-ttu-id="49d19-126">字符串</span><span class="sxs-lookup"><span data-stu-id="49d19-126">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Char?displayProperty=nameWithType>
