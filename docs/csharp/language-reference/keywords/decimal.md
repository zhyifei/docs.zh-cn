---
title: decimal 关键字（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
ms.openlocfilehash: c9d40238ca4c34238d5663185f93afbce73195cf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506514"
---
# <a name="decimal-c-reference"></a><span data-ttu-id="04e7e-102">decimal（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="04e7e-102">decimal (C# Reference)</span></span>

<span data-ttu-id="04e7e-103">`decimal` 关键字指示 128 位数据类型。</span><span class="sxs-lookup"><span data-stu-id="04e7e-103">The `decimal` keyword indicates a 128-bit data type.</span></span> <span data-ttu-id="04e7e-104">与其他浮点型相比，`decimal` 类型具有更高的精度和更小的范围，这使它适合于财务和货币计算。</span><span class="sxs-lookup"><span data-stu-id="04e7e-104">Compared to other floating-point types, the `decimal` type has more precision and a smaller range, which makes it appropriate for financial and monetary calculations.</span></span> <span data-ttu-id="04e7e-105">`decimal` 类型的大致范围和精度如下表所示。</span><span class="sxs-lookup"><span data-stu-id="04e7e-105">The approximate range and precision for the `decimal` type are shown in the following table.</span></span>

|<span data-ttu-id="04e7e-106">类型</span><span class="sxs-lookup"><span data-stu-id="04e7e-106">Type</span></span>|<span data-ttu-id="04e7e-107">大致范围</span><span class="sxs-lookup"><span data-stu-id="04e7e-107">Approximate Range</span></span>|<span data-ttu-id="04e7e-108">精度</span><span class="sxs-lookup"><span data-stu-id="04e7e-108">Precision</span></span>|<span data-ttu-id="04e7e-109">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="04e7e-109">.NET type</span></span>|
|----------|-----------------------|---------------|-------------------------|
|`decimal`|<span data-ttu-id="04e7e-110">±1.0 x 10<sup>-28</sup> 至 ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="04e7e-110">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="04e7e-111">28-29 个有效位</span><span class="sxs-lookup"><span data-stu-id="04e7e-111">28-29 significant digits</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="04e7e-112">`decimal` 的默认值为 0m。</span><span class="sxs-lookup"><span data-stu-id="04e7e-112">The default value of a `decimal` is 0m.</span></span>

## <a name="literals"></a><span data-ttu-id="04e7e-113">文本</span><span class="sxs-lookup"><span data-stu-id="04e7e-113">Literals</span></span>

<span data-ttu-id="04e7e-114">如果希望实数被视为 `decimal` 类型，请使用后缀 m 或 M，例如：</span><span class="sxs-lookup"><span data-stu-id="04e7e-114">If you want a numeric real literal to be treated as `decimal`, use the suffix m or M, for example:</span></span>

```csharp
decimal myMoney = 300.5m;
```

<span data-ttu-id="04e7e-115">如果没有后缀 m，则数字将被视为 [double](../../../csharp/language-reference/keywords/double.md) 类型并会生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="04e7e-115">Without the suffix m, the number is treated as a [double](../../../csharp/language-reference/keywords/double.md) and generates a compiler error.</span></span>

## <a name="conversions"></a><span data-ttu-id="04e7e-116">转换</span><span class="sxs-lookup"><span data-stu-id="04e7e-116">Conversions</span></span>

<span data-ttu-id="04e7e-117">整型将被隐式转换为 `decimal` 类型，其计算结果为 `decimal`。</span><span class="sxs-lookup"><span data-stu-id="04e7e-117">The integral types are implicitly converted to `decimal` and the result evaluates to `decimal`.</span></span> <span data-ttu-id="04e7e-118">因此，你可以用整数字面量初始化 decimal 变量而不使用后缀，如下所示：</span><span class="sxs-lookup"><span data-stu-id="04e7e-118">Therefore you can initialize a decimal variable using an integer literal, without the suffix, as follows:</span></span>

```csharp
decimal myMoney = 300;
```

<span data-ttu-id="04e7e-119">其他浮点类型和 `decimal` 类型之间不存在隐式转换；因此，必须使用强制转换来转换这两个类型。</span><span class="sxs-lookup"><span data-stu-id="04e7e-119">There is no implicit conversion between other floating-point types and the `decimal` type; therefore, a cast must be used to convert between these two types.</span></span> <span data-ttu-id="04e7e-120">例如:</span><span class="sxs-lookup"><span data-stu-id="04e7e-120">For example:</span></span>

```csharp
decimal myMoney = 99.9m;
double x = (double)myMoney;
myMoney = (decimal)x;
```

<span data-ttu-id="04e7e-121">你还可以在同一表达式中混合使用 `decimal` 和数值整型。</span><span class="sxs-lookup"><span data-stu-id="04e7e-121">You can also mix `decimal` and numeric integral types in the same expression.</span></span> <span data-ttu-id="04e7e-122">但是，不进行强制转换就混合使用 `decimal` 和其他浮点型将导致编译错误。</span><span class="sxs-lookup"><span data-stu-id="04e7e-122">However, mixing `decimal` and other floating-point types without a cast causes a compilation error.</span></span>

<span data-ttu-id="04e7e-123">有关隐式数值转换的详细信息，请参阅[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="04e7e-123">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="04e7e-124">有关显式数值转换的详细信息，请参阅[显式数值转换表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="04e7e-124">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="formatting-decimal-output"></a><span data-ttu-id="04e7e-125">设置十进制输出的格式</span><span class="sxs-lookup"><span data-stu-id="04e7e-125">Formatting decimal output</span></span>

<span data-ttu-id="04e7e-126">你可以通过使用 `String.Format` 方法或 <xref:System.Console.Write%2A?displayProperty=nameWithType> 方法（其调用 `String.Format()`）来设置结果的格式。</span><span class="sxs-lookup"><span data-stu-id="04e7e-126">You can format the results by using the `String.Format` method, or through the <xref:System.Console.Write%2A?displayProperty=nameWithType> method, which calls `String.Format()`.</span></span> <span data-ttu-id="04e7e-127">货币格式是使用标准货币格式字符串“C”或“c”指定的，如本文后面的第二个示例所示。</span><span class="sxs-lookup"><span data-stu-id="04e7e-127">The currency format is specified by using the standard currency format string "C" or "c," as shown in the second example later in this article.</span></span> <span data-ttu-id="04e7e-128">有关 `String.Format` 方法的更多信息，请参见 <xref:System.String.Format%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="04e7e-128">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="04e7e-129">示例</span><span class="sxs-lookup"><span data-stu-id="04e7e-129">Example</span></span>

<span data-ttu-id="04e7e-130">下面的示例尝试添加 [double](../../../csharp/language-reference/keywords/double.md) 和 `decimal` 变量，这会导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="04e7e-130">The following example causes a compiler error by trying to add [double](../../../csharp/language-reference/keywords/double.md) and `decimal` variables.</span></span>

```csharp
decimal dec = 0m;
double dub = 9;
// The following line causes an error that reads "Operator '+' cannot be applied to
// operands of type 'double' and 'decimal'"
Console.WriteLine(dec + dub);

// You can fix the error by using explicit casting of either operand.
Console.WriteLine(dec + (decimal)dub);
Console.WriteLine((double)dec + dub);
```

<span data-ttu-id="04e7e-131">其结果为以下错误：</span><span class="sxs-lookup"><span data-stu-id="04e7e-131">The result is the following error:</span></span>

`Operator '+' cannot be applied to operands of type 'double' and 'decimal'`

<span data-ttu-id="04e7e-132">在此示例中，同一个表达式中混合使用了 `decimal` 和 [int](../../../csharp/language-reference/keywords/int.md)。</span><span class="sxs-lookup"><span data-stu-id="04e7e-132">In this example, a `decimal` and an [int](../../../csharp/language-reference/keywords/int.md) are mixed in the same expression.</span></span> <span data-ttu-id="04e7e-133">计算结果为 `decimal` 类型。</span><span class="sxs-lookup"><span data-stu-id="04e7e-133">The result evaluates to the `decimal` type.</span></span>

[!code-csharp[csrefKeywordsTypes#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#6)]

## <a name="example"></a><span data-ttu-id="04e7e-134">示例</span><span class="sxs-lookup"><span data-stu-id="04e7e-134">Example</span></span>

<span data-ttu-id="04e7e-135">在此示例中，通过使用货币格式字符串来设置输出的格式。</span><span class="sxs-lookup"><span data-stu-id="04e7e-135">In this example, the output is formatted by using the currency format string.</span></span> <span data-ttu-id="04e7e-136">请注意，`x` 被舍入，因为其小数位数超出了 $0.99。</span><span class="sxs-lookup"><span data-stu-id="04e7e-136">Notice that `x` is rounded because the decimal places exceed $0.99.</span></span> <span data-ttu-id="04e7e-137">表示最大精确位数的变量 `y` 严格按照正确的格式显示。</span><span class="sxs-lookup"><span data-stu-id="04e7e-137">The variable `y`, which represents the maximum exact digits, is displayed exactly in the correct format.</span></span>

[!code-csharp[csrefKeywordsTypes#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#7)]

## <a name="c-language-specification"></a><span data-ttu-id="04e7e-138">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="04e7e-138">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="04e7e-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="04e7e-139">See also</span></span>

- <xref:System.Decimal>  
- [<span data-ttu-id="04e7e-140">C# 参考</span><span class="sxs-lookup"><span data-stu-id="04e7e-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="04e7e-141">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="04e7e-141">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="04e7e-142">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="04e7e-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="04e7e-143">整型表</span><span class="sxs-lookup"><span data-stu-id="04e7e-143">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="04e7e-144">内置类型表</span><span class="sxs-lookup"><span data-stu-id="04e7e-144">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="04e7e-145">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="04e7e-145">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="04e7e-146">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="04e7e-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
- [<span data-ttu-id="04e7e-147">标准数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="04e7e-147">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)