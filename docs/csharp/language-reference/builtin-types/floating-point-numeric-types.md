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
ms.openlocfilehash: 738368abd9db75fbd97d1913324cab3b6e869c56
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "67664187"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="bbfe6-103">浮点数值类型（C# 引用）</span><span class="sxs-lookup"><span data-stu-id="bbfe6-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="bbfe6-104">“浮点类型”是“简单类型”的子集，可以使用[文本](#floating-point-literals)**进行初始化**   。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#floating-point-literals).</span></span> <span data-ttu-id="bbfe6-105">所有浮点类型也是值类型。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-105">All floating-point types are also value types.</span></span> <span data-ttu-id="bbfe6-106">所有浮点数值类型都支持[算术](../operators/arithmetic-operators.md)、[比较和相等](../operators/equality-operators.md)运算符。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md) [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

<span data-ttu-id="bbfe6-107">下表显示了浮点类型的精度和大致范围：</span><span class="sxs-lookup"><span data-stu-id="bbfe6-107">The following table shows the precision and approximate ranges for the floating-point types:</span></span>
  
|<span data-ttu-id="bbfe6-108">类型</span><span class="sxs-lookup"><span data-stu-id="bbfe6-108">Type</span></span>|<span data-ttu-id="bbfe6-109">大致范围</span><span class="sxs-lookup"><span data-stu-id="bbfe6-109">Approximate range</span></span>|<span data-ttu-id="bbfe6-110">精度</span><span class="sxs-lookup"><span data-stu-id="bbfe6-110">Precision</span></span>|  
|----------|-----------------------|---------------|  
|`float`|<span data-ttu-id="bbfe6-111">±1.5 x 10<sup>−45</sup> 至 ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="bbfe6-111">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="bbfe6-112">大约 6-9 位数字</span><span class="sxs-lookup"><span data-stu-id="bbfe6-112">~6-9 digits</span></span>|  
|`double`|<span data-ttu-id="bbfe6-113">±5.0 × 10<sup>−324</sup> 到 ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="bbfe6-113">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="bbfe6-114">大约 15-17 位数字</span><span class="sxs-lookup"><span data-stu-id="bbfe6-114">~15-17 digits</span></span>|  
|`decimal`|<span data-ttu-id="bbfe6-115">±1.0 x 10<sup>-28</sup> 至 ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="bbfe6-115">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="bbfe6-116">28-29 位</span><span class="sxs-lookup"><span data-stu-id="bbfe6-116">28-29 digits</span></span>|  

<span data-ttu-id="bbfe6-117">所有浮点类型的默认值都为 `0`。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-117">The default value for all floating-point types is `0`.</span></span> <span data-ttu-id="bbfe6-118">每个浮点类型都有名为 `MinValue` 和 `MaxValue` 的常量，分别表示该类型的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-118">Each of the floating-point types has constants named `MinValue` and `MaxValue` for the minimum and maximum value for that type.</span></span> <span data-ttu-id="bbfe6-119">`float` 和 `double` 类型包括 `PositiveInfinity`、`NegativeInfinity` 和 `NaN` 其他常量（适用于“非数字”）。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-119">The `float` and `double` types have additional constants for `PositiveInfinity`, `NegativeInfinity`, and `NaN` (for "Not a Number").</span></span> <span data-ttu-id="bbfe6-120">`decimal` 类型包括 `Zero`、`One` 和 `MinusOne` 常量。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-120">The `decimal` type includes constants for `Zero`, `One`, and `MinusOne`.</span></span>

<span data-ttu-id="bbfe6-121">与 `float` 和 `double` 相比，`decimal` 类型具有更高的精度和更小的范围，这使它适合于财务和货币计算。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-121">The `decimal` type has more precision and a smaller range than both `float` and `double`, which makes it appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="bbfe6-122">可以在表达式中混合使用整型类型和浮点类型。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-122">You can mix integral types and floating-point types in an expression.</span></span> <span data-ttu-id="bbfe6-123">在这种情况下，整数类型将转换为浮点类型。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-123">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="bbfe6-124">根据以下规则对表达式求值：</span><span class="sxs-lookup"><span data-stu-id="bbfe6-124">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="bbfe6-125">如果其中一个浮点类型是 `double`，该表达式在关系比较或相等比较中求值类型为 `double` 或 [bool](../keywords/bool.md)。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-125">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>
- <span data-ttu-id="bbfe6-126">如果表达式中没有 `double` 类型，则表达式在关系比较或相等比较中求值类型为 `float` 或 [bool](../keywords/bool.md)。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-126">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="bbfe6-127">浮点表达式可以包含下列值集：</span><span class="sxs-lookup"><span data-stu-id="bbfe6-127">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="bbfe6-128">正和负零</span><span class="sxs-lookup"><span data-stu-id="bbfe6-128">Positive and negative zero</span></span>
- <span data-ttu-id="bbfe6-129">正和负无穷大</span><span class="sxs-lookup"><span data-stu-id="bbfe6-129">Positive and negative infinity</span></span>
- <span data-ttu-id="bbfe6-130">非数字值 (NaN)</span><span class="sxs-lookup"><span data-stu-id="bbfe6-130">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="bbfe6-131">一组有限的非零值</span><span class="sxs-lookup"><span data-stu-id="bbfe6-131">The finite set of nonzero values</span></span>

<span data-ttu-id="bbfe6-132">有关这些值的详细信息，请参阅 [IEEE](https://www.ieee.org) 网站中提供的二进制浮点算术的 IEEE 标准。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-132">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="bbfe6-133">可以使用[标准数字格式字符串](../../../standard/base-types/standard-numeric-format-strings.md)或[自定义数字格式字符串](../../../standard/base-types/custom-numeric-format-strings.md)设置浮点值的格式。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-133">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="floating-point-literals"></a><span data-ttu-id="bbfe6-134">浮点文本</span><span class="sxs-lookup"><span data-stu-id="bbfe6-134">Floating-point literals</span></span>

<span data-ttu-id="bbfe6-135">默认情况下，赋值运算符右侧的浮点数值文本被视为 `double`。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-135">By default, a floating-point numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="bbfe6-136">后缀可用于将浮点或整型文本转换为特定类型：</span><span class="sxs-lookup"><span data-stu-id="bbfe6-136">You can use suffixes to convert a floating-point or integral literal to a specific type:</span></span>

- <span data-ttu-id="bbfe6-137">`d` 或 `D` 后缀用于将文本转换为 `double`。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-137">The `d` or `D` suffix converts a literal to a `double`.</span></span>
- <span data-ttu-id="bbfe6-138">`f` 或 `F` 后缀用于将文本转换为 `float`。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-138">The `f` or `F` suffix converts a literal to a `float`.</span></span>
- <span data-ttu-id="bbfe6-139">`m` 或 `M` 后缀用于将文本转换为 `decimal`。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-139">The `m` or `M` suffix converts a literal to a `decimal`.</span></span>

<span data-ttu-id="bbfe6-140">下面的示例显示了每种后缀：</span><span class="sxs-lookup"><span data-stu-id="bbfe6-140">The following examples show each suffix:</span></span>

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a><span data-ttu-id="bbfe6-141">转换</span><span class="sxs-lookup"><span data-stu-id="bbfe6-141">Conversions</span></span>

<span data-ttu-id="bbfe6-142">存在从 `float` 到 `double` 的隐式转换（称为扩大转换），因为 `float` 值的范围是 `double` 的正确子集，并且从 `float` 到 `double` 不会丢失精度  。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-142">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span> 

<span data-ttu-id="bbfe6-143">未定义从源类型到目标类型的隐式转换时，必须使用显式强制转换将一个浮点类型转换为另一个浮点类型。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-143">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="bbfe6-144">这称为收缩转换  。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-144">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="bbfe6-145">由于转换可能导致数据丢失，因此必须使用显式用例。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-145">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="bbfe6-146">其他浮点类型与 `decimal` 类型之间不存在隐式转换，因为 `decimal` 类型的精度高于 `float` 或 `double`。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-146">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="bbfe6-147">有关隐式数值转换的详细信息，请参阅[隐式数值转换表](../keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-147">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="bbfe6-148">有关显式数值转换的详细信息，请参阅[显式数值转换表](../keywords/explicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="bbfe6-148">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bbfe6-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbfe6-149">See also</span></span>

- [<span data-ttu-id="bbfe6-150">C# 参考</span><span class="sxs-lookup"><span data-stu-id="bbfe6-150">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bbfe6-151">整型类型</span><span class="sxs-lookup"><span data-stu-id="bbfe6-151">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="bbfe6-152">默认值表</span><span class="sxs-lookup"><span data-stu-id="bbfe6-152">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="bbfe6-153">设置数值结果表的格式</span><span class="sxs-lookup"><span data-stu-id="bbfe6-153">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="bbfe6-154">内置类型表</span><span class="sxs-lookup"><span data-stu-id="bbfe6-154">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="bbfe6-155">.NET 中的数字</span><span class="sxs-lookup"><span data-stu-id="bbfe6-155">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="bbfe6-156">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="bbfe6-156">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="bbfe6-157">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="bbfe6-157">Implicit Numeric Conversions Table</span></span>](../keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="bbfe6-158">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="bbfe6-158">Explicit Numeric Conversions Table</span></span>](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="bbfe6-159">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="bbfe6-159">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
