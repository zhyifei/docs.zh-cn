---
title: "char（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- char
- char_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c6601a58804d6ecfcbedbc19da09560884e54e7f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="char-c-reference"></a><span data-ttu-id="ab8c2-102">char（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ab8c2-102">char (C# Reference)</span></span>
<span data-ttu-id="ab8c2-103">`char` 关键字用于声明 <xref:System.Char?displayProperty=fullName> 结构的实例，.NET Framework 使用该结构来表示 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="ab8c2-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=fullName> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="ab8c2-104">`Char` 对象的值为 16 位的数字（序号）值。</span><span class="sxs-lookup"><span data-stu-id="ab8c2-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>  
  
 <span data-ttu-id="ab8c2-105">Unicode 字符用于表示世界各地大多数的书面语言。</span><span class="sxs-lookup"><span data-stu-id="ab8c2-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>  
  
|<span data-ttu-id="ab8c2-106">类型</span><span class="sxs-lookup"><span data-stu-id="ab8c2-106">Type</span></span>|<span data-ttu-id="ab8c2-107">范围</span><span class="sxs-lookup"><span data-stu-id="ab8c2-107">Range</span></span>|<span data-ttu-id="ab8c2-108">大小</span><span class="sxs-lookup"><span data-stu-id="ab8c2-108">Size</span></span>|<span data-ttu-id="ab8c2-109">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="ab8c2-109">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`char`|<span data-ttu-id="ab8c2-110">U+0000 到 U+FFFF</span><span class="sxs-lookup"><span data-stu-id="ab8c2-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="ab8c2-111">Unicode 16 位字符</span><span class="sxs-lookup"><span data-stu-id="ab8c2-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="ab8c2-112">文本</span><span class="sxs-lookup"><span data-stu-id="ab8c2-112">Literals</span></span>  
 <span data-ttu-id="ab8c2-113">`char` 类型的常量可以编写为字符文本、十六进制转义序列或 Unicode 表示形式。</span><span class="sxs-lookup"><span data-stu-id="ab8c2-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="ab8c2-114">还可转换整型字符代码。</span><span class="sxs-lookup"><span data-stu-id="ab8c2-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="ab8c2-115">在下面的示例中，使用相同的字符 `X` 对四个 `char` 变量进行初始化：</span><span class="sxs-lookup"><span data-stu-id="ab8c2-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>  
  
 <span data-ttu-id="ab8c2-116">[!code-cs[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ab8c2-116">[!code-cs[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="ab8c2-117">转换</span><span class="sxs-lookup"><span data-stu-id="ab8c2-117">Conversions</span></span>  
 <span data-ttu-id="ab8c2-118">`char` 可隐式转换为 [ushort](../../../csharp/language-reference/keywords/ushort.md)、[int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md)、[ulong](../../../csharp/language-reference/keywords/ulong.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md)。</span><span class="sxs-lookup"><span data-stu-id="ab8c2-118">A `char` can be implicitly converted to [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="ab8c2-119">但是无法将其他类型隐式转换为 `char` 类型。</span><span class="sxs-lookup"><span data-stu-id="ab8c2-119">However, there are no implicit conversions from other types to the `char` type.</span></span>  
  
 <span data-ttu-id="ab8c2-120"><xref:System.Char?displayProperty=fullName> 类型提供多种适用于 `char` 值的静态方法。</span><span class="sxs-lookup"><span data-stu-id="ab8c2-120">The <xref:System.Char?displayProperty=fullName> type provides several static methods for working with `char` values.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ab8c2-121">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ab8c2-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ab8c2-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab8c2-122">See Also</span></span>  
 <span data-ttu-id="ab8c2-123"><xref:System.Char></span><span class="sxs-lookup"><span data-stu-id="ab8c2-123"><xref:System.Char></span></span>   
 <span data-ttu-id="ab8c2-124">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ab8c2-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ab8c2-125">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ab8c2-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ab8c2-126">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="ab8c2-126">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="ab8c2-127">[整型类型表](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="ab8c2-127">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="ab8c2-128">[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="ab8c2-128">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="ab8c2-129">[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="ab8c2-129">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 <span data-ttu-id="ab8c2-130">[显式数值转换表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="ab8c2-130">[Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span></span>  
 <span data-ttu-id="ab8c2-131">[可以为 null 的类型](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="ab8c2-131">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="ab8c2-132">字符串</span><span class="sxs-lookup"><span data-stu-id="ab8c2-132">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

