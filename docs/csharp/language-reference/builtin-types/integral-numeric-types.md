---
title: 整型数值类型 - C# 参考
description: 了解每种整型数值类型的范围、存储大小和用途。
ms.date: 10/22/2019
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
ms.openlocfilehash: 394a809a9a2f45f4aee652d0eca892f62f0f2e54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093196"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="4f2e1-103">整型数值类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="4f2e1-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="4f2e1-104">整型数值类型  表示整数。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-104">The *integral numeric types* represent integer numbers.</span></span> <span data-ttu-id="4f2e1-105">所有的整型数值类型均为[值类型](value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-105">All integral numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="4f2e1-106">它们还是[简单类型](value-types.md#built-in-value-types)，可以使用[文本](#integer-literals)进行初始化。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#integer-literals).</span></span> <span data-ttu-id="4f2e1-107">所有整型数值类型都支持[算术](../operators/arithmetic-operators.md)、[位逻辑](../operators/bitwise-and-shift-operators.md)、[比较](../operators/comparison-operators.md)和[相等](../operators/equality-operators.md)运算符。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-107">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="4f2e1-108">整型类型的特征</span><span class="sxs-lookup"><span data-stu-id="4f2e1-108">Characteristics of the integral types</span></span>

<span data-ttu-id="4f2e1-109">C# 支持以下预定义整型类型：</span><span class="sxs-lookup"><span data-stu-id="4f2e1-109">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="4f2e1-110">C# 类型/关键字</span><span class="sxs-lookup"><span data-stu-id="4f2e1-110">C# type/keyword</span></span>|<span data-ttu-id="4f2e1-111">范围</span><span class="sxs-lookup"><span data-stu-id="4f2e1-111">Range</span></span>|<span data-ttu-id="4f2e1-112">大小</span><span class="sxs-lookup"><span data-stu-id="4f2e1-112">Size</span></span>|<span data-ttu-id="4f2e1-113">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="4f2e1-113">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="4f2e1-114">-128 到 127</span><span class="sxs-lookup"><span data-stu-id="4f2e1-114">-128 to 127</span></span>|<span data-ttu-id="4f2e1-115">8 位带符号整数</span><span class="sxs-lookup"><span data-stu-id="4f2e1-115">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="4f2e1-116">0 到 255</span><span class="sxs-lookup"><span data-stu-id="4f2e1-116">0 to 255</span></span>|<span data-ttu-id="4f2e1-117">无符号的 8 位整数</span><span class="sxs-lookup"><span data-stu-id="4f2e1-117">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="4f2e1-118">-32,768 到 32,767</span><span class="sxs-lookup"><span data-stu-id="4f2e1-118">-32,768 to 32,767</span></span>|<span data-ttu-id="4f2e1-119">有符号 16 位整数</span><span class="sxs-lookup"><span data-stu-id="4f2e1-119">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="4f2e1-120">0 到 65,535</span><span class="sxs-lookup"><span data-stu-id="4f2e1-120">0 to 65,535</span></span>|<span data-ttu-id="4f2e1-121">无符号 16 位整数</span><span class="sxs-lookup"><span data-stu-id="4f2e1-121">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="4f2e1-122">-2,147,483,648 到 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="4f2e1-122">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="4f2e1-123">带符号的 32 位整数</span><span class="sxs-lookup"><span data-stu-id="4f2e1-123">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="4f2e1-124">0 到 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="4f2e1-124">0 to 4,294,967,295</span></span>|<span data-ttu-id="4f2e1-125">无符号的 32 位整数</span><span class="sxs-lookup"><span data-stu-id="4f2e1-125">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="4f2e1-126">-9,223,372,036,854,775,808 到 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="4f2e1-126">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="4f2e1-127">64 位带符号整数</span><span class="sxs-lookup"><span data-stu-id="4f2e1-127">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="4f2e1-128">0 到 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="4f2e1-128">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="4f2e1-129">无符号 64 位整数</span><span class="sxs-lookup"><span data-stu-id="4f2e1-129">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="4f2e1-130">在上表中，最左侧列中的每个 C# 类型关键字都是相应 .NET 类型的别名。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-130">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="4f2e1-131">它们是可互换的。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-131">They are interchangeable.</span></span> <span data-ttu-id="4f2e1-132">例如，以下声明声明了相同类型的变量：</span><span class="sxs-lookup"><span data-stu-id="4f2e1-132">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="4f2e1-133">每个整型类型的默认值都为零 `0`。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-133">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="4f2e1-134">每个整型类型都有 `MinValue` 和 `MaxValue` 常量，提供该类型的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-134">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="4f2e1-135"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 结构用于表示没有上限或下限的带符号整数。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-135">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="4f2e1-136">整数文本</span><span class="sxs-lookup"><span data-stu-id="4f2e1-136">Integer literals</span></span>

<span data-ttu-id="4f2e1-137">整数文本可以是</span><span class="sxs-lookup"><span data-stu-id="4f2e1-137">Integer literals can be</span></span>

- <span data-ttu-id="4f2e1-138"> 十进制：不使用任何前缀</span><span class="sxs-lookup"><span data-stu-id="4f2e1-138">*decimal*: without any prefix</span></span>
- <span data-ttu-id="4f2e1-139"> 十六进制：使用 `0x` 或 `0X` 前缀</span><span class="sxs-lookup"><span data-stu-id="4f2e1-139">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="4f2e1-140"> 二进制：使用 `0b` 或 `0B` 前缀（在 C# 7.0 和更高版本中可用）</span><span class="sxs-lookup"><span data-stu-id="4f2e1-140">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="4f2e1-141">下面的代码演示每种类型的示例：</span><span class="sxs-lookup"><span data-stu-id="4f2e1-141">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="4f2e1-142">前面的示例还演示了如何将 `_` 用作数字分隔符  （从 C# 7.0 开始提供支持）。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-142">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="4f2e1-143">可以将数字分隔符用于所有类型的数字文本。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-143">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="4f2e1-144">整数文本的类型由其后缀确定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4f2e1-144">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="4f2e1-145">如果文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：`int`、`uint`、`long`、`ulong`。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-145">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="4f2e1-146">如果文本以 `U` 或 `u` 为后缀，则其类型为以下类型中可表示其值的第一个类型：`uint`、`ulong`。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-146">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="4f2e1-147">如果文本以 `L` 或 `l` 为后缀，则其类型为以下类型中可表示其值的第一个类型：`long`、`ulong`。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-147">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4f2e1-148">可以使用小写字母 `l` 作为后缀。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-148">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="4f2e1-149">但是，这会生成一个编译器警告，因为字母 `l` 可能与数字 `1` 混淆。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-149">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="4f2e1-150">为清楚起见，请使用 `L`。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-150">Use `L` for clarity.</span></span>

- <span data-ttu-id="4f2e1-151">如果文本的后缀为 `UL`、`Ul`、`uL`、`ul`、`LU`、`Lu`、`lU` 或 `lu`，则其类型为 `ulong`。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-151">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="4f2e1-152">如果由整数字面量所表示的值超出了 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>，则将出现编译器错误 [CS1021](../../misc/cs1021.md)。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-152">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="4f2e1-153">如果确定的整数文本的类型为 `int`，且文本所表示的值位于目标类型的范围内，则该值可以隐式转换为 `sbyte`、`byte`、`short`、`ushort`、`uint` 或 `ulong`：</span><span class="sxs-lookup"><span data-stu-id="4f2e1-153">If the determined type of an integer literal is `int` and the value represented by the literal is within the range of the destination type, the value can be implicitly converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="4f2e1-154">如前面的示例所示，如果文本的值不在目标类型的范围内，则发生编译器错误 [CS0031](../../misc/cs0031.md)。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-154">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="4f2e1-155">还可以使用强制转换将整数文本所表示的值转换为除确定的文本类型之外的类型：</span><span class="sxs-lookup"><span data-stu-id="4f2e1-155">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="4f2e1-156">转换</span><span class="sxs-lookup"><span data-stu-id="4f2e1-156">Conversions</span></span>

<span data-ttu-id="4f2e1-157">可以将任何整型数值类型转换为其他整数数值类型。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-157">You can convert any integral numeric type to any other integral numeric type.</span></span> <span data-ttu-id="4f2e1-158">如果目标类型可以存储源类型的所有值，则转换是隐式的。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-158">If the destination type can store all values of the source type, the conversion is implicit.</span></span> <span data-ttu-id="4f2e1-159">否则，必须使用[强制转换运算符 `()`](../operators/type-testing-and-cast.md#cast-operator-) 来调用显式转换。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-159">Otherwise, you need to use the [cast operator `()`](../operators/type-testing-and-cast.md#cast-operator-) to invoke an explicit conversion.</span></span> <span data-ttu-id="4f2e1-160">有关详细信息，请参阅[内置数值转换](numeric-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="4f2e1-160">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4f2e1-161">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="4f2e1-161">C# language specification</span></span>

<span data-ttu-id="4f2e1-162">有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：</span><span class="sxs-lookup"><span data-stu-id="4f2e1-162">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="4f2e1-163">整型类型</span><span class="sxs-lookup"><span data-stu-id="4f2e1-163">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="4f2e1-164">整数文本</span><span class="sxs-lookup"><span data-stu-id="4f2e1-164">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="4f2e1-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f2e1-165">See also</span></span>

- [<span data-ttu-id="4f2e1-166">C# 参考</span><span class="sxs-lookup"><span data-stu-id="4f2e1-166">C# reference</span></span>](../index.md)
- [<span data-ttu-id="4f2e1-167">值类型</span><span class="sxs-lookup"><span data-stu-id="4f2e1-167">Value types</span></span>](value-types.md)
- [<span data-ttu-id="4f2e1-168">浮点类型</span><span class="sxs-lookup"><span data-stu-id="4f2e1-168">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="4f2e1-169">标准数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="4f2e1-169">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="4f2e1-170">.NET 中的数字</span><span class="sxs-lookup"><span data-stu-id="4f2e1-170">Numerics in .NET</span></span>](../../../standard/numerics.md)
