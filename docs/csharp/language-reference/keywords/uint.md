---
title: uint 关键字 - C# 参考
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.openlocfilehash: 9a60460f67f9b6cf0b57d40ebf2789536e870d75
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633150"
---
# <a name="uint-c-reference"></a><span data-ttu-id="15c25-102">uint（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="15c25-102">uint (C# Reference)</span></span>

<span data-ttu-id="15c25-103">`uint` 关键字表示一种整型类型，该类型根据下表显示的大小和范围存储值。</span><span class="sxs-lookup"><span data-stu-id="15c25-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="15c25-104">类型</span><span class="sxs-lookup"><span data-stu-id="15c25-104">Type</span></span>|<span data-ttu-id="15c25-105">范围</span><span class="sxs-lookup"><span data-stu-id="15c25-105">Range</span></span>|<span data-ttu-id="15c25-106">大小</span><span class="sxs-lookup"><span data-stu-id="15c25-106">Size</span></span>|<span data-ttu-id="15c25-107">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="15c25-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`uint`|<span data-ttu-id="15c25-108">0 到 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="15c25-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="15c25-109">无符号的 32 位整数</span><span class="sxs-lookup"><span data-stu-id="15c25-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|

<span data-ttu-id="15c25-110">**请注意**：`uint` 类型不符合 CLS。</span><span class="sxs-lookup"><span data-stu-id="15c25-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="15c25-111">请尽可能使用 `int`。</span><span class="sxs-lookup"><span data-stu-id="15c25-111">Use `int` whenever possible.</span></span>

## <a name="literals"></a><span data-ttu-id="15c25-112">文本</span><span class="sxs-lookup"><span data-stu-id="15c25-112">Literals</span></span>

<span data-ttu-id="15c25-113">可以通过为其分配十进制文本、十六进制文本或（从 C# 7.0 开始）二进制文本来声明和初始化 `uint` 变量。</span><span class="sxs-lookup"><span data-stu-id="15c25-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="15c25-114">如果整数文本在 `uint` 范围之外（即，如果它小于 <xref:System.UInt32.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="15c25-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="15c25-115">在以下示例中，表示为十进制、十六进制和二进制文本且等于 3,000,000,000 的整数被分配给 `uint` 值。</span><span class="sxs-lookup"><span data-stu-id="15c25-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]

> [!NOTE]
> <span data-ttu-id="15c25-116">使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。</span><span class="sxs-lookup"><span data-stu-id="15c25-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="15c25-117">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="15c25-117">Decimal literals have no prefix.</span></span>

<span data-ttu-id="15c25-118">从 C# 7.0 开始，添加了一些功能以增强可读性：</span><span class="sxs-lookup"><span data-stu-id="15c25-118">Starting with C# 7.0, a couple of features have been added to enhance readability:</span></span>

- <span data-ttu-id="15c25-119">C# 7.0 允许将下划线字符 (`_`) 用作数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="15c25-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="15c25-120">C# 7.2 允许将 `_` 用作二进制或十六进制文本的数字分隔符，位于前缀之后。</span><span class="sxs-lookup"><span data-stu-id="15c25-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="15c25-121">十进制文本不能够有前导下划线。</span><span class="sxs-lookup"><span data-stu-id="15c25-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="15c25-122">下面是一些示例。</span><span class="sxs-lookup"><span data-stu-id="15c25-122">Some examples are shown below.</span></span>

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]

<span data-ttu-id="15c25-123">整数文本还可包含表示类型的后缀。</span><span class="sxs-lookup"><span data-stu-id="15c25-123">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="15c25-124">后缀 `U` 或“u”表示 `uint` 或 `ulong`，具体取决于文本的数字值。</span><span class="sxs-lookup"><span data-stu-id="15c25-124">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="15c25-125">以下示例使用 `u` 后缀来表示这两种类型的无符号整数。</span><span class="sxs-lookup"><span data-stu-id="15c25-125">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="15c25-126">请注意第一个文本为 `uint`，因为其值小于 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>，而第二个文本为 `ulong`，因为其值大于 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="15c25-126">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>

[!code-csharp[usuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]

<span data-ttu-id="15c25-127">如果整数文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：</span><span class="sxs-lookup"><span data-stu-id="15c25-127">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. [<span data-ttu-id="15c25-128">int</span><span class="sxs-lookup"><span data-stu-id="15c25-128">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="15c25-129">long</span><span class="sxs-lookup"><span data-stu-id="15c25-129">long</span></span>](long.md)
4. [<span data-ttu-id="15c25-130">ulong</span><span class="sxs-lookup"><span data-stu-id="15c25-130">ulong</span></span>](ulong.md)

## <a name="conversions"></a><span data-ttu-id="15c25-131">转换</span><span class="sxs-lookup"><span data-stu-id="15c25-131">Conversions</span></span>

<span data-ttu-id="15c25-132">存在从 `uint` 到 [long](long.md)、[ulong](ulong.md)、[float](float.md)、[double](double.md) 或 [decimal](decimal.md) 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="15c25-132">There is a predefined implicit conversion from `uint` to [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span> <span data-ttu-id="15c25-133">例如:</span><span class="sxs-lookup"><span data-stu-id="15c25-133">For example:</span></span>

```csharp
float myFloat = 4294967290;   // OK: implicit conversion to float
```

<span data-ttu-id="15c25-134">存在从 [byte](byte.md)、[ushort](ushort.md) 或 [char](char.md) 到 `uint` 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="15c25-134">There is a predefined implicit conversion from [byte](byte.md), [ushort](ushort.md), or [char](char.md) to `uint`.</span></span> <span data-ttu-id="15c25-135">否则必须使用转换。</span><span class="sxs-lookup"><span data-stu-id="15c25-135">Otherwise you must use a cast.</span></span> <span data-ttu-id="15c25-136">例如，如果不使用转换，以下赋值语句会生成编译错误：</span><span class="sxs-lookup"><span data-stu-id="15c25-136">For example, the following assignment statement will produce a compilation error without a cast:</span></span>

```csharp
long aLong = 22;
// Error -- no implicit conversion from long:
uint uInt1 = aLong;
// OK -- explicit conversion:
uint uInt2 = (uint)aLong;
```

<span data-ttu-id="15c25-137">另请注意，不存在从浮点类型到 `uint` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="15c25-137">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="15c25-138">例如，除非使用显式强制转换，否则以下语句将生成编译器错误：</span><span class="sxs-lookup"><span data-stu-id="15c25-138">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error -- no implicit conversion from double:
uint x = 3.0;
// OK -- explicit conversion:
uint y = (uint)3.0;
```

<span data-ttu-id="15c25-139">有关兼用浮点类型和整型类型的算术表达式的信息，请参阅 [float](float.md) 和 [double](double.md)。</span><span class="sxs-lookup"><span data-stu-id="15c25-139">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="15c25-140">有关隐式数值转换规则的详细信息，请参阅[隐式数值转换表](implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="15c25-140">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="15c25-141">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="15c25-141">C# language specification</span></span>

<span data-ttu-id="15c25-142">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[整型类型](~/_csharplang/spec/types.md#integral-types)。</span><span class="sxs-lookup"><span data-stu-id="15c25-142">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="15c25-143">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="15c25-143">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="15c25-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="15c25-144">See also</span></span>

- <xref:System.UInt32>
- [<span data-ttu-id="15c25-145">C# 参考</span><span class="sxs-lookup"><span data-stu-id="15c25-145">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="15c25-146">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="15c25-146">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="15c25-147">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="15c25-147">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="15c25-148">整型表</span><span class="sxs-lookup"><span data-stu-id="15c25-148">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="15c25-149">内置类型表</span><span class="sxs-lookup"><span data-stu-id="15c25-149">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="15c25-150">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="15c25-150">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="15c25-151">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="15c25-151">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
