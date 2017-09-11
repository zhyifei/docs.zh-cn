---
title: "double（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- double
- double_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
caps.latest.revision: 26
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
ms.openlocfilehash: d5588f8391157fb56a5e5067bb8e11f9269fe733
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="double-c-reference"></a><span data-ttu-id="d13b5-102">double（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d13b5-102">double (C# Reference)</span></span>
<span data-ttu-id="d13b5-103">`double` 关键字表示存储 64 位浮点值的简单类型。</span><span class="sxs-lookup"><span data-stu-id="d13b5-103">The `double` keyword signifies a simple type that stores 64-bit floating-point values.</span></span> <span data-ttu-id="d13b5-104">下表显示了 `double` 类型的精度和大致范围。</span><span class="sxs-lookup"><span data-stu-id="d13b5-104">The following table shows the precision and approximate range for the `double` type.</span></span>  
  
|<span data-ttu-id="d13b5-105">类型</span><span class="sxs-lookup"><span data-stu-id="d13b5-105">Type</span></span>|<span data-ttu-id="d13b5-106">大致范围</span><span class="sxs-lookup"><span data-stu-id="d13b5-106">Approximate range</span></span>|<span data-ttu-id="d13b5-107">精度</span><span class="sxs-lookup"><span data-stu-id="d13b5-107">Precision</span></span>|<span data-ttu-id="d13b5-108">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="d13b5-108">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`double`|<span data-ttu-id="d13b5-109">±5.0 × 10<sup>−324</sup> 到 ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="d13b5-109">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="d13b5-110">15-16 位</span><span class="sxs-lookup"><span data-stu-id="d13b5-110">15-16 digits</span></span>|<xref:System.Double?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="d13b5-111">文本</span><span class="sxs-lookup"><span data-stu-id="d13b5-111">Literals</span></span>  
 <span data-ttu-id="d13b5-112">默认情况下，赋值运算符右侧的实数被视为 `double`。</span><span class="sxs-lookup"><span data-stu-id="d13b5-112">By default, a real numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="d13b5-113">但是，如果希望整数被视为 `double`，可使用后缀 d 或 D，例如：</span><span class="sxs-lookup"><span data-stu-id="d13b5-113">However, if you want an integer number to be treated as `double`, use the suffix d or D, for example:</span></span>  
  
```  
double x = 3D;  
```  
  
## <a name="conversions"></a><span data-ttu-id="d13b5-114">转换</span><span class="sxs-lookup"><span data-stu-id="d13b5-114">Conversions</span></span>  
 <span data-ttu-id="d13b5-115">可以在表达式中混合使用数值整型和浮点类型。</span><span class="sxs-lookup"><span data-stu-id="d13b5-115">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="d13b5-116">在这种情况下，整数类型将转换为浮点类型。</span><span class="sxs-lookup"><span data-stu-id="d13b5-116">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="d13b5-117">根据以下规则对表达式求值：</span><span class="sxs-lookup"><span data-stu-id="d13b5-117">The evaluation of the expression is performed according to the following rules:</span></span>  
  
-   <span data-ttu-id="d13b5-118">如果浮点类型之一是 `double`，则该表达式的计算结果为 `double` 类型，在关系表达式或布尔表达式中为 [bool](../../../csharp/language-reference/keywords/bool.md) 类型。</span><span class="sxs-lookup"><span data-stu-id="d13b5-118">If one of the floating-point types is `double`, the expression evaluates to `double`, or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>  
  
-   <span data-ttu-id="d13b5-119">如果表达式中无 `double` 类型，则该表达式的计算结果为 [float](../../../csharp/language-reference/keywords/float.md) 类型，在关系表达式或布尔表达式中为 [bool](../../../csharp/language-reference/keywords/bool.md) 类型。</span><span class="sxs-lookup"><span data-stu-id="d13b5-119">If there is no `double` type in the expression, it evaluates to [float](../../../csharp/language-reference/keywords/float.md), or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>  
  
 <span data-ttu-id="d13b5-120">浮点表达式可以包含下列值集：</span><span class="sxs-lookup"><span data-stu-id="d13b5-120">A floating-point expression can contain the following sets of values:</span></span>  
  
-   <span data-ttu-id="d13b5-121">正零和负零。</span><span class="sxs-lookup"><span data-stu-id="d13b5-121">Positive and negative zero.</span></span>  
  
-   <span data-ttu-id="d13b5-122">正无穷大和负无穷大。</span><span class="sxs-lookup"><span data-stu-id="d13b5-122">Positive and negative infinity.</span></span>  
  
-   <span data-ttu-id="d13b5-123">非数字值 (NaN)。</span><span class="sxs-lookup"><span data-stu-id="d13b5-123">Not-a-Number value (NaN).</span></span>  
  
-   <span data-ttu-id="d13b5-124">一组有限的非零值。</span><span class="sxs-lookup"><span data-stu-id="d13b5-124">The finite set of nonzero values.</span></span>  
  
 <span data-ttu-id="d13b5-125">有关这些值的详细信息，请参阅 [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) 网站中提供的二进制浮点算术的 IEEE 标准。</span><span class="sxs-lookup"><span data-stu-id="d13b5-125">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) Web site.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d13b5-126">示例</span><span class="sxs-lookup"><span data-stu-id="d13b5-126">Example</span></span>  
 <span data-ttu-id="d13b5-127">在下面的示例中，将 [int](../../../csharp/language-reference/keywords/int.md)、[short](../../../csharp/language-reference/keywords/short.md)、 [float](../../../csharp/language-reference/keywords/float.md) 和 `double` 添加在一起可得出 `double` 结果。</span><span class="sxs-lookup"><span data-stu-id="d13b5-127">In the following example, an [int](../../../csharp/language-reference/keywords/int.md), a [short](../../../csharp/language-reference/keywords/short.md), a [float](../../../csharp/language-reference/keywords/float.md), and a `double` are added together giving a `double` result.</span></span>  
  
 <span data-ttu-id="d13b5-128">[!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d13b5-128">[!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d13b5-129">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="d13b5-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d13b5-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="d13b5-130">See Also</span></span>  
 <span data-ttu-id="d13b5-131">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d13b5-131">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d13b5-132">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d13b5-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d13b5-133">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d13b5-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d13b5-134">[默认值表](../../../csharp/language-reference/keywords/default-values-table.md) </span><span class="sxs-lookup"><span data-stu-id="d13b5-134">[Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md) </span></span>  
 <span data-ttu-id="d13b5-135">[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="d13b5-135">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="d13b5-136">[浮点型表](../../../csharp/language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="d13b5-136">[Floating-Point Types Table](../../../csharp/language-reference/keywords/floating-point-types-table.md) </span></span>  
 <span data-ttu-id="d13b5-137">[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="d13b5-137">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="d13b5-138">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="d13b5-138">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

