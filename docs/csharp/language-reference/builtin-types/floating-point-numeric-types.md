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
# <a name="floating-point-numeric-types-c-reference"></a>浮点数值类型（C# 引用）

“浮点类型”是“简单类型”的子集，可以使用[文本](#real-literals)**进行初始化**   。 所有浮点类型也是值类型。 所有浮点数值类型都支持[算术](../operators/arithmetic-operators.md)、[比较](../operators/comparison-operators.md)和[相等](../operators/equality-operators.md)运算符。

## <a name="characteristics-of-the-floating-point-types"></a>浮点类型的特征

C# 支持以下预定义浮点类型：
  
|C# 类型/关键字|大致范围|精度|大小|.NET 类型|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|±1.5 x 10<sup>−45</sup> 至 ±3.4 x 10<sup>38</sup>|大约 6-9 位数字|4 个字节|<xref:System.Single?displayProperty=nameWithType>|
|`double`|±5.0 × 10<sup>−324</sup> 到 ±1.7 × 10<sup>308</sup>|大约 15-17 位数字|8 个字节|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|±1.0 x 10<sup>-28</sup> 至 ±7.9228 x 10<sup>28</sup>|28-29 位|16 个字节|<xref:System.Decimal?displayProperty=nameWithType>|

在上表中，最左侧列中的每个 C# 类型关键字都是相应 .NET 类型的别名。 它们是可互换的。 例如，以下声明声明了相同类型的变量：

```csharp
double a = 12.3;
System.Double b = 12.3;
```

每个浮点类型的默认值都为零，`0`。 每个浮点类型都有 `MinValue` 和 `MaxValue` 常量，提供该类型的最小值和最大有限值。 `float` and `double` 类型还提供可表示非数字和无穷大值的常量。 例如，`double` 类型提供以下常量：<xref:System.Double.NaN?displayProperty=nameWithType>、<xref:System.Double.NegativeInfinity?displayProperty=nameWithType> 和 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>。

与 `float` 和 `double` 相比，`decimal` 类型具有更高的精度和更小的范围，因此它适合于财务和货币计算。

可以在表达式中混合使用[整型](integral-numeric-types.md)类型和浮点类型。 在这种情况下，整数类型将转换为浮点类型。 根据以下规则对表达式求值：

- 如果其中一个浮点类型是 `double`，该表达式在关系比较和相等比较中求值类型为 `double` 或 [bool](../keywords/bool.md)。
- 如果表达式中没有 `double` 类型，则表达式在关系比较和相等比较中求值类型为 `float` 或 [bool](../keywords/bool.md)。

浮点表达式可以包含下列值集：

- 正和负零
- 正和负无穷大
- 非数字值 (NaN)
- 一组有限的非零值

有关这些值的详细信息，请参阅 [IEEE](https://www.ieee.org) 网站中提供的二进制浮点算术的 IEEE 标准。

可以使用[标准数字格式字符串](../../../standard/base-types/standard-numeric-format-strings.md)或[自定义数字格式字符串](../../../standard/base-types/custom-numeric-format-strings.md)设置浮点值的格式。

## <a name="real-literals"></a>真实文本

真实文本的类型由其后缀确定，如下所示：

- 不带后缀的文本或带有 `d` 或 `D` 后缀的文本的类型为 `double`
- 带有 `f` 或 `F` 后缀的文本的类型为 `float`
- 带有 `m` 或 `M` 后缀的文本的类型为 `decimal`

下面的代码演示每种类型的示例：

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

前面的示例还演示了如何将 `_` 用作*数字分隔符*（从 C# 7.0 开始支持）。 可以将数字分隔符用于所有类型的数字文本。

还可以使用科学记数法，即指定真实文本的指数部分，如以下示例所示：

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a>转换

存在从 `float` 到 `double` 的隐式转换（称为扩大转换），因为 `float` 值的范围是 `double` 的正确子集，并且从 `float` 到 `double` 不会丢失精度  。

未定义从源类型到目标类型的隐式转换时，必须使用显式强制转换将一个浮点类型转换为另一个浮点类型。 这称为收缩转换  。 由于转换可能导致数据丢失，因此必须使用显式用例。 其他浮点类型与 `decimal` 类型之间不存在隐式转换，因为 `decimal` 类型的精度高于 `float` 或 `double`。

有关隐式数值转换的详细信息，请参阅[隐式数值转换表](../keywords/implicit-numeric-conversions-table.md)。

有关显式数值转换的详细信息，请参阅[显式数值转换表](../keywords/explicit-numeric-conversions-table.md)。

## <a name="c-language-specification"></a>C# 语言规范

有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：

- [浮点类型](~/_csharplang/spec/types.md#floating-point-types)
- [十进制类型](~/_csharplang/spec/types.md#the-decimal-type)
- [真实文本](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [整型类型](integral-numeric-types.md)
- [内置类型表](../keywords/built-in-types-table.md)
- [.NET 中的数字](../../../standard/numerics.md)
- [强制转换和类型转换](../../programming-guide/types/casting-and-type-conversions.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [设置数值结果表的格式](../keywords/formatting-numeric-results-table.md)
- [标准数字格式字符串](../../../standard/base-types/standard-numeric-format-strings.md)
