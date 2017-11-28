---
title: "char（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords: char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 41f672e9b12481fa5cce78015e95d2c5245a26db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="char-c-reference"></a><span data-ttu-id="e743c-102">char（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e743c-102">char (C# Reference)</span></span>
<span data-ttu-id="e743c-103">`char` 关键字用于声明 <xref:System.Char?displayProperty=nameWithType> 结构的实例，.NET Framework 使用该结构来表示 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="e743c-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="e743c-104">`Char` 对象的值为 16 位的数字（序号）值。</span><span class="sxs-lookup"><span data-stu-id="e743c-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>  
  
 <span data-ttu-id="e743c-105">Unicode 字符用于表示世界各地大多数的书面语言。</span><span class="sxs-lookup"><span data-stu-id="e743c-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>  
  
|<span data-ttu-id="e743c-106">类型</span><span class="sxs-lookup"><span data-stu-id="e743c-106">Type</span></span>|<span data-ttu-id="e743c-107">范围</span><span class="sxs-lookup"><span data-stu-id="e743c-107">Range</span></span>|<span data-ttu-id="e743c-108">大小</span><span class="sxs-lookup"><span data-stu-id="e743c-108">Size</span></span>|<span data-ttu-id="e743c-109">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="e743c-109">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`char`|<span data-ttu-id="e743c-110">U+0000 到 U+FFFF</span><span class="sxs-lookup"><span data-stu-id="e743c-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="e743c-111">Unicode 16 位字符</span><span class="sxs-lookup"><span data-stu-id="e743c-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="e743c-112">文本</span><span class="sxs-lookup"><span data-stu-id="e743c-112">Literals</span></span>  
 <span data-ttu-id="e743c-113">`char` 类型的常量可以编写为字符文本、十六进制转义序列或 Unicode 表示形式。</span><span class="sxs-lookup"><span data-stu-id="e743c-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="e743c-114">还可转换整型字符代码。</span><span class="sxs-lookup"><span data-stu-id="e743c-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="e743c-115">在下面的示例中，使用相同的字符 `X` 对四个 `char` 变量进行初始化：</span><span class="sxs-lookup"><span data-stu-id="e743c-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]  
  
## <a name="conversions"></a><span data-ttu-id="e743c-116">转换</span><span class="sxs-lookup"><span data-stu-id="e743c-116">Conversions</span></span>  
 <span data-ttu-id="e743c-117">`char` 可隐式转换为 [ushort](../../../csharp/language-reference/keywords/ushort.md)、[int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md)、[ulong](../../../csharp/language-reference/keywords/ulong.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md)。</span><span class="sxs-lookup"><span data-stu-id="e743c-117">A `char` can be implicitly converted to [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="e743c-118">但是无法将其他类型隐式转换为 `char` 类型。</span><span class="sxs-lookup"><span data-stu-id="e743c-118">However, there are no implicit conversions from other types to the `char` type.</span></span>  
  
 <span data-ttu-id="e743c-119"><xref:System.Char?displayProperty=nameWithType> 类型提供多种适用于 `char` 值的静态方法。</span><span class="sxs-lookup"><span data-stu-id="e743c-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e743c-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="e743c-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e743c-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e743c-121">See Also</span></span>  
 <xref:System.Char>  
 [<span data-ttu-id="e743c-122">C# 参考</span><span class="sxs-lookup"><span data-stu-id="e743c-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e743c-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e743c-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e743c-124">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="e743c-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="e743c-125">整型表</span><span class="sxs-lookup"><span data-stu-id="e743c-125">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="e743c-126">内置类型表</span><span class="sxs-lookup"><span data-stu-id="e743c-126">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="e743c-127">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="e743c-127">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="e743c-128">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="e743c-128">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [<span data-ttu-id="e743c-129">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="e743c-129">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="e743c-130">字符串</span><span class="sxs-lookup"><span data-stu-id="e743c-130">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
