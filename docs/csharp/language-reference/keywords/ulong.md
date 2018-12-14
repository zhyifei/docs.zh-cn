---
title: ulong 关键字（C# 引用）
ms.date: 03/14/2017
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
ms.openlocfilehash: d0c7df4ebda13a59e51e9599699f6abf4bbf1d71
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143423"
---
# <a name="ulong-c-reference"></a><span data-ttu-id="7d214-102">ulong（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="7d214-102">ulong (C# Reference)</span></span>

<span data-ttu-id="7d214-103">`ulong` 关键字表示一种整型类型，该类型根据下表显示的大小和范围存储值。</span><span class="sxs-lookup"><span data-stu-id="7d214-103">The `ulong` keyword denotes an integral type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="7d214-104">类型</span><span class="sxs-lookup"><span data-stu-id="7d214-104">Type</span></span>|<span data-ttu-id="7d214-105">范围</span><span class="sxs-lookup"><span data-stu-id="7d214-105">Range</span></span>|<span data-ttu-id="7d214-106">大小</span><span class="sxs-lookup"><span data-stu-id="7d214-106">Size</span></span>|<span data-ttu-id="7d214-107">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="7d214-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`ulong`|<span data-ttu-id="7d214-108">0 到 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="7d214-108">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="7d214-109">无符号 64 位整数</span><span class="sxs-lookup"><span data-stu-id="7d214-109">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="7d214-110">文本</span><span class="sxs-lookup"><span data-stu-id="7d214-110">Literals</span></span>

<span data-ttu-id="7d214-111">可以通过为其分配十进制文本、十六进制文本或（从 C# 7.0 开始）二进制文本来声明和初始化 `ulong` 变量。</span><span class="sxs-lookup"><span data-stu-id="7d214-111">You can declare and initialize a `ulong` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="7d214-112">如果整数文本在 `ulong` 范围之外（即，如果它小于 <xref:System.UInt64.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="7d214-112">If the integer literal is outside the range of `ulong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="7d214-113">在以下示例中，表示为十进制、十六进制和二进制文本且等于 7,934,076,125 的整数被分配给 `ulong` 值。</span><span class="sxs-lookup"><span data-stu-id="7d214-113">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ulong` values.</span></span>

[!code-csharp[ulong](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]

> [!NOTE]
> <span data-ttu-id="7d214-114">使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。</span><span class="sxs-lookup"><span data-stu-id="7d214-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="7d214-115">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="7d214-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="7d214-116">从 C# 7.0 开始，添加了一些功能以增强可读性：</span><span class="sxs-lookup"><span data-stu-id="7d214-116">Starting with C# 7.0, a couple of features have been added to enhance readability:</span></span>

- <span data-ttu-id="7d214-117">C# 7.0 允许将下划线字符 (`_`) 用作数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="7d214-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="7d214-118">C# 7.2 允许将 `_` 用作二进制或十六进制文本的数字分隔符，位于前缀之后。</span><span class="sxs-lookup"><span data-stu-id="7d214-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="7d214-119">十进制文本不能够有前导下划线。</span><span class="sxs-lookup"><span data-stu-id="7d214-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="7d214-120">下面是一些示例。</span><span class="sxs-lookup"><span data-stu-id="7d214-120">Some examples are shown below.</span></span>

[!code-csharp[long](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]

<span data-ttu-id="7d214-121">整数文本还可包含表示类型的后缀。</span><span class="sxs-lookup"><span data-stu-id="7d214-121">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="7d214-122">后缀 `UL` 或 `ul` 将数字文本明确标识为 `ulong` 值。</span><span class="sxs-lookup"><span data-stu-id="7d214-122">The suffix `UL` or `ul` unambiguously identifies a numeric literal as a `ulong` value.</span></span> <span data-ttu-id="7d214-123">如果文本值超过 <xref:System.Int64.MaxValue?displayProperty=nameWithType>，则 `L` 后缀表示 `ulong`。</span><span class="sxs-lookup"><span data-stu-id="7d214-123">The `L` suffix denotes a `ulong` if the literal value exceeds <xref:System.Int64.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7d214-124">如果文本值超过 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>，则 `U` 或 `u` 后缀表示 `ulong`。</span><span class="sxs-lookup"><span data-stu-id="7d214-124">And the `U` or `u` suffix denotes a `ulong` if the literal value exceeds <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7d214-125">以下示例使用 `ul` 后缀来表示长整型：</span><span class="sxs-lookup"><span data-stu-id="7d214-125">The following example uses the `ul` suffix to denote a long integer:</span></span>

[!code-csharp[ulsuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

<span data-ttu-id="7d214-126">如果整数文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：</span><span class="sxs-lookup"><span data-stu-id="7d214-126">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. [<span data-ttu-id="7d214-127">int</span><span class="sxs-lookup"><span data-stu-id="7d214-127">int</span></span>](int.md)
2. [<span data-ttu-id="7d214-128">uint</span><span class="sxs-lookup"><span data-stu-id="7d214-128">uint</span></span>](uint.md)
3. [<span data-ttu-id="7d214-129">long</span><span class="sxs-lookup"><span data-stu-id="7d214-129">long</span></span>](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a><span data-ttu-id="7d214-130">编译器重载解析</span><span class="sxs-lookup"><span data-stu-id="7d214-130">Compiler overload resolution</span></span>

<span data-ttu-id="7d214-131">此后缀常用于调用重载方法。</span><span class="sxs-lookup"><span data-stu-id="7d214-131">A common use of the suffix is with calling overloaded methods.</span></span> <span data-ttu-id="7d214-132">以下面使用 `ulong` 和 [int](int.md) 参数的重载方法为例：</span><span class="sxs-lookup"><span data-stu-id="7d214-132">Consider, for example, the following overloaded methods that use `ulong` and [int](int.md) parameters:</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ulong l) {}
```

<span data-ttu-id="7d214-133">在 `ulong` 参数后加上后缀可保证调用正确的类型，例如：</span><span class="sxs-lookup"><span data-stu-id="7d214-133">Using a suffix with the `ulong` parameter guarantees that the correct type is called, for example:</span></span>

```csharp
SampleMethod(5);    // Calling the method with the int parameter
SampleMethod(5UL);  // Calling the method with the ulong parameter
```

## <a name="conversions"></a><span data-ttu-id="7d214-134">转换</span><span class="sxs-lookup"><span data-stu-id="7d214-134">Conversions</span></span>

<span data-ttu-id="7d214-135">存在从 `ulong` 到 [float](float.md)、[double](double.md) 或 [decimal](decimal.md) 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="7d214-135">There is a predefined implicit conversion from `ulong` to [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span>

<span data-ttu-id="7d214-136">不存在从 `ulong` 到任何整型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="7d214-136">There is no implicit conversion from `ulong` to any integral type.</span></span> <span data-ttu-id="7d214-137">例如，如果不使用显式强制转换，以下语句会生成编译错误：</span><span class="sxs-lookup"><span data-stu-id="7d214-137">For example, the following statement will produce a compilation error without an explicit cast:</span></span>

```csharp
long long1 = 8UL;   // Error: no implicit conversion from ulong
```

<span data-ttu-id="7d214-138">存在从 [byte](byte.md)、[ushort](ushort.md)、[uint](uint.md) 或 [char](char.md) 到 `ulong` 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="7d214-138">There is a predefined implicit conversion from [byte](byte.md), [ushort](ushort.md), [uint](uint.md), or [char](char.md) to `ulong`.</span></span>

<span data-ttu-id="7d214-139">此外，不存在从浮点类型到 `ulong` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="7d214-139">Also, there is no implicit conversion from floating-point types to `ulong`.</span></span> <span data-ttu-id="7d214-140">例如，除非使用显式强制转换，否则以下语句将生成编译器错误：</span><span class="sxs-lookup"><span data-stu-id="7d214-140">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error -- no implicit conversion from double:
ulong x = 3.0;
// OK -- explicit conversion:
ulong y = (ulong)3.0;
```

<span data-ttu-id="7d214-141">有关兼用浮点类型和整型类型的算术表达式的信息，请参阅 [float](float.md) 和 [double](double.md)。</span><span class="sxs-lookup"><span data-stu-id="7d214-141">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="7d214-142">有关隐式数值转换规则的详细信息，请参阅[隐式数值转换表](implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="7d214-142">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7d214-143">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="7d214-143">C# language specification</span></span>

<span data-ttu-id="7d214-144">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[整型类型](~/_csharplang/spec/types.md#integral-types)。</span><span class="sxs-lookup"><span data-stu-id="7d214-144">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="7d214-145">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="7d214-145">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d214-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d214-146">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="7d214-147">C# 参考</span><span class="sxs-lookup"><span data-stu-id="7d214-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7d214-148">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7d214-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7d214-149">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="7d214-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="7d214-150">整型表</span><span class="sxs-lookup"><span data-stu-id="7d214-150">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="7d214-151">内置类型表</span><span class="sxs-lookup"><span data-stu-id="7d214-151">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="7d214-152">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="7d214-152">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="7d214-153">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="7d214-153">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
