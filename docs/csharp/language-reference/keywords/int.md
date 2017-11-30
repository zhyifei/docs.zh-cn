---
title: "int（C# 参考）"
ms.date: 03/14/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- int_CSharpKeyword
- int
helpviewer_keywords: int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e7acb8bb482ebf8f5c2b508e7cfd45b5b64aae3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="int-c-reference"></a><span data-ttu-id="5b4a6-102">int（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5b4a6-102">int (C# Reference)</span></span>

<span data-ttu-id="5b4a6-103">`int` 表示一种整型类型，该类型根据下表显示的大小和范围存储值。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="5b4a6-104">类型</span><span class="sxs-lookup"><span data-stu-id="5b4a6-104">Type</span></span>|<span data-ttu-id="5b4a6-105">范围</span><span class="sxs-lookup"><span data-stu-id="5b4a6-105">Range</span></span>|<span data-ttu-id="5b4a6-106">大小</span><span class="sxs-lookup"><span data-stu-id="5b4a6-106">Size</span></span>|<span data-ttu-id="5b4a6-107">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="5b4a6-107">.NET Framework type</span></span>|<span data-ttu-id="5b4a6-108">默认值</span><span class="sxs-lookup"><span data-stu-id="5b4a6-108">Default Value</span></span>|  
|----------|-----------|----------|-------------------------|-------------------|  
|`int`|<span data-ttu-id="5b4a6-109">-2,147,483,648 到 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="5b4a6-109">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="5b4a6-110">带符号的 32 位整数</span><span class="sxs-lookup"><span data-stu-id="5b4a6-110">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="5b4a6-111">0</span><span class="sxs-lookup"><span data-stu-id="5b4a6-111">0</span></span>|  
  
## <a name="literals"></a><span data-ttu-id="5b4a6-112">文本</span><span class="sxs-lookup"><span data-stu-id="5b4a6-112">Literals</span></span>  
 
<span data-ttu-id="5b4a6-113">可以通过为其分配十进制文本、十六进制文本或（从 C# 7 开始）二进制文本来声明和初始化 `int` 变量。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-113">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="5b4a6-114">如果整数文本在 `int` 范围之外（即，如果它小于 <xref:System.Int32.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Int32.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-114">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="5b4a6-115">在以下示例中，表示为十进制、十六进制和二进制文本且等于 90,946 的整数被分配给 `int` 值。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-115">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]  

> [!NOTE] 
> <span data-ttu-id="5b4a6-116">使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="5b4a6-117">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-117">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="5b4a6-118">C# 从 7 开始，已添加几个功能以增强可读性。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-118">Starting with C# 7, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="5b4a6-119">C# 7.0 允许使用下划线字符， `_`，作为数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="5b4a6-120">C# 7.2 允许`_`前缀后要使用作为二进制或十六进制文本中，数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="5b4a6-121">十进制文本不允许具有前导下划线。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="5b4a6-122">下面显示了一些示例。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-122">Some examples are shown below.</span></span>

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]  
 
 <span data-ttu-id="5b4a6-123">整数文本还可以包括一个表示类型的后缀，尽管没有表示 `int` 类型的后缀。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-123">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="5b4a6-124">如果整数文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：</span><span class="sxs-lookup"><span data-stu-id="5b4a6-124">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="5b4a6-125">uint</span><span class="sxs-lookup"><span data-stu-id="5b4a6-125">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="5b4a6-126">long</span><span class="sxs-lookup"><span data-stu-id="5b4a6-126">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="5b4a6-127">ulong</span><span class="sxs-lookup"><span data-stu-id="5b4a6-127">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="5b4a6-128">在这些示例中，文本 90946 属于类型 `int`。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-128">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="5b4a6-129">转换</span><span class="sxs-lookup"><span data-stu-id="5b4a6-129">Conversions</span></span>  
 <span data-ttu-id="5b4a6-130">存在从 `int` 到 [long](../../../csharp/language-reference/keywords/long.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md) 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-130">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="5b4a6-131">例如: </span><span class="sxs-lookup"><span data-stu-id="5b4a6-131">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="5b4a6-132">存在从 [sbyte](../../../csharp/language-reference/keywords/sbyte.md)、[byte](../../../csharp/language-reference/keywords/byte.md)、[short](../../../csharp/language-reference/keywords/short.md)、[ushort](../../../csharp/language-reference/keywords/ushort.md) 或 [char](../../../csharp/language-reference/keywords/char.md) 到 `int` 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-132">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="5b4a6-133">例如，如果不使用转换，以下赋值语句会生成编译错误：</span><span class="sxs-lookup"><span data-stu-id="5b4a6-133">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="5b4a6-134">另请注意，不存在从浮点类型到 `int` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-134">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="5b4a6-135">例如，除非使用显式强制转换，否则以下语句将生成编译器错误：</span><span class="sxs-lookup"><span data-stu-id="5b4a6-135">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="5b4a6-136">有关兼用浮点类型和整型类型的算术表达式的详细信息，请参阅 [float](../../../csharp/language-reference/keywords/float.md) 和 [double](../../../csharp/language-reference/keywords/double.md)。</span><span class="sxs-lookup"><span data-stu-id="5b4a6-136">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5b4a6-137">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5b4a6-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5b4a6-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b4a6-138">See Also</span></span>  
 <xref:System.Int32>  
 [<span data-ttu-id="5b4a6-139">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5b4a6-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5b4a6-140">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5b4a6-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5b4a6-141">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="5b4a6-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5b4a6-142">整型表</span><span class="sxs-lookup"><span data-stu-id="5b4a6-142">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="5b4a6-143">内置类型表</span><span class="sxs-lookup"><span data-stu-id="5b4a6-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="5b4a6-144">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="5b4a6-144">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="5b4a6-145">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="5b4a6-145">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
