---
title: sbyte（C# 参考）
ms.date: 03/14/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sbyte_CSharpKeyword
- sbyte
helpviewer_keywords:
- sbyte keyword [C#]
ms.assetid: 1a9c7b48-73d1-4d33-b485-c4faf0a816bc
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1c3950e11e1a81cf7263e146705c351e3dd8a6e9
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="sbyte-c-reference"></a><span data-ttu-id="92612-102">sbyte（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="92612-102">sbyte (C# Reference)</span></span>

<span data-ttu-id="92612-103">`sbyte` 表示一种整型类型，该类型根据下表显示的大小和范围存储值。</span><span class="sxs-lookup"><span data-stu-id="92612-103">`sbyte` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="92612-104">类型</span><span class="sxs-lookup"><span data-stu-id="92612-104">Type</span></span>|<span data-ttu-id="92612-105">范围</span><span class="sxs-lookup"><span data-stu-id="92612-105">Range</span></span>|<span data-ttu-id="92612-106">大小</span><span class="sxs-lookup"><span data-stu-id="92612-106">Size</span></span>|<span data-ttu-id="92612-107">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="92612-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`sbyte`|<span data-ttu-id="92612-108">-128 到 127</span><span class="sxs-lookup"><span data-stu-id="92612-108">-128 to 127</span></span>|<span data-ttu-id="92612-109">8 位带符号整数</span><span class="sxs-lookup"><span data-stu-id="92612-109">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="92612-110">文本</span><span class="sxs-lookup"><span data-stu-id="92612-110">Literals</span></span>  

<span data-ttu-id="92612-111">可以通过为其分配十进制文本、十六进制文本或（从 C# 7.0 开始）二进制文本来声明和初始化 `sbyte` 变量。</span><span class="sxs-lookup"><span data-stu-id="92612-111">You can declare and initialize an `sbyte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> 

<span data-ttu-id="92612-112">在以下示例中，等于 -102、表示为十进制、十六进制和二进制文本的整数从 [int](../../../csharp/language-reference/keywords/int.md) 转换为 `sbyte` 值。</span><span class="sxs-lookup"><span data-stu-id="92612-112">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are converted from [int](../../../csharp/language-reference/keywords/int.md) to `sbyte` values.</span></span>    
  
[!code-csharp[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]  

> [!NOTE] 
> <span data-ttu-id="92612-113">使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。</span><span class="sxs-lookup"><span data-stu-id="92612-113">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="92612-114">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="92612-114">Decimal literals have no prefix.</span></span>

<span data-ttu-id="92612-115">从 C# 7.0 开始，添加了一些功能以增强可读性。</span><span class="sxs-lookup"><span data-stu-id="92612-115">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="92612-116">C# 7.0 允许将下划线字符 (`_`) 用作数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="92612-116">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="92612-117">C# 7.2 允许将 `_` 用作二进制或十六进制文本的数字分隔符，位于前缀之后。</span><span class="sxs-lookup"><span data-stu-id="92612-117">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="92612-118">十进制文本不能够有前导下划线。</span><span class="sxs-lookup"><span data-stu-id="92612-118">A decimal literal isn't permitted to have a leading underscore.</span></span>

 <span data-ttu-id="92612-119">下面是一些示例。</span><span class="sxs-lookup"><span data-stu-id="92612-119">Some examples are shown below.</span></span>

[!code-csharp[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]  

<span data-ttu-id="92612-120">如果整数文本在 `sbyte` 范围之外（即，如果它小于 <xref:System.SByte.MinValue?displayProperty=nameWithType> 或大于 <xref:System.SByte.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="92612-120">If the integer literal is outside the range of `sbyte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="92612-121">如果整数文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：[int](int.md)、[uint](uint.md)、[long](long.md)、[ulong](ulong.md)。</span><span class="sxs-lookup"><span data-stu-id="92612-121">When an integer literal has no suffix, its type is the first of these types in which its value can be represented: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md).</span></span> <span data-ttu-id="92612-122">这意味着，在此示例中，数字文本 `0x9A` 和 `0b10011010` 被解释为值为 156 的 32 位带符号整数，该值超过了 <xref:System.SByte.MaxValue?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="92612-122">This means that, in this example, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="92612-123">因此，需要使用强制转换运算符，并且赋值必须在[取消选中](unchecked.md)的上下文中发生。</span><span class="sxs-lookup"><span data-stu-id="92612-123">Because of this, the casting operator is needed, and the assignment must occur in an [unchecked](unchecked.md) context.</span></span> 

## <a name="compiler-overload-resolution"></a><span data-ttu-id="92612-124">编译器重载解析</span><span class="sxs-lookup"><span data-stu-id="92612-124">Compiler overload resolution</span></span>

 <span data-ttu-id="92612-125">调用重载方法时必须使用强制转换。</span><span class="sxs-lookup"><span data-stu-id="92612-125">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="92612-126">以下面使用 `sbyte` 和 [int](../../../csharp/language-reference/keywords/int.md) 参数的重载方法为例：</span><span class="sxs-lookup"><span data-stu-id="92612-126">Consider, for example, the following overloaded methods that use `sbyte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(sbyte b) {}  
```  
  
 <span data-ttu-id="92612-127">使用 `sbyte` 强制转换可保证调用正确的类型，例如：</span><span class="sxs-lookup"><span data-stu-id="92612-127">Using the `sbyte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp 
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the sbyte parameter:  
SampleMethod((sbyte)5);  
```  
  
## <a name="conversions"></a><span data-ttu-id="92612-128">转换</span><span class="sxs-lookup"><span data-stu-id="92612-128">Conversions</span></span>  
 <span data-ttu-id="92612-129">存在从 `sbyte` 到 [short](../../../csharp/language-reference/keywords/short.md)、[int](../../../csharp/language-reference/keywords/int.md)、[long](../../../csharp/language-reference/keywords/long.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md) 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="92612-129">There is a predefined implicit conversion from `sbyte` to [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="92612-130">不能将存储大小更大的非文本数值类型隐式转换为 `sbyte` 类型（有关整型类型的存储大小的信息，请参阅[整型类型表](../../../csharp/language-reference/keywords/integral-types-table.md)）。</span><span class="sxs-lookup"><span data-stu-id="92612-130">You cannot implicitly convert nonliteral numeric types of larger storage size to `sbyte` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="92612-131">以下面两个 `sbyte` 变量 `x` 和 `y` 为例：</span><span class="sxs-lookup"><span data-stu-id="92612-131">Consider, for example, the following two `sbyte` variables `x` and `y`:</span></span>  
  
```csharp  
sbyte x = 10, y = 20;  
```  
  
 <span data-ttu-id="92612-132">以下赋值语句会生成一个编译错误，原因是赋值运算符右侧的算术表达式在默认情况下的计算结果为 [int](../../../csharp/language-reference/keywords/int.md)。</span><span class="sxs-lookup"><span data-stu-id="92612-132">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp  
sbyte z = x + y;   // Error: conversion from int to sbyte  
```  
  
 <span data-ttu-id="92612-133">若要更正此问题，请对该表达式执行强制转换，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="92612-133">To fix this problem, cast the expression as in the following example:</span></span>  
  
```csharp  
sbyte z = (sbyte)(x + y);   // OK: explicit conversion  
```  
  
 <span data-ttu-id="92612-134">但是，在目标变量具有相同或更大的存储大小时，可以使用下列语句：</span><span class="sxs-lookup"><span data-stu-id="92612-134">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
sbyte x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="92612-135">另请注意，不存在从浮点类型到 `sbyte` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="92612-135">Notice also that there is no implicit conversion from floating-point types to `sbyte`.</span></span> <span data-ttu-id="92612-136">例如，除非使用显式强制转换，否则以下语句将生成编译器错误：</span><span class="sxs-lookup"><span data-stu-id="92612-136">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
sbyte x = 3.0;         // Error: no implicit conversion from double  
sbyte y = (sbyte)3.0;  // OK: explicit conversion  
```  
  
 <span data-ttu-id="92612-137">有关兼用浮点类型和整型类型的算术表达式的信息，请参阅 [float](../../../csharp/language-reference/keywords/float.md) 和 [double](../../../csharp/language-reference/keywords/double.md)。</span><span class="sxs-lookup"><span data-stu-id="92612-137">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="92612-138">有关隐式数值转换规则的详细信息，请参阅[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="92612-138">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="92612-139">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="92612-139">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="92612-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="92612-140">See Also</span></span>  
 <xref:System.SByte>  
 [<span data-ttu-id="92612-141">C# 参考</span><span class="sxs-lookup"><span data-stu-id="92612-141">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="92612-142">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="92612-142">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="92612-143">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="92612-143">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="92612-144">整型表</span><span class="sxs-lookup"><span data-stu-id="92612-144">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="92612-145">内置类型表</span><span class="sxs-lookup"><span data-stu-id="92612-145">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="92612-146">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="92612-146">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="92612-147">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="92612-147">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
