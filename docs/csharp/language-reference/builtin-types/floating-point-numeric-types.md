---
title: 浮点数值类型 - C# 引用
description: 内置 C# 浮点类型概述
ms.date: 10/18/2019
f1_keywords:
- float
- float_CSharpKeyword
- double
- double_CSharpKeyword
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- floating-point numbers [C#]
- ranges of floating-point types [C#]
- size of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: fa6cbb869d90113414cc6f8ffe231386c3596b1d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579374"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="09ca5-103">浮点数值类型（C# 引用）</span><span class="sxs-lookup"><span data-stu-id="09ca5-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="09ca5-104">“浮点类型”是“简单类型”的子集，可以使用[文本](#real-literals)**进行初始化**   。</span><span class="sxs-lookup"><span data-stu-id="09ca5-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#real-literals).</span></span> <span data-ttu-id="09ca5-105">所有浮点类型也是值类型。</span><span class="sxs-lookup"><span data-stu-id="09ca5-105">All floating-point types are also value types.</span></span> <span data-ttu-id="09ca5-106">所有浮点数值类型都支持[算术](../operators/arithmetic-operators.md)、[比较](../operators/comparison-operators.md)和[相等](../operators/equality-operators.md)运算符。</span><span class="sxs-lookup"><span data-stu-id="09ca5-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="09ca5-107">浮点类型的特征</span><span class="sxs-lookup"><span data-stu-id="09ca5-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="09ca5-108">C# 支持以下预定义浮点类型：</span><span class="sxs-lookup"><span data-stu-id="09ca5-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="09ca5-109">C# 类型/关键字</span><span class="sxs-lookup"><span data-stu-id="09ca5-109">C# type/keyword</span></span>|<span data-ttu-id="09ca5-110">大致范围</span><span class="sxs-lookup"><span data-stu-id="09ca5-110">Approximate range</span></span>|<span data-ttu-id="09ca5-111">精度</span><span class="sxs-lookup"><span data-stu-id="09ca5-111">Precision</span></span>|<span data-ttu-id="09ca5-112">大小</span><span class="sxs-lookup"><span data-stu-id="09ca5-112">Size</span></span>|<span data-ttu-id="09ca5-113">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="09ca5-113">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="09ca5-114">±1.5 x 10<sup>−45</sup> 至 ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="09ca5-114">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="09ca5-115">大约 6-9 位数字</span><span class="sxs-lookup"><span data-stu-id="09ca5-115">~6-9 digits</span></span>|<span data-ttu-id="09ca5-116">4 个字节</span><span class="sxs-lookup"><span data-stu-id="09ca5-116">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="09ca5-117">±5.0 × 10<sup>−324</sup> 到 ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="09ca5-117">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="09ca5-118">大约 15-17 位数字</span><span class="sxs-lookup"><span data-stu-id="09ca5-118">~15-17 digits</span></span>|<span data-ttu-id="09ca5-119">8 个字节</span><span class="sxs-lookup"><span data-stu-id="09ca5-119">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="09ca5-120">±1.0 x 10<sup>-28</sup> 至 ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="09ca5-120">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="09ca5-121">28-29 位</span><span class="sxs-lookup"><span data-stu-id="09ca5-121">28-29 digits</span></span>|<span data-ttu-id="09ca5-122">16 个字节</span><span class="sxs-lookup"><span data-stu-id="09ca5-122">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="09ca5-123">在上表中，最左侧列中的每个 C# 类型关键字都是相应 .NET 类型的别名。</span><span class="sxs-lookup"><span data-stu-id="09ca5-123">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="09ca5-124">它们是可互换的。</span><span class="sxs-lookup"><span data-stu-id="09ca5-124">They are interchangeable.</span></span> <span data-ttu-id="09ca5-125">例如，以下声明声明了相同类型的变量：</span><span class="sxs-lookup"><span data-stu-id="09ca5-125">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="09ca5-126">每个浮点类型的默认值都为零，`0`。</span><span class="sxs-lookup"><span data-stu-id="09ca5-126">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="09ca5-127">每个浮点类型都有 `MinValue` 和 `MaxValue` 常量，提供该类型的最小值和最大有限值。</span><span class="sxs-lookup"><span data-stu-id="09ca5-127">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="09ca5-128">`float` and `double` 类型还提供可表示非数字和无穷大值的常量。</span><span class="sxs-lookup"><span data-stu-id="09ca5-128">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="09ca5-129">例如，`double` 类型提供以下常量：<xref:System.Double.NaN?displayProperty=nameWithType>、<xref:System.Double.NegativeInfinity?displayProperty=nameWithType> 和 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="09ca5-129">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="09ca5-130">与 `float` 和 `double` 相比，`decimal` 类型具有更高的精度和更小的范围，因此它适合于财务和货币计算。</span><span class="sxs-lookup"><span data-stu-id="09ca5-130">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="09ca5-131">可以在表达式中混合使用[整型](integral-numeric-types.md)类型和浮点类型。</span><span class="sxs-lookup"><span data-stu-id="09ca5-131">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="09ca5-132">在这种情况下，整数类型将转换为浮点类型。</span><span class="sxs-lookup"><span data-stu-id="09ca5-132">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="09ca5-133">根据以下规则对表达式求值：</span><span class="sxs-lookup"><span data-stu-id="09ca5-133">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="09ca5-134">如果其中一个浮点类型是 `double`，该表达式在关系比较和相等比较中求值类型为 `double` 或 [bool](../keywords/bool.md)。</span><span class="sxs-lookup"><span data-stu-id="09ca5-134">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="09ca5-135">如果表达式中没有 `double` 类型，则表达式在关系比较和相等比较中求值类型为 `float` 或 [bool](../keywords/bool.md)。</span><span class="sxs-lookup"><span data-stu-id="09ca5-135">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational and equality comparisons.</span></span>

<span data-ttu-id="09ca5-136">浮点表达式可以包含下列值集：</span><span class="sxs-lookup"><span data-stu-id="09ca5-136">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="09ca5-137">正和负零</span><span class="sxs-lookup"><span data-stu-id="09ca5-137">Positive and negative zero</span></span>
- <span data-ttu-id="09ca5-138">正和负无穷大</span><span class="sxs-lookup"><span data-stu-id="09ca5-138">Positive and negative infinity</span></span>
- <span data-ttu-id="09ca5-139">非数字值 (NaN)</span><span class="sxs-lookup"><span data-stu-id="09ca5-139">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="09ca5-140">一组有限的非零值</span><span class="sxs-lookup"><span data-stu-id="09ca5-140">The finite set of nonzero values</span></span>

<span data-ttu-id="09ca5-141">有关这些值的详细信息，请参阅 [IEEE](https://www.ieee.org) 网站中提供的二进制浮点算术的 IEEE 标准。</span><span class="sxs-lookup"><span data-stu-id="09ca5-141">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="09ca5-142">可以使用[标准数字格式字符串](../../../standard/base-types/standard-numeric-format-strings.md)或[自定义数字格式字符串](../../../standard/base-types/custom-numeric-format-strings.md)设置浮点值的格式。</span><span class="sxs-lookup"><span data-stu-id="09ca5-142">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="09ca5-143">真实文本</span><span class="sxs-lookup"><span data-stu-id="09ca5-143">Real literals</span></span>

<span data-ttu-id="09ca5-144">真实文本的类型由其后缀确定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="09ca5-144">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="09ca5-145">不带后缀的文本或带有 `d` 或 `D` 后缀的文本的类型为 `double`</span><span class="sxs-lookup"><span data-stu-id="09ca5-145">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="09ca5-146">带有 `f` 或 `F` 后缀的文本的类型为 `float`</span><span class="sxs-lookup"><span data-stu-id="09ca5-146">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="09ca5-147">带有 `m` 或 `M` 后缀的文本的类型为 `decimal`</span><span class="sxs-lookup"><span data-stu-id="09ca5-147">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="09ca5-148">下面的代码演示每种类型的示例：</span><span class="sxs-lookup"><span data-stu-id="09ca5-148">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="09ca5-149">前面的示例还演示了如何将 `_` 用作*数字分隔符*（从 C# 7.0 开始支持）。</span><span class="sxs-lookup"><span data-stu-id="09ca5-149">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="09ca5-150">可以将数字分隔符用于所有类型的数字文本。</span><span class="sxs-lookup"><span data-stu-id="09ca5-150">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="09ca5-151">还可以使用科学记数法，即指定真实文本的指数部分，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="09ca5-151">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="09ca5-152">转换</span><span class="sxs-lookup"><span data-stu-id="09ca5-152">Conversions</span></span>

<span data-ttu-id="09ca5-153">存在从 `float` 到 `double` 的隐式转换（称为扩大转换），因为 `float` 值的范围是 `double` 的正确子集，并且从 `float` 到 `double` 不会丢失精度  。</span><span class="sxs-lookup"><span data-stu-id="09ca5-153">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span>

<span data-ttu-id="09ca5-154">未定义从源类型到目标类型的隐式转换时，必须使用显式强制转换将一个浮点类型转换为另一个浮点类型。</span><span class="sxs-lookup"><span data-stu-id="09ca5-154">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="09ca5-155">这称为收缩转换  。</span><span class="sxs-lookup"><span data-stu-id="09ca5-155">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="09ca5-156">由于转换可能导致数据丢失，因此必须使用显式用例。</span><span class="sxs-lookup"><span data-stu-id="09ca5-156">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="09ca5-157">其他浮点类型与 `decimal` 类型之间不存在隐式转换，因为 `decimal` 类型的精度高于 `float` 或 `double`。</span><span class="sxs-lookup"><span data-stu-id="09ca5-157">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="09ca5-158">有关隐式数值转换的详细信息，请参阅[隐式数值转换表](../keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="09ca5-158">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="09ca5-159">有关显式数值转换的详细信息，请参阅[显式数值转换表](../keywords/explicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="09ca5-159">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="09ca5-160">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="09ca5-160">C# language specification</span></span>

<span data-ttu-id="09ca5-161">有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：</span><span class="sxs-lookup"><span data-stu-id="09ca5-161">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="09ca5-162">浮点类型</span><span class="sxs-lookup"><span data-stu-id="09ca5-162">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- [<span data-ttu-id="09ca5-163">十进制类型</span><span class="sxs-lookup"><span data-stu-id="09ca5-163">The decimal type</span></span>](~/_csharplang/spec/types.md#the-decimal-type)
- [<span data-ttu-id="09ca5-164">真实文本</span><span class="sxs-lookup"><span data-stu-id="09ca5-164">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="09ca5-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="09ca5-165">See also</span></span>

- [<span data-ttu-id="09ca5-166">C# 参考</span><span class="sxs-lookup"><span data-stu-id="09ca5-166">C# reference</span></span>](../index.md)
- [<span data-ttu-id="09ca5-167">整型类型</span><span class="sxs-lookup"><span data-stu-id="09ca5-167">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="09ca5-168">内置类型表</span><span class="sxs-lookup"><span data-stu-id="09ca5-168">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="09ca5-169">.NET 中的数字</span><span class="sxs-lookup"><span data-stu-id="09ca5-169">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="09ca5-170">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="09ca5-170">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="09ca5-171">设置数值结果表的格式</span><span class="sxs-lookup"><span data-stu-id="09ca5-171">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="09ca5-172">标准数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="09ca5-172">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
