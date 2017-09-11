---
title: "int（C# 参考）"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- int_CSharpKeyword
- int
dev_langs:
- CSharp
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
caps.latest.revision: 19
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
ms.sourcegitcommit: 935428cc9442a3e1d15eeb8942176c237bff4e22
ms.openlocfilehash: 6e87893bcd9800b61297e71b782028fec5116479
ms.contentlocale: zh-cn
ms.lasthandoff: 08/22/2017

---
# <a name="int-c-reference"></a><span data-ttu-id="1968d-102">int（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="1968d-102">int (C# Reference)</span></span>

<span data-ttu-id="1968d-103">`int` 表示一种整型类型，该类型根据下表显示的大小和范围存储值。</span><span class="sxs-lookup"><span data-stu-id="1968d-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="1968d-104">类型</span><span class="sxs-lookup"><span data-stu-id="1968d-104">Type</span></span>|<span data-ttu-id="1968d-105">范围</span><span class="sxs-lookup"><span data-stu-id="1968d-105">Range</span></span>|<span data-ttu-id="1968d-106">大小</span><span class="sxs-lookup"><span data-stu-id="1968d-106">Size</span></span>|<span data-ttu-id="1968d-107">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="1968d-107">.NET Framework type</span></span>|<span data-ttu-id="1968d-108">默认值</span><span class="sxs-lookup"><span data-stu-id="1968d-108">Default Value</span></span>|  
|----------|-----------|----------|-------------------------|-------------------|  
|`int`|<span data-ttu-id="1968d-109">-2,147,483,648 到 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="1968d-109">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="1968d-110">带符号的 32 位整数</span><span class="sxs-lookup"><span data-stu-id="1968d-110">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=fullName>|<span data-ttu-id="1968d-111">0</span><span class="sxs-lookup"><span data-stu-id="1968d-111">0</span></span>|  
  
## <a name="literals"></a><span data-ttu-id="1968d-112">文本</span><span class="sxs-lookup"><span data-stu-id="1968d-112">Literals</span></span>  
 
<span data-ttu-id="1968d-113">可以通过为其分配十进制文本、十六进制文本或（从 C# 7 开始）二进制文本来声明和初始化 `int` 变量。</span><span class="sxs-lookup"><span data-stu-id="1968d-113">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="1968d-114">如果整数文本在 `int` 范围之外（即，如果它小于 <xref:System.Int32.MinValue?displayProperty=fullName> 或大于 <xref:System.Int32.MaxValue?displayProperty=fullName>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="1968d-114">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=fullName> or greater than <xref:System.Int32.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="1968d-115">在以下示例中，表示为十进制、十六进制和二进制文本且等于 90,946 的整数被分配给 `int` 值。</span><span class="sxs-lookup"><span data-stu-id="1968d-115">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
<span data-ttu-id="1968d-116">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]</span><span class="sxs-lookup"><span data-stu-id="1968d-116">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="1968d-117">使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。</span><span class="sxs-lookup"><span data-stu-id="1968d-117">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="1968d-118">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="1968d-118">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="1968d-119">从 C# 7 开始，还可以使用下划线字符 `_` 作为数字分隔符，以增强可读性，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="1968d-119">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="1968d-120">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]</span><span class="sxs-lookup"><span data-stu-id="1968d-120">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]</span></span>  
 
 <span data-ttu-id="1968d-121">整数文本还可以包括一个表示类型的后缀，尽管没有表示 `int` 类型的后缀。</span><span class="sxs-lookup"><span data-stu-id="1968d-121">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="1968d-122">如果整数文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：</span><span class="sxs-lookup"><span data-stu-id="1968d-122">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="1968d-123">uint</span><span class="sxs-lookup"><span data-stu-id="1968d-123">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="1968d-124">long</span><span class="sxs-lookup"><span data-stu-id="1968d-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="1968d-125">ulong</span><span class="sxs-lookup"><span data-stu-id="1968d-125">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="1968d-126">在这些示例中，文本 90946 属于类型 `int`。</span><span class="sxs-lookup"><span data-stu-id="1968d-126">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="1968d-127">转换</span><span class="sxs-lookup"><span data-stu-id="1968d-127">Conversions</span></span>  
 <span data-ttu-id="1968d-128">存在从 `int` 到 [long](../../../csharp/language-reference/keywords/long.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md) 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="1968d-128">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="1968d-129">例如: </span><span class="sxs-lookup"><span data-stu-id="1968d-129">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="1968d-130">存在从 [sbyte](../../../csharp/language-reference/keywords/sbyte.md)、[byte](../../../csharp/language-reference/keywords/byte.md)、[short](../../../csharp/language-reference/keywords/short.md)、[ushort](../../../csharp/language-reference/keywords/ushort.md) 或 [char](../../../csharp/language-reference/keywords/char.md) 到 `int` 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="1968d-130">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="1968d-131">例如，如果不使用转换，以下赋值语句会生成编译错误：</span><span class="sxs-lookup"><span data-stu-id="1968d-131">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="1968d-132">另请注意，不存在从浮点类型到 `int` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="1968d-132">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="1968d-133">例如，除非使用显式强制转换，否则以下语句将生成编译器错误：</span><span class="sxs-lookup"><span data-stu-id="1968d-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="1968d-134">有关兼用浮点类型和整型类型的算术表达式的详细信息，请参阅 [float](../../../csharp/language-reference/keywords/float.md) 和 [double](../../../csharp/language-reference/keywords/double.md)。</span><span class="sxs-lookup"><span data-stu-id="1968d-134">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1968d-135">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="1968d-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1968d-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1968d-136">See Also</span></span>  
 <span data-ttu-id="1968d-137"><xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="1968d-137"><xref:System.Int32></span></span>   
 <span data-ttu-id="1968d-138">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1968d-138">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1968d-139">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1968d-139">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1968d-140">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="1968d-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="1968d-141">[整型类型表](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="1968d-141">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="1968d-142">[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="1968d-142">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="1968d-143">[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="1968d-143">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="1968d-144">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="1968d-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

