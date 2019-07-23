---
title: 整型数值类型 - C# 参考
description: 了解每种整型数值类型的范围、存储大小和用途。
ms.date: 06/25/2019
f1_keywords:
- byte
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- sbyte
- short
- short_CSharpKeyword
- ushort
- ushort_CSharpKeyword
- int_CSharpKeyword
- int
- uint
- uint_CSharpKeyword
- long_CSharpKeyword
- long
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
- byte keyword [C#]
- sbyte keyword [C#]
- short keyword [C#]
- ushort keyword [C#]
- int keyword [C#]
- uint keyword [C#]
- long keyword [C#]
- ulong keyword [C#]
ms.openlocfilehash: dfb1298abaff0cfe8eae7536f94511a30012a4a9
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236080"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="389da-103">整型数值类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="389da-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="389da-104">“整型数值类型”是“简单类型”的子集，可以使用[文本](#integral-literals)**进行初始化**   。</span><span class="sxs-lookup"><span data-stu-id="389da-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integral-literals).</span></span> <span data-ttu-id="389da-105">所有整型类型同时也是值类型。</span><span class="sxs-lookup"><span data-stu-id="389da-105">All integral types are also value types.</span></span> <span data-ttu-id="389da-106">所有整型数值类型都支持[算术](../operators/arithmetic-operators.md)、[位逻辑](../operators/bitwise-and-shift-operators.md)、[比较和相等](../operators/equality-operators.md)运算符。</span><span class="sxs-lookup"><span data-stu-id="389da-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="389da-107">整型类型的特征</span><span class="sxs-lookup"><span data-stu-id="389da-107">Characteristics of the integral types</span></span>

<span data-ttu-id="389da-108">C# 支持以下预定义整型类型：</span><span class="sxs-lookup"><span data-stu-id="389da-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="389da-109">C# 类型/关键字</span><span class="sxs-lookup"><span data-stu-id="389da-109">C# type/keyword</span></span>|<span data-ttu-id="389da-110">范围</span><span class="sxs-lookup"><span data-stu-id="389da-110">Range</span></span>|<span data-ttu-id="389da-111">大小</span><span class="sxs-lookup"><span data-stu-id="389da-111">Size</span></span>|<span data-ttu-id="389da-112">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="389da-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="389da-113">-128 到 127</span><span class="sxs-lookup"><span data-stu-id="389da-113">-128 to 127</span></span>|<span data-ttu-id="389da-114">8 位带符号整数</span><span class="sxs-lookup"><span data-stu-id="389da-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="389da-115">0 到 255</span><span class="sxs-lookup"><span data-stu-id="389da-115">0 to 255</span></span>|<span data-ttu-id="389da-116">无符号的 8 位整数</span><span class="sxs-lookup"><span data-stu-id="389da-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="389da-117">-32,768 到 32,767</span><span class="sxs-lookup"><span data-stu-id="389da-117">-32,768 to 32,767</span></span>|<span data-ttu-id="389da-118">有符号 16 位整数</span><span class="sxs-lookup"><span data-stu-id="389da-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="389da-119">0 到 65,535</span><span class="sxs-lookup"><span data-stu-id="389da-119">0 to 65,535</span></span>|<span data-ttu-id="389da-120">无符号 16 位整数</span><span class="sxs-lookup"><span data-stu-id="389da-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="389da-121">-2,147,483,648 到 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="389da-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="389da-122">带符号的 32 位整数</span><span class="sxs-lookup"><span data-stu-id="389da-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="389da-123">0 到 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="389da-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="389da-124">无符号的 32 位整数</span><span class="sxs-lookup"><span data-stu-id="389da-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="389da-125">-9,223,372,036,854,775,808 到 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="389da-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="389da-126">64 位带符号整数</span><span class="sxs-lookup"><span data-stu-id="389da-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="389da-127">0 到 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="389da-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="389da-128">无符号 64 位整数</span><span class="sxs-lookup"><span data-stu-id="389da-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="389da-129">在上表中，最左侧列中的每个 C# 类型关键字都是相应 .NET 类型的别名。</span><span class="sxs-lookup"><span data-stu-id="389da-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="389da-130">它们是可互换的。</span><span class="sxs-lookup"><span data-stu-id="389da-130">They are interchangeable.</span></span> <span data-ttu-id="389da-131">例如，以下声明声明了相同类型的变量：</span><span class="sxs-lookup"><span data-stu-id="389da-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="389da-132">每个整型类型的默认值都为零 `0`。</span><span class="sxs-lookup"><span data-stu-id="389da-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="389da-133">每个整型类型都有 `MinValue` 和 `MaxValue` 常量，提供该类型的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="389da-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="389da-134"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 结构用于表示没有上限或下限的带符号整数。</span><span class="sxs-lookup"><span data-stu-id="389da-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integral-literals"></a><span data-ttu-id="389da-135">整型文本</span><span class="sxs-lookup"><span data-stu-id="389da-135">Integral literals</span></span>

<span data-ttu-id="389da-136">整型文本可以指定为十进制文本、十六进制文本或二进制文本    。</span><span class="sxs-lookup"><span data-stu-id="389da-136">Integral literals can be specified as *decimal literals*, *hexadecimal literals*, or *binary literals*.</span></span> <span data-ttu-id="389da-137">每种文本的示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="389da-137">An example of each is shown below:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="389da-138">十进制文本不需要任何前缀。</span><span class="sxs-lookup"><span data-stu-id="389da-138">Decimal literals don't require any prefix.</span></span> <span data-ttu-id="389da-139">`x` 或 `X` 前缀表示十六进制文本  。</span><span class="sxs-lookup"><span data-stu-id="389da-139">The `x` or `X` prefix signifies a *hexadecimal literal*.</span></span> <span data-ttu-id="389da-140">`b` 或 `B` 前缀表示二进制文本  。</span><span class="sxs-lookup"><span data-stu-id="389da-140">The `b` or `B` prefix signifies a *binary literal*.</span></span> <span data-ttu-id="389da-141">`binaryLiteral` 的声明演示将 `_` 用作数字分隔符  。</span><span class="sxs-lookup"><span data-stu-id="389da-141">The declaration of `binaryLiteral` demonstrates the use of `_` as a *digit separator*.</span></span> <span data-ttu-id="389da-142">数字分隔符可以与所有数值文本一起使用。</span><span class="sxs-lookup"><span data-stu-id="389da-142">The digit separator can be used with all numeric literals.</span></span> <span data-ttu-id="389da-143">C# 7.0 及以后版本均支持二进制文本和数字分隔符 `_`。</span><span class="sxs-lookup"><span data-stu-id="389da-143">Binary literals and the digit separator `_` are supported starting with C# 7.0.</span></span>

### <a name="literal-suffixes"></a><span data-ttu-id="389da-144">文本后缀</span><span class="sxs-lookup"><span data-stu-id="389da-144">Literal suffixes</span></span>

<span data-ttu-id="389da-145">`l` 或 `L` 后缀指定整型文本应为 `long` 类型。</span><span class="sxs-lookup"><span data-stu-id="389da-145">The `l` or `L` suffix specifies that the integral literal should be of the `long` type.</span></span> <span data-ttu-id="389da-146">`ul` 或 `UL` 后缀指定 `ulong` 类型。</span><span class="sxs-lookup"><span data-stu-id="389da-146">The `ul` or `UL` suffix specifies the `ulong` type.</span></span> <span data-ttu-id="389da-147">如果对大于 9,223,372,036,854,775,807（`long` 的最大值）的文本使用 `L` 后缀，则该值将转换为 `ulong` 类型。</span><span class="sxs-lookup"><span data-stu-id="389da-147">If the `L` suffix is used on a literal that is greater than 9,223,372,036,854,775,807 (the maximum value of `long`), the value is converted to the `ulong` type.</span></span> <span data-ttu-id="389da-148">如果整型文本表示的值超出了 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>，就会出现编译器错误 [CS1021](../../misc/cs1021.md)。</span><span class="sxs-lookup"><span data-stu-id="389da-148">If the value represented by an integral literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span> 

> [!NOTE]
> <span data-ttu-id="389da-149">也可用小写字母“l”作后缀。</span><span class="sxs-lookup"><span data-stu-id="389da-149">You can use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="389da-150">但是，字母“l”容易与数字“1”混淆，因此会生成编译器警告。</span><span class="sxs-lookup"><span data-stu-id="389da-150">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="389da-151">为清楚起见，请使用“L”。</span><span class="sxs-lookup"><span data-stu-id="389da-151">Use "L" for clarity.</span></span>

### <a name="type-of-an-integral-literal"></a><span data-ttu-id="389da-152">整型文本类型</span><span class="sxs-lookup"><span data-stu-id="389da-152">Type of an integral literal</span></span>

<span data-ttu-id="389da-153">如果整型文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：</span><span class="sxs-lookup"><span data-stu-id="389da-153">If an integral literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
1. `uint`
1. `long`
1. `ulong`

<span data-ttu-id="389da-154">可以通过赋值或强制转换，将整型文本转换为范围小于默认值的类型：</span><span class="sxs-lookup"><span data-stu-id="389da-154">You can convert an integral literal to a type with a smaller range than the default using either an assignment or a cast:</span></span>

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

<span data-ttu-id="389da-155">可以通过赋值、强制转换或文本后缀将整型文本转换为范围大于默认值的类型：</span><span class="sxs-lookup"><span data-stu-id="389da-155">You can convert an integral literal to a type with a larger range than the default using either assignment, a cast, or a suffix on the literal:</span></span>

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="389da-156">转换</span><span class="sxs-lookup"><span data-stu-id="389da-156">Conversions</span></span>

<span data-ttu-id="389da-157">任何两个整型类型之间均可进行隐式转换（称为扩大转换），在转换中，目标类型可以存储源类型的所有值  。</span><span class="sxs-lookup"><span data-stu-id="389da-157">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="389da-158">例如，`int` 可隐式转换为 `long`，因为 `int` 值的范围是 `long` 的真子集。</span><span class="sxs-lookup"><span data-stu-id="389da-158">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="389da-159">小型无符号整型类型可隐式转换为大型带符号整型类型。</span><span class="sxs-lookup"><span data-stu-id="389da-159">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="389da-160">任何整型类型都可隐式转换为任何浮点类型。</span><span class="sxs-lookup"><span data-stu-id="389da-160">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="389da-161">任何带符号整型类型无法隐式转换为任何无符号整型类型。</span><span class="sxs-lookup"><span data-stu-id="389da-161">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="389da-162">如果未定义源类型到目标类型的隐式转换，必须使用显式强制转换将整型类型转换为其他整型类型。</span><span class="sxs-lookup"><span data-stu-id="389da-162">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="389da-163">这称为收缩转换  。</span><span class="sxs-lookup"><span data-stu-id="389da-163">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="389da-164">由于转换可能导致数据丢失，因此必须使用显式用例。</span><span class="sxs-lookup"><span data-stu-id="389da-164">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="see-also"></a><span data-ttu-id="389da-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="389da-165">See also</span></span>

- [<span data-ttu-id="389da-166">C# 语言规范 - 整型类型</span><span class="sxs-lookup"><span data-stu-id="389da-166">C# language specification - Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="389da-167">C# 参考</span><span class="sxs-lookup"><span data-stu-id="389da-167">C# reference</span></span>](../index.md)
- [<span data-ttu-id="389da-168">浮点类型</span><span class="sxs-lookup"><span data-stu-id="389da-168">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="389da-169">默认值表</span><span class="sxs-lookup"><span data-stu-id="389da-169">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="389da-170">设置数值结果表的格式</span><span class="sxs-lookup"><span data-stu-id="389da-170">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="389da-171">内置类型表</span><span class="sxs-lookup"><span data-stu-id="389da-171">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="389da-172">.NET 中的数字</span><span class="sxs-lookup"><span data-stu-id="389da-172">Numerics in .NET</span></span>](../../../standard/numerics.md)
