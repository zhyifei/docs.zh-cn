---
title: "decimal（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- decimal_CSharpKeyword
- decimal
dev_langs:
- CSharp
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4c06d14f01302a21427845d0269fc8181a380914
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="decimal-c-reference"></a><span data-ttu-id="b6270-102">decimal（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b6270-102">decimal (C# Reference)</span></span>
<span data-ttu-id="b6270-103">`decimal` 关键字指示 128 位数据类型。</span><span class="sxs-lookup"><span data-stu-id="b6270-103">The `decimal` keyword indicates a 128-bit data type.</span></span> <span data-ttu-id="b6270-104">与其他浮点型相比，`decimal` 类型具有更高的精度和更小的范围，这使它适合于财务和货币计算。</span><span class="sxs-lookup"><span data-stu-id="b6270-104">Compared to other floating-point types, the `decimal` type has more precision and a smaller range, which makes it appropriate for financial and monetary calculations.</span></span> <span data-ttu-id="b6270-105">`decimal` 类型的大致范围和精度如下表所示。</span><span class="sxs-lookup"><span data-stu-id="b6270-105">The approximate range and precision for the `decimal` type are shown in the following table.</span></span>  
  
|<span data-ttu-id="b6270-106">类型</span><span class="sxs-lookup"><span data-stu-id="b6270-106">Type</span></span>|<span data-ttu-id="b6270-107">大致范围</span><span class="sxs-lookup"><span data-stu-id="b6270-107">Approximate Range</span></span>|<span data-ttu-id="b6270-108">精度</span><span class="sxs-lookup"><span data-stu-id="b6270-108">Precision</span></span>|<span data-ttu-id="b6270-109">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="b6270-109">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`decimal`|<span data-ttu-id="b6270-110">(-7.9 x 10<sup>28</sup> - 7.9 x 10<sup>28</sup>) / (10<sup>0</sup> - 10<sup>28</sup>)</span><span class="sxs-lookup"><span data-stu-id="b6270-110">(-7.9 x 10<sup>28</sup> to 7.9 x 10<sup>28</sup>) / (10<sup>0</sup> to 10<sup>28</sup>)</span></span>|<span data-ttu-id="b6270-111">28-29 个有效位</span><span class="sxs-lookup"><span data-stu-id="b6270-111">28-29 significant digits</span></span>|<xref:System.Decimal?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="b6270-112">文本</span><span class="sxs-lookup"><span data-stu-id="b6270-112">Literals</span></span>  
 <span data-ttu-id="b6270-113">如果希望实数被视为 `decimal` 类型，请使用后缀 m 或 M，例如：</span><span class="sxs-lookup"><span data-stu-id="b6270-113">If you want a numeric real literal to be treated as `decimal`, use the suffix m or M, for example:</span></span>  
  
```csharp
decimal myMoney = 300.5m;  
```  
  
 <span data-ttu-id="b6270-114">如果没有后缀 m，则数字将被视为 [double](../../../csharp/language-reference/keywords/double.md) 类型并会生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="b6270-114">Without the suffix m, the number is treated as a [double](../../../csharp/language-reference/keywords/double.md) and generates a compiler error.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="b6270-115">转换</span><span class="sxs-lookup"><span data-stu-id="b6270-115">Conversions</span></span>  
 <span data-ttu-id="b6270-116">整型将被隐式转换为 `decimal` 类型，其计算结果为 `decimal`。</span><span class="sxs-lookup"><span data-stu-id="b6270-116">The integral types are implicitly converted to `decimal` and the result evaluates to `decimal`.</span></span> <span data-ttu-id="b6270-117">因此，你可以使用整数文本初始化十进制变量而不使用后缀，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6270-117">Therefore you can initialize a decimal variable using an integer literal, without the suffix, as follows:</span></span>  
  
```csharp
decimal myMoney = 300;  
```  
  
 <span data-ttu-id="b6270-118">在其他浮点型和 `decimal` 类型之间不存在隐式转换；因此，必须使用强制转换在这两个类型之间转换。</span><span class="sxs-lookup"><span data-stu-id="b6270-118">There is no implicit conversion between other floating-point types and the `decimal` type; therefore, a cast must be used to convert between these two types.</span></span> <span data-ttu-id="b6270-119">例如: </span><span class="sxs-lookup"><span data-stu-id="b6270-119">For example:</span></span>  
  
```csharp
decimal myMoney = 99.9m;  
double x = (double)myMoney;  
myMoney = (decimal)x;  
```  
  
 <span data-ttu-id="b6270-120">你还可以在同一表达式中混合使用 `decimal` 和数值整型。</span><span class="sxs-lookup"><span data-stu-id="b6270-120">You can also mix `decimal` and numeric integral types in the same expression.</span></span> <span data-ttu-id="b6270-121">但是，不进行强制转换就混合使用 `decimal` 和其他浮点型将导致编译错误。</span><span class="sxs-lookup"><span data-stu-id="b6270-121">However, mixing `decimal` and other floating-point types without a cast causes a compilation error.</span></span>  
  
 <span data-ttu-id="b6270-122">有关隐式数值转换的详细信息，请参阅[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="b6270-122">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="b6270-123">有关显式数值转换的详细信息，请参阅[显式数值转换表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="b6270-123">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>  
  
## <a name="formatting-decimal-output"></a><span data-ttu-id="b6270-124">设置十进制输出的格式</span><span class="sxs-lookup"><span data-stu-id="b6270-124">Formatting Decimal Output</span></span>  
 <span data-ttu-id="b6270-125">你可以通过使用 `String.Format` 方法或 <xref:System.Console.Write%2A?displayProperty=fullName> 方法（其调用 `String.Format()`）来设置结果的格式。</span><span class="sxs-lookup"><span data-stu-id="b6270-125">You can format the results by using the `String.Format` method, or through the <xref:System.Console.Write%2A?displayProperty=fullName> method, which calls `String.Format()`.</span></span> <span data-ttu-id="b6270-126">货币格式是使用标准货币格式字符串“C”或“c”指定的，如本文后面的第二个示例所示。</span><span class="sxs-lookup"><span data-stu-id="b6270-126">The currency format is specified by using the standard currency format string "C" or "c," as shown in the second example later in this article.</span></span> <span data-ttu-id="b6270-127">有关 `String.Format` 方法的更多信息，请参见 <xref:System.String.Format%2A?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="b6270-127">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=fullName>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6270-128">示例</span><span class="sxs-lookup"><span data-stu-id="b6270-128">Example</span></span>  
 <span data-ttu-id="b6270-129">下面的示例尝试添加 [double](../../../csharp/language-reference/keywords/double.md) 和 `decimal` 变量，这会导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="b6270-129">The following example causes a compiler error by trying to add [double](../../../csharp/language-reference/keywords/double.md) and `decimal` variables.</span></span>  
  
```csharp  
double dub = 9;  
// The following line causes an error that reads "Operator '+' cannot be applied to   
// operands of type 'double' and 'decimal'"  
Console.WriteLine(dec + dub);   
  
// You can fix the error by using explicit casting of either operand.  
Console.WriteLine(dec + (decimal)dub);  
Console.WriteLine((double)dec + dub);  
```  
  
 <span data-ttu-id="b6270-130">其结果为以下错误：</span><span class="sxs-lookup"><span data-stu-id="b6270-130">The result is the following error:</span></span>  
  
 `Operator '+' cannot be applied to operands of type 'double' and 'decimal'`  
  
 <span data-ttu-id="b6270-131">在此示例中，同一个表达式中混合使用了 `decimal` 和 [int](../../../csharp/language-reference/keywords/int.md)。</span><span class="sxs-lookup"><span data-stu-id="b6270-131">In this example, a `decimal` and an [int](../../../csharp/language-reference/keywords/int.md) are mixed in the same expression.</span></span> <span data-ttu-id="b6270-132">计算结果为 `decimal` 类型。</span><span class="sxs-lookup"><span data-stu-id="b6270-132">The result evaluates to the `decimal` type.</span></span>  
  
 <span data-ttu-id="b6270-133">[!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b6270-133">[!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6270-134">示例</span><span class="sxs-lookup"><span data-stu-id="b6270-134">Example</span></span>  
 <span data-ttu-id="b6270-135">在此示例中，通过使用货币格式字符串来设置输出的格式。</span><span class="sxs-lookup"><span data-stu-id="b6270-135">In this example, the output is formatted by using the currency format string.</span></span> <span data-ttu-id="b6270-136">请注意，`x` 被舍入，因为其小数位数超出了 $0.99。</span><span class="sxs-lookup"><span data-stu-id="b6270-136">Notice that `x` is rounded because the decimal places exceed $0.99.</span></span> <span data-ttu-id="b6270-137">表示最大精确位数的变量 `y` 严格按照正确的格式显示。</span><span class="sxs-lookup"><span data-stu-id="b6270-137">The variable `y`, which represents the maximum exact digits, is displayed exactly in the correct format.</span></span>  
  
 <span data-ttu-id="b6270-138">[!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b6270-138">[!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b6270-139">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b6270-139">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b6270-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6270-140">See Also</span></span>  
 <span data-ttu-id="b6270-141"><xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="b6270-141"><xref:System.Decimal></span></span>   
 <span data-ttu-id="b6270-142">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b6270-142">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b6270-143">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b6270-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b6270-144">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="b6270-144">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="b6270-145">[整型类型表](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="b6270-145">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="b6270-146">[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="b6270-146">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="b6270-147">[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="b6270-147">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 <span data-ttu-id="b6270-148">[显式数值转换表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="b6270-148">[Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="b6270-149">标准数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="b6270-149">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)

