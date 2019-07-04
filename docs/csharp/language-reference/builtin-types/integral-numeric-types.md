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
ms.openlocfilehash: bde0b7cea52951cd72bde6cfd7d8f1c7dbcb8f46
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425592"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="9ad47-103">整型数值类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="9ad47-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="9ad47-104">“整型数值类型”是“简单类型”的子集，可以使用[文本](#integral-literals)**进行初始化**   。</span><span class="sxs-lookup"><span data-stu-id="9ad47-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integral-literals).</span></span> <span data-ttu-id="9ad47-105">所有整型类型同时也是值类型。</span><span class="sxs-lookup"><span data-stu-id="9ad47-105">All integral types are also value types.</span></span>

<span data-ttu-id="9ad47-106">所有整型数值类型都支持[算术](../operators/arithmetic-operators.md)、[位逻辑](../operators/bitwise-and-shift-operators.md)、[比较和相等](../operators/equality-operators.md)运算符。</span><span class="sxs-lookup"><span data-stu-id="9ad47-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="sizes-and-ranges"></a><span data-ttu-id="9ad47-107">大小和范围</span><span class="sxs-lookup"><span data-stu-id="9ad47-107">Sizes and ranges</span></span>

<span data-ttu-id="9ad47-108">下表显示整型类型的大小和范围：</span><span class="sxs-lookup"><span data-stu-id="9ad47-108">The following table shows the sizes and ranges of the integral types:</span></span>

|<span data-ttu-id="9ad47-109">类型</span><span class="sxs-lookup"><span data-stu-id="9ad47-109">Type</span></span>|<span data-ttu-id="9ad47-110">范围</span><span class="sxs-lookup"><span data-stu-id="9ad47-110">Range</span></span>|<span data-ttu-id="9ad47-111">大小</span><span class="sxs-lookup"><span data-stu-id="9ad47-111">Size</span></span>|  
|----------|-----------|----------|  
|`sbyte`|<span data-ttu-id="9ad47-112">-128 到 127</span><span class="sxs-lookup"><span data-stu-id="9ad47-112">-128 to 127</span></span>|<span data-ttu-id="9ad47-113">8 位带符号整数</span><span class="sxs-lookup"><span data-stu-id="9ad47-113">Signed 8-bit integer</span></span>|  
|`byte`|<span data-ttu-id="9ad47-114">0 到 255</span><span class="sxs-lookup"><span data-stu-id="9ad47-114">0 to 255</span></span>|<span data-ttu-id="9ad47-115">无符号的 8 位整数</span><span class="sxs-lookup"><span data-stu-id="9ad47-115">Unsigned 8-bit integer</span></span>|  
|`short`|<span data-ttu-id="9ad47-116">-32,768 到 32,767</span><span class="sxs-lookup"><span data-stu-id="9ad47-116">-32,768 to 32,767</span></span>|<span data-ttu-id="9ad47-117">有符号 16 位整数</span><span class="sxs-lookup"><span data-stu-id="9ad47-117">Signed 16-bit integer</span></span>|  
|`ushort`|<span data-ttu-id="9ad47-118">0 到 65,535</span><span class="sxs-lookup"><span data-stu-id="9ad47-118">0 to 65,535</span></span>|<span data-ttu-id="9ad47-119">无符号 16 位整数</span><span class="sxs-lookup"><span data-stu-id="9ad47-119">Unsigned 16-bit integer</span></span>|  
|`int`|<span data-ttu-id="9ad47-120">-2,147,483,648 到 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="9ad47-120">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="9ad47-121">带符号的 32 位整数</span><span class="sxs-lookup"><span data-stu-id="9ad47-121">Signed 32-bit integer</span></span>|  
|`uint`|<span data-ttu-id="9ad47-122">0 到 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="9ad47-122">0 to 4,294,967,295</span></span>|<span data-ttu-id="9ad47-123">无符号的 32 位整数</span><span class="sxs-lookup"><span data-stu-id="9ad47-123">Unsigned 32-bit integer</span></span>|  
|`long`|<span data-ttu-id="9ad47-124">-9,223,372,036,854,775,808 到 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="9ad47-124">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="9ad47-125">64 位带符号整数</span><span class="sxs-lookup"><span data-stu-id="9ad47-125">Signed 64-bit integer</span></span>|  
|`ulong`|<span data-ttu-id="9ad47-126">0 到 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="9ad47-126">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="9ad47-127">无符号 64 位整数</span><span class="sxs-lookup"><span data-stu-id="9ad47-127">Unsigned 64-bit integer</span></span>|  

<span data-ttu-id="9ad47-128">所有整型类型的默认值都是 `0`。</span><span class="sxs-lookup"><span data-stu-id="9ad47-128">The default value for all integral types is `0`.</span></span> <span data-ttu-id="9ad47-129">每个整型类型都有名为 `MinValue` 和 `MaxValue` 的常量，且分别为该类型的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="9ad47-129">Each of the integral types has constants named `MinValue` and `MaxValue` for the minimum and maximum value for that type.</span></span>

<span data-ttu-id="9ad47-130"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 结构用于表示没有上限或下限的带符号整数。</span><span class="sxs-lookup"><span data-stu-id="9ad47-130">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integral-literals"></a><span data-ttu-id="9ad47-131">整型文本</span><span class="sxs-lookup"><span data-stu-id="9ad47-131">Integral literals</span></span>

<span data-ttu-id="9ad47-132">整型文本可以指定为十进制文本、十六进制文本或二进制文本    。</span><span class="sxs-lookup"><span data-stu-id="9ad47-132">Integral literals can be specified as *decimal literals*, *hexadecimal literals*, or *binary literals*.</span></span> <span data-ttu-id="9ad47-133">每种文本的示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="9ad47-133">An example of each is shown below:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="9ad47-134">十进制文本不需要任何前缀。</span><span class="sxs-lookup"><span data-stu-id="9ad47-134">Decimal literals don't require any prefix.</span></span> <span data-ttu-id="9ad47-135">`x` 或 `X` 前缀表示十六进制文本  。</span><span class="sxs-lookup"><span data-stu-id="9ad47-135">The `x` or `X` prefix signifies a *hexadecimal literal*.</span></span> <span data-ttu-id="9ad47-136">`b` 或 `B` 前缀表示二进制文本  。</span><span class="sxs-lookup"><span data-stu-id="9ad47-136">The `b` or `B` prefix signifies a *binary literal*.</span></span> <span data-ttu-id="9ad47-137">`binaryLiteral` 的声明演示将 `_` 用作数字分隔符  。</span><span class="sxs-lookup"><span data-stu-id="9ad47-137">The declaration of `binaryLiteral` demonstrates the use of `_` as a *digit separator*.</span></span> <span data-ttu-id="9ad47-138">数字分隔符可以与所有数值文本一起使用。</span><span class="sxs-lookup"><span data-stu-id="9ad47-138">The digit separator can be used with all numeric literals.</span></span> <span data-ttu-id="9ad47-139">C# 7.0 及以后版本均支持二进制文本和数字分隔符 `_`。</span><span class="sxs-lookup"><span data-stu-id="9ad47-139">Binary literals and the digit separator `_` are supported starting with C# 7.0.</span></span>

## <a name="literal-suffixes"></a><span data-ttu-id="9ad47-140">文本后缀</span><span class="sxs-lookup"><span data-stu-id="9ad47-140">Literal suffixes</span></span> 

<span data-ttu-id="9ad47-141">`l` 或 `L` 后缀指定整型文本应为 `long` 类型。</span><span class="sxs-lookup"><span data-stu-id="9ad47-141">The `l` or `L` suffix specifies that the integral literal should be of the `long` type.</span></span> <span data-ttu-id="9ad47-142">`ul` 或 `UL` 后缀指定 `ulong` 类型。</span><span class="sxs-lookup"><span data-stu-id="9ad47-142">The `ul` or `UL` suffix specifies the `ulong` type.</span></span> <span data-ttu-id="9ad47-143">如果对大于 9,223,372,036,854,775,807（`long` 的最大值）的文本使用 `L` 后缀，则该值将转换为 `ulong` 类型。</span><span class="sxs-lookup"><span data-stu-id="9ad47-143">If the `L` suffix is used on a literal that is greater than 9,223,372,036,854,775,807 (the maximum value of `long`), the value is converted to the `ulong` type.</span></span> <span data-ttu-id="9ad47-144">如果由整数字面量所表示的值超出了 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>，则将出现编译器错误 [CS1021](../../misc/cs1021.md)。</span><span class="sxs-lookup"><span data-stu-id="9ad47-144">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span> 

> [!NOTE]
> <span data-ttu-id="9ad47-145">也可用小写字母“l”作后缀。</span><span class="sxs-lookup"><span data-stu-id="9ad47-145">You can use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="9ad47-146">但是，字母“l”容易与数字“1”混淆，因此会生成编译器警告。</span><span class="sxs-lookup"><span data-stu-id="9ad47-146">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="9ad47-147">为清楚起见，请使用“L”。</span><span class="sxs-lookup"><span data-stu-id="9ad47-147">Use "L" for clarity.</span></span>

## <a name="type-of-an-integral-literal"></a><span data-ttu-id="9ad47-148">整型文本类型</span><span class="sxs-lookup"><span data-stu-id="9ad47-148">Type of an integral literal</span></span>

<span data-ttu-id="9ad47-149">如果整型文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：</span><span class="sxs-lookup"><span data-stu-id="9ad47-149">If an integral literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
1. `uint`
1. `long`
1. `ulong`

<span data-ttu-id="9ad47-150">可以通过赋值或强制转换，将整型文本转换为范围小于默认值的类型：</span><span class="sxs-lookup"><span data-stu-id="9ad47-150">You can convert an integral literal to a type with a smaller range than the default using either an assignment or a cast:</span></span>

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

<span data-ttu-id="9ad47-151">可以通过赋值、强制转换或文本后缀将整型文本转换为范围大于默认值的类型：</span><span class="sxs-lookup"><span data-stu-id="9ad47-151">You can convert an integral literal to a type with a larger range than the default using either assignment, a cast, or a suffix on the literal:</span></span>

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="9ad47-152">转换</span><span class="sxs-lookup"><span data-stu-id="9ad47-152">Conversions</span></span>

<span data-ttu-id="9ad47-153">任何两个整型类型之间均可进行隐式转换（称为扩大转换），在转换中，目标类型可以存储源类型的所有值  。</span><span class="sxs-lookup"><span data-stu-id="9ad47-153">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="9ad47-154">例如，`int` 可隐式转换为 `long`，因为 `int` 值的范围是 `long` 的真子集。</span><span class="sxs-lookup"><span data-stu-id="9ad47-154">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="9ad47-155">小型无符号整型类型可隐式转换为大型带符号整型类型。</span><span class="sxs-lookup"><span data-stu-id="9ad47-155">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="9ad47-156">任何整型类型都可隐式转换为任何浮点类型。</span><span class="sxs-lookup"><span data-stu-id="9ad47-156">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="9ad47-157">任何带符号整型类型无法隐式转换为任何无符号整型类型。</span><span class="sxs-lookup"><span data-stu-id="9ad47-157">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="9ad47-158">如果未定义源类型到目标类型的隐式转换，必须使用显式强制转换将整型类型转换为其他整型类型。</span><span class="sxs-lookup"><span data-stu-id="9ad47-158">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="9ad47-159">这称为收缩转换  。</span><span class="sxs-lookup"><span data-stu-id="9ad47-159">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="9ad47-160">由于转换可能导致数据丢失，因此必须使用显式用例。</span><span class="sxs-lookup"><span data-stu-id="9ad47-160">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ad47-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ad47-161">See also</span></span>

- [<span data-ttu-id="9ad47-162">C# 语言规范 - 整型类型</span><span class="sxs-lookup"><span data-stu-id="9ad47-162">C# language specification - Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="9ad47-163">C# 参考</span><span class="sxs-lookup"><span data-stu-id="9ad47-163">C# reference</span></span>](../index.md)
- [<span data-ttu-id="9ad47-164">浮点型表</span><span class="sxs-lookup"><span data-stu-id="9ad47-164">Floating-point types table</span></span>](../keywords/floating-point-types-table.md)
- [<span data-ttu-id="9ad47-165">默认值表</span><span class="sxs-lookup"><span data-stu-id="9ad47-165">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="9ad47-166">设置数值结果表的格式</span><span class="sxs-lookup"><span data-stu-id="9ad47-166">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="9ad47-167">内置类型表</span><span class="sxs-lookup"><span data-stu-id="9ad47-167">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="9ad47-168">.NET 中的数字</span><span class="sxs-lookup"><span data-stu-id="9ad47-168">Numerics in .NET</span></span>](../../../standard/numerics.md)
