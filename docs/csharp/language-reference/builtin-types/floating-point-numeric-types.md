---
title: 浮点数值类型 - C# 引用
description: 内置 C# 浮点类型概述
ms.date: 10/22/2019
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
ms.openlocfilehash: 4d71f7eea3f574e483dc4250f5c87e1ffd551f2f
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771907"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="8cf16-103">浮点数值类型（C# 引用）</span><span class="sxs-lookup"><span data-stu-id="8cf16-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="8cf16-104">“浮点类型”是“简单类型”的子集，可以使用[文本](#real-literals)**进行初始化**   。</span><span class="sxs-lookup"><span data-stu-id="8cf16-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#real-literals).</span></span> <span data-ttu-id="8cf16-105">所有浮点类型也是值类型。</span><span class="sxs-lookup"><span data-stu-id="8cf16-105">All floating-point types are also value types.</span></span> <span data-ttu-id="8cf16-106">所有浮点数值类型都支持[算术](../operators/arithmetic-operators.md)、[比较](../operators/comparison-operators.md)和[相等](../operators/equality-operators.md)运算符。</span><span class="sxs-lookup"><span data-stu-id="8cf16-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="8cf16-107">浮点类型的特征</span><span class="sxs-lookup"><span data-stu-id="8cf16-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="8cf16-108">C# 支持以下预定义浮点类型：</span><span class="sxs-lookup"><span data-stu-id="8cf16-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="8cf16-109">C# 类型/关键字</span><span class="sxs-lookup"><span data-stu-id="8cf16-109">C# type/keyword</span></span>|<span data-ttu-id="8cf16-110">大致范围</span><span class="sxs-lookup"><span data-stu-id="8cf16-110">Approximate range</span></span>|<span data-ttu-id="8cf16-111">精度</span><span class="sxs-lookup"><span data-stu-id="8cf16-111">Precision</span></span>|<span data-ttu-id="8cf16-112">大小</span><span class="sxs-lookup"><span data-stu-id="8cf16-112">Size</span></span>|<span data-ttu-id="8cf16-113">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="8cf16-113">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="8cf16-114">±1.5 x 10<sup>−45</sup> 至 ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="8cf16-114">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="8cf16-115">大约 6-9 位数字</span><span class="sxs-lookup"><span data-stu-id="8cf16-115">~6-9 digits</span></span>|<span data-ttu-id="8cf16-116">4 个字节</span><span class="sxs-lookup"><span data-stu-id="8cf16-116">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="8cf16-117">±5.0 × 10<sup>−324</sup> 到 ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="8cf16-117">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="8cf16-118">大约 15-17 位数字</span><span class="sxs-lookup"><span data-stu-id="8cf16-118">~15-17 digits</span></span>|<span data-ttu-id="8cf16-119">8 个字节</span><span class="sxs-lookup"><span data-stu-id="8cf16-119">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="8cf16-120">±1.0 x 10<sup>-28</sup> 至 ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="8cf16-120">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="8cf16-121">28-29 位</span><span class="sxs-lookup"><span data-stu-id="8cf16-121">28-29 digits</span></span>|<span data-ttu-id="8cf16-122">16 个字节</span><span class="sxs-lookup"><span data-stu-id="8cf16-122">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="8cf16-123">在上表中，最左侧列中的每个 C# 类型关键字都是相应 .NET 类型的别名。</span><span class="sxs-lookup"><span data-stu-id="8cf16-123">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="8cf16-124">它们是可互换的。</span><span class="sxs-lookup"><span data-stu-id="8cf16-124">They are interchangeable.</span></span> <span data-ttu-id="8cf16-125">例如，以下声明声明了相同类型的变量：</span><span class="sxs-lookup"><span data-stu-id="8cf16-125">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="8cf16-126">每个浮点类型的默认值都为零，`0`。</span><span class="sxs-lookup"><span data-stu-id="8cf16-126">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="8cf16-127">每个浮点类型都有 `MinValue` 和 `MaxValue` 常量，提供该类型的最小值和最大有限值。</span><span class="sxs-lookup"><span data-stu-id="8cf16-127">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="8cf16-128">`float` and `double` 类型还提供可表示非数字和无穷大值的常量。</span><span class="sxs-lookup"><span data-stu-id="8cf16-128">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="8cf16-129">例如，`double` 类型提供以下常量：<xref:System.Double.NaN?displayProperty=nameWithType>、<xref:System.Double.NegativeInfinity?displayProperty=nameWithType> 和 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="8cf16-129">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="8cf16-130">与 `float` 和 `double` 相比，`decimal` 类型具有更高的精度和更小的范围，因此它适合于财务和货币计算。</span><span class="sxs-lookup"><span data-stu-id="8cf16-130">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="8cf16-131">可以在表达式中混合使用[整型](integral-numeric-types.md)类型和浮点类型。</span><span class="sxs-lookup"><span data-stu-id="8cf16-131">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="8cf16-132">在这种情况下，整数类型将转换为浮点类型。</span><span class="sxs-lookup"><span data-stu-id="8cf16-132">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="8cf16-133">根据以下规则对表达式求值：</span><span class="sxs-lookup"><span data-stu-id="8cf16-133">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="8cf16-134">如果其中一个浮点类型是 `double`，该表达式在关系比较和相等比较中求值类型为 `double` 或 [bool](../keywords/bool.md)。</span><span class="sxs-lookup"><span data-stu-id="8cf16-134">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="8cf16-135">如果表达式中没有 `double` 类型，则表达式在关系比较和相等比较中求值类型为 `float` 或 [bool](../keywords/bool.md)。</span><span class="sxs-lookup"><span data-stu-id="8cf16-135">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational and equality comparisons.</span></span>

<span data-ttu-id="8cf16-136">浮点表达式可以包含下列值集：</span><span class="sxs-lookup"><span data-stu-id="8cf16-136">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="8cf16-137">正和负零</span><span class="sxs-lookup"><span data-stu-id="8cf16-137">Positive and negative zero</span></span>
- <span data-ttu-id="8cf16-138">正和负无穷大</span><span class="sxs-lookup"><span data-stu-id="8cf16-138">Positive and negative infinity</span></span>
- <span data-ttu-id="8cf16-139">非数字值 (NaN)</span><span class="sxs-lookup"><span data-stu-id="8cf16-139">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="8cf16-140">一组有限的非零值</span><span class="sxs-lookup"><span data-stu-id="8cf16-140">The finite set of nonzero values</span></span>

<span data-ttu-id="8cf16-141">有关这些值的详细信息，请参阅 [IEEE](https://www.ieee.org) 网站中提供的二进制浮点算术的 IEEE 标准。</span><span class="sxs-lookup"><span data-stu-id="8cf16-141">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="8cf16-142">可以使用[标准数字格式字符串](../../../standard/base-types/standard-numeric-format-strings.md)或[自定义数字格式字符串](../../../standard/base-types/custom-numeric-format-strings.md)设置浮点值的格式。</span><span class="sxs-lookup"><span data-stu-id="8cf16-142">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="8cf16-143">真实文本</span><span class="sxs-lookup"><span data-stu-id="8cf16-143">Real literals</span></span>

<span data-ttu-id="8cf16-144">真实文本的类型由其后缀确定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8cf16-144">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="8cf16-145">不带后缀的文本或带有 `d` 或 `D` 后缀的文本的类型为 `double`</span><span class="sxs-lookup"><span data-stu-id="8cf16-145">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="8cf16-146">带有 `f` 或 `F` 后缀的文本的类型为 `float`</span><span class="sxs-lookup"><span data-stu-id="8cf16-146">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="8cf16-147">带有 `m` 或 `M` 后缀的文本的类型为 `decimal`</span><span class="sxs-lookup"><span data-stu-id="8cf16-147">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="8cf16-148">下面的代码演示每种类型的示例：</span><span class="sxs-lookup"><span data-stu-id="8cf16-148">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="8cf16-149">前面的示例还演示了如何将 `_` 用作数字分隔符  （从 C# 7.0 开始提供支持）。</span><span class="sxs-lookup"><span data-stu-id="8cf16-149">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="8cf16-150">可以将数字分隔符用于所有类型的数字文本。</span><span class="sxs-lookup"><span data-stu-id="8cf16-150">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="8cf16-151">还可以使用科学记数法，即指定真实文本的指数部分，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="8cf16-151">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="8cf16-152">转换</span><span class="sxs-lookup"><span data-stu-id="8cf16-152">Conversions</span></span>

<span data-ttu-id="8cf16-153">浮点数值类型之间只有一种隐式转换：从 `float` 到 `double`。</span><span class="sxs-lookup"><span data-stu-id="8cf16-153">There is only one implicit conversion between floating-point numeric types: from `float` to `double`.</span></span> <span data-ttu-id="8cf16-154">但是，可以使用[显式强制转换](../operators/type-testing-and-cast.md#cast-operator-)将任何浮点类型转换为任何其他浮点类型。</span><span class="sxs-lookup"><span data-stu-id="8cf16-154">However, you can convert any floating-point type to any other floating-point type with the [explicit cast](../operators/type-testing-and-cast.md#cast-operator-).</span></span> <span data-ttu-id="8cf16-155">有关详细信息，请参阅[内置数值转换](numeric-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="8cf16-155">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8cf16-156">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="8cf16-156">C# language specification</span></span>

<span data-ttu-id="8cf16-157">有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：</span><span class="sxs-lookup"><span data-stu-id="8cf16-157">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="8cf16-158">浮点类型</span><span class="sxs-lookup"><span data-stu-id="8cf16-158">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- [<span data-ttu-id="8cf16-159">十进制类型</span><span class="sxs-lookup"><span data-stu-id="8cf16-159">The decimal type</span></span>](~/_csharplang/spec/types.md#the-decimal-type)
- [<span data-ttu-id="8cf16-160">真实文本</span><span class="sxs-lookup"><span data-stu-id="8cf16-160">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="8cf16-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="8cf16-161">See also</span></span>

- [<span data-ttu-id="8cf16-162">C# 参考</span><span class="sxs-lookup"><span data-stu-id="8cf16-162">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8cf16-163">内置类型表</span><span class="sxs-lookup"><span data-stu-id="8cf16-163">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="8cf16-164">整型类型</span><span class="sxs-lookup"><span data-stu-id="8cf16-164">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="8cf16-165">设置数值结果表的格式</span><span class="sxs-lookup"><span data-stu-id="8cf16-165">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="8cf16-166">标准数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="8cf16-166">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="8cf16-167">.NET 中的数字</span><span class="sxs-lookup"><span data-stu-id="8cf16-167">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
