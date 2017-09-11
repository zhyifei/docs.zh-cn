---
title: "ushort（C# 参考）"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ushort
- ushort_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
caps.latest.revision: 16
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
ms.openlocfilehash: 2b067a2ffd0fbffe06dc5c9f2a9910c9563eec4b
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="ushort-c-reference"></a><span data-ttu-id="bc5a5-102">ushort（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="bc5a5-102">ushort (C# Reference)</span></span>

<span data-ttu-id="bc5a5-103">`ushort` 关键字表示一种整型数据类型，该类型根据下表显示的大小和范围存储值。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="bc5a5-104">类型</span><span class="sxs-lookup"><span data-stu-id="bc5a5-104">Type</span></span>|<span data-ttu-id="bc5a5-105">范围</span><span class="sxs-lookup"><span data-stu-id="bc5a5-105">Range</span></span>|<span data-ttu-id="bc5a5-106">大小</span><span class="sxs-lookup"><span data-stu-id="bc5a5-106">Size</span></span>|<span data-ttu-id="bc5a5-107">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="bc5a5-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ushort`|<span data-ttu-id="bc5a5-108">0 到 65,535</span><span class="sxs-lookup"><span data-stu-id="bc5a5-108">0 to 65,535</span></span>|<span data-ttu-id="bc5a5-109">无符号 16 位整数</span><span class="sxs-lookup"><span data-stu-id="bc5a5-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="bc5a5-110">文本</span><span class="sxs-lookup"><span data-stu-id="bc5a5-110">Literals</span></span>  

<span data-ttu-id="bc5a5-111">可以通过为其分配十进制文本、十六进制文本或（从 C# 7 开始）二进制文本来声明和初始化 `ushort` 变量。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="bc5a5-112">如果整数文本在 `ushort` 范围之外（即，如果它小于 <xref:System.UInt16.MinValue?displayProperty=fullName> 或大于 <xref:System.UInt16.MaxValue?displayProperty=fullName>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=fullName> or greater than <xref:System.UInt16.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span>

<span data-ttu-id="bc5a5-113">在以下示例中，等于 65,034、表示为十进制、十六进制和二进制文本的整数从 [int](../../../csharp/language-reference/keywords/int.md) 隐式转换为 `ushort` 值。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `ushort` values.</span></span>    
  
<span data-ttu-id="bc5a5-114">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]</span><span class="sxs-lookup"><span data-stu-id="bc5a5-114">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="bc5a5-115">使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="bc5a5-116">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-116">Decimal literals have no prefix.</span></span>

<span data-ttu-id="bc5a5-117">从 C# 7 开始，还可以使用下划线字符 `_` 作为数字分隔符，以增强可读性，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="bc5a5-118">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]</span><span class="sxs-lookup"><span data-stu-id="bc5a5-118">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]</span></span>  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="bc5a5-119">编译器重载解析</span><span class="sxs-lookup"><span data-stu-id="bc5a5-119">Compiler overload resolution</span></span>
  
 <span data-ttu-id="bc5a5-120">调用重载方法时必须使用强制转换。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-120">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="bc5a5-121">以下面使用 `ushort` 和 [int](../../../csharp/language-reference/keywords/int.md) 参数的重载方法为例：</span><span class="sxs-lookup"><span data-stu-id="bc5a5-121">Consider, for example, the following overloaded methods that use `ushort` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
 
 <span data-ttu-id="bc5a5-122">使用 `ushort` 强制转换可保证调用正确的类型，例如：</span><span class="sxs-lookup"><span data-stu-id="bc5a5-122">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## <a name="conversions"></a><span data-ttu-id="bc5a5-123">转换</span><span class="sxs-lookup"><span data-stu-id="bc5a5-123">Conversions</span></span>  
 <span data-ttu-id="bc5a5-124">存在从 `ushort` 到 [int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md)、[ulong](../../../csharp/language-reference/keywords/ulong.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md) 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-124">There is a predefined implicit conversion from `ushort` to [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="bc5a5-125">存在从 [byte](../../../csharp/language-reference/keywords/byte.md) 或 [char](../../../csharp/language-reference/keywords/char.md) 到 `ushort` 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-125">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md) or [char](../../../csharp/language-reference/keywords/char.md) to `ushort`.</span></span> <span data-ttu-id="bc5a5-126">其他情况下必须使用强制转换来执行显式转换。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-126">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="bc5a5-127">以下面两个 `ushort` 变量 `x` 和 `y` 为例：</span><span class="sxs-lookup"><span data-stu-id="bc5a5-127">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>  
  
```csharp 
ushort x = 5, y = 12;  
```  
  
 <span data-ttu-id="bc5a5-128">以下赋值语句会生成一个编译错误，原因是赋值运算符右侧的算术表达式在默认情况下的计算结果为 `int`。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-128">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 <span data-ttu-id="bc5a5-129">若要解决此问题，请使用强制转换：</span><span class="sxs-lookup"><span data-stu-id="bc5a5-129">To fix this problem, use a cast:</span></span>  
  
```csharp 
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 <span data-ttu-id="bc5a5-130">但是，在目标变量具有相同或更大的存储大小时，可以使用下列语句：</span><span class="sxs-lookup"><span data-stu-id="bc5a5-130">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="bc5a5-131">另请注意，不存在从浮点类型到 `ushort` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-131">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="bc5a5-132">例如，除非使用显式强制转换，否则以下语句将生成编译器错误：</span><span class="sxs-lookup"><span data-stu-id="bc5a5-132">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 <span data-ttu-id="bc5a5-133">有关兼用浮点类型和整型类型的算术表达式的信息，请参阅 [float](../../../csharp/language-reference/keywords/float.md) 和 [double](../../../csharp/language-reference/keywords/double.md)。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-133">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="bc5a5-134">有关隐式数值转换规则的详细信息，请参阅[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="bc5a5-134">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="bc5a5-135">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="bc5a5-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bc5a5-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc5a5-136">See Also</span></span>  
 <span data-ttu-id="bc5a5-137"><xref:System.UInt16></span><span class="sxs-lookup"><span data-stu-id="bc5a5-137"><xref:System.UInt16></span></span>   
 <span data-ttu-id="bc5a5-138">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bc5a5-138">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bc5a5-139">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bc5a5-139">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bc5a5-140">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="bc5a5-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="bc5a5-141">[整型类型表](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="bc5a5-141">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="bc5a5-142">[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="bc5a5-142">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="bc5a5-143">[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="bc5a5-143">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="bc5a5-144">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="bc5a5-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

