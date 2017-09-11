---
title: "uint（C# 参考）"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- uint
- uint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- uint keyword [C#]
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
caps.latest.revision: 18
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
ms.openlocfilehash: 4342c08ab536f45a2e3b5fa6fe94839436600a4a
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="uint-c-reference"></a><span data-ttu-id="e6853-102">uint（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e6853-102">uint (C# Reference)</span></span>

<span data-ttu-id="e6853-103">`uint` 关键字表示一种整型类型，该类型根据下表显示的大小和范围存储值。</span><span class="sxs-lookup"><span data-stu-id="e6853-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="e6853-104">类型</span><span class="sxs-lookup"><span data-stu-id="e6853-104">Type</span></span>|<span data-ttu-id="e6853-105">范围</span><span class="sxs-lookup"><span data-stu-id="e6853-105">Range</span></span>|<span data-ttu-id="e6853-106">大小</span><span class="sxs-lookup"><span data-stu-id="e6853-106">Size</span></span>|<span data-ttu-id="e6853-107">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="e6853-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`uint`|<span data-ttu-id="e6853-108">0 到 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="e6853-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="e6853-109">无符号的 32 位整数</span><span class="sxs-lookup"><span data-stu-id="e6853-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=fullName>|  
  
 <span data-ttu-id="e6853-110">**请注意**：`uint` 类型不符合 CLS。</span><span class="sxs-lookup"><span data-stu-id="e6853-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="e6853-111">请尽可能使用 `int`。</span><span class="sxs-lookup"><span data-stu-id="e6853-111">Use `int` whenever possible.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="e6853-112">文本</span><span class="sxs-lookup"><span data-stu-id="e6853-112">Literals</span></span>  

<span data-ttu-id="e6853-113">可以通过为其分配十进制文本、十六进制文本或（从 C# 7 开始）二进制文本来声明和初始化 `uint` 变量。</span><span class="sxs-lookup"><span data-stu-id="e6853-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="e6853-114">如果整数文本在 `uint` 范围之外（即，如果它小于 <xref:System.UInt32.MinValue?displayProperty=fullName> 或大于 <xref:System.UInt32.MaxValue?displayProperty=fullName>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="e6853-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=fullName> or greater than <xref:System.UInt32.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span>

<span data-ttu-id="e6853-115">在以下示例中，表示为十进制、十六进制和二进制文本且等于 3,000,000,000 的整数被分配给 `uint` 值。</span><span class="sxs-lookup"><span data-stu-id="e6853-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>  
  
<span data-ttu-id="e6853-116">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]</span><span class="sxs-lookup"><span data-stu-id="e6853-116">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="e6853-117">使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。</span><span class="sxs-lookup"><span data-stu-id="e6853-117">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="e6853-118">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="e6853-118">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="e6853-119">从 C# 7 开始，还可以使用下划线字符 `_` 作为数字分隔符，以增强可读性，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="e6853-119">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="e6853-120">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]</span><span class="sxs-lookup"><span data-stu-id="e6853-120">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]</span></span>  
 
 <span data-ttu-id="e6853-121">整数文本还可包含表示类型的后缀。</span><span class="sxs-lookup"><span data-stu-id="e6853-121">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="e6853-122">后缀 `U` 或“u”表示 `uint` 或 `ulong`，具体取决于文本的数字值。</span><span class="sxs-lookup"><span data-stu-id="e6853-122">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="e6853-123">以下示例使用 `u` 后缀来表示这两种类型的无符号整数。</span><span class="sxs-lookup"><span data-stu-id="e6853-123">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="e6853-124">请注意第一个文本为 `uint`，因为其值小于 <xref:System.UInt32.MaxValue?displayProperty=fullName>，而第二个文本为 `ulong`，因为其值大于 <xref:System.UInt32.MaxValue?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="e6853-124">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=fullName>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span></span>

<span data-ttu-id="e6853-125">[!code-cs[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="e6853-125">[!code-cs[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]</span></span>  
 
<span data-ttu-id="e6853-126">如果整数文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：</span><span class="sxs-lookup"><span data-stu-id="e6853-126">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="e6853-127">int</span><span class="sxs-lookup"><span data-stu-id="e6853-127">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="e6853-128">long</span><span class="sxs-lookup"><span data-stu-id="e6853-128">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="e6853-129">ulong</span><span class="sxs-lookup"><span data-stu-id="e6853-129">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
  
## <a name="conversions"></a><span data-ttu-id="e6853-130">转换</span><span class="sxs-lookup"><span data-stu-id="e6853-130">Conversions</span></span>  
 <span data-ttu-id="e6853-131">存在从 `uint` 到 [long](../../../csharp/language-reference/keywords/long.md)、[ulong](../../../csharp/language-reference/keywords/ulong.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md) 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="e6853-131">There is a predefined implicit conversion from `uint` to [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="e6853-132">例如: </span><span class="sxs-lookup"><span data-stu-id="e6853-132">For example:</span></span>  
  
```csharp  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 <span data-ttu-id="e6853-133">存在从 [byte](../../../csharp/language-reference/keywords/byte.md)、[ushort](../../../csharp/language-reference/keywords/ushort.md) 或 [char](../../../csharp/language-reference/keywords/char.md) 到 `uint` 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="e6853-133">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `uint`.</span></span> <span data-ttu-id="e6853-134">否则必须使用转换。</span><span class="sxs-lookup"><span data-stu-id="e6853-134">Otherwise you must use a cast.</span></span> <span data-ttu-id="e6853-135">例如，如果不使用转换，以下赋值语句会生成编译错误：</span><span class="sxs-lookup"><span data-stu-id="e6853-135">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 <span data-ttu-id="e6853-136">另请注意，不存在从浮点类型到 `uint` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="e6853-136">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="e6853-137">例如，除非使用显式强制转换，否则以下语句将生成编译器错误：</span><span class="sxs-lookup"><span data-stu-id="e6853-137">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 <span data-ttu-id="e6853-138">有关兼用浮点类型和整型类型的算术表达式的信息，请参阅 [float](../../../csharp/language-reference/keywords/float.md) 和 [double](../../../csharp/language-reference/keywords/double.md)。</span><span class="sxs-lookup"><span data-stu-id="e6853-138">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="e6853-139">有关隐式数值转换规则的详细信息，请参阅[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="e6853-139">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e6853-140">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="e6853-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e6853-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6853-141">See Also</span></span>  
 <span data-ttu-id="e6853-142"><xref:System.UInt32></span><span class="sxs-lookup"><span data-stu-id="e6853-142"><xref:System.UInt32></span></span>   
 <span data-ttu-id="e6853-143">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6853-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e6853-144">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6853-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e6853-145">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6853-145">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e6853-146">[整型类型表](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="e6853-146">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="e6853-147">[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="e6853-147">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="e6853-148">[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="e6853-148">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="e6853-149">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="e6853-149">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

