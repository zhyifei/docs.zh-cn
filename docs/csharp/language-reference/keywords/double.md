---
title: double 关键字（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- double
- double_CSharpKeyword
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
ms.openlocfilehash: 8e3a94bb79d46f2815e46b86f1aca92acc73e5c2
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37027845"
---
# <a name="double-c-reference"></a><span data-ttu-id="0469a-102">double（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0469a-102">double (C# Reference)</span></span>

<span data-ttu-id="0469a-103">`double` 关键字表示存储 64 位浮点值的简单类型。</span><span class="sxs-lookup"><span data-stu-id="0469a-103">The `double` keyword signifies a simple type that stores 64-bit floating-point values.</span></span> <span data-ttu-id="0469a-104">下表显示了 `double` 类型的精度和大致范围。</span><span class="sxs-lookup"><span data-stu-id="0469a-104">The following table shows the precision and approximate range for the `double` type.</span></span>

|<span data-ttu-id="0469a-105">类型</span><span class="sxs-lookup"><span data-stu-id="0469a-105">Type</span></span>|<span data-ttu-id="0469a-106">大致范围</span><span class="sxs-lookup"><span data-stu-id="0469a-106">Approximate range</span></span>|<span data-ttu-id="0469a-107">精度</span><span class="sxs-lookup"><span data-stu-id="0469a-107">Precision</span></span>|<span data-ttu-id="0469a-108">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="0469a-108">.NET type</span></span>|
|----------|-----------------------|---------------|-------------------------|
|`double`|<span data-ttu-id="0469a-109">±5.0 × 10<sup>−324</sup> 到 ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="0469a-109">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="0469a-110">15-16 位</span><span class="sxs-lookup"><span data-stu-id="0469a-110">15-16 digits</span></span>|<xref:System.Double?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="0469a-111">文本</span><span class="sxs-lookup"><span data-stu-id="0469a-111">Literals</span></span>

<span data-ttu-id="0469a-112">默认情况下，赋值运算符右侧的实数被视为 `double`。</span><span class="sxs-lookup"><span data-stu-id="0469a-112">By default, a real numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="0469a-113">但是，如果希望整数被视为 `double`，可使用后缀 d 或 D，例如：</span><span class="sxs-lookup"><span data-stu-id="0469a-113">However, if you want an integer number to be treated as `double`, use the suffix d or D, for example:</span></span>

```csharp
double x = 3D;
```

## <a name="conversions"></a><span data-ttu-id="0469a-114">转换</span><span class="sxs-lookup"><span data-stu-id="0469a-114">Conversions</span></span>

<span data-ttu-id="0469a-115">可以在表达式中混合使用数值整型和浮点类型。</span><span class="sxs-lookup"><span data-stu-id="0469a-115">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="0469a-116">在这种情况下，整数类型将转换为浮点类型。</span><span class="sxs-lookup"><span data-stu-id="0469a-116">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="0469a-117">根据以下规则对表达式求值：</span><span class="sxs-lookup"><span data-stu-id="0469a-117">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="0469a-118">如果浮点类型之一是 `double`，则该表达式的计算结果为 `double` 类型，在关系表达式或布尔表达式中为 [bool](../../../csharp/language-reference/keywords/bool.md) 类型。</span><span class="sxs-lookup"><span data-stu-id="0469a-118">If one of the floating-point types is `double`, the expression evaluates to `double`, or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>

- <span data-ttu-id="0469a-119">如果表达式中无 `double` 类型，则该表达式的计算结果为 [float](../../../csharp/language-reference/keywords/float.md) 类型，在关系表达式或布尔表达式中为 [bool](../../../csharp/language-reference/keywords/bool.md) 类型。</span><span class="sxs-lookup"><span data-stu-id="0469a-119">If there is no `double` type in the expression, it evaluates to [float](../../../csharp/language-reference/keywords/float.md), or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>

 <span data-ttu-id="0469a-120">浮点表达式可以包含下列值集：</span><span class="sxs-lookup"><span data-stu-id="0469a-120">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="0469a-121">正零和负零。</span><span class="sxs-lookup"><span data-stu-id="0469a-121">Positive and negative zero.</span></span>

- <span data-ttu-id="0469a-122">正无穷大和负无穷大。</span><span class="sxs-lookup"><span data-stu-id="0469a-122">Positive and negative infinity.</span></span>

- <span data-ttu-id="0469a-123">非数字值 (NaN)。</span><span class="sxs-lookup"><span data-stu-id="0469a-123">Not-a-Number value (NaN).</span></span>

- <span data-ttu-id="0469a-124">一组有限的非零值。</span><span class="sxs-lookup"><span data-stu-id="0469a-124">The finite set of nonzero values.</span></span>

<span data-ttu-id="0469a-125">有关这些值的详细信息，请参阅 [IEEE](https://www.ieee.org) 网站中提供的二进制浮点算术的 IEEE 标准。</span><span class="sxs-lookup"><span data-stu-id="0469a-125">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) Web site.</span></span>

## <a name="example"></a><span data-ttu-id="0469a-126">示例</span><span class="sxs-lookup"><span data-stu-id="0469a-126">Example</span></span>

<span data-ttu-id="0469a-127">在下面的示例中，将 [int](../../../csharp/language-reference/keywords/int.md)、[short](../../../csharp/language-reference/keywords/short.md)、[float](../../../csharp/language-reference/keywords/float.md) 和 `double` 相加可得出 `double` 结果。</span><span class="sxs-lookup"><span data-stu-id="0469a-127">In the following example, an [int](../../../csharp/language-reference/keywords/int.md), a [short](../../../csharp/language-reference/keywords/short.md), a [float](../../../csharp/language-reference/keywords/float.md), and a `double` are added together giving a `double` result.</span></span>

[!code-csharp[csrefKeywordsTypes#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="0469a-128">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="0469a-128">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0469a-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="0469a-129">See Also</span></span>

[<span data-ttu-id="0469a-130">C# 参考</span><span class="sxs-lookup"><span data-stu-id="0469a-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
[<span data-ttu-id="0469a-131">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="0469a-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="0469a-132">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="0469a-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
[<span data-ttu-id="0469a-133">默认值表</span><span class="sxs-lookup"><span data-stu-id="0469a-133">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
[<span data-ttu-id="0469a-134">内置类型表</span><span class="sxs-lookup"><span data-stu-id="0469a-134">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
[<span data-ttu-id="0469a-135">浮点型表</span><span class="sxs-lookup"><span data-stu-id="0469a-135">Floating-Point Types Table</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
[<span data-ttu-id="0469a-136">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="0469a-136">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
[<span data-ttu-id="0469a-137">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="0469a-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
