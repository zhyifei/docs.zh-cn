---
title: 整型数值类型 - C# 参考
description: 了解每种整型数值类型的范围、存储大小和用途。
ms.date: 10/18/2019
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
ms.openlocfilehash: 3d4f3164d67a000123417619f3be6be455d5ab87
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579186"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="667db-103">整型数值类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="667db-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="667db-104">“整型数值类型”是“简单类型”的子集，可以使用[文本](#integer-literals)**进行初始化**   。</span><span class="sxs-lookup"><span data-stu-id="667db-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integer-literals).</span></span> <span data-ttu-id="667db-105">所有整型类型同时也是值类型。</span><span class="sxs-lookup"><span data-stu-id="667db-105">All integral types are also value types.</span></span> <span data-ttu-id="667db-106">所有整型数值类型都支持[算术](../operators/arithmetic-operators.md)、[位逻辑](../operators/bitwise-and-shift-operators.md)、[比较](../operators/comparison-operators.md)和[相等](../operators/equality-operators.md)运算符。</span><span class="sxs-lookup"><span data-stu-id="667db-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="667db-107">整型类型的特征</span><span class="sxs-lookup"><span data-stu-id="667db-107">Characteristics of the integral types</span></span>

<span data-ttu-id="667db-108">C# 支持以下预定义整型类型：</span><span class="sxs-lookup"><span data-stu-id="667db-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="667db-109">C# 类型/关键字</span><span class="sxs-lookup"><span data-stu-id="667db-109">C# type/keyword</span></span>|<span data-ttu-id="667db-110">范围</span><span class="sxs-lookup"><span data-stu-id="667db-110">Range</span></span>|<span data-ttu-id="667db-111">大小</span><span class="sxs-lookup"><span data-stu-id="667db-111">Size</span></span>|<span data-ttu-id="667db-112">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="667db-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="667db-113">-128 到 127</span><span class="sxs-lookup"><span data-stu-id="667db-113">-128 to 127</span></span>|<span data-ttu-id="667db-114">8 位带符号整数</span><span class="sxs-lookup"><span data-stu-id="667db-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="667db-115">0 到 255</span><span class="sxs-lookup"><span data-stu-id="667db-115">0 to 255</span></span>|<span data-ttu-id="667db-116">无符号的 8 位整数</span><span class="sxs-lookup"><span data-stu-id="667db-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="667db-117">-32,768 到 32,767</span><span class="sxs-lookup"><span data-stu-id="667db-117">-32,768 to 32,767</span></span>|<span data-ttu-id="667db-118">有符号 16 位整数</span><span class="sxs-lookup"><span data-stu-id="667db-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="667db-119">0 到 65,535</span><span class="sxs-lookup"><span data-stu-id="667db-119">0 to 65,535</span></span>|<span data-ttu-id="667db-120">无符号 16 位整数</span><span class="sxs-lookup"><span data-stu-id="667db-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="667db-121">-2,147,483,648 到 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="667db-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="667db-122">带符号的 32 位整数</span><span class="sxs-lookup"><span data-stu-id="667db-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="667db-123">0 到 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="667db-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="667db-124">无符号的 32 位整数</span><span class="sxs-lookup"><span data-stu-id="667db-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="667db-125">-9,223,372,036,854,775,808 到 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="667db-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="667db-126">64 位带符号整数</span><span class="sxs-lookup"><span data-stu-id="667db-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="667db-127">0 到 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="667db-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="667db-128">无符号 64 位整数</span><span class="sxs-lookup"><span data-stu-id="667db-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="667db-129">在上表中，最左侧列中的每个 C# 类型关键字都是相应 .NET 类型的别名。</span><span class="sxs-lookup"><span data-stu-id="667db-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="667db-130">它们是可互换的。</span><span class="sxs-lookup"><span data-stu-id="667db-130">They are interchangeable.</span></span> <span data-ttu-id="667db-131">例如，以下声明声明了相同类型的变量：</span><span class="sxs-lookup"><span data-stu-id="667db-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="667db-132">每个整型类型的默认值都为零 `0`。</span><span class="sxs-lookup"><span data-stu-id="667db-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="667db-133">每个整型类型都有 `MinValue` 和 `MaxValue` 常量，提供该类型的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="667db-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="667db-134"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 结构用于表示没有上限或下限的带符号整数。</span><span class="sxs-lookup"><span data-stu-id="667db-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="667db-135">整数文本</span><span class="sxs-lookup"><span data-stu-id="667db-135">Integer literals</span></span>

<span data-ttu-id="667db-136">整数文本可以是</span><span class="sxs-lookup"><span data-stu-id="667db-136">Integer literals can be</span></span>

- <span data-ttu-id="667db-137"> 十进制：不使用任何前缀</span><span class="sxs-lookup"><span data-stu-id="667db-137">*decimal*: without any prefix</span></span>
- <span data-ttu-id="667db-138"> 十六进制：使用 `0x` 或 `0X` 前缀</span><span class="sxs-lookup"><span data-stu-id="667db-138">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="667db-139"> 二进制：使用 `0b` 或 `0B` 前缀（在 C# 7.0 和更高版本中可用）</span><span class="sxs-lookup"><span data-stu-id="667db-139">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="667db-140">下面的代码演示每种类型的示例：</span><span class="sxs-lookup"><span data-stu-id="667db-140">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="667db-141">前面的示例还演示了如何将 `_` 用作数字分隔符  （从 C# 7.0 开始提供支持）。</span><span class="sxs-lookup"><span data-stu-id="667db-141">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="667db-142">可以将数字分隔符用于所有类型的数字文本。</span><span class="sxs-lookup"><span data-stu-id="667db-142">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="667db-143">整数文本的类型由其后缀确定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="667db-143">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="667db-144">如果文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：`int`、`uint`、`long`、`ulong`。</span><span class="sxs-lookup"><span data-stu-id="667db-144">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="667db-145">如果文本以 `U` 或 `u` 为后缀，则其类型为以下类型中可表示其值的第一个类型：`uint`、`ulong`。</span><span class="sxs-lookup"><span data-stu-id="667db-145">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="667db-146">如果文本以 `L` 或 `l` 为后缀，则其类型为以下类型中可表示其值的第一个类型：`long`、`ulong`。</span><span class="sxs-lookup"><span data-stu-id="667db-146">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="667db-147">可以使用小写字母 `l` 作为后缀。</span><span class="sxs-lookup"><span data-stu-id="667db-147">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="667db-148">但是，这会生成一个编译器警告，因为字母 `l` 可能与数字 `1` 混淆。</span><span class="sxs-lookup"><span data-stu-id="667db-148">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="667db-149">为清楚起见，请使用 `L`。</span><span class="sxs-lookup"><span data-stu-id="667db-149">Use `L` for clarity.</span></span>

- <span data-ttu-id="667db-150">如果文本的后缀为 `UL`、`Ul`、`uL`、`ul`、`LU`、`Lu`、`lU` 或 `lu`，则其类型为 `ulong`。</span><span class="sxs-lookup"><span data-stu-id="667db-150">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="667db-151">如果由整数字面量所表示的值超出了 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>，则将出现编译器错误 [CS1021](../../misc/cs1021.md)。</span><span class="sxs-lookup"><span data-stu-id="667db-151">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="667db-152">整数文本所表示的值可以隐式转换为范围比确定的文本类型小的类型。</span><span class="sxs-lookup"><span data-stu-id="667db-152">The value represented by an integer literal can be implicitly converted to a type with a smaller range than the determined type of the literal.</span></span> <span data-ttu-id="667db-153">当值处于目标类型的范围内时，可能会出现这种情况：</span><span class="sxs-lookup"><span data-stu-id="667db-153">That's possible when the value is within the range of the destination type:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="667db-154">如前面的示例所示，如果文本的值不在目标类型的范围内，则发生编译器错误 [CS0031](../../misc/cs0031.md)。</span><span class="sxs-lookup"><span data-stu-id="667db-154">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="667db-155">还可以使用强制转换将整数文本所表示的值转换为除确定的文本类型之外的类型：</span><span class="sxs-lookup"><span data-stu-id="667db-155">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="667db-156">转换</span><span class="sxs-lookup"><span data-stu-id="667db-156">Conversions</span></span>

<span data-ttu-id="667db-157">任何两个整型类型之间均可进行隐式转换（称为扩大转换），在转换中，目标类型可以存储源类型的所有值  。</span><span class="sxs-lookup"><span data-stu-id="667db-157">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="667db-158">例如，`int` 可隐式转换为 `long`，因为 `int` 值的范围是 `long` 的真子集。</span><span class="sxs-lookup"><span data-stu-id="667db-158">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="667db-159">小型无符号整型类型可隐式转换为大型带符号整型类型。</span><span class="sxs-lookup"><span data-stu-id="667db-159">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="667db-160">任何整型类型都可隐式转换为任何浮点类型。</span><span class="sxs-lookup"><span data-stu-id="667db-160">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="667db-161">任何带符号整型类型无法隐式转换为任何无符号整型类型。</span><span class="sxs-lookup"><span data-stu-id="667db-161">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="667db-162">如果未定义源类型到目标类型的隐式转换，必须使用显式强制转换将整型类型转换为其他整型类型。</span><span class="sxs-lookup"><span data-stu-id="667db-162">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="667db-163">这称为收缩转换  。</span><span class="sxs-lookup"><span data-stu-id="667db-163">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="667db-164">由于转换可能导致数据丢失，因此必须使用显式用例。</span><span class="sxs-lookup"><span data-stu-id="667db-164">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="667db-165">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="667db-165">C# language specification</span></span>

<span data-ttu-id="667db-166">有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：</span><span class="sxs-lookup"><span data-stu-id="667db-166">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="667db-167">整型类型</span><span class="sxs-lookup"><span data-stu-id="667db-167">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="667db-168">整数文本</span><span class="sxs-lookup"><span data-stu-id="667db-168">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="667db-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="667db-169">See also</span></span>

- [<span data-ttu-id="667db-170">C# 参考</span><span class="sxs-lookup"><span data-stu-id="667db-170">C# reference</span></span>](../index.md)
- [<span data-ttu-id="667db-171">浮点类型</span><span class="sxs-lookup"><span data-stu-id="667db-171">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="667db-172">默认值表</span><span class="sxs-lookup"><span data-stu-id="667db-172">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="667db-173">设置数值结果表的格式</span><span class="sxs-lookup"><span data-stu-id="667db-173">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="667db-174">内置类型表</span><span class="sxs-lookup"><span data-stu-id="667db-174">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="667db-175">.NET 中的数字</span><span class="sxs-lookup"><span data-stu-id="667db-175">Numerics in .NET</span></span>](../../../standard/numerics.md)
