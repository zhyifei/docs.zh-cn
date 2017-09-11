---
title: "float（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- float
- float_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: 24
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
ms.openlocfilehash: 2f1fb02f84de504112eee826dbee1275fa3ccb7a
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="float-c-reference"></a><span data-ttu-id="6e26d-102">float（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="6e26d-102">float (C# Reference)</span></span>
<span data-ttu-id="6e26d-103">`float` 关键字表示存储 32 位浮点值的简单类型。</span><span class="sxs-lookup"><span data-stu-id="6e26d-103">The `float` keyword signifies a simple type that stores 32-bit floating-point values.</span></span> <span data-ttu-id="6e26d-104">下表显示了 `float` 类型的精度和大致范围。</span><span class="sxs-lookup"><span data-stu-id="6e26d-104">The following table shows the precision and approximate range for the `float` type.</span></span>  
  
|<span data-ttu-id="6e26d-105">类型</span><span class="sxs-lookup"><span data-stu-id="6e26d-105">Type</span></span>|<span data-ttu-id="6e26d-106">大致范围</span><span class="sxs-lookup"><span data-stu-id="6e26d-106">Approximate range</span></span>|<span data-ttu-id="6e26d-107">精度</span><span class="sxs-lookup"><span data-stu-id="6e26d-107">Precision</span></span>|<span data-ttu-id="6e26d-108">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="6e26d-108">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|<span data-ttu-id="6e26d-109">-3.4 × 10<sup>38</sup>to +3.4 × 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="6e26d-109">-3.4 × 10<sup>38</sup>to +3.4 × 10<sup>38</sup></span></span>|<span data-ttu-id="6e26d-110">7 位</span><span class="sxs-lookup"><span data-stu-id="6e26d-110">7 digits</span></span>|<xref:System.Single?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="6e26d-111">文本</span><span class="sxs-lookup"><span data-stu-id="6e26d-111">Literals</span></span>  
 <span data-ttu-id="6e26d-112">默认情况下，赋值运算符右侧的实数被视为 [double](double.md)。</span><span class="sxs-lookup"><span data-stu-id="6e26d-112">By default, a real numeric literal on the right side of the assignment operator is treated as [double](double.md).</span></span> <span data-ttu-id="6e26d-113">因此，若要初始化浮点型变量，请使用后缀 `f` 或 `F`，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="6e26d-113">Therefore, to initialize a float variable, use the suffix `f` or `F`, as in the following example:</span></span>  
  
```csharp
float x = 3.5F;  
```
  
 <span data-ttu-id="6e26d-114">如果不在前面的声明中使用后缀，则会收到编译错误，因为你正尝试将 [double](double.md) 值存储到 `float` 变量。</span><span class="sxs-lookup"><span data-stu-id="6e26d-114">If you do not use the suffix in the previous declaration, you will get a compilation error because you are trying to store a [double](double.md) value into a `float` variable.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="6e26d-115">转换</span><span class="sxs-lookup"><span data-stu-id="6e26d-115">Conversions</span></span>  
 <span data-ttu-id="6e26d-116">可以在表达式中混合使用数值整型和浮点类型。</span><span class="sxs-lookup"><span data-stu-id="6e26d-116">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="6e26d-117">在这种情况下，整数类型将转换为浮点类型。</span><span class="sxs-lookup"><span data-stu-id="6e26d-117">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="6e26d-118">根据以下规则对表达式求值：</span><span class="sxs-lookup"><span data-stu-id="6e26d-118">The evaluation of the expression is performed according to the following rules:</span></span>  
  
-   <span data-ttu-id="6e26d-119">如果浮点类型之一是 [double](double.md)，该表达式的计算结果为关系或布尔表达式中 [double](double.md) 或 [bool](bool.md)。</span><span class="sxs-lookup"><span data-stu-id="6e26d-119">If one of the floating-point types is [double](double.md), the expression evaluates to [double](double.md) or [bool](bool.md) in relational or Boolean expressions.</span></span>  
  
-   <span data-ttu-id="6e26d-120">如果表达式中无 [double](double.md) 类型，则该表达式的计算结果为关系或布尔表达式中 `float` 或 [bool](bool.md)。</span><span class="sxs-lookup"><span data-stu-id="6e26d-120">If there is no [double](double.md) type in the expression, the expression evaluates to `float` or [bool](bool.md) in relational or Boolean expressions.</span></span>  
  
 <span data-ttu-id="6e26d-121">浮点表达式可以包含下列值集：</span><span class="sxs-lookup"><span data-stu-id="6e26d-121">A floating-point expression can contain the following sets of values:</span></span>  
  
-   <span data-ttu-id="6e26d-122">正和负零</span><span class="sxs-lookup"><span data-stu-id="6e26d-122">Positive and negative zero</span></span>  
  
-   <span data-ttu-id="6e26d-123">正和负无穷大</span><span class="sxs-lookup"><span data-stu-id="6e26d-123">Positive and negative infinity</span></span>  
  
-   <span data-ttu-id="6e26d-124">非数字值 (NaN)</span><span class="sxs-lookup"><span data-stu-id="6e26d-124">Not-a-Number value (NaN)</span></span>  
  
-   <span data-ttu-id="6e26d-125">一组有限的非零值</span><span class="sxs-lookup"><span data-stu-id="6e26d-125">The finite set of nonzero values</span></span>  
  
 <span data-ttu-id="6e26d-126">有关这些值的详细信息，请参阅 [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) 网站中提供的二进制浮点算术的 IEEE 标准。</span><span class="sxs-lookup"><span data-stu-id="6e26d-126">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) Web site.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e26d-127">示例</span><span class="sxs-lookup"><span data-stu-id="6e26d-127">Example</span></span>  
 <span data-ttu-id="6e26d-128">在下面的示例中，提供 `float` 结果的数学表达式中包含 [int](int.md)、[short](short.md) 和 `float`。</span><span class="sxs-lookup"><span data-stu-id="6e26d-128">In the following example, an [int](int.md), a [short](short.md), and a `float` are included in a mathematical expression giving a `float` result.</span></span> <span data-ttu-id="6e26d-129">（请记住，`float` 是 <xref:System.Single?displayProperty=fullName> 类型的别名。）请注意，表达式中没有任何 [double](double.md)。</span><span class="sxs-lookup"><span data-stu-id="6e26d-129">(Remember that `float` is an alias for the <xref:System.Single?displayProperty=fullName> type.) Notice that there is no [double](double.md) in the expression.</span></span>  
  
 <span data-ttu-id="6e26d-130">[!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e26d-130">[!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6e26d-131">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="6e26d-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6e26d-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e26d-132">See Also</span></span>  
 <span data-ttu-id="6e26d-133"><xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="6e26d-133"><xref:System.Single></span></span>   
 <span data-ttu-id="6e26d-134">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6e26d-134">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6e26d-135">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6e26d-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6e26d-136">[强制转换和类型转换](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="6e26d-136">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 <span data-ttu-id="6e26d-137">[C# 关键字](index.md) </span><span class="sxs-lookup"><span data-stu-id="6e26d-137">[C# Keywords](index.md) </span></span>  
 <span data-ttu-id="6e26d-138">[整型类型表](integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="6e26d-138">[Integral Types Table](integral-types-table.md) </span></span>  
 <span data-ttu-id="6e26d-139">[内置类型表](built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="6e26d-139">[Built-In Types Table](built-in-types-table.md) </span></span>  
 <span data-ttu-id="6e26d-140">[隐式数值转换表](implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="6e26d-140">[Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="6e26d-141">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="6e26d-141">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)

