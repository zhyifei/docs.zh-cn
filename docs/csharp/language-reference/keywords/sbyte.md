---
title: "sbyte（C# 参考）"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sbyte_CSharpKeyword
- sbyte
dev_langs:
- CSharp
helpviewer_keywords:
- sbyte keyword [C#]
ms.assetid: 1a9c7b48-73d1-4d33-b485-c4faf0a816bc
caps.latest.revision: 17
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
ms.openlocfilehash: 69741a5b9556c769156687584041667312550c17
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="sbyte-c-reference"></a><span data-ttu-id="36518-102">sbyte（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="36518-102">sbyte (C# Reference)</span></span>

<span data-ttu-id="36518-103">`sbyte` 表示一种整型类型，该类型根据下表显示的大小和范围存储值。</span><span class="sxs-lookup"><span data-stu-id="36518-103">`sbyte` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="36518-104">类型</span><span class="sxs-lookup"><span data-stu-id="36518-104">Type</span></span>|<span data-ttu-id="36518-105">范围</span><span class="sxs-lookup"><span data-stu-id="36518-105">Range</span></span>|<span data-ttu-id="36518-106">大小</span><span class="sxs-lookup"><span data-stu-id="36518-106">Size</span></span>|<span data-ttu-id="36518-107">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="36518-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`sbyte`|<span data-ttu-id="36518-108">-128 到 127</span><span class="sxs-lookup"><span data-stu-id="36518-108">-128 to 127</span></span>|<span data-ttu-id="36518-109">8 位带符号整数</span><span class="sxs-lookup"><span data-stu-id="36518-109">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="36518-110">文本</span><span class="sxs-lookup"><span data-stu-id="36518-110">Literals</span></span>  

<span data-ttu-id="36518-111">可以通过为其分配十进制文本、十六进制文本或（从 C# 7 开始）二进制文本来声明和初始化 `sbyte` 变量。</span><span class="sxs-lookup"><span data-stu-id="36518-111">You can declare and initialize an `sbyte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> 

<span data-ttu-id="36518-112">在以下示例中，等于 -102、表示为十进制、十六进制和二进制文本的整数从 [int](../../../csharp/language-reference/keywords/int.md) 转换为 `sbyte` 值。</span><span class="sxs-lookup"><span data-stu-id="36518-112">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are converted from [int](../../../csharp/language-reference/keywords/int.md) to `sbyte` values.</span></span>    
  
<span data-ttu-id="36518-113">[!code-cs[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]</span><span class="sxs-lookup"><span data-stu-id="36518-113">[!code-cs[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="36518-114">使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。</span><span class="sxs-lookup"><span data-stu-id="36518-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="36518-115">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="36518-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="36518-116">从 C# 7 开始，还可以使用下划线字符 `_` 作为数字分隔符，以增强可读性，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="36518-116">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="36518-117">[!code-cs[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]</span><span class="sxs-lookup"><span data-stu-id="36518-117">[!code-cs[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]</span></span>  

<span data-ttu-id="36518-118">如果整数文本在 `sbyte` 范围之外（即，如果它小于 <xref:System.SByte.MinValue?displayProperty=fullName> 或大于 <xref:System.SByte.MaxValue?displayProperty=fullName>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="36518-118">If the integer literal is outside the range of `sbyte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=fullName> or greater than <xref:System.SByte.MaxValue?displayProperty=fullName>, a compilation error occurs.</span></span> <span data-ttu-id="36518-119">如果整数文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：[int](int.md)、[uint](uint.md)、[long](long.md)、[ulong](ulong.md)。</span><span class="sxs-lookup"><span data-stu-id="36518-119">When an integer literal has no suffix, its type is the first of these types in which its value can be represented: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md).</span></span> <span data-ttu-id="36518-120">这意味着，在此示例中，数字文本 `0x9A` 和 `0b10011010` 被解释为值为 156 的 32 位带符号整数，该值超过了 <xref:System.SByte.MaxValue?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="36518-120">This means that, in this example, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="36518-121">因此，需要使用强制转换运算符，并且赋值必须在[取消选中](unchecked.md)的上下文中发生。</span><span class="sxs-lookup"><span data-stu-id="36518-121">Because of this, the casting operator is needed, and the assignment must occur in an [unchecked](unchecked.md) context.</span></span> 

## <a name="compiler-overload-resolution"></a><span data-ttu-id="36518-122">编译器重载解析</span><span class="sxs-lookup"><span data-stu-id="36518-122">Compiler overload resolution</span></span>

 <span data-ttu-id="36518-123">调用重载方法时必须使用强制转换。</span><span class="sxs-lookup"><span data-stu-id="36518-123">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="36518-124">以下面使用 `sbyte` 和 [int](../../../csharp/language-reference/keywords/int.md) 参数的重载方法为例：</span><span class="sxs-lookup"><span data-stu-id="36518-124">Consider, for example, the following overloaded methods that use `sbyte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(sbyte b) {}  
```  
  
 <span data-ttu-id="36518-125">使用 `sbyte` 强制转换可保证调用正确的类型，例如：</span><span class="sxs-lookup"><span data-stu-id="36518-125">Using the `sbyte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp 
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the sbyte parameter:  
SampleMethod((sbyte)5);  
```  
  
## <a name="conversions"></a><span data-ttu-id="36518-126">转换</span><span class="sxs-lookup"><span data-stu-id="36518-126">Conversions</span></span>  
 <span data-ttu-id="36518-127">存在从 `sbyte` 到 [short](../../../csharp/language-reference/keywords/short.md)、[int](../../../csharp/language-reference/keywords/int.md)、[long](../../../csharp/language-reference/keywords/long.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md) 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="36518-127">There is a predefined implicit conversion from `sbyte` to [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="36518-128">不能将存储大小更大的非文本数值类型隐式转换为 `sbyte` 类型（有关整型类型的存储大小的信息，请参阅[整型类型表](../../../csharp/language-reference/keywords/integral-types-table.md)）。</span><span class="sxs-lookup"><span data-stu-id="36518-128">You cannot implicitly convert nonliteral numeric types of larger storage size to `sbyte` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="36518-129">以下面两个 `sbyte` 变量 `x` 和 `y` 为例：</span><span class="sxs-lookup"><span data-stu-id="36518-129">Consider, for example, the following two `sbyte` variables `x` and `y`:</span></span>  
  
```csharp  
sbyte x = 10, y = 20;  
```  
  
 <span data-ttu-id="36518-130">以下赋值语句会生成一个编译错误，原因是赋值运算符右侧的算术表达式在默认情况下的计算结果为 [int](../../../csharp/language-reference/keywords/int.md)。</span><span class="sxs-lookup"><span data-stu-id="36518-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp  
sbyte z = x + y;   // Error: conversion from int to sbyte  
```  
  
 <span data-ttu-id="36518-131">若要更正此问题，请对该表达式执行强制转换，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="36518-131">To fix this problem, cast the expression as in the following example:</span></span>  
  
```csharp  
sbyte z = (sbyte)(x + y);   // OK: explicit conversion  
```  
  
 <span data-ttu-id="36518-132">但是，在目标变量具有相同或更大的存储大小时，可以使用下列语句：</span><span class="sxs-lookup"><span data-stu-id="36518-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
sbyte x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="36518-133">另请注意，不存在从浮点类型到 `sbyte` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="36518-133">Notice also that there is no implicit conversion from floating-point types to `sbyte`.</span></span> <span data-ttu-id="36518-134">例如，除非使用显式强制转换，否则以下语句将生成编译器错误：</span><span class="sxs-lookup"><span data-stu-id="36518-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
sbyte x = 3.0;         // Error: no implicit conversion from double  
sbyte y = (sbyte)3.0;  // OK: explicit conversion  
```  
  
 <span data-ttu-id="36518-135">有关兼用浮点类型和整型类型的算术表达式的信息，请参阅 [float](../../../csharp/language-reference/keywords/float.md) 和 [double](../../../csharp/language-reference/keywords/double.md)。</span><span class="sxs-lookup"><span data-stu-id="36518-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="36518-136">有关隐式数值转换规则的详细信息，请参阅[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="36518-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="36518-137">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="36518-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="36518-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36518-138">See Also</span></span>  
 <span data-ttu-id="36518-139"><xref:System.SByte></span><span class="sxs-lookup"><span data-stu-id="36518-139"><xref:System.SByte></span></span>   
 <span data-ttu-id="36518-140">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="36518-140">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="36518-141">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="36518-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="36518-142">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="36518-142">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="36518-143">[整型类型表](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="36518-143">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="36518-144">[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="36518-144">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="36518-145">[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="36518-145">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="36518-146">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="36518-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

