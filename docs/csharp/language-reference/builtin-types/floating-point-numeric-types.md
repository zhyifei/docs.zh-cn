---
title: 浮点数值类型 - C# 引用
description: 内置 C# 浮点类型概述
ms.date: 06/30/2019
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
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 0d97b3ffd587e8398e5572706a47937716a6e709
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236059"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="00864-103">浮点数值类型（C# 引用）</span><span class="sxs-lookup"><span data-stu-id="00864-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="00864-104">“浮点类型”是“简单类型”的子集，可以使用[文本](#floating-point-literals)**进行初始化**   。</span><span class="sxs-lookup"><span data-stu-id="00864-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#floating-point-literals).</span></span> <span data-ttu-id="00864-105">所有浮点类型也是值类型。</span><span class="sxs-lookup"><span data-stu-id="00864-105">All floating-point types are also value types.</span></span> <span data-ttu-id="00864-106">所有浮点数值类型都支持[算术](../operators/arithmetic-operators.md)、[比较和相等](../operators/equality-operators.md)运算符。</span><span class="sxs-lookup"><span data-stu-id="00864-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="00864-107">浮点类型的特征</span><span class="sxs-lookup"><span data-stu-id="00864-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="00864-108">C# 支持以下预定义浮点类型：</span><span class="sxs-lookup"><span data-stu-id="00864-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="00864-109">C# 类型/关键字</span><span class="sxs-lookup"><span data-stu-id="00864-109">C# type/keyword</span></span>|<span data-ttu-id="00864-110">大致范围</span><span class="sxs-lookup"><span data-stu-id="00864-110">Approximate range</span></span>|<span data-ttu-id="00864-111">精度</span><span class="sxs-lookup"><span data-stu-id="00864-111">Precision</span></span>|<span data-ttu-id="00864-112">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="00864-112">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|
|`float`|<span data-ttu-id="00864-113">±1.5 x 10<sup>−45</sup> 至 ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="00864-113">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="00864-114">大约 6-9 位数字</span><span class="sxs-lookup"><span data-stu-id="00864-114">~6-9 digits</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="00864-115">±5.0 × 10<sup>−324</sup> 到 ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="00864-115">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="00864-116">大约 15-17 位数字</span><span class="sxs-lookup"><span data-stu-id="00864-116">~15-17 digits</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="00864-117">±1.0 x 10<sup>-28</sup> 至 ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="00864-117">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="00864-118">28-29 位</span><span class="sxs-lookup"><span data-stu-id="00864-118">28-29 digits</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="00864-119">在上表中，最左侧列中的每个 C# 类型关键字都是相应 .NET 类型的别名。</span><span class="sxs-lookup"><span data-stu-id="00864-119">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="00864-120">它们是可互换的。</span><span class="sxs-lookup"><span data-stu-id="00864-120">They are interchangeable.</span></span> <span data-ttu-id="00864-121">例如，以下声明声明了相同类型的变量：</span><span class="sxs-lookup"><span data-stu-id="00864-121">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="00864-122">每个浮点类型的默认值都为零，`0`。</span><span class="sxs-lookup"><span data-stu-id="00864-122">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="00864-123">每个浮点类型都有 `MinValue` 和 `MaxValue` 常量，提供该类型的最小值和最大有限值。</span><span class="sxs-lookup"><span data-stu-id="00864-123">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="00864-124">`float` and `double` 类型还提供可表示非数字和无穷大值的常量。</span><span class="sxs-lookup"><span data-stu-id="00864-124">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="00864-125">例如，`double` 类型提供以下常量：<xref:System.Double.NaN?displayProperty=nameWithType>、<xref:System.Double.NegativeInfinity?displayProperty=nameWithType> 和 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="00864-125">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="00864-126">与 `float` 和 `double` 相比，`decimal` 类型具有更高的精度和更小的范围，因此它适合于财务和货币计算。</span><span class="sxs-lookup"><span data-stu-id="00864-126">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="00864-127">可以在表达式中混合使用[整型](integral-numeric-types.md)类型和浮点类型。</span><span class="sxs-lookup"><span data-stu-id="00864-127">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="00864-128">在这种情况下，整数类型将转换为浮点类型。</span><span class="sxs-lookup"><span data-stu-id="00864-128">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="00864-129">根据以下规则对表达式求值：</span><span class="sxs-lookup"><span data-stu-id="00864-129">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="00864-130">如果其中一个浮点类型是 `double`，该表达式在关系比较或相等比较中求值类型为 `double` 或 [bool](../keywords/bool.md)。</span><span class="sxs-lookup"><span data-stu-id="00864-130">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>
- <span data-ttu-id="00864-131">如果表达式中没有 `double` 类型，则表达式在关系比较或相等比较中求值类型为 `float` 或 [bool](../keywords/bool.md)。</span><span class="sxs-lookup"><span data-stu-id="00864-131">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="00864-132">浮点表达式可以包含下列值集：</span><span class="sxs-lookup"><span data-stu-id="00864-132">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="00864-133">正和负零</span><span class="sxs-lookup"><span data-stu-id="00864-133">Positive and negative zero</span></span>
- <span data-ttu-id="00864-134">正和负无穷大</span><span class="sxs-lookup"><span data-stu-id="00864-134">Positive and negative infinity</span></span>
- <span data-ttu-id="00864-135">非数字值 (NaN)</span><span class="sxs-lookup"><span data-stu-id="00864-135">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="00864-136">一组有限的非零值</span><span class="sxs-lookup"><span data-stu-id="00864-136">The finite set of nonzero values</span></span>

<span data-ttu-id="00864-137">有关这些值的详细信息，请参阅 [IEEE](https://www.ieee.org) 网站中提供的二进制浮点算术的 IEEE 标准。</span><span class="sxs-lookup"><span data-stu-id="00864-137">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="00864-138">可以使用[标准数字格式字符串](../../../standard/base-types/standard-numeric-format-strings.md)或[自定义数字格式字符串](../../../standard/base-types/custom-numeric-format-strings.md)设置浮点值的格式。</span><span class="sxs-lookup"><span data-stu-id="00864-138">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="floating-point-literals"></a><span data-ttu-id="00864-139">浮点文本</span><span class="sxs-lookup"><span data-stu-id="00864-139">Floating-point literals</span></span>

<span data-ttu-id="00864-140">默认情况下，赋值运算符右侧的浮点数值文本被视为 `double`。</span><span class="sxs-lookup"><span data-stu-id="00864-140">By default, a floating-point numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="00864-141">后缀可用于将浮点或整型文本转换为特定类型：</span><span class="sxs-lookup"><span data-stu-id="00864-141">You can use suffixes to convert a floating-point or integral literal to a specific type:</span></span>

- <span data-ttu-id="00864-142">`d` 或 `D` 后缀用于将文本转换为 `double`。</span><span class="sxs-lookup"><span data-stu-id="00864-142">The `d` or `D` suffix converts a literal to a `double`.</span></span>
- <span data-ttu-id="00864-143">`f` 或 `F` 后缀用于将文本转换为 `float`。</span><span class="sxs-lookup"><span data-stu-id="00864-143">The `f` or `F` suffix converts a literal to a `float`.</span></span>
- <span data-ttu-id="00864-144">`m` 或 `M` 后缀用于将文本转换为 `decimal`。</span><span class="sxs-lookup"><span data-stu-id="00864-144">The `m` or `M` suffix converts a literal to a `decimal`.</span></span>

<span data-ttu-id="00864-145">下面的示例显示了每种后缀：</span><span class="sxs-lookup"><span data-stu-id="00864-145">The following examples show each suffix:</span></span>

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a><span data-ttu-id="00864-146">转换</span><span class="sxs-lookup"><span data-stu-id="00864-146">Conversions</span></span>

<span data-ttu-id="00864-147">存在从 `float` 到 `double` 的隐式转换（称为扩大转换），因为 `float` 值的范围是 `double` 的正确子集，并且从 `float` 到 `double` 不会丢失精度  。</span><span class="sxs-lookup"><span data-stu-id="00864-147">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span>

<span data-ttu-id="00864-148">未定义从源类型到目标类型的隐式转换时，必须使用显式强制转换将一个浮点类型转换为另一个浮点类型。</span><span class="sxs-lookup"><span data-stu-id="00864-148">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="00864-149">这称为收缩转换  。</span><span class="sxs-lookup"><span data-stu-id="00864-149">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="00864-150">由于转换可能导致数据丢失，因此必须使用显式用例。</span><span class="sxs-lookup"><span data-stu-id="00864-150">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="00864-151">其他浮点类型与 `decimal` 类型之间不存在隐式转换，因为 `decimal` 类型的精度高于 `float` 或 `double`。</span><span class="sxs-lookup"><span data-stu-id="00864-151">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="00864-152">有关隐式数值转换的详细信息，请参阅[隐式数值转换表](../keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="00864-152">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="00864-153">有关显式数值转换的详细信息，请参阅[显式数值转换表](../keywords/explicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="00864-153">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="00864-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="00864-154">See also</span></span>

- [<span data-ttu-id="00864-155">C# 参考</span><span class="sxs-lookup"><span data-stu-id="00864-155">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="00864-156">整型类型</span><span class="sxs-lookup"><span data-stu-id="00864-156">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="00864-157">内置类型表</span><span class="sxs-lookup"><span data-stu-id="00864-157">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="00864-158">.NET 中的数字</span><span class="sxs-lookup"><span data-stu-id="00864-158">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="00864-159">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="00864-159">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="00864-160">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="00864-160">Implicit Numeric Conversions Table</span></span>](../keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="00864-161">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="00864-161">Explicit Numeric Conversions Table</span></span>](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="00864-162">设置数值结果表的格式</span><span class="sxs-lookup"><span data-stu-id="00864-162">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="00864-163">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="00864-163">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
